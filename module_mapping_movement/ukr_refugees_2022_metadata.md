This readme file was generated on [2026-03-09] by [Anna He]

# GENERAL INFORMATION

* Title of Dataset: Mapping the Flow of Ukrainian Refugees to Countries of Asylum by End of 2022

## Author/Principal Investigator Information
* Name: Anna He
* Institution: Harvard University


* **Date of data collection**: through end of 2022 
* **Geographic location of data collection**: Global

# SHARING/ACCESS INFORMATION

* **Licenses/restrictions placed on the data**: Creative Commons Attribution International License 4.0; https://www.unhcr.org/what-we-do/data-and-publications/data-and-statistics/terms-use-datasets
* **Data Source**: United Nations High Commissioner for Refugees (UNHCR)
* **Data Download Link**: https://www.unhcr.org/refugee-statistics/download
* **Recommended citation for this dataset**: “UNHCR Refugee Population Statistics Database”


# DATA & FILE OVERVIEW

## File List: 
* **Folder**: country_centroids_data/
	* **country_centroids.zip**: zipped shapefile of point data for world country centroids in EPSG 4326 with 3-letter ISO_A3 country code and (x, y) coordinates
	* **country_centroids.gpkg**: geopackage of point data for world country centroids in EPSG 4326  with 3-letter ISO_A3 country code and (x, y) coordinates

* **Folder**: ukr_2022_data/
* source/
	* **persons_of_concern_ukr22.csv**: original data downloaded from UNHCR Refugee Data Finder for Ukraine by end of 2022 and appended with _ukr22 in the file name
	* **footnotes_ukr22.csv**: contains notes about methodology a/o sources of original refugee data for various countries in 2022
	* **UNHCR_RefugeeDataFinder_Copyright.pdf**: licensing info

* for_mapping/
	* **ukr_refugees_2022.gpkg**: final geopackage file showing flow lines from Ukraine to various countries of asylum; data represents Ukrainian refugee populations in countries of asylum by end of 2022
	* **ukr_refugees_2022.zip**: final zipped shapefile showing flow lines from Ukraine to various countries of asylum; data represents Ukrainian refugee populations in countries of asylum by end of 2022

* ukr_refugees_2021.gpkg: for Belle's mapping purposes only; final geopackage file showing flow lines from Ukraine to various countries of asylum; data represents Ukrainian refugee populations in countries of asylum by end of 2022

* **Relationship between files, if important**: ukr_refugees_2022 files are the processed, map-ready version of persons_of_concern_ukr22.csv

# METHODOLOGICAL INFORMATION

## Description of methods used for collection/generation of data: 
* Read more about methodology: https://www.unhcr.org/refugee-statistics/methodology
* Read more about definitions: https://www.unhcr.org/refugee-statistics/methodology/definition


## Methods for processing the data: 
### For Country Centroid Data:
* Goal: from world country polygons, create a point file of each country's centroid and obtain the x and y coordinates for each centroid. 
* Open QGIS. In the bottom bar's "Coordinate" field, type "world" and press Enter. A "World Map" polygon file of all world countries will pop up. 
* Get centroids of the country polygons using the "Centroids" tool: 
	* At the top of the QGIS toolbar, click "Vector" --> "Geometry Tools" --> "Centroids"
	* Set the following parameters and click Run.  
		* Input Layer: "World Map"
		* Output Layer: "country_centroids.gpkg" --> This is a point file containing the centroids of all the countries.
* Create columns of X and Y coordinates for each centroid using the Field Calculator and field expressions:
	* Open the attribute table for country_centroids.gpkg
	* Turn on editing and click Field Calculator.
	* Set the following parameters for Field Calculator to obtain the x coordinate of each centroid:
		* Create New Field.
		* Output Field Name: x_dest
		* Output Field Type: Decimal number (real)
		* Expression: x($geometry)
		* Click Run.
	* Open field calculator to repeat and obtain the y coordinate of the centroid:
		* Create New Field.
		* Output Field Name: y_dest
		* Output Field Type: Decimal number (real)
		* Expression: y($geometry)
		* Click Run.
	* Save changes and turn off editing. 
	* Final Output: country_centroids.gpkg layer of centroids. Export and save as shapefile: country_centroids.shp. Each centroid has a 3-letter ISO_A3 country code and x and y coordinates.

### For Refugee Data:
#### Accessing Data
* Visit UNHCR Refugee Data Finder: https://www.unhcr.org/refugee-statistics/download
* Set the following data filters: Year - 2022; Country of Origin - Ukraine; Country of Asylum - All countries
* Click Download Summary Data.
* Rename persons_of_concern.csv to persons_of_concern_ukr22.csv.

#### Creating columns for x and y origin coordinates for refugee data using the Field Calculator.  
* Goal: From persons_of_concern_ukr22.csv and country_centroids.gpkg, add the x and y coordinates for our origin country, Ukraine, to the refugee data.
* Input: persons_of_concern_ukr22.csv --> export and save as geopackage so you can edit the table --> persons_of_concern_ukr22_origin.gpkg (has no geometry)
* country_centroids.gpkg --> open attribute table and find the row where the name of the country == Ukraine. Copy the coordinate for x_dest --> 31.386168629361723
* persons_of_concern_ukr_origin.gpkg --> open the attribute table, turn on editing, open the field calculator and set the following parameters:
	* Create New Field.
	* Output Field Name x_origin
	* Output Field Type: Decimal number (real)
	* Expression --> paste the x-dest coordinate for Ukraine: 31.386168629361723
	* Click OK.
* Repeat to obtain the y coordinate for Ukraine:
* country_centroids.gpkg --> open attribute table and find the row where the name of the country == Ukraine. Copy the coordinate for y_dest --> 48.996846585840046
* persons_of_concern_ukr_origin.gpkg --> open the attribute table, turn on editing, open the field calculator and set the following parameters:
	* Create New Field.
	* Output Field Name x_origin
	* Output Field Type: Decimal number (real)
	* Expression --> paste the y-dest coordinate for Ukraine: 48.996846585840046
	* Click OK.
* Save edits and turn off editing. 

#### Joining columns with x and y destination coordinates from the centroids data to the refugee data 
* Goal: Create columns of x and y destination coordinates for the refugee data by joining country_centroids.gpkg to persons_of_concern_ukr22.gpkg using the 3-letter ISO_A3 country codes. Use the "Join Attributes by Field Value" tool.
* In QGIS, go to the Processing Toolbox and click "Join Attributes by Field Value" tool. Set the following parameters:
	* Input Layer 1: persons_of_concern_ukr22.gpkg
	* Table Field 1: Country of Asylum ISO
	* Input Layer 2: country_centroids.gpkg
	* Table Field 2: ISO_A3
	* Layer 2 fields to copy: x_dest, y_dest
	* Join Type: Create separate feature for each matching feature (one-to-many)
	* Joined Layer: ukr_refugees_2022_joined.gpkg
	* Run.
* Output: ukr_refugees_2022_joined.gpkg --> joined geopackage  with the x and y coordinates for the country of asylum, x and y coordinates for the country of origin, and # of refugees.

#### Create and symbolize flow lines from XY points using the XY to Line tool 
* Goal: From ukr_refugees_2022_joined.gpkg, create flow lines from the (x,y) origin coordinates to the (x,y) destination coordinates.
* QGIS --> Vector --> Shape Tools --> XY to line. Set the following parameters:
	* Input layer: ukr_refugees_2021_joined
	* EPSG: 4326
	* Line type: Geodesic
	* Starting x field: x_origin
	* Starting y field: y_origin
	* Ending x field: x_dest
	* Ending y field: y_dest:
	* Output line layer: ukr_refugees_2022.gpkg
	* Run.
* Convert "Refugees" column from text (string) to numeric:
	* Open field calculator, create new field "Refugees_num" as an integer with the expression to_int("Refugees").
* Outputs: ukr_refugees_2022.gpkg; and ukr_refugees_2022.shp (converted from geopackage). EPSG 4326
* Symbology: can choose to symbolize line widths by size using the column "Refugee_num", the # of refugees. 


# DATA-SPECIFIC INFORMATION FOR: ukr_refugees_2022.shp
*repeat this section for each dataset, folder or file, as appropriate*

* **Number of variables**: 17
* **Number of cases/rows**: 78
* **Variable List**: For the exact definitions below, see https://www.unhcr.org/refugee-statistics/methodology/definition
	* **Year**: end year until which refugee data is included
	* **Country of Asylum**: country of asylum
	* **Country of Origin**: country of origin
	* **Country of Asylum ISO**: ISO3 country code
	* **Country of Origin ISO**: ISO3 country code
	* **Refugees**: # of refugees; " individuals recognized under the 1951 Convention relating to the Status of Refugees, its 1967 Protocol, the 1969 Organization of African Unity (OAU) Convention Governing the Specific Aspects of Refugee Problems in Africa, the refugee definition contained in the 1984 Cartagena Declaration on Refugees as incorporated into national laws, those recognized in accordance with the UNHCR Statute, individuals granted complementary forms of protection, and those enjoying temporary protection. The refugee population also includes people in refugee-like situations."
	* **Asylum-seekers**: # of asylum-seekers; "individuals who have sought international protection and whose claims for refugee status have not yet been determined."
	* **IDPs**: # of internationally-displaced persons; "persons or groups of persons who have been forced or obliged to flee or to leave their homes or places of habitual residence, in particular as a result of, or in order to avoid the effects of armed conflict, situations of generalized violence, violations of human rights or natural or human-made disasters, and who have not crossed an internationally recognized State border
	* **Other people in need of international protection**": # of other people in need of international protection; "people who are outside their country or territory of origin, typically because they have been forcibly displaced across international borders, who have not been reported under other categories (asylum-seekers, refugees, people in refugee-like situations) but who likely need international protection, including protection against forced return, as well as access to basic services on a temporary or longer-term basis."
	* **Stateless persons**: # of stateless persons; "defined under the 1954 Convention Relating to the Status of Stateless People as those not considered as nationals by any State under the operation of its law"
	* **Host community**: # of host communities; "a community that hosts large populations of refugees or internally displaced persons, whether in camps, integrated into households, or independently"
	* **Others of concern**: # of others of concerns;"individuals who do not necessarily fall directly into any of these groups above but to whom UNHCR has extended its protection and/or assistance services, based on humanitarian or other special grounds"
	* **x_origin**: x coordinate for the origin country, Ukraine
	* **y_origin**: y coordinate for the origin country, Ukraine
	* **x_dest**: x coordinate for the destination country, the country of asylum
	* **y_dest**: y coordinate for the destination country, the country of asylum
	* **Refugees_num**: # of refugees; same as "Refugees" column above but in this case converted to a numeric data type
	
	https://www.unhcr.org/refugee-statistics/methodology/data-content

