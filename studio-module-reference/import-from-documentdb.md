---
title: "Import from DocumentDB | Microsoft Docs"
ms.custom: ""
ms.date: 09/20/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2460018-5139-434b-881e-3e22de9c7917
caps.latest.revision: 22
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlun"
---
# Import from DocumentDB
This article describes how to the [Import Data](import-data.md) module in Azure Machine Learning to import data from Azure DocumentDB, for use in a machine learning experiment.  
  
Azure DocumentDB is a fully managed NoSQL database service that lets you store data using a flexible data model. The advantages of DocumentDB for machine learning include fast and predictable performance, automatic scaling, global distribution, and rich query capabilities that let you filter incoming datasets.  
  
 To use Microsoft Azure DocumentDB, you must have access to an existing DocumentDB account containing a collection of related documents.  
 
    
> [!TIP]
> New to DocumentDB? See these resources to learn how it works:  
> 
> [Learn about DocumentDB](https://azure.microsoft.com/documentation/learning-paths/documentdb/)  
> 
> [Introduction to DocumentDB: A NoSQL JSON Database](https://azure.microsoft.com/en-us/documentation/articles/documentdb-introduction/)  
  
## How to Import Data from DocumentDB  

We strongly recommend that you profile your data before importing, to make sure that the schema is as expected. The import process will scan some number of head rows to determine the schema, but later rows might contain extra columns, or data that cause errors.

### Use the Data Import Wizard

The module features a new wizard to help you choose a storage option,  select from among existing subscriptions and accounts, and quickly configure all options.

1. Add the **Import Data** module to your experiment. You can find the module under **Data Input and Output**.

2. Click **Launch Import Data Wizard** and follow the prompts.

3. When configuration is complete, to actually copy the data into your experiment, right-click the module, and select **Run Selected**. 

If you need to edit an existing data connection, the wizard loads all previous configuration details so that you don't have to start again from scratch.

### Manually set properties in the Import Data module

The following steps describe how to manually configure the import source.
  
1.  Add the [Import Data](import-data.md) module to your experiment. You can find this module in the [Data Input and Output](data-input-and-output.md) group in the **experiment items** list in Azure Machine Learning Studio. 
  
2.  For **Data source**, select **Azure DocumentDB**.  
  
3.  Provide connection information for an existing document database. The document store must have been created using  Microsoft Azure DocumentDB.  

    - **Endpoint URL**. To get the endpoint URL for your DocumentDB, in the Azure Portal, click **Keys**, and copy the contents of the **URI** field at the top of the page.
  
    -   **Database ID**. Paste the name of the database to use.  To view the database name in the Azure Portal, click **Document Explorer**. You can view the list of databases and collections in this pane.
  
    -   **DocumentDB Key**. Paste one of the access keys for the account. To locate the keys, click **Keys**, and then copy the content of either the **PRIMARY KEY** or **SECONDARY KEY** fields.  
  
    -   **Collection ID**. Type the name of a collection from the specified Azure DocumentDB database.  
  
    > [!TIP]
    >  If you don't already have a document store, see these articles to get started.  
    >  -   [How to create a DocumentDB account](https://azure.microsoft.com/documentation/articles/documentdb-create-account/)  
    > -   [How to create a database for DocumentDB](https://azure.microsoft.com/documentation/articles/documentdb-create-database/)  
    > -   [How to create a DocumentDB collection](https://azure.microsoft.com/documentation/articles/documentdb-create-collection/)  
    > - [Download the DocumentDB Migration Tool](https://www.microsoft.com/download/details.aspx?id=46436)
      
4.  In the **SQL query** text box, type a query that defines the data to retrieve from the collection.  See the [Technical Notes](#TechnicalNotes) section for known issues and additional advice about retrieving data from DocumentDB.

    For example, you could use the following query to get only the volcanoes with elevations under 10000 feet.
    
    <code>Select * from volcanodb where volcanodb.Elevation < 10000</code>

    > [!NOTE]
    >  We recommend that you use the [Query Explorer for DocumentDB](https://azure.microsoft.com/documentation/articles/documentdb-query-collections-query-explorer/) to create and test your queries beforehand.    
  
6.  In the **SQL query parameters** box, type a value in JSON format that can be used to dynamically filter the data returned from the DocumentDB store. You can then provide the parameter value when running as part of a Web service.

    To use this parameter, you must first define the filter variable name, as part of the WHERE clause specified in the **SQL query** text box.

    For example, to get only the data related to a specific country, define a `@Country` variable and then specify its value as the parameter. 
    
    + In the **SQL query** text box:
    <code>Select * from volcanodb where volcanodb.Country = @param1</code>
    + In the **SQL query parameters** text box: 
    <code>{"@param1":"Turkey"}</code>
 
    This parameter is required; however, by default, the value is set to "{}", in which case all records are returned. 

7. Select the **Use cached results** option if you want to reuse existing results.  
  
     If you deselect this option, the data will be read from the source each time the experiment is run, regardless of whether the data is the same or not. 
       
     Note that Azure Machine Learning cannot compare the cached data against the data in your DocumentDB account, and therefore there is no way to perform incremental updates from Azure Machine Learning. If you want to re-import only when the data changes, you must define that logic in another application, such as Azure Data Factory. For more information, see [Move data to and from DocumentDB using Azure Data Factory](https://azure.microsoft.com/documentation/articles/data-factory-azure-documentdb-connector/). 
  
7.  Run the experiment, or select just the [Import Data](import-data.md) module and click **Run selected**.  

### Results

After you have run the module or experiment, you can right-click the output of hte module to visualize the results in tabular format.

To capture a snapshot of this data in your Azure Machine Learning workspace as a dataset, you can right-click the module's output and select **Save As Dataset**. However doing so will capture only the data available at the time of import. If the data is expected to change frequently, rerun **Import Data** as needed. 

  
##  <a name="Examples"></a> Examples  
 
 For a detailed walkthrough of how to use DocumentDB as a data source for machine learning, see this experiment in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/).  
 
+ [Reading data from Azure DocumentDB in Azure Machine Learning](https://gallery.cortanaintelligence.com/Experiment/Reading-data-from-Azure-DocumentDB-in-Azure-Machine-Learning-1) 

This blog provides additional examples of parameterized queries on a DocumentDb store. [SQL Parameterization in DocumentDB](https://azure.microsoft.com/en-us/blog/announcing-sql-parameterization-in-documentdb/)

   
##  <a name="TechnicalNotes"></a> Technical Notes  

This section contains advanced configuration options and answers to commonly asked questions.  

### Data migration and query syntax help

For samples of queries on a JSON data store, download the [DocumentDB SQL query cheat sheet](http://docs.microsoft.com/azure/documentdb/documentdb-sql-query-cheat-sheet).

If you need to upload content into DocumentDB, we recommend the [DocumentDB migration tool](http://docs.microsoft.com/azure/documentdb/documentdb-import-data). It will validate, upload, and index your data. The tool supports multiple sources, including MongoDB, Amazon DynamoDB, HBase, SQL Server databases, and CSV files.
  
### Using schema-less queries  
  
If the data is consistent and predictable, you can use straightforward SQL-like syntax, such as `SELECT * FROM <document collection>`.  This is called a *schema_less query* because you have not named the exact attributes to return. Such a query would return all the fields and all the rows from the specified collection. 

However, not specifying a schema can lead to unexpected results or a run-time error if the documents have inconsistent schemas. This is because the [Import Data](import-data.md) module will attempt to infer the schema based on a predetermined number of rows as follows:

1. When no attributes are specified, the module will scan the first row in the DocumentDB database.
2.  The module will create column (attribute) names and guess what the column data types should be based on that example row.  
3. If later rows contain any new or different attributes, a run-time error will be generated. 

Therefore, we recommend that you always specify the attributes and values to return from the DocumentDB data store.  For example, rather than use the `SELECT *` syntax, we recommend that you name all attributes retrieved by the query, like this:

`SELECT MyTable.Gender, MyTable.Age, MyTable.Name FROM <document collection>`  
       
  
##  <a name="parameters"></a> Module Parameters  

The following table includes only those parameters for the **Import Data** module that are applicable to the DocumentDB option.
  
|Name|Range|Type|Required|Default|Description|  
|----------|-----------|-- |--------|-------------|-----------------|  
|Data source |list|HTTP| required|none | Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, a Hive table, an OData endpoint, or DocumentDB.|  
|Endpoint URL|any|string|required|none|Provide the URI for the Azure DocumentDB server|  
|Database ID|any|string|required|none|Provide the name of the DocumentDB database|  
|DocumentDB Key|any|SecureString|required|none|Provide a valid API key for the DocumentDB account|  
|Collection ID|any|string|required|none|Provide the name of a collection in the DocumentDB database|  
|SQL Query|any|string|required|none|A SQL query specifying records to return from the DocumentDB data store| 

  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with downloaded data|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](error-0003.md)|An exception occurs if one or more of inputs are null or empty.|  
|[Error 0029](error-0029.md)|An exception occurs when an invalid URI is passed.|  
|[Error 0002](error-0002.md)|An exception occurs if one or more parameters could not be parsed or converted from the specified type to the type required by the target method.|  
|[Error 0048](error-0048.md)|An exception occurs when it is not possible to open a file.|  
|[Error 0049](error-0049.md)|An exception occurs when it is not possible to parse a file.|  
  
## See Also  
 [DocumentDB documentation](https://azure.microsoft.com/en-us/documentation/services/documentdb/)   
 [Import Data](import-data.md)   
 [Export Data](export-data.md)   
 [Import from Web URL via HTTP](import-from-web-url-via-http.md)   
 [Import from Hive Query](import-from-hive-query.md)   
 [Import from Azure SQL Database](import-from-azure-sql-database.md)   
 [Import from Azure Blob Storage](import-from-azure-blob-storage.md)   
 [Import from Data Feed Providers](import-from-data-feed-providers.md)   
 [Import from On-Premises SQL Server Database](import-from-on-premises-sql-server-database.md)