## Workflow Data Ingestion and File Conversion</h1>

### **Data Ingestion:** 

**Data ingestion** is the transportation of data from assorted sources to a storage medium where it can be accessed, used, and analyzed by an organization.

![tsd](img/image003.png)

The destination is typically a data warehouse, data mart, database, or a document store. 

Data Connector Utils | File Conversion Utils |
------------ | ------------- | 
[Microsoft Access](https://help.tableau.com/current/pro/desktop/en-us/examples_access.htm) | CSV & text files, PDF
[Spatial File]()| JSON
[Statistical File]()|HTML
[Tableau Server or Tableau Online]()|Excel files
[Actian Matrix]()|openDocument Spreadsheets
[Actian Vectorwise]()|Binary Excel (.xlsb) files
[Alibaba AnalyticDB for MySQL]()|Clipboard
[Alibaba Data Lake Analytics]()|Pickling
[Alibaba MaxCompute]()|msgpack
[Amazon Athena]()|HDF5 (PyTables)
[Amazon Aurora for MySQL]()|Feather
[Amazon EMR Hadoop Hive]()|Parquet
[Amazon Redshift]()|ORC
[Anaplan]()|Google BigQuery
[Apache Drill]()|Stata format
[Aster Database]()|SAS formats
[Azure SQL Synapse Analytics]()|SPSS formats
[Box]()|Other file formats
[Cloudera Hadoop]()|Performance considerations
[Databricks]()|
[Denodo]()|
[Dropbo]()|
[Esri ArcGIS Server]()|
[Exasol]()|
[Firebird 3]()|
[Google Ads]()|
[Google Analytics]()|
[Google BigQuery]()|
[Google Cloud SQL]()|
[Google Drive]()|
[Google Sheets]()|
[Hortonworks Hadoop Hive]()|
[IBM BigInsights]()|
[IBM DB2]()|
[IBM PDA (Netezza)]()|
[Impala]()|
[Intuit QuickBooks Online]()|
[Kognitio]()|
[Kyvos]()|
[LinkedIn Sales Navigator]()|
[MapR Hadoop Hive]()|
[MariaDB]()|
[arketo]()|
[MarkLogic]()|
[MemSQL]()|
[Microsoft Analysis Services]()|
[Microsoft PowerPivot]()|
[Microsoft SQL Server]()|
[MonetDB]()|
[MongoDB BI Connector]()|
[MySQL]()|
[OData]()|
[OneDrive]()|
[Oracle]()|
[Oracle Eloqua]()|
[Oracle Essbase]()|
[Pivotal Greenplum]()|
[PostgreSQL]()|
[Presto]()|
[Progress OpenEdge]()|
[Qubole Presto]()|
[Salesforce]()|
[Splunk]()|
[SAP HANA]()|
[SAP NetWeaver Business Warehouse]()|
[SAP Sybase ASE]()|
[SAP Sybase IQ]()|
[ServiceNow ITSM]()|
[SharePoint Lists]()|
[Snowflake]()|
[Spark SQL]()|
[Connector Plugin]()|
[Web Data Connector]()|
[Other Databases (JDBC)]()|
[Other Databases (ODBC)]()|


**Phase 2:**

Data Connector Utils | File Conversion Utils |
------------ | ------------- | 
[Spatial File](https://help.tableau.com/current/pro/desktop/en-us/examples_spatial_files.htm)| OpenDocument Spreadsheets
[Statistical File](https://help.tableau.com/current/pro/desktop/en-us/examples_statfile.htm)| 
[Tableau Server or Tableau Online](https://help.tableau.com/current/pro/desktop/en-us/examples_tableauserver.htm)|
[Actian Matrix](https://help.tableau.com/current/pro/desktop/en-us/examples_actianmatrix.htm)|
[Teradata OLAP Connector](https://help.tableau.com/current/pro/desktop/en-us/examples_teradata_olap.htm)|
[TIBCO Data Virtualization](https://help.tableau.com/current/pro/desktop/en-us/examples_ciscoinfoserver.htm)|
[Vertica](https://help.tableau.com/current/pro/desktop/en-us/examples_vertica.htm)|
[Teradata](https://help.tableau.com/current/pro/desktop/en-us/examples_teradata.htm)|

![Technical solution design](img/TSD-1.png)

Class Name | DataGetter |  |
------------ | ------------- | -----|
Method Name    |read_data_from_csv    |
| | Method Description |This method will be used to read data from a csv file or a flat file
 | |Input parameter  names |self,file_name, header,names, use_cols, separator 
 | |Input Parameter Description|   file_name: name of the file to be read header: Row number(s) to be used as column names names : array-like, optional List of column names to use. If file contains no header row, then you should explicitly pass ``header=None``. Use_cols:  To load a subset of columns Separator: Delimiter to use 
 | |ouptput    |A pandas Dataframe 
 | |On Exception|  Write the exception in the log file. Raise an exception with the appropriate error message 
Method Name|   read_data_from_json||
| |Method Description  |This method will be used to read data from a json file.
| |Input parameter  names| self,file_name
| |Input Parameter Description |file_name: name of the file to be read
| |ouptput|    A pandas Dataframe
| |On Exception| Write the exception in the log file. Raise an exception with the appropriate error message
Method Name    |read_data_from_html   |
| |Method Description  |This method will be used to read data from an HTML web page Input parameter  names    self,url
| |Input Parameter Description|    url: URL of the HTML page to be read. 
| |ouptput |A pandas Dataframe
| |On Exception    |Write the exception in the log file. Raise an exception with the appropriate error message
Method Name    |read_data_from_excel  |
| |Method Description| This method will be used to read data from an MS Excel File
| |Input parameter  names| self,file_name,sheet_name, header,names, use_cols, separator
| |    Input Parameter Description    |file_name: name of the file to be read sheet_name: Lists of strings/integers are used to request multiple sheets. Specify None to get all sheets. header: Row number(s) to be used as column names names : array-like, optional List of column names to use. If file contains no header row, then you should explicitly pass ``header=None``. Use_cols:  To load a subset of columns Separator: Delimiter to use
| | ouptput    |A pandas Dataframe
| |On Exception    |Write the exception in the log file. Raise an exception with the appropriate error message
Method Name    |Connect_to_sqldb  |
| |Method Description| This method will be used to connect to a SQL Databases
| |Input parameter  names| self,host,port, username, password
   | |Input Parameter Description|    host: the server hostname/IP where the DB server is hosted Port: the port at which the DB Server is running username: The username to connect to the DB server password: The password to connect to the DB server
| |ouptput|    A DB connection object
| |    On Exception   |Write the exception in the log file. Raise an exception with the appropriate error message
Method Name    |read_data_from_sqldb| |
| |Method Description  |This method will be used to read data from SQL Databases
| |Input parameter  names  |self,db_name,host,port, username, password, schema_name,query_string
   | |Input Parameter Description|    db_name: For example, SQL, MySQL, SQLLite etc. host: the server hostname/IP where the DB server is hosted Port: the port at which the DB Server is running username: The username to connect to the DB server password: The password to connect to the DB server schema_name: The name of the DB schema the user wants to connect to. query_string: the query to be executed to load the data
| |ouptput |A Pandas Dataframe
| |    On Exception   |Write the exception in the log file. Raise an exception with the appropriate error message Method Name    read_data_from_mongdb  
| |Method Description| This method will be used to read data from Mongo DB
| |Input parameter  names  |self,host,port, username, password, db_name,collection_name, query_string. Input Parameter Description    |host: the server hostname/IP where the DB server is hosted Port: the port at which the DB Server is running username: The username to connect to the DB server password: The password to connect to the DB server db_name: The name of the database collection_name: The name of the collection the user wants to connect to. query_string: the query to be executed to load the data
   | |output| A Pandas Dataframe
   | |On Exception    |Write the exception in the log file. Raise an exception with the appropriate error message


**Exceptions Scenarios**

|Step  |Exception |Mitigation|
--------|----------|----|
User gives Wrong Data Source|  Give proper error message| Ask the user to re-enter the details
User gives corrupted data |    Give proper error message  



<h2>Data Profiling</h2>

**Data profiling** is the process of reviewing source data, understanding structure, content and interrelationships, and identifying potential for data projects.   

![Data Profiling](img/data_profiling.png)


After reading the data, automatically the following details should be shown:
a) The number of rows
b) The number of columns
c) Number of missing values per column and their percentage
d) Total missing values and it’s percentage
e) Number of categorical columns and their list
f) Number of numerical columns and their list
g) Number of duplicate rows
h) Number of columns with zero standard deviation and their list
i) Size occupied in RAM

Method Definition

Class Name |DataProfiler||
---------|--------|-------|
Method Name    |get_data_profile  |
||Method Description|  This method will be used to give various insighst about data.
| |Input parameter  names| self, dataframe
| |Input Parameter Description |dataframe: the inpt data just loaded from source 
| |ouptput |a)    The number of rows 
| | |b)    The number of columns
| | |c)    Number of missing values per column and their percentage
| | |d)    Total missing values and it’s percentage
| | |e)    Number of categorical columns and their list
| | |f)    Number of numerical columns and their list
| | |g)    Number of duplicate rows
| | |h)    Number of columns with zero standard deviation and their list
| | |i)    Size occupied in RAM
| |On Exception    |Write the exception in the log file. Raise an exception with the appropriate error message
