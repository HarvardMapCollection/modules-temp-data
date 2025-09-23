This readme file was generated on [2025-09-19] by [Anna He]


# GENERAL INFORMATION

* **Title of Dataset**: TRI_Facilities_MA_2024.gpkg

## Author Information
**Name**: Anna He  
**ORCID**: N/A  
**Institution**: Harvard University ITS MMPS  
**Address**: Harvard Map Collection, Pusey Library, Harvard Yard, Cambridge, MA 02138  
**Email**: anna_he@harvard.edu  


* **Date of data collection**: 2024 TRI data for Massachusetts downloaded from source on 2025-09-08. Cleaned and processed by 2025-09-12.
* **Geographic location of data collection**: Massachusetts state-wide
* **Information about funding sources that supported the collection of the data**: N/A


# SHARING/ACCESS INFORMATION

* Licenses/restrictions placed on the data: N/A
* Links to publications that cite or use the data: N/A
* Links to other publicly accessible locations of the data: N/A
* **Links/relationships to ancillary data sets**: 
	* **Original source data in text file format as downloaded from the EPA website**: "module2_env_public_health\tri\source\MA_1a_2024.txt"
	* **Original source data in CSV format**: "module2_env_public_health\tri\source\TRI_MA_2024_full.csv"
	* **Original source data documentation**: "module2_env_public_health\tri\source\TRI_basic_plus_data_files_documentation_full_2024.pdf"

	* **Cleaned data in CSV format**: "module2_env_public_health\tri\for_mapping\TRI_MA_2024_for_mapping.csv"
	* **Cleaned data in shapefile format**: "module2_env_public_health\tri\for_mapping\TRI_Facilities_MA_2024.zip" 
	* **Cleaned data in geopackage format**: "module2_env_public_health\tri\for_mapping\TRI_Facilities_MA_2024.gpkg"
* Was data derived from another source?
	* If yes, list source(s): Yes, MA_1a_2024.txt
	* **Download source**: EPA. (2025a). 2024 TRI Preliminary Dataset: Basic Plus Data Files. Retrieved on September 8, 2025 from https://www.epa.gov/toxics-release-inventory-tri-program/2024-tri-preliminary-dataset-basic-plus-data-files 
	* **Documentation source**: EPA. (2025b). TRI Basic Plus Data Files Guides. Retrieved on September 8, 2025 from https://www.epa.gov/toxics-release-inventory-tri-program/2024-tri-preliminary-dataset-basic-plus-data-files#contents 
	* Recommended citation for this dataset: 


# DATA & FILE OVERVIEW

## File List: *list all files (or folders, as appropriate for dataset organization) contained in the dataset, with a brief description*
The most important file to be used for mapping is [TRI_Facilities_MA_2024.gpkg](#data-specific-information-for-tri_facilities_ma_2024gpkg). I have documented the origin, description, and creation date of all associated TRI files below.

* Parent Folder: **tri/source**
	* File: **MA_1a_2024.txt**
		* **Description**: This file is the original source data. It was downloaded from the EPA's Toxic Release Inventory Program TRI Data and Tools, 2024 TRI Preliminary Dataset: Basic Plus Data Files page (linked in source above) for the State of Massachusetts. The downloaded folder contains many files, but only File 1A is relevant for the purposes of our learning module. The file is a text file containing data, including the latitude and longitude coordinates of toxic release inventory (TRI) sites in Massachusetts reported as of 2025-08-13. The file also contains data on on-site chemical releases, maximum amount on site, off-site transfers, details of on-site recycling and energy recovery, and more. Full descriptions of the data columns can be found in the file: TRI_basic_plus_data_files_documentation_full_2024.pdf
		* **Date Downloaded**: 2025-09-8 	

	* File: **TRI_MA_2024_full.csv**
		* **Description**: This file is the CSV version of the original source data, text file MA_1a_2024.txt. It contains all the original data. I converted the .txt file to a .csv for easier viewing purposes. 
		* **Date Created**: 2025-09-08

	* File: **TRI_basic_plus_data_files_documentation_full_2024.pdf**
		* **Description**: This PDF file is the documentation for the original source data, MA_1a_2024.txt. It contains the column heading, data type, and column data description. It was downloaded directly from the EPA's Toxic Release Inventory Program TRI Data and Tools, 2024 TRI Preliminary Dataset: Basic Plus Data Files page.
		* **Date Downloaded**: 2025-09-08

* Parent Folder: **tri/for_mapping**
	* File: **TRI_MA_2024_for_mapping.csv**
		* **Description**: This CSV file was derived from TRI_MA_2024_full.csv. It contains only the relevant columns for mapping, such as ID, facility name, latitude, and longitude. It also contains data on reported chemicals, chemical classifications, and total air emissions.
		* **Date Created**: 2025-09-08	

	* File: **TRI_Facilities_MA_2024.zip**
		* **Description**: This zipped folder contains a shapefile for a layer titled TRI_MA_2024. It was created by converting TRI_MA_2024_for_mapping.csv into spatial data using the latitude and longitude columns. The layer contains 819 point features representing reported TRI facilities in Massachusetts in 2024. The coordinate reference system is EPSG 26986 for NAD83 Massachusetts State Plane Coordinate System, Mainland Zone (Fipszone 2001, meters).
		* **Date Created**: 2025-09-12

	* File: **TRI_Facilities_MA_2024.gpkg**
		* **Description**: This file is the geopackage version of TRI_MA_2024.shp. It was created by converting TRI_MA_2024.shp into a geopackage. It contains 819 point features representing reported TRI facilities in Massachusetts in 2024. It also contains attribute data on facility ID, facility name and location, reported chemicals, chemical classifications, and total air emissions that may be of interest for students to symbolize. The coordinate reference system is EPSG 26986 for NAD83 Massachusetts State Plane Coordinate System, Mainland Zone (Fipszone 2001, meters). Exact attribute descriptions can be found in the [Data-Specific Information](#data-specific-information-for-filename).
		* **Date Created**: 2025-09-12


* Relationship between files, if important: the /for_mapping files were derived from the /source files as described in the section [Methods for processing the data](#methods-for-processing-the-data)
* Additional related data collected that was not included in the current data package: N/A
* Are there multiple versions of the dataset?
	* If yes, name of file(s) that was updated: 
	* Why was the file updated? 
	* When was the file updated? 


# METHODOLOGICAL INFORMATION

## Description of methods used for collection/generation of data: 

The source data, **MA_1a_2024.txt**, was downloaded from the EPA's 2024 TRI Preliminary Dataset: Basic Plus Data Files (EPA, 2025a) for the State of Massachusetts. Per the documentation in the file TRI_basic_plus_data_files_documentation_full_2024.pdf: "The “Type 1A” file contains the bulk of the data found on the TRI Reporting Form R... each record in File Type 1A represents data from a single chemical reporting form (i.e., Form R) submitted by a facility. Thus, the complete file contains records for all chemicals that were reported to TRI from a specific state and reporting year." File Type 1A contains information regarding facility names and locations, "on-site chemical releases, maximum amount on site, off-site transfers, and details of on-site recycling and energy recovery" (EPA 2025a).

## Methods for processing the data: 

1. Download source file and open **MA_1a_2024.txt**
2. Input: **MA_1a_2024.txt** --> convert to a CSV --> output: **TRI_MA_2024_full.csv**
3. Input: **TRI_MA_2024_full.csv** --> examine columns using the **TRI_basic_plus_data_files_documentation_full_2024.pdf** and delete unwanted columns in the CSV. Make sure "Latitude" and "Longitude" columns are formatted correctly. --> output: **TRI_Facilities_MA_2024_for_mapping.csv**
4. Input: **TRI_Facilities_MA_2024_for_mapping.csv** --> open a GIS and convert XY table to point using the lat/long columns. Then project to the coordinate reference system EPSG 26986 and save as a shapefile --> output: **TRI_Facilities_MA_2024.shp** (in a zipped folder)
5. Input: **TRI_Facilities_MA_2024.shp** --> right-click layer in QGIS: export -> save features as, and save as a geopackage --> output: **TRI_Faciliities_MA_2024.gpkg**


## Instrument- or software-specific information needed to interpret the data: 

* Standards and calibration information, if appropriate: N/A
* Environmental/experimental conditions: N/A
* Describe any quality-assurance procedures performed on the data: N/A
* People involved with sample collection, processing, analysis and/or submission: N/A


# DATA-SPECIFIC INFORMATION FOR: [TRI_Facilities_MA_2024.gpkg]

* **Number of variables**: 16
* **Number of cases/rows**: 819
* **Variable List**: All variable descriptions taken directly from **TRI_basic_plus_data_files_documentation_full_2024.pdf**
	* **9. TRIFD**: The unique TRI facility identification (TRIFID) number assigned to each facility for TRI reporting purposes
	* **10. FACILITY NAME**: Name of the reporting facility.
	* **12. FACILITY CITY**: City in which the reporting facility is located.
	* **13. FACILITY COUNTY**: County in which the reporting facility is located.
	* **14. FACILITY STATE**: Two-letter state code of the reporting facility.
	* **15. FACILITY ZIPCODE**: ZIP code of the reporting facility.
	* **LATITUDE**: The latitude value that best represents the facility according to EPA’s Facility Registry System (FRS). Format: 2-digit whole number followed by a decimal point and 6 digits (+nn.nnnnnn).
	* **LONGITUDE**: The longitude value that best represents the facility according to EPA’s Facility Registry System (FRS). Format: 3digit whole number followed by 6 digits (+nnn.nnnnnn).
	* **81. CHEMICAL NAME**: Name of the chemical as listed on the TRI chemical list, or generic name, if the chemical is claimed as a trade secret.
	* **84. CHEMICAL CLASS**: Indicates the classification of the chemical. Chemicals can be classified as either a dioxin or dioxin-like compound, a Persistent, Bioaccumulative and Toxic chemical, or a general EPCRA Section 313 chemical.
	* **85 UNIT OF MEASURE**: Indicates the unit of measure used to quantify the chemical. Dioxin and dioxin-like compounds are reported in grams, while all other TRI chemicals are reported in pounds.
	* **86. HAZARDOUS AIR POLLUTANT - HAPS**: Flag indicating whether the chemical is listed as a hazardous air pollutant under the Clean Air Act (CAA). Yes = CAAC; No = Non-CAAC
	* **87. CARCINOGEN**: Flag indicating whether the chemical is classified as a carcinogen by the Occupational Safety and Health Administration (OSHA). Yes = CARC; No = Non-CARC
	* **88. PFAS_IND**: Flag indicating whether the chemical is a per- and polyfluoroalkyl substance (PFAS) or not. Yes = PFAS; No = non-PFAS
	* **89. METAL IND**: Flag indicating whether the chemical is a metal with TRI reporting restrictions. Yes = Metal with reporting restrictions; No = TRI chemical without reporting restrictions
	* **118. TOTAL AIR EMISSIONS**: Total quantity of reported air emissions. Units: pounds. Total is calculated as the sum of TOTAL FUGITIVE AIR EMISSIONS (#110) and TOTAL STACK AIR EMISSIONS (#113) -- Columns 110 and 113 were deleted during Step 3 of data processing. 


* Missing data codes:  N/A
* Specialized formats or other abbreviations used: N/A
