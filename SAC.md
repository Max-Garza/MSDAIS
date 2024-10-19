An cloud environment made by the makers of SAP BW 4HANA. Allows one to create data warehouses and analyze data within them.

- Background
	- [[Data Warehouse]]
	- [[SAP BW 4HANA]]

# [[exam_2#SAC (SAP Analytics Cloud)|SAC]] MODEL CREATION
## Illustration
![[Pasted image 20240423110148.png]]

## Basic Process
1. Create [[exam_2#Model|Model]] and Assign Data
	1. Create a [[exam_2#Model|model]]
	2. Select data source
2. Alter [[exam_2#Dimension (SAC)|Dimension]] Types
	1. Convert erroneous [[exam_2#Measure (SAC)|measures]] to [[exam_2#Dimension (SAC)|dimensions]]
3. Link Related [[exam_2#Dimension (SAC)|Dimensions]]
	1. Link [[exam_2#Dimension (SAC)|dimensions]] together
	2. Add description
4. Alter and Delete [[exam_2#Dimension (SAC)|Dimensions]]/[[exam_2#Measure (SAC)|Measures]]
	1. Delete as needed
	2. Add [[exam_2#Hierarchy (SAC)|hierarchies]] as needed
	3. Alter data types as needed
5. Create [[exam_2#Dimension Table (SAC)|Dimension Tables]]
	1. Select [[exam_2#Dimension (SAC)|dimensions]] or linked [[exam_2#Dimension (SAC)|dimensions]]
	2. Convert to [[exam_2#Dimension Table (SAC)|dimension table]]
6. Final [[exam_2#Dimension (SAC)|Dimension]] Adjustments
	1. [[exam_2#Transform (SAC)|Transform]] [[exam_2#Dimension (SAC)|dimensions]]
	2. Edit [[exam_2#Measure (SAC)|measures]]

## Detailed Process
1. SAP Analytics Cloud website, “Modeler”
2. “Create new [[exam_2#Model|model]]”
3. “Start with data”, “Next”
4. “File”
5. Select source, define headers, and import	
6. Change variables to [[exam_2#Dimension (SAC)|dimensions]]/[[exam_2#Measure (SAC)|measures]] as needed
	1. Select checkboxes next to variables to convert
	2. Three dots in upper left
	3. “Convert to X”
7.	Link related variables (prepare to make proper [[exam_2#Dimension Table (SAC)|dimension tables]])
	1. Select column of interest
	2. Put a description if desired
	3. Under “Properties”, hit + and select proper property from column list
	4. Iterate as needed
8.	Add [[exam_2#Hierarchy (SAC)|hierarchies]] as needed
	1. Select column of interest
	2. Hit + close to “Hierarchies”
	3. Set up [[exam_2#Hierarchy (SAC)|hierarchies]]
9.	Delete variables as needed
10.	Change data types as needed
	1. Select column of interest
	2. Hit three dots on its row
	3. “Change property type”
	4. May need to change descriptions; avoid keywords
	5. Can change data type from dimension page as well
11.	Convert [[exam_2#Dimension (SAC)|dimension]] w/ attributes to [[exam_2#Dimension Table (SAC)|dimension table]]
	1. Select dimension of interest
	2. “Generate dimension table”
12.	[[exam_2#Transform (SAC)|Transform]] columns as needed
	1. Select relevant columns
	2. In “Data Foundation”, hit “Transform data”
	3. Select relevant columns and “Create a Transformation”
	4. “Concatenate” or other commands
	5. Adjust details panel for new column as needed
13.	[[exam_2#Measure (SAC)|Measure]] editing as needed
	1. Select relevant [[exam_2#Measure (SAC)|measure]]
	2. Change data type, currency, and/or unit type

# [[exam_2#SAC (SAP Analytics Cloud)|SAC]] STORY CREATION
## Illustration
![[Pasted image 20240423113011.png]]

## Basic Process
1. Create a [[exam_2#Canvas (SAC)|Canvas]]
2. Add Data to [[exam_2#Canvas (SAC)|Canvas]]
	1. Existing [[exam_2#Model|model]] or new [[exam_2#Model|model]]
3. Correct Data
	1. Necessary if creating new [[exam_2#Model|model]]
	2. Similar to [[exam_2#exam_2 SAC (SAP Analytics Cloud) SAC MODEL CREATION|SAC Model Creation Process]]
		1. Convert to [[exam_2#Dimension (SAC)|dimension]]/[[exam_2#Measure (SAC)|measure]]
		2. [[exam_2#Transform (SAC)|Transform]] [[exam_2#Dimension (SAC)|dimensions]]
		3. Create [[exam_2#Hierarchy (SAC)|hierarchies]]
		4. Change data types
4. Run a [[exam_2#Smart Discovery|Smart Discovery]]
	1. Select data to use and generate
	2. Provides auto-generated ML results and visualizations
5. Get Custom Visualizations and reports
	1. Create new chart/report and select data

## Detailed Process
1.	“[[exam_2#Story|Stories]]” tab
2.	“[[exam_2#Canvas (SAC)|Canvas]]”
3.	“Add data”
4.	Select proper source
5.	Convert [[exam_2#Measure (SAC)|measures]] to [[exam_2#Dimension (SAC)|dimensions]] or vice-versa as needed
	1. Find column
	2. Three dots
	3. “change to X”
6.	Transform columns and create [[exam_2#Hierarchy (SAC)|hierarchies]] as needed
7.	Change data type as needed
	1. Must change datatype to correct one before transformations
8.	“Story” tab
9.	“Run a [[exam_2#Smart Discovery|Smart Discovery]]”
10.	Select target, entity, and filters
11.	“Run”
12.	Add new chart/info
	1. Insert new tab
	2. Select object to add

# SAC NOTES
## SAC (SAP Analytics Cloud)
A cloud-based data warehouse or other [[exam_2#Reference Architecture|reference architecture]].
## Model
An [[exam_2#SAC (SAP Analytics Cloud)|SAC]] object that stores a data warehouse or other [[exam_2#Reference Architecture|reference architecture]].
## Dimension (SAC)
Information about an entity stored in a column.
## Measure (SAC)
KPI used in fact reporting stored in a column.
## Dimension Table (SAC)
A table storing entity information; dimension in data warehousing terms
## Transform (SAC)
An alteration to column or set of columns.
## Hierarchy (SAC)
Allows one to filter data by a column granularly; applies to [[exam_2#Dimension (SAC)|dimension-type columns]].
## Canvas (SAC)
Visualization area.
## Smart Discovery
Option to auto-generate visualizations and ML results.
## Story
Collection of visualizations.