A data warehouse platform frequently used by banks and finance-related companies.

- Background
	- [[Data Warehouse]]

# FLOW OF DATA IN [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]]

## Illustration
![[Pasted image 20240423093353.png]]

## Basic Explanation
1. Extract data to [[exam_2#DataSource|DataSource]]
2. T/L data from [[exam_2#DataSource|DataSource]] to [[exam_2#InfoObject|InfoObject]]
3. build [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] from [[exam_2#InfoObject|InfoObject]] data
4. build [[exam_2#CompositeProvider|CompositeProvider]] from [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] data
5. build [[exam_2#Query|query]] from [[exam_2#CompositeProvider|CompositeProvider]] data
6. access [[exam_2#Query|query]] data in [[exam_2#B.I. Client|B.I. client]]
## Detailed Explanation
1. [[exam_2#DataSource|DataSource]] - Data brought into the warehouse via [[exam_2#ETL|ETL]] or manual definition
	1. [[exam_2#Extract (Etl)|Extract]] - [[exam_2#DataSource|DataSource]] pulls data from some external source
	2. [[exam_2#Transform (eTl)|Transform]] - A [[exam_2#Transformation|transformation]] in the [[exam_2#InfoObject|InfoObject's]] [[exam_2#DataFlow|DataFlow]]
	3. [[exam_2#Load (etL)|Load]] - A [[exam_2#DTP (Data Transfer Process)|DTP]] in the [[exam_2#InfoObject|InfoObject's]] [[exam_2#DataFlow|DataFlow]]
2. [[exam_2#InfoObject|InfoObject]] - Building blocks created
	1. [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] is connected to the [[exam_2#DataSource|DataSource]]
	2. [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] is assigned [[exam_2#Field|fields]] and [[exam_2#InfoObject|InfoObjects]]
	3. [[exam_2#Transformation|Transformation]] in the [[exam_2#aDSO (Advanced Data Store Object)|aDSO's]] [[exam_2#DataFlow|DataFlow]]
	4. [[exam_2#DTP (Data Transfer Process)|DTP]] in the [[exam_2#aDSO (Advanced Data Store Object)|aDSO's]] [[exam_2#DataFlow|DataFlow]]
3. [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] - Base structure of warehouse or other [[exam_2#Reference Architecture|reference architecture]] created
	1. [[exam_2#CompositeProvider|CompositeProvider]] is assigned an [[exam_2#aDSO (Advanced Data Store Object)|aDSO]]
	2. [[exam_2#CompositeProvider|CompositeProvider]] source is connected to target
4. [[exam_2#CompositeProvider|CompositeProvider]] - [[exam_2#Query|Query]]-able form of [[exam_2#aDSO (Advanced Data Store Object)|aDSO]]
	1. [[exam_2#CompositeProvider|CompositeProvider]] navigation defined
	2. [[exam_2#Query|Query]] elements selected
5. [[exam_2#Query|Query]] - Virtual [[exam_2#Data View|data view]]
6. [[exam_2#B.I. Client|B.I. client]] - Analysis of data in [[exam_2#Data View|data view]]

## Theoretical Explanation
1. Get data into database via [[exam_2#DataSource|DataSource]]; physical
2. Make data useable by placing into [[exam_2#InfoObject|InfoObjects]]; physical
3. Connect [[exam_2#InfoObject|InfoObjects]] and other [[exam_2#Field|fields]] into useable form via [[exam_2#aDSO (Advanced Data Store Object)|aDSO]]; physical
4. Make [[exam_2#Data Mart|data mart]] (or other [[exam_2#Reference Architecture|reference architecture]] component) [[exam_2#Query|query]]-able via [[exam_2#CompositeProvider|CompositeProvider]]; virtual
5. Create [[exam_2#Query|query]] to access necessary data virtually
6. Pull [[exam_2#Query|query]] data into a [[exam_2#B.I. Client|B.I. client]] for analysis

# CREATION OF REFERENCE ARCHITECTURE IN [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]]
## Illustration
![[Pasted image 20240423100742.png]]

## Basic Process
1. Create [[exam_2#InfoObject|InfoObject(s)]]
	- Create [[exam_2#InfoObject|InfoObject]]
	- Define as [[exam_2#Characteristic|characteristic]] or [[exam_2#Key Figure|key figure]]
	- Mark "Useable as InfoProvider" if needed
2. Populate [[exam_2#InfoObject|InfoObjects]] with data via [[exam_2#ETL|ETL]] or manual process
	- Create [[exam_2#DataSource|DataSource]]
	- [[exam_2#Extract (Etl)|Extract]] - Map [[exam_2#DataSource|DataSource]] to an external source and [[exam_2#Extract (Etl)|extract]] the data
	- [[exam_2#Transform (eTl)|Transform]] - Create a [[exam_2#DataFlow|DataFlow]], add [[exam_2#InfoObject|InfoObject]] and [[exam_2#DataSource|DataSource]], and create a [[exam_2#Transformation|transformation]]
	- [[exam_2#Load (etL)|Load]] - Select [[exam_2#DTP (Data Transfer Process)|DTP]] in said [[exam_2#DataFlow|DataFlow]] and execute it
3. Create and populate an [[exam_2#aDSO (Advanced Data Store Object)|aDSO]]
	- Create the [[exam_2#aDSO (Advanced Data Store Object)|aDSO]]
	- Connect [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] to the [[exam_2#DataSource|DataSource]]
	- Assign [[exam_2#aDSO (Advanced Data Store Object)|aDSO's]] [[exam_2#Field|fields]] and [[exam_2#InfoObject|InfoObjects]]
	- Create a [[exam_2#DataFlow|DataFlow]] and a [[exam_2#Transformation|transformation]]
	- In said [[exam_2#DataFlow|DataFlow]], select and execute the [[exam_2#DTP (Data Transfer Process)|DTP]]
4. Create and populate a [[exam_2#CompositeProvider|CompositeProvider]]
	- Create the [[exam_2#CompositeProvider|CompositeProvider]]
	- Assign [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] to said [[exam_2#CompositeProvider|CompositeProvider]]
	- Connect source [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] to [[exam_2#CompositeProvider|CompositeProvider]] target
5. Change [[exam_2#CompositeProvider|CompositeProvider's]] structure
	- "Output" tab within [[exam_2#CompositeProvider|CompositeProvider]]
	- Add [[exam_2#Navigation Attribute|navigation attributes]]
6. Create a [[exam_2#Query|Query]]
	- "Info Provider" panel within [[exam_2#CompositeProvider|CompositeProvider]]
	- Drag desired elements into the info provider panel
	- Check reporting preview
7. Access [[exam_2#Query|Query]] via [[exam_2#B.I. Client|B.I. Client]] (namely Excel)
	- Open Excel
	- "Analysis" tab from SAP add-in
	- "Insert Data Source" and "Select Data Source"
	- Select [[exam_2#Query|query]]

## Detailed Process
1.	Create [[exam_2#InfoObject|InfoObjects]] ([[exam_2#Characteristic|Characteristics]] and [[exam_2#Key Figure|Key Figures]])
	1. Use correct [[exam_2#InfoObject|InfoObject]] type and data type
	2. Ensure proper units/aggregation ([[exam_2#Key Figure|key figure]])
	3. Ensure proper length and properties
	4. Check other tabs and select options as needed; [[exam_2#Language Dependent|language dependent]] may be true for [[exam_2#Characteristic|characteristics]]
	5. Choose whether to display the key or something else ([[exam_2#Characteristic|characteristic]])
	6. Check “Useable as InfoProvider” if data will be imported via [[exam_2#ETL|ETL]] process
	7. Add attributes ([[exam_2#Field|fields]])
2.	Populate [[exam_2#InfoObject|InfoObjects]] with Data – Manual and [[exam_2#ETL|ETL]]
	- Manual – small amnt of data
		1. Go to SAP cockpit (fiori)
		2. “Data Display and Maintenance”
		3. “Info Object Master Data Maintenance”
		4. Search for and select [[exam_2#InfoObject|InfoObject]]
		5. “Texts”
		6. Fill in fields
		7. Save and log out
	- [[exam_2#ETL|ETL]] – large amnt of data
		1. [[exam_2#Extract (Etl)|Extract]] – You may be able to copy data sources and repurpose them
			1.	Check separator in your data
			2.	“Data Sources”
			3.	“File”
			4.	“Flat-File”
			5.	Area
			6.	User Area
			7.	“New”
			8.	“[[exam_2#DataSource|DataSource]]”
			9.	May copy info from other [[exam_2#DataSource|DataSources]]
			10.	Choose appropriate [[exam_2#DataSource|DataSource]] type
			11.	“Extraction” tab – choose proper settings
			12.	“Derive fields from file”
			13.	May need to correct data types, lengths, references, and format settings ([[exam_2#Internal|internal]] vs [[exam_2#External|external]])
			14.	Save/activate and check data preview; note [[exam_2#Internal/External Format Option|internal format option]]
		2. [[exam_2#Transform (eTl)|Transform]]
			1.	Go to your [[exam_2#InfoArea|InfoArea]] and create a [[exam_2#DataFlow|DataFlow]] object
			2.	“copy from” if needed
			3.	Add an [[exam_2#InfoObject|InfoObject]] to the flow canvas
			4.	Assign correct [[exam_2#InfoObject|InfoObject]] to [[exam_2#InfoObject|InfoObject(s)]] on the canvas
			5.	Add [[exam_2#DataSource|DataSource]] to the [[exam_2#DataFlow|DataFlow]]
			6.	Assign correct [[exam_2#DataSource|DataSource]] to [[exam_2#DataSource|DataSource(s)]] on the canvas
			7.	Hover over [[exam_2#DataSource|DataSource]], click thin arrow on side, and drag towards the important [[exam_2#InfoObject|InfoObject]]
			8.	Double-click the [[exam_2#Transformation|Transformation]] icon on the [[exam_2#InfoObject|InfoObject]]
			9.	Copy rules as needed
			10.	“rules” tab
			11.	Define [[exam_2#Transformation Rules|transformation rules]] by dragging/dropping
				- May need to define [[exam_2#Language Key|language key]]
			12.	Save/activate the [[exam_2#Transformation|transformation]] and [[exam_2#DataFlow|DataFlow]]
		3. [[exam_2#Load (etL)|Load]]
			1.	Double-click the [[exam_2#DTP (Data Transfer Process)|DTP]] icon on the [[exam_2#InfoObject|InfoObject]] ([[exam_2#DataFlow|DataFlow]])
			2.	Copy from if needed
			3.	In the [[exam_2#DTP (Data Transfer Process)|DTP]] editor, check settings on all tabs
			4.	Save/Activate [[exam_2#DTP (Data Transfer Process)|DTP]] editor
			5.	Click on green bubble w/ arrow (start execution of [[exam_2#DTP (Data Transfer Process)|DTP]])
			6.	“Execute” and go back to [[exam_2#DTP (Data Transfer Process)|DTP]] tab
			7.	Save/Activate
			8.	Check if the [[exam_2#DTP (Data Transfer Process)|DTP]] on the [[exam_2#DataFlow|DataFlow]] tab has turned blue. If so, success
			9.	Go to Fiori to see if the data was loaded properly
3.	Create and Populate an [[exam_2#aDSO (Advanced Data Store Object)|aDSO]]
	- Create
		1. Create [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] in [[exam_2#InfoArea|InfoArea]]
		2. Select correct [[exam_2#DataSource|DataSource]]
		3. May select “[[exam_2#Data Mart|Data Mart]] Data Store Object”
		4. Add relevant groups that pull data from [[exam_2#InfoObject|InfoObjects]]
		6. Assign [[exam_2#Field|field(s)]] to groups and correct them to [[exam_2#InfoObject|InfoObjects]] as needed
		7. Add/assign [[exam_2#InfoObject|InfoObjects]] as needed
		8. Save/activate
	- Populate
		1. Create a new [[exam_2#DataFlow|DataFlow]] object
		2. Copy From if needed
		3. Add a [[exam_2#DataSource|DataSource]] into the canvas
		4. Assign [[exam_2#InfoObject|InfoObject(s)]] to [[exam_2#DataSource|DataSource(s)]]
		5. Add the [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] to the canvas
		6. Save/activate
		7. Connect one source to the [[exam_2#aDSO (Advanced Data Store Object)|aDSO]]
		8. Create a [[exam_2#Transformation|transformation]] (see prior notes)
		9. Create and execute a [[exam_2#DTP (Data Transfer Process)|DTP]] (see prior notes)
		10. Save all/activate
	- Activate – Make [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] useable for analytics
		1. Log on to Fiori
		2. “DataStore Objects Manage Requests”
		3. Find your [[exam_2#aDSO (Advanced Data Store Object)|aDSO]]
		4. Select [[exam_2#DTP (Data Transfer Process)|DTP]] request
		5. Activate [[exam_2#DTP (Data Transfer Process)|DTP]] request
		6. Return to Eclipse
		7. Go to [[exam_2#DataFlow|DataFlow]]
		8. Save/activate [[exam_2#DataFlow|DataFlow]]
4.	Create a [[exam_2#CompositeProvider|CompositeProvider]]
	1. Create [[exam_2#CompositeProvider|CompositeProvider]] in [[exam_2#InfoArea|InfoArea]]
	2. "Next”
	3. Add [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] into “Union Providers” (may go into join providers)
	4. “Finish” and save
	5. “Scenarios” tab
	6. Drag from source to target (NOT INDIVIDUAL FIELDS)
	7. Save/activate
5.	Change [[exam_2#CompositeProvider|CompositeProvider's]] output structure (if needed)
	1. “Output”
	2. Add [[exam_2#Navigation Attribute|navigation attributes]] as needed
	3. Save/activate
6.	Create a [[exam_2#Query|Query]]
	1. Create [[exam_2#Query|query]] by right-clicking the [[exam_2#CompositeProvider|CompositeProvider]]
	2. “Info provider” panel on the left navigation pane
	3. “Sheet Definition” tab on the right pane
	4. Drag elements from info provider panel to “columns” “rows” etc.
	5. Save
	6. Check reporting preview to see how [[exam_2#Query|query]] looks to end user
7.	[[exam_2#B.I. Client|B.I. Client]] Analysis (Excel)
	1. Open Excel
	2. “analysis”
	3. “Insert Data Source” dropdown
	4. “Select Data Source for Analysis”
	5. Follow steps and select [[exam_2#Query|query]]
	6. Analyze

## Note on [[exam_2#Master Data|Master Data]]
[[exam_2#Master Data|Master Data]] [[exam_2#InfoObject|InfoObjects]] should be created and populated before other [[exam_2#InfoObject|InfoObjects]];

# SAP BW 4/HANA NOTES
## SAP BW 4/HANA
A local database and data warehouse system that multiple users can join. Capable of building many [[exam_2#Reference Architecture|reference architectures]]. Uses [[exam_2#PMEM (Persistent Memory)|PMEM]] and DRAM, allowing entire databases to be stored in-memory and accessed quickly.
## PMEM (Persistent Memory)
Data retained during a power surge; cheaper and larger than DRAM and lower latency than disk access.
## SAP BW 4/HANA Data Warehouse Components
- [[exam_2#DataSource|DataSources]]
- [[exam_2#Modeling Objects|Modeling Objects]]
## Modeling Objects
- [[exam_2#InfoObject|InfoObjects]]
- [[exam_2#Open ODS View (Operational Data Store)|Open ODS Views]]
- [[exam_2#InfoProvider|InfoProviders]]
## DataSource
An [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]] object that stores data physically prior to the [[exam_2#ETL|ETL]] process. Serves as a base for which [[exam_2#InfoObject|InfoObjects]] can draw data from.
## Open ODS View (Operational Data Store)
Allow direct data access without the need for [[exam_2#InfoObject|InfoObjects]]. It is simply a view of the data and is virtual. Often used to pull in external data.
## InfoObject
An [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]] object that stores data physically. These are the building blocks for the database, being relevant mainly to the [[exam_2#aDSO (Advanced Data Store Object)|aDSO]]. These can be [[exam_2#Characteristic|characteristic]] or [[exam_2#Key Figure|key figure]] type.
## aDSO (Advanced Data Store Object)
An [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]] object that combines [[exam_2#InfoObject|InfoObjects]] into larger, but still physical, data collections. These can be [[exam_2#Data Mart|data marts]] or other parts of [[exam_2#Reference Architecture|reference architectures]].
## [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] Tables
- Inbound table (data is written here)
- Change log
- Active data
## Reporting in an [[exam_2#aDSO (Advanced Data Store Object)|aDSO]]
Done with a union of the inbound and active [[exam_2#exam_2 aDSO (Advanced Data Store Object) aDSO Tables|aDSO Tables]]
## CompositeProvider
An [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]] object that refers to an [[exam_2#aDSO (Advanced Data Store Object)|aDSO]], or many of then, and contains all of its/their data virtually. "Logical layer."
## Query
Part of a [[exam_2#CompositeProvider|CompositeProvider]] or [[exam_2#aDSO (Advanced Data Store Object)|aDSO]] that allows users to access subsets of that object's data via [[exam_2#B.I. Client|B.I. clients]].
## B.I. Client
A program, such as Excel, that exists outside of the data warehouse and allows one to analyze data retrieved from a [[exam_2#Query|query]].
## DTP (Data Transfer Process)
Part of [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA's]] [[exam_2#Load (etL)|loading]] ([[exam_2#ETL|ETL]]) step and other data sourcing steps that loads data into the object.
## Transformation
Part of [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA's]] [[exam_2#Transform (eTl)|transformation]] ([[exam_2#ETL|ETL]]) step and other data sourcing steps that defines how data is to be brought into the object via [[exam_2#Transformation Rules|transformation rules]].
## DataFlow
An [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]] object that allows one to connect objects together, allowing [[exam_2#DTP (Data Transfer Process)|DTPs]] and [[exam_2#Transformation|transformations]] to bring data into unpopulated objects from populated ones.
## Field
A [[exam_2#Characteristic|characteristic]] or [[exam_2#Key Figure|key figure]] that is may or may not be included in any user-defined object.
## Characteristic
A [[exam_2#Field|field]] which describes an entity or descriptor relevant to a fact.
## Key Figure
A [[exam_2#Field|field]] which contains a KPI; metric of a fact.
## InfoProvider
An [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]] object that allows one to [[exam_2#Query|query]] the data. There are two types of InfoProvider: [[exam_2#aDSO (Advanced Data Store Object)|aDSOs]] and [[exam_2#CompositeProvider|CompositeProviders]].
## Navigation Attribute
A [[exam_2#Field|field]] which, when set to "navigation attribute", can be filtered by its values. For instance, if there is a "State" [[exam_2#Field|field]], making it a navigation attribute means we can filter to individual states later.
## Language Dependent
A [[exam_2#Field|field]] that allows users to see data written in their language of choice; refers to and makes the [[exam_2#Language Key|language key]] a key [[exam_2#Field|field]].
## Internal Format
A [[exam_2#Field|field]] option selected when the format of the data being brought in is what is expected by [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]].
## External Format
A [[exam_2#Field|field]] option selected when the format of the data being brought in is not what is expected by [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]].
## Internal/External Format Option
A data preview option toggled based on when you want to see [[exam_2#SAP BW 4/HANA|SAP BW 4HANA's]] view of the data vs. how users will see the data. This is only relevant when some or all of your [[exam_2#Field|fields]] are in the [[exam_2#External Format|external format]].
## InfoArea
An area in [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]] that houses all objects except for [[exam_2#DataSource|DataSources]].
## Transformation Rules
[[exam_2#Field|Field]] mappings that define how the source object's data is to be mapped to the target object. Can include custom calculations and/or refer to multiple columns; not always a direct mapping.
## Language Key
A key [[exam_2#Field|field]] that defines the language a given entry is in.
## Master Data
Data stored in a [[exam_2#DataSource|DataSource]]; stored physically and never altered - the original form of the data. It also helps define how data brought into the warehouse is read. It can be created manually or through an [[exam_2#ETL|ETL]] process and is contained in [[exam_2#DataSource|DataSources]] before being brought into [[exam_2#InfoObject|InfoObjects]]. "*When the indicator “Master Data” is set, the system creates a special table which can hold the keys and potential attributes for product category. Although product category does not have any attributes in our case, this table can be used to ensure referential data integrity.*"
## Persistent Staging Area
[[exam_2#SAP BW 4/HANA|SAP BW 4/HANA's]] [[exam_2#Data Staging Area|data staging area]].
## Process Chain
[[exam_2#SAP BW 4/HANA|SAP BW 4/HANA's]] terminology for the entire [[exam_2#ETL|ETL]] process, somewhat like [[exam_2#Data Warehouse Bus Architecture|data warehouse bus architecture]].
## Material vs. Product
In [[exam_2#SAP BW 4/HANA|SAP BW 4/HANA]], it is best practice to store semi-finished products, complete products, and raw materials together in one "Material" object.
## Aggregation in [[exam_2#InfoObject|InfoObjects]]
Summation, minimum, maximum
## Standard Aggregation
A case in [[exam_2#InfoObject|InfoObjects]] where the user requests a standard form of [[exam_2#Aggregation in exam_2 InfoObject InfoObjects|aggregation]]
## Exception Aggregation
A case in [[exam_2#InfoObject|InfoObjects]] where the user needs a custom calculation of a [[exam_2#Key Figure|key figure]] alongside [[exam_2#Aggregation in exam_2 InfoObject InfoObjects|standard aggregation]]
