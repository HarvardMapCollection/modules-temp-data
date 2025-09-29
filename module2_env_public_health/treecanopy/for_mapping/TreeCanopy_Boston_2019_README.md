This readme file was generated on [2025-09-29] by [Anna He]


# GENERAL INFORMATION

* **Title of Dataset**: TreeCanopy_Boston_2019.gpkg

## Author Information
**Name**: Anna He  
**ORCID**: N/A  
**Institution**: Harvard University ITS MMPS  
**Address**: Harvard Map Collection, Pusey Library, Harvard Yard, Cambridge, MA 02138  
**Email**: anna_he@harvard.edu  


* **Date of data collection**: 2019 tree canopy data for Boston downloaded from source on 2025-09-12. Cleaned and processed by 2025-09-12.
* **Geographic location of data collection**: Boston
* **Information about funding sources that supported the collection of the data**: N/A


# SHARING/ACCESS INFORMATION

* Licenses/restrictions placed on the data: [Source data](https://data.boston.gov/dataset/ct-tree-canopy-metrics) is under an Open Data Commons Public Domain Dedication and License (PDDL)
* Links to publications that cite or use the data: 
* Links to other publicly accessible locations of the data: 
* **Links/relationships to ancillary data sets**: 
	* **Original source data downloaded as a polygon shapefile from the Analyze Boston data portal**: "module2_env_public_health\treecanopy\source\Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.zip"
	* **Original source data downloaded as a CSV from Analyze Boston data portal**: "module2_env_public_health\treecanopy\source\Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.csv"
	* **Original source data documentation downloaded from Analyze Boston data portal**: "module2_env_public_health\treecanopy\source\data-dictionary-canopy-change-assessment-.pdf""

	* **Cleaned data in CSV format**: "module2_env_public_health\treecanopy\for_mapping\TreeCanopy_Boston_2019.csv"
	* **Cleaned data in shapefile format**: "module2_env_public_health\treecanopy\for_mapping\TreeCanopy_Boston_2019_shp.zip" 
	* **Cleaned data in geopackage format**: "module2_env_public_health\treecanopy\for_mapping\TreeCanopy_Boston_2019.gpkg"
* Was data derived from another source?
	* If yes, list source(s): Yes, [Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.shp](https://data.boston.gov/dataset/ct-tree-canopy-metrics)
	* **Download source**: Analyze Boston. (2021a, May 14). CT (Census Tract) Tree Canopy Metrics - Dataset - Analyze Boston. Analyze Boston. Retrieved on September 12, 2025 from https://data.boston.gov/dataset/ct-tree-canopy-metrics 
	* **Documentation source**: Analyze Boston. (2021b). Canopy Change Assessment Data Dictionary. Retrieved on September 12, 2025 from https://data.boston.gov/dataset/canopy-change-assessment-data-dictionary/resource/b57c98ef-bce3-4011-b2bb-b853698c9e90 
	* Recommended citation for this dataset: 


# DATA & FILE OVERVIEW

## File List: *list all files (or folders, as appropriate for dataset organization) contained in the dataset, with a brief description*
The most important file to be used for mapping is [TreeCanopy_Boston_2019.gpkg](#data-specific-information-for-treecanopy_boston_2019gpkg). I have documented the origin, description, and creation date of all associated tree canopy metrics files below.

* Parent Folder: **treecanopy/source**
	* File: **Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.zip**
		* **Description**: This file is the original source data downloaded from Analyze Boston. Unzipped, it contains a polygon shapefile titled **Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.shp** that represents CT (Census Tract) Tree Canopy Metrics for Boston. The coordinate reference system is EPSG: 2249 (NAD 1983 StatePlane Massachusetts FIPS 2001(USFeet)_1). Per the source documentation, the census tracts are based on 2010 census tract geographies. The attribute table for the shapefile contains 211 polygons and 40 columns containing tree canopy metrics based on 2019 high-resolution land cover and 2019-leaf-on LIDAR. For detailed information on attributes included, see page 3 of the source documentation. THe most relevant column is TC_E_P. From the documentation: "TC_E_P = Existing percent. The amount of tree canopy present when viewed from above using aerial or satellite imagery, excluding water as a percentage. This is the value most used for reporting out current canopy coverage."
		
		* **Date Downloaded**: 2025-09-12 	

	* File: **Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.csv**
		* **Description**: This file is the CSV version of the original source data, Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.shp. It contains all the original data. It was downloaded from Analyze Boston. The CSV file is included for convenient examination of the data.
		* **Date Created**: 2025-09-12

	* File: **data-dictionary-canopy-change-assessment-.pdf**
		* **Description**: This PDF file is the documentation for the original source data, Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.zip. It describes the project, 2014-2019 Canopy Change Assessment for Boston. It provides an overview and describes the geographies, shapefiles, shapefile attributes, and raster data for this project. 
		* **Date Downloaded**: 2025-09-12

* Parent Folder: **treecanopy/for_mapping**

	* File: **TreeCanopy_Boston_2019_shp.zip**
		* **Description**: This zipped folder contains a shapefile for a layer titled **Tree_Canopy_Boston_2019.shp**. It was derived from **Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.shp**, but this layer was projected into coordinate reference system EPSG 26986: NAD83 Massachusetts State Plane Coordinate System, Mainland Zone (Fipszone 2001, meters) and contains only relevant columns for mapping. The attribute table contains 211 polygon census tract features with columns for IDs and a column titled PctTreeCanopy. PctTreeCanopy is the same as the original TC_E_P column in the documentation, just renamed for clarity ("TC_E_P = Existing percent. The amount of tree canopy present when viewed from above using aerial or satellite imagery, excluding water as a percentage. This is the value most used for reporting out current canopy coverage.") 
		* **Date Created**: 2025-09-12

	* File: **TreeCanopy_Boston_2019.csv**
		* **Description**: This file is the CSV format for the attribute table of **Tree_Canopy_Boston_2019.shp**. It contains only the relevant columns for mapping, such as ID and PctTreeCanopy. 
		* **Date Created**: 2025-09-08	

	* File: **TreeCanopy_Boston_2019.gpkg**
		* **Description**: This file is the geopackage version of **TreeCanopy_Boston_2019.shp**. It was created by converting TreeCanopy_Boston_2019.shp into a geopackage. It contains 211 polygon census tract features with columns for IDs and a column titled PctTreeCanopy to be used for mapping and visualization. The coordinate reference system is EPSG 26986 for NAD83 Massachusetts State Plane Coordinate System, Mainland Zone (Fipszone 2001, meters). Exact attribute descriptions can be found in the [Data-Specific Information](#data-specific-information-for-treecanopy_boston_2019gpkg)
		* **Date Created**: 2025-09-12


* Relationship between files, if important: the /for_mapping files were derived from the /source files as described in the section [Methods for processing the data](#methods-for-processing-the-data)
* Additional related data collected that was not included in the current data package: N/A
* Are there multiple versions of the dataset?
	* If yes, name of file(s) that was updated: 
	* Why was the file updated? 
	* When was the file updated? 


# METHODOLOGICAL INFORMATION

## Description of methods used for collection/generation of data: 

The source data, **Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.zip**, was downloaded in shapefile format from the Analyze Boston open data portal for CT Tree Canopy Metrics (Analyze Boston, 2021a).  
Per the original source documentation **data-dictionary-canopy-change-assessment-.pdf**, the census tracts are based on 2010 census tract geographies. The attribute table for the shapefile contains 211 polygons and 40 columns containing tree canopy metrics based on 2019 high-resolution land cover and 2019-leaf-on LIDAR. "[The purpose of the Tree Canopy Assessment] is to integrate high resolution land cover data with other GIS datasets to produce a set of detailed metrics on the forest that allow decision makers to know how much tree canopy currently exists (termed Existing TC) (Analyze Boston, 2021b). The column TC_E_P, or tree canopy existing percent, is the most relevant column for reporting current canopy coverage.


## Methods for processing the data: 

1. Download source file as a shapefile: **Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.zip** from source [(Analyze Boston, 2021a)](#https://data.boston.gov/dataset/ct-tree-canopy-metrics)
2. Download source file as a CSV: **Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.csv** from source [(Analyze Boston, 2021a)](#https://data.boston.gov/dataset/ct-tree-canopy-metrics)
3. Input: **Canopy_Change_Assessment%3A_Tree_Canopy_Metrics.shp** --> open a GIS. Project the layer to EPSG 26986. Edit fields to delete all irrelevant columns besides the columns: ID, NAME, ST_ABBREV, Shape_Length, Shape_Area, and TC_E_P. Manually rename TC_E_P column as PctTreeCanopy. (note: new shape length and area columns will be automatically added when you project into EPSG 26986 with a unit of meters, so you will need to delete the original shape length and area columns whose units were in feet) --> output: **Tree_Canopy_Boston_2019.shp** (The zipped file is titled **TreeCanopy_Boston_2019_shp.zip**).
4. Input: **Tree_Canopy_Boston_2019.shp** --> export attribute table as CSV --> output: **TreeCanopy_Boston_2019.csv**
5. Input: **Tree_Canopy_Boston_2019.shp** --> right-click layer in QGIS: export -> save features as, and save as a geopackage --> output: **TreeCanopy_Boston_2019.gpkg**



## Instrument- or software-specific information needed to interpret the data: 

* Standards and calibration information, if appropriate: N/A
* Environmental/experimental conditions: N/A
* Describe any quality-assurance procedures performed on the data: N/A
* People involved with sample collection, processing, analysis and/or submission: N/A


# DATA-SPECIFIC INFORMATION FOR: [TreeCanopy_Boston_2019.gpkg]

* **Number of variables**: 8
* **Number of cases/rows**: 211
* **Variable List**: 
	* **FID**: GIS-generated ID
	* **Shape**: Geometry shape
	* **ID**: Census tract GEOID based on the 2010 Census data
	* **NAME**: Census tract name ID based on 2010 census data
	* **ST_ABBREV**: State location, abbreviated
	* **PctTreeCanopy**: "Existing percent of tree canopy. The amount of tree canopy present when viewed from above using aerial or satellite imagery, excluding water as a percentage. This is the value most used for reporting out current canopy coverage." (Analyze Boston, 2021b)
	* **Shape_Length**: Polygon peremeter (meters)
	* **Shape_Area**: Polygon area (meters)


* Missing data codes:  N/A
* Specialized formats or other abbreviations used: N/A
