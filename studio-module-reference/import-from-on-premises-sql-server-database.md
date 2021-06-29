---
title: "ML Studio (classic): Import from On-Prem SQL Server Database - Azure"
description: Learn how to use the Import Data module to import data from an on-premises SQL Server database into a machine learning experiment.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Import from On-Premises SQL Server Database

This article describes how to use the [Import Data](import-data.md) module in Machine Learning Studio (classic), to import data from an on-premises SQL Server database into a machine learning experiment.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

Machine Learning can access an on-premises SQL Server database if the data is provided using a Microsoft Data Management Gateway. Therefore, before you use [Import Data](import-data.md),  you must meet these requirements:

- Install a [Microsoft Data Management Gateway](/azure/data-factory/v1/data-factory-data-management-gateway) that can access the data source
- Register the gateway in your Machine Learning workspace
- Configure the [Import Data](import-data.md) to identify the gateway

After the gateway connection is established, you can then specify additional properties, such as the server and database names, authentication method, and a database query.

## How to install a Microsoft Data Management Gateway

To access an on-premises SQL Server database in Machine Learning, you need to download and install the **Microsoft Data Management Gateway**, and then register the gateway in Machine Learning Studio (classic).

For details about installing and registering the gateway, see these articles:

- [Perform advanced analytics with Machine Learning using data from an on-premises SQL Server database](/azure/machine-learning/studio/use-data-from-an-on-premises-sql-server)

- [Troubleshoot issues with using Data Management Gateway](/azure/data-factory/v1/data-factory-troubleshoot-gateway-issues)]

## How to import data from an on-premises SQL Server database

After a Data Management Gateway has been installed on a computer where it can access your SQL Server database, and you have registered the gateway in Machine Learning Studio (classic), you must configure the [Import Data](import-data.md) module.

Before you start, disable your browser's pop-up blocker for the site, `studio.azureml.net`.

If you are using the Google Chrome browser, you must download and install one of the plug-ins that are available at the Google Chrome WebStore: [Click Once App Extension](https://chrome.google.com/webstore/search/clickonce?_category=extensions).

### Use the Data Import Wizard

The module features a new wizard to help you choose a storage option, select from among existing subscriptions and accounts, and quickly configure all options.

1. Add the **Import Data** module to your experiment. You can find the module in Studio (classic), in the **Data Input and Output** category.

2. Click **Launch Import Data Wizard** and follow the prompts.

3. When configuration is complete, to actually copy the data into your experiment, right-click the module, and select **Run Selected**. 

If you need to edit an existing data connection, the wizard loads all previous configuration details so that you don't have to start again from scratch.

### Manually set properties in the Import Data module

1. Add the [Import Data](import-data.md) module to your experiment. You can find the module in Studio (classic), in the **Data Input and Output** category.

2. For **Data source**, select **On-Premises SQL Database**.  

3. Set the following options specific to the SQL Server database.  

    - **Data gateway**: Select the gateway you created. The gateway must be registered or it does not show in the list.
    - **Database server name**: Type the name of the SQL Server instance.
    - **Database name**: Type the database name.

    - Click **Enter values** under **User name and password** and enter your database credentials. You can use Windows Integrated Authentication or SQL Server Authentication depending upon how your on-premises SQL Server is configured. 

        > [!IMPORTANT]
        > The credential manager must be launched from within the same network as the SQL Server instance and the gateway client. Credentials cannot be passed across domains.

    - Type or paste into **Database query** a SQL statement that describes the data you want to read. Always validate the SQL statement and verify the query results beforehand, using a tool such as Visual Studio Server Explorer or SQL Server Data Tools.

    - If the dataset is not expected to change between runs of the experiment, select the **Use cached results** option. When this is selected, if there are no other changes to module parameters, the experiment will load the data the first time the module is run, and thereafter use a cached version of the dataset.

4. Run the experiment.

### Results

As [Import Data](import-data.md) loads the data into Studio (classic), some implicit type conversion might be performed, depending on the data types used in the source database. For more information about data types, see [Module Data Types](machine-learning-module-data-types.md).

When complete, click the output dataset and select **Visualize** to see if the data was imported successfully.

Optionally, you can change the dataset and its metadata using the tools in Studio (classic):

- Use [Edit Metadata](edit-metadata.md) to change column names, convert a column to a different data type, or to indicate which columns are labels or features.

- Use [Select Columns in Dataset](select-columns-in-dataset.md) to select a subset of columns.

- Use [Partition and Sample](partition-and-sample.md) to separate the dataset by criteria, or get the top *n* rows.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Common questions

#### Can I filter data as it is being read from the source?

The [Import Data](import-data.md) module itself does not support filtering as data is being read. We recommend that you create a view or define a query that generates only the rows you need.

> [!NOTE]
> If you find that you have loaded more data than you need, you can overwrite the cached dataset by reading a new dataset, and saving it with the same name as the older, larger data.

#### Why do I get the error, “Type Decimal is not supported”

When reading data from a SQL database, you might encounter an error message reporting an unsupported data type.

If the data you get from the SQL database includes data types that are not supported in Machine Learning, you should cast or convert the decimals to a supported data type before reading the data. The reason is that [Import Data](import-data.md) cannot automatically perform any conversions that would result in a loss of precision.

#### Why are some characters not displayed correctly

Machine Learning supports the UTF-8 encoding. If string columns in your database use a different encoding, the characters might not be imported correctly.

One option for preserving these characters is to export the data to a CSV  file in Azure storage, and use the option **CSV with encoding** to specify parameters for custom delimiters, the code page, and so forth.

#### I set up a Data Management Gateway on my on-premises server. Can I share the same gateway between workspaces

No. You must create a separate gateway for each workspace.

While you can set up multiple Data Management Gateways in a single workspace (for example, one each for development, testing, production, etc.), a gateway can’t be shared across workspaces.

#### I have set up a Data Management Gateway on my on-premises server that I use for Power BI or Azure Data Factory and want to use the same gateway for Machine Learning

Each service requires a separate Data Management Gateway. If you already have a gateway that's being used for Power BI or Azure Data Factory, you must set up a separate server and install a gateway for machine learning.

You can't install multiple gateways on a single server.

#### I want to be able to export data to my on-premises SQL server. Can I use the gateway with the Export Data module to write data to my on-premises SQL server?

Currently, Machine Learning only supports importing data. We're evaluating whether you'll be able to write to your on-premises database in the future. In the meantime, you can use Azure Data Factory to copy data from the cloud to your on-premises database.

#### I have a data source that is not Microsoft SQL Server (Oracle, Teradata, etc.). Can I read the data in Machine Learning using the on-premises option in the Import Data module?

Currently the Machine Learning [Import Data](import-data.md) module supports only Microsoft SQL Server.

As a workaround, you can use Azure Data Factory to copy your on-premises data into cloud storage such as Azure Blob Storage or Azure Database, and then use your cloud data source in the [Import Data](import-data.md) module.

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Data source|List|Data Source Or Sink|Azure Blob Storage|Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, an on-premises SQL Server database, a Hive table, or an OData endpoint.|  
|Data gateway|any|DataGatewayName|none|Data gateway name|  
|Database server name|any|String|none|On-premises SQL Server|  
|Database name|any|String|none|On-premises SQL Server database instance|  
|User name and password|any|SecureString|none|User name and password|  
|Database query|any|StreamReader|none|On-premises SQL query|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with downloaded data|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0027](errors/error-0027.md)|An exception occurs when two objects have to be the same size, but they are not.|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of inputs are null or empty.|  
|[Error 0029](errors/error-0029.md)|An exception occurs when an invalid URI is passed.|  
|[Error 0030](errors/error-0030.md)|an exception occurs in when it is not possible to download a file.|  
|[Error 0002](errors/error-0002.md)|An exception occurs if one or more parameters could not be parsed or converted from the specified type to the type required by the target method.|  
|[Error 0048](errors/error-0048.md)|An exception occurs when it is not possible to open a file.|  
|[Error 0015](errors/error-0015.md)|An exception occurs if the database connection has failed.|  
|[Error 0046](errors/error-0046.md)|An exception occurs when it is not possible to create a directory on specified path.|  
|[Error 0049](errors/error-0049.md)|An exception occurs when it is not possible to parse a file.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).

## See also

 [Import Data](import-data.md)   
 [Export Data](export-data.md)   
 [Import from Web URL via HTTP](import-from-web-url-via-http.md)   
 [Import from Hive Query](import-from-hive-query.md)   
 [Import from Azure SQL Database](import-from-azure-sql-database.md)   
 [Import from Azure Table](import-from-azure-table.md)   
 [Import from Azure Blob Storage](import-from-azure-blob-storage.md)   
 [Import from Data Feed Providers](import-from-data-feed-providers.md)
