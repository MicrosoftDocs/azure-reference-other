---
title: "ML Studio (classic): Import from Azure Cosmos DB - Azure"
description: Learn how to use the Import Data module to import data from Azure Cosmos DB for use in a machine learning experiment.
ms.date: 07/03/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"


author: xiaoharper
ms.author: amlstudiodocs

---
# Import from Azure Cosmos DB

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes how to use the [Import Data](import-data.md) module in Machine Learning Studio (classic), to import data from Azure Cosmos DB for use in a machine learning experiment.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
[Azure Cosmos DB](/azure/cosmos-db/sql-api-introduction) supports NoSQL database storage, using a flexible data model. The advantages of using the SQL APIs in this data store for machine learning include fast and predictable performance, automatic scaling, global distribution, and rich query capabilities. 

Together with Azure SQL Database, this option lets you dynamically filter incoming datasets.

Learn how it works: [Learn about Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/)  

+ To get started with machine learning using data from Azure Cosmos DB, you must have access to an existing Azure Cosmos DB account containing a collection of related documents. 

> [!NOTE]
> The user interface in Machine Learning Studio (classic) still uses the name DocumentDB in many places. Therefore, you may continue to see references to DocumentDB, even though the API has been incorporated into Azure Cosmos DB. 

## How to use Import Data with Azure Cosmos DB

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

    You might need to provide connection information for the document database. 

    > [!TIP]
    > Look for the name of the option in Machine Learning Studio (classic) to change at a later date. The import functionality was not affected by the name change.

3. For **Endpoint URL**, in the Azure Portal, click **Keys**, and copy the contents of the **URI** field at the top of the page.

4. For **Database ID**, paste the name of the database to use. 

    To get the database name from the Azure Portal, click **Document Explorer**. You can view the list of databases and collections in this pane.

5. For **DocumentDB Key**, paste in an access key for the account. 

    To locate the keys, click **Keys**, and then copy the content of either the **PRIMARY KEY** or **SECONDARY KEY** fields.  

6. For **Collection ID**, type the name of the collection as shown in the specified CosmosDB database.  

7. Define a SQL query and filter condition on the data, by using the **SQL query** and **SQL query parameters** options.

    For **SQL query**, type a query that defines the data to retrieve from the collection. We recommend that you use the [Query Explorer](/azure/cosmos-db/tutorial-query-sql-api) to create and test your CosmosDB queries beforehand.

    For **SQL query parameters**, provide an expression in JSON format that can be used to dynamically filter the data returned. Typically you supply the actual value of the parameter value when running the experiment as part of a Web service. 

    If you use a parameter, you must define the filter variable name as part of the WHERE clause specified in the **SQL query** text box.

    If you do not specify a filter expression, by default, the value is set to "{}", and all records are returned. 

    See the [Technical Notes](#TechnicalNotes) section for examples, known issues, and additional advice about SQL queries on CosmosDB.

8. Select the **Use cached results** option if you want to reuse existing results.

    If you deselect this option, the data is read from the source each time the experiment is run, regardless of whether the data is the same or not.

    Machine Learning **cannot** compare the cached data against the data in your CosmosDB account. Hence, there is no way to perform incremental updates from Machine Learning.

    If you want to re-import only when the data changes, you must define that logic in another application, such as Azure Data Factory. For more information, see [Move data to and from Azure Cosmos DB using Azure Data Factory](/azure/data-factory/v1/data-factory-azure-documentdb-connector).

9. Run the experiment, or select just the [Import Data](import-data.md) module and click **Run selected**.

### Results

After you have run the module or experiment, you can right-click the output of the module to visualize the results in tabular format.

To capture a snapshot of this data in your Machine Learning workspace as a dataset, you can right-click the module's output and select **Save As Dataset**. However, doing so captures only the data available at the time of import. If the data is expected to change frequently, rerun **Import Data** as needed. 

## Examples

For a detailed walkthrough of how to use Azure Cosmos DB as a data source for machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/).

+ [SQL queries for Azure Cosmos DB](/azure/cosmos-db/sql-api-sql-query): This article explains how to perform SQL queries on Azure Cosmos DB data.

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

+ [Azure Cosmos DB: Build a SQL API web app with .NET and the Azure portal](/azure/cosmos-db/create-sql-api-dotnet)

+ [Quickstart: Build a .NET console app to manage Azure Cosmos DB SQL API resources](/azure/cosmos-db/create-sql-api-dotnet)

+ [Azure Cosmos DB Migration Tool](https://www.microsoft.com/download/details.aspx?id=46436)

### Data migration and query syntax help

For samples of queries on a JSON data store, download the [Azure Cosmos DB query cheat sheet](/azure/cosmos-db/query-cheat-sheet).

If you need to upload content into Azure Cosmos DB, we recommend the [Azure Cosmos DB migration tool](/azure/cosmos-db/import-data). It validates, uploads, and indexes your data. The tool supports multiple sources, including MongoDB, Amazon DynamoDB, HBase, SQL Server databases, and CSV files.

### Using schema-less queries

If the data is consistent and predictable, you can use straightforward SQL-like syntax, such as `SELECT * FROM <document collection>`.  This is called a *schema-less query* because you have not named the exact attributes to return. Such a query would return all the fields and all the rows from the specified collection.

However, not specifying a schema can lead to unexpected results or a run-time error if the documents have inconsistent schemas. This is because the [Import Data](import-data.md) module attempts to infer the schema based on a predetermined number of rows as follows:

1. When no attributes are specified, the module scans the first row in the CosmosDB database.
2. The module creates column names based on attributes, and guesses what the column data types should be based on the example row.
3. If later rows contain any new or different attributes, a run-time error is generated.

Therefore, we recommend that you always specify the attributes and values to return from the CosmosDB data store.  For example, rather than use the `SELECT *` syntax, we recommend that you name all attributes retrieved by the query, like this:

`SELECT MyTable.Gender, MyTable.Age, MyTable.Name FROM <document collection>`  

## Module parameters

The following table includes only those parameters for the **Import Data** module that are applicable to the Azure Cosmos DB option.

|Name|Range|Type|Required|Default|Description|  
|----------|-----------|-- |--------|-------------|-----------------|  
|Data source |list|HTTP| required|none | Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, a Hive table, an OData endpoint, or Azure Cosmos dB.|  
|Endpoint URL|any|string|required|none|Provide the URI for the Azure Cosmos DB server|  
|Database ID|any|string|required|none|Provide the name of the Azure Cosmos DB database|  
|DocumentDB Key|any|SecureString|required|none|Provide a valid API key for the Azure Cosmos DB account|  
|Collection ID|any|string|required|none|Provide the name of a collection in the Azure Cosmos DB database|  
|SQL Query|any|string|required|none|A SQL query specifying records to return from the Azure Cosmos DB data store| 

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

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [Import Data](import-data.md)   
 [Export Data](export-data.md)   
 [Import from Web URL via HTTP](import-from-web-url-via-http.md)   
 [Import from Hive Query](import-from-hive-query.md)   
 [Import from Azure SQL Database](import-from-azure-sql-database.md)   
 [Import from Azure Blob Storage](import-from-azure-blob-storage.md)   
 [Import from Data Feed Providers](import-from-data-feed-providers.md)   
 [Import from On-Premises SQL Server Database](import-from-on-premises-sql-server-database.md)
