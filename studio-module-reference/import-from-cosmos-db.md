---
title: "Import from DocumentDB (CosmosDB) | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/24/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2460018-5139-434b-881e-3e22de9c7917
caps.latest.revision: 22
author: rastala
ms.author: roastala
manager: cgronlun
---
# Import from DocumentDB (CosmosDB)

This article describes how to use the [Import Data](import-data.md) module in Azure Machine Learning Studio, to import data from Azure CosmosDB for use in a machine learning experiment.
  
[Azure CosmosDB](https://docs.microsoft.com/azure/cosmos-db/sql-api-introduction) includes the service formerly known as DocumentDB. CosmosDB supports NoSQL database storage, using a flexible data model. The advantages of using the SQL APIs in this data store for machine learning include fast and predictable performance, automatic scaling, global distribution, and rich query capabilities. 

Together with Azure SQL Database, this option lets you dynamically filter incoming datasets.

Learn how it works: [Learn about CosmosDB](https://azure.microsoft.com/services/cosmos-db/)  

**What is new?**

The service provides the same functionality as before, but has been renamed the "Azure Cosmos DB SQL API". See this article for information about the new name and other changes: [Azure Cosmos DB FAQ](https://docs.microsoft.com/azure/cosmos-db/faq)

Because the underlying API fully supports DocumentDB, you don't need to change anything to continue running machine learning experiments that rely on DocumentDB.  

+ To get started with machine learning using data from Microsoft Azure CosmosDB, you must have access to an existing CosmosDB account containing a collection of related documents. 
+ If you had a DocumentDB API account before, you now have a CosmosDB SQL API account, with no change to your billing.

> [!NOTE]
> The user interface in Azure Machine Learning Studio still uses the name DocumentDB in many places. Therefore, you may continue to see references to DocumentDB, even though the API has been incorporated into CosmosDB. 

## How to use Import Data with CosmosDB

We strongly recommend that you profile your data before importing, to make sure that the schema is as expected. The import process scans some number of head rows to determine the schema, but later rows might contain extra columns, or data that cause errors.

### Import data using the wizard

The module features a new wizard to help you choose a storage option,  select from among existing subscriptions and accounts, and quickly configure all options.

1. Add the **Import Data** module to your experiment. You can find the module under **Data Input and Output**.

2. Click **Launch Import Data Wizard** and follow the prompts.

3. When configuration is complete, to actually copy the data into your experiment, right-click the module, and select **Run Selected**. 

> [!TIP]
> If you need to edit an existing data connection, the wizard loads all previous configuration details. You don't have to start again from scratch.

### Manually set properties in the Import Data module

The following steps describe how to manually configure the import source.

1. Add the [Import Data](import-data.md) module to your experiment. You can find this module in the [Data Input and Output](data-input-and-output.md) category. 

2. For **Data source**, select **Azure DocumentDB**.

    The document store must have been created using Microsoft Azure CosmosDB. Accounts that were created using Microsoft Azure DocumentDB are seamlessly upgraded.

    You might need to provide connection information for the document database. 

    > [!TIP]
    > Look for the name of the option in Machine Learning Studio to change at a later date. The import functionality was not affected by the name change.

3. For **Endpoint URL**, in the Azure Portal, click **Keys**, and copy the contents of the **URI** field at the top of the page.

4. For **Database ID**, paste the name of the database to use. 

    To get the database name from the Azure Portal, click **Document Explorer**. You can view the list of databases and collections in this pane.

5. For **DocumentDB Key**, paste in an access key for the account. 

    To locate the keys, click **Keys**, and then copy the content of either the **PRIMARY KEY** or **SECONDARY KEY** fields.  

6. For **Collection ID**, type the name of the collection as shown in the specified CosmosDB database.  

7. Define a SQL query and filter condition on the data, by using the **SQL query** and **SQL query parameters** options.

    For **SQL query**, type a query that defines the data to retrieve from the collection. We recommend that you use the [Query Explorer](https://docs.microsoft.com/azure/cosmos-db/tutorial-query-sql-api) to create and test your CosmosDB queries beforehand.

    For **SQL query parameters**, provide an expression in JSON format that can be used to dynamically filter the data returned. Typically you supply the actual value of the parameter value when running the experiment as part of a Web service. 

    If you use a parameter, you must define the filter variable name as part of the WHERE clause specified in the **SQL query** text box.

    If you do not specify a filter expression, by default, the value is set to "{}", and all records are returned. 

    See the [Technical Notes](#TechnicalNotes) section for examples, known issues, and additional advice about SQL queries on CosmosDB.

8. Select the **Use cached results** option if you want to reuse existing results.

    If you deselect this option, the data is read from the source each time the experiment is run, regardless of whether the data is the same or not.

    Azure Machine Learning **cannot** compare the cached data against the data in your CosmosDB account. Hence, there is no way to perform incremental updates from Azure Machine Learning.

    If you want to re-import only when the data changes, you must define that logic in another application, such as Azure Data Factory. For more information, see [Move data to and from DocumentDB using Azure Data Factory](https://azure.microsoft.com/documentation/articles/data-factory-azure-documentdb-connector/).

9. Run the experiment, or select just the [Import Data](import-data.md) module and click **Run selected**.

### Results

After you have run the module or experiment, you can right-click the output of the module to visualize the results in tabular format.

To capture a snapshot of this data in your Azure Machine Learning workspace as a dataset, you can right-click the module's output and select **Save As Dataset**. However, doing so captures only the data available at the time of import. If the data is expected to change frequently, rerun **Import Data** as needed. 

## Examples

For a detailed walkthrough of how to use DocumentDB as a data source for machine learning, see the [Azure AI Gallery](https://gallery.cortanaintelligence.com/).

+ [Reading data from Azure DocumentDB in Azure Machine Learning](https://gallery.cortanaintelligence.com/Experiment/Reading-data-from-Azure-DocumentDB-in-Azure-Machine-Learning-1)

+ [SQL Parameterization in DocumentDB](https://azure.microsoft.com/blog/announcing-sql-parameterization-in-documentdb/): This blog provides additional examples of parameterized queries on a DocumentDb store.

## <a name="TechnicalNotes"></a> Technical notes

This section contains advanced configuration options and answers to commonly asked questions.

### Examples of simple and parameterized queries

Suppose you want to use only the data on volcanoes with elevations under 10000 feet.

#### Simple query

Paste the following query in the **SQL query** text box: `Select * from volcanodb where volcanodb.Elevation < 10000`

In this case, the value of the filter expression is set to "{}", and all records are returned.

#### Parameterized query 

To get only the volcano data related to a specific country, you can specify the country value as a parameter passed to the query at run time. This requires these changes:

1. In the **SQL query** text box,  define a variable to apply to the `Country` field as part of the SQL query:

    `Select * from volcanodb where volcanodb.Country = @param1`

2. In the **SQL query parameters** text box, specify the parameter name and its value in JSON format, like this: 

    `{"@param1":"Turkey"}`

### Resources

If you don't have an existing document store, see these articles to get started.

+ [Azure Cosmos DB: Build a SQL API web app with .NET and the Azure portal](https://docs.microsoft.com/azure/cosmos-db/create-sql-api-dotnet)

+ [Create a database](https://docs.microsoft.com/azure/cosmos-db/create-sql-api-dotnet#create-collection)

+ [Add a collection](https://docs.microsoft.com/azure/cosmos-db/create-sql-api-dotnet#create-collection)

+ [Azure DocumentDB Migration Tool](https://www.microsoft.com/download/details.aspx?id=46436)

### Data migration and query syntax help

For samples of queries on a JSON data store, download the [DocumentDB SQL query cheat sheet](http://docs.microsoft.com/azure/documentdb/documentdb-sql-query-cheat-sheet).

If you need to upload content into DocumentDB, we recommend the [DocumentDB migration tool](https://docs.microsoft.com/azure/cosmos-db/import-data). It validates, uploads, and indexes your data. The tool supports multiple sources, including MongoDB, Amazon DynamoDB, HBase, SQL Server databases, and CSV files.

### Using schema-less queries

If the data is consistent and predictable, you can use straightforward SQL-like syntax, such as `SELECT * FROM <document collection>`.  This is called a *schema-less query* because you have not named the exact attributes to return. Such a query would return all the fields and all the rows from the specified collection.

However, not specifying a schema can lead to unexpected results or a run-time error if the documents have inconsistent schemas. This is because the [Import Data](import-data.md) module attempts to infer the schema based on a predetermined number of rows as follows:

1. When no attributes are specified, the module scans the first row in the CosmosDB database.
2. The module creates column names based on attributes, and guesses what the column data types should be based on the example row.
3. If later rows contain any new or different attributes, a run-time error is generated.

Therefore, we recommend that you always specify the attributes and values to return from the CosmosDB data store.  For example, rather than use the `SELECT *` syntax, we recommend that you name all attributes retrieved by the query, like this:

`SELECT MyTable.Gender, MyTable.Age, MyTable.Name FROM <document collection>`  

## Module parameters

The following table includes only those parameters for the **Import Data** module that are applicable to the DocumentDB option.

|Name|Range|Type|Required|Default|Description|  
|----------|-----------|-- |--------|-------------|-----------------|  
|Data source |list|HTTP| required|none | Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, a Hive table, an OData endpoint, or DocumentDB.|  
|Endpoint URL|any|string|required|none|Provide the URI for the Azure DocumentDB server|  
|Database ID|any|string|required|none|Provide the name of the DocumentDB database|  
|DocumentDB Key|any|SecureString|required|none|Provide a valid API key for the DocumentDB account|  
|Collection ID|any|string|required|none|Provide the name of a collection in the DocumentDB database|  
|SQL Query|any|string|required|none|A SQL query specifying records to return from the DocumentDB data store| 

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with downloaded data|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of inputs are null or empty.|  
|[Error 0029](errors/error-0029.md)|An exception occurs when an invalid URI is passed.|  
|[Error 0002](errors/error-0002.md)|An exception occurs if one or more parameters could not be parsed or converted from the specified type to the type required by the target method.|  
|[Error 0048](errors/error-0048.md)|An exception occurs when it is not possible to open a file.|  
|[Error 0049](errors/error-0049.md)|An exception occurs when it is not possible to parse a file.|  

For a list of errors specific to Studio modules, see [Machine Learning Error codes](\errors\machine-learning-module-error-codes.md)

For a list of API exceptions, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [Import Data](import-data.md)   
 [Export Data](export-data.md)   
 [Import from Web URL via HTTP](import-from-web-url-via-http.md)   
 [Import from Hive Query](import-from-hive-query.md)   
 [Import from Azure SQL Database](import-from-azure-sql-database.md)   
 [Import from Azure Blob Storage](import-from-azure-blob-storage.md)   
 [Import from Data Feed Providers](import-from-data-feed-providers.md)   
 [Import from On-Premises SQL Server Database](import-from-on-premises-sql-server-database.md)