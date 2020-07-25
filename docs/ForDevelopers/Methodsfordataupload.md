#Data Ingestion and File Conversion


**Data ingestion** is the transportation of data from assorted sources to a storage medium where it can be accessed, used, and analyzed by an organization.

![tsd](../img/image003.png)

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


## Upload Data

In this application you can upload data of different format.
* CSV
* Excel
* Json
* HTML
* SQL
* Mongodb

### Read from csv
Method Name    |read_data_from_csv|   |
------------ | ------------- | -----|
| | Method Description |This method will be used to read data from a csv file or a flat file
 | |Input parameter  names |self,file_name, header,names, use_cols, separator 
 | |Input Parameter Description|   file_name: name of the file to be read header: Row number(s) to be used as column names names : array-like, optional List of column names to use. If file contains no header row, then you should explicitly pass ``header=None``. Use_cols:  To load a subset of columns Separator: Delimiter to use 
 | |ouptput    |A pandas Dataframe 
 | |On Exception|  Write the exception in the log file. Raise an exception with the appropriate error message 

