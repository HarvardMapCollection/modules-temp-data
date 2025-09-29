This readme file was generated on [2025-09-29] by [Anna He]


# GENERAL INFORMATION

* **Title of Dataset**: EnvJusticePop_Boston_2020.gpkg

## Author Information
**Name**: Anna He  
**ORCID**: N/A  
**Institution**: Harvard University ITS MMPS  
**Address**: Harvard Map Collection, Pusey Library, Harvard Yard, Cambridge, MA 02138  
**Email**: anna_he@harvard.edu  


* **Date of data collection**: 2020 Environmental Justice population data for Massachusetts downloaded from source on 2025-09-10. Cleaned and processed by 2025-09-12.
* **Geographic location of data collection**: Boston
* **Information about funding sources that supported the collection of the data**: N/A


# SHARING/ACCESS INFORMATION

* Licenses/restrictions placed on the data: 
* Links to publications that cite or use the data: 
* Links to other publicly accessible locations of the data: 
* **Links/relationships to ancillary data sets**: 
	* **Original source data downloaded as a polygon shapefile from MassGIS**: "module2_env_public_health\envjusticepop\source\ej2020_shp.zip" --> the shapefile layer is titled **EJ_POLY.shp**
	* **Original source data as a CSV**: "module2_env_public_health\envjusticepop\source\EJ_POLY.csv"
	* **Original source data documentation (aka saved the source web page as a PDF)**: "module2_env_public_health\envjusticepop\source\MassGISData_2020_Environmental_Justice_Populations.pdf""

	* **Cleaned data in CSV format**: "module2_env_public_health\envjusticepop\for_mapping\EnvJusticePop_Boston_2020.csv"
	* **Cleaned data in shapefile format**: "module2_env_public_health\envjusticepop\for_mapping\EnvJusticePop_Boston_2020_shp.zip" --> the shapefile layer is titled **EnvJusticePop_Boston_2020.shp**
	* **Cleaned data in geopackage format**: "module2_env_public_health\envjusticepop\for_mapping\EnvJusticePop_Boston_2020.gpkg"
* Was data derived from another source?
	* If yes, list source(s): Yes, [EJ_POLY.shp](https://www.mass.gov/info-details/massgis-data-2020-environmental-justice-populations)
	* **Download source**: MassGIS. (2024, June). Massgis Data: 2020 environmental justice populations. Mass.gov. Retrieved September 10, 2025 from https://www.mass.gov/info-details/massgis-data-2020-environmental-justice-populations
		* **Documentation source**: MassGIS. (2024, June). Massgis Data: 2020 environmental justice populations. Mass.gov. Retrieved September 10, 2025 from https://www.mass.gov/info-details/massgis-data-2020-environmental-justice-populations 
	* Recommended citation for this dataset: 


# DATA & FILE OVERVIEW

## File List: *list all files (or folders, as appropriate for dataset organization) contained in the dataset, with a brief description*
The most important file to be used for mapping is [EnvJusticePop_Boston_2020.gpkg](#data-specific-information-for-EnvJusticePop_Boston_2020gpkg). I have documented the origin, description, and creation date of all associated environmental justice population files below.

* Parent Folder: **envjusticepop/source**
	* File: **ej2020_shp.zip**
		* **Description**: This file is the original source data downloaded from MassGIS (MassGIS, 2024). It was originally titled ej2020.zip and renamed to clarify that it contains a shapefile. Unzipped, it contains a polygon shapefile titled **EJ_POLY.shp**. Per the source documentation, **EJ_POLY.shp** contains "polygons in the 2020 Environmental Justice (EJ) Populations layer [that] are 2020 Census block groups across the [Massachusetts] that meet **one or more** of the criteria listed below:
			* (i) the annual median household income is not more than 65 percent of the statewide annual median household income; 
			* (ii) minorities comprise 40 percent or more of the population; 
			* (iii) 25 percent or more of households lack English language proficiency; or 
			* (iv) minorities comprise 25 percent or more of the population and the annual median household income of the municipality in which the neighborhood is located does not exceed 150 percent of the statewide annual median household income."

		The dataset contains 2604 polygon features for all of Massachusetts and 24 variables. The coordinate reference system is EPSG 26986 (NAD 1983 StatePlane Massachusetts FIPS 2001 (Meters)). The column to use for mapping is "EJ_CRIT_DE", or environmental justice criteria description, which lists which of the above criteria (Income, Minority, English isolation) that a block group has met to be designated as an Environmental Justice population. 			
		* **Date Downloaded**: 2025-09-10 	

	* File: **EJ_POLY.csv**
		* **Description**: This file is the CSV version of the attribute table for the original source data, EJ_POLY.shp. It was created by exporting the attribute table for **EJ_POLY.shp** in a GIS.
		* **Date Created**: 2025-09-10

	* File: **MassGISData_2020_Environmental_Justice_Populations.pdf**
		* **Description**: This file is a PDF of the web page for [MassGIS 2020 environmental justice populations](https://www.mass.gov/info-details/massgis-data-2020-environmental-justice-populations) where I downloaded the data. The web page includes download links, a project overview, attribute descriptions, production information, summary tables, and maintenance information.		
		* **Date Downloaded**: 2025-09-10

* Parent Folder: **envjusticepop/for_mapping**

	* File: **EnvJusticePop_Boston_2020_shp.zip**
		* **Description**: This zipped folder contains a shapefile for a layer titled **EnvJusticePop_Boston_2020.shp**. It was derived from **EJ_POLY.shp** by selecting only block groups located in Boston, rather than all of Massachusetts. The new attribute table contains 462 polygon features and all 24 original variables. The coordinate reference system is EPSG 26986 (NAD 1983 StatePlane Massachusetts FIPS 2001 (Meters)). The column to use for mapping is "EJ_CRIT_DE", or environmental justice criteria description, which lists which of the criteria (Income, Minority, English isolation) that a block group has met to be designated as an Environmental Justice population
		* **Date Created**: 2025-09-12

	* File: **EnvJusticePop_Boston_2020.csv**
		* **Description**: This file is the CSV format for the attribute table of **EnvJusticePop_Boston_2020.shp**. It contains 462 features and 24 columns. 
		* **Date Created**: 2025-09-12	

	* File: **EnvJusticePop_Boston_2020.gpkg**
		* **Description**: This file is the geopackage version of **EnvJusticePop_Boston_2020.shp**. It was created by converting EnvJusticePop_Boston_2020.shp into a geopackage. It contains 462 polygon features and all 24 original variables. The coordinate reference system is EPSG 26986 (NAD 1983 StatePlane Massachusetts FIPS 2001 (Meters)). The column to use for mapping is "EJ_CRIT_DE", or environmental justice criteria description, which lists which of the criteria (Income, Minority, English isolation) that a block group has met to be designated as an Environmental Justice population. Exact attribute descriptions can be found in the [Data-Specific Information](#data-specific-information-for-EnvJusticePop_Boston_2020gpkg)
		* **Date Created**: 2025-09-12


* Relationship between files, if important: the /for_mapping files were derived from the /source files as described in the section [Methods for processing the data](#methods-for-processing-the-data)
* Additional related data collected that was not included in the current data package: N/A
* Are there multiple versions of the dataset?
	* If yes, name of file(s) that was updated: 
	* Why was the file updated? 
	* When was the file updated? 


# METHODOLOGICAL INFORMATION

## Description of methods used for collection/generation of data: 
The source data, **ej2020_shp.zip**, was downloaded in shapefile format from MassGIS 2020 environmental justice populations page (MassGIS, 2024). Per the webpage documetnation:

* "The Environmental Justice layer was produced by designating Census 2020 block groups as an Environmental Justice population using three criteria: Minority population, median household income (of the block group, the municipality of the block and the state), and household English language isolation. Block groups are statistical divisions of census tracts and their boundaries are based on population numbers rather than geographic size, generally between 600 and 3,000 people. Therefore, block groups can vary greatly in size. Where block groups cover more than one town, most often in the western part of the state, the block group has been split along the town boundary and the attributes, with the exception of TOWN_ID, Municipality and MUNI2, have been duplicated in each part of the block group. These polygons are coded ‘Y’ in the split_for_muni field.
	
	**Environmental Justice neighborhood**, i.e., block groups as defined in Chapter 8 of the Acts of 2021 were evaluated with the 2020 biennial Census population table and  American Community Survey 2016-2020 5-year-estimate tables to produce the updated 2020 EJ datalayer, released in November, 2022.
	
	**Minority population**: 2020 Census Redistricting Data: Table P2: HISPANIC OR LATINO, AND NOT HISPANIC OR LATINO BY RACE

	**Median Household Income**: (block groups, municipalities and state):American Community Survey 2020 5-year estimates: Table B19013: MEDIAN HOUSEHOLD INCOME IN THE PAST 12 MONTHS (IN 2020 INFLATION-ADJUSTED DOLLARS)

	**Limited English Households**: American Community Survey 2020 5-year estimates: Table C16002: HOUSEHOLD LANGUAGE BY HOUSEHOLD LIMITED ENGLISH SPEAKING STATUS

	*Additional data adjustments: Block groups with a total population of fewer than 50 were removed." (MassGIS, 2024)


## Methods for processing the data: 

1. Download source file as a shapefile: **ej2020.zip** from source [(MassGIS, 2024)](https://www.mass.gov/info-details/massgis-data-2020-environmental-justice-populations). Rename the zipped folder to **ej2020_shp.zip** and unzip the folder. The shapefile layer is titled **EJ_POLY.shp**.
2. Input: **EJ_POLY.shp**  --> open this layer a GIS and export the attribute table as a CSV --> output: **EJ_POLY.csv** 
3. Input: **EJ_POLY.shp** --> use a "select by attributes" tool to select block group polygons where the MUNICIPALITY == "Boston" and save the selected features as a new file --> output: **EnvJusticePop_Boston_2020.shp** (I zipped up the shapefile folder and titled it **EnvJusticePop_Boston_2020_shp.zip**).
4. Input: **EnvJusticePop_Boston_2020.shp** --> export attribute table as CSV --> output: **EnvJusticePop_Boston_2020.csv**
5. Input: **EnvJusticePop_Boston_2020.shp** --> right-click layer in QGIS: export -> save features as, and save as a geopackage --> output: **EnvJusticePop_Boston_2020.gpkg**

**Note: I decided to keep all the variables from the original source because the variables are fairly easy to underestand if you have the variable descriptions, and it would be good practice for students to explore how you can choose from many layers for map symbology. The primary column to be used for symbology in this case is still "EJ_CRIT_DE", but students could also symbolize using the columns "TOTAL_POP", "PCT_MINORITY", and other variables of interest. 

## Instrument- or software-specific information needed to interpret the data: 

* Standards and calibration information, if appropriate: N/A
* Environmental/experimental conditions: N/A
* Describe any quality-assurance procedures performed on the data: N/A
* People involved with sample collection, processing, analysis and/or submission: N/A


# DATA-SPECIFIC INFORMATION FOR: [EnvJusticePop_Boston_2020.gpkg]

* **Number of variables**: 24
* **Number of cases/rows**: 462
* **Variable List**: Attribute descriptions taken from the source [(MassGIS, 2024)](https://www.mass.gov/info-details/massgis-data-2020-environmental-justice-populations)
	* **GeographicAreaName**: Name of block group, Census tract, county, and state
	* **GEOID10**: Geo_ID
	* **SPLIT_FOR_MUNI**: A flag (Y/N) denoting if the block group has been divided at a town boundary
	* **MUNICIPALITY**: Municipality name
	* **NonHispWHITEALONE**: Total population of persons identifying as white alone and non-Hispanic/Latino
	* **PCT_MINORITY**: Percentage of Block Group population identified as minority (persons other than non-Hispanic white)
	* **TOTAL_HH**: Total number of households (ACS 2016-2020 5-year estimates)
	* **LimEngHH**: Number of households without a person 14 years of age or older who speaks English ‘very well’.
	* **LimEngHHpct**: Percent of limited English-speaking households (ACS 2016-2020 5-year estimates)
	* **BG_MHHI**: Median 2020 household income
	* **BG_MHHI_pct_MAHHI**: Block group 2020 MHHI as percent of MA 2020 MHHI.
	* **BG_MUNI_is_2019**: A flag for when the block group MHHI in the 2016-2020 ACS estimate is blank. In these cases, the block group and state MHHI from the 2015-2019 ACS estimate were used to evaluate the EJ designation.
	* **MUNI_MHHI**: Municipal 2020 MHHI
	* **MUNIMHHI_PCTMAHHI**: Municipal 2020 MHHI as percent of MA 2020 MHHI
	* **MEDIANHHI**: Flag (I) for the income EJ criterion
	* **LIMITEDENGLISH**: Flag (E) for the limited English household EJ criterion
	* **MINORITY_POPULATION**: Flag (M) for the minority population EJ criterion
	* **EJ**: Flag (Yes) for designation as an EJ block group
	* **EJ_CRITERIA**: EJ criteria (I, E, M) designated for the block group
	* **EJ_CRITERIA_CNT**: Number of EJ criteria designated for the block group (1-3)
	* **EJ_CRIT_DESC**: EJ criteria description (Income a/o Minority a/o English isolation)

* Missing data codes:  N/A
* Specialized formats or other abbreviations used: N/A
