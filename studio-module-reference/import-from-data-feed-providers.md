---
title: "Import from Data Feed Providers | Microsoft Docs"
ms.custom: ""
ms.date: 09/20/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1ca59bb6-dc5b-4a1d-a59a-bbf17e26fdc0
caps.latest.revision: 21
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlun"
---
# Import from Data Feed Providers
This article describes how to use the [Import Data](import-data.md) module in Azure Machine Learning Studio, to import data provided in the OData format into a machine learning experiment.  
  
 Creating an OData endpoint for a data set is one way to make a data model available for consumption via URL. You can also specify which OData operations the endpoint will support. For more information about creating Odata endpoints, see [OData v4 (ASP.NET)](http://www.asp.net/web-api/overview/odata-support-in-aspnet-web-api/odata-v4/create-an-odata-v4-endpoint).  

  
## How to Import Data from a Feed  

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
  
2.  For **Data source**, select **Data Feed Provider**.  
  
3.  For **Data content type**, select the type of feed. Currently only OData endpoints are supported.  
  
4.  For **Source URL**, paste the URL of a site that provides data in the required format.  
  
     For example, the following statement gets the list of Products from the Northwind sample database:  
  
     `http://services.odata.org/northwind/northwind.svc/Products`  
  
    > [!NOTE]
    >  The query must return a flat table. Flattening nested OData records is not supported.  
    >   
    >  Some columns included in OData feeds might have data types that are not supported in Studio, such as decimals. You can ingest the data as strings and convert them later using the **Execute R Script** or **Metadata Editor** modules.  
  
     For more information about OData syntax and URLs, see [http://www.odata.org/documentation/odata-version-2-0/uri-conventions/](http://www.odata.org/documentation/odata-version-2-0/uri-conventions/).  
  
5.  Select the **Use cached results** option if you don't need to re-load the data after the first time. This is a good option if the data is not expected to change between runs of the experiment. If there are no other changes to module parameters, the experiment will load the data the first time the module is run, and thereafter use a cached version of the dataset.  
  
     If you need to regularly refresh the data obtained form the feed, deselect this option.  
  
6.  Run the experiment.  

  
### Results

When complete, you can click the output dataset and select **Visualize** to see if the data was imported successfully.     

When [Import Data](import-data.md) loads the feed data into Studio, it infers the data type of each column based on the values it contains, either numerical or categorical.  
  
+ If a header is present, the header is used to name the columns of the output dataset.  
  
+ If there are no existing column headers in the data, new column names are generated using the format <code>col1, col2,… ,coln</code>.    
##  <a name="TechnicalNotes"></a> Technical Notes  
 This section contains some answers to commonly asked questions.  
  
-   **How can I filter data as it is being read from the source?**  
  
     The [Import Data](import-data.md) module generally does not support filtering as data is being read. However, you can specify a filter condition as part of the feed resource URL.  
  
     To filter data from the feed, use statements supported by the [OData protocol](http://www.odata.org/documentation/odata-version-2-0/uri-conventions/). For example, this URL uses the `$filter` expression to get only the orders related to  the employee with ID equal to 1.  
  
     `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=Employee/EmployeeID eq 1`  
  
     For more examples of filter syntax, see [Using Filter Expressions in OData URIs](https://msdn.microsoft.com/library/hh169248\(v=nav.90\).aspx).  
  
     Alternatively, you can get all the data, and filter it after loading it into Azure Machine Learning Studio:  
  
    -   Use a custom R script to get only the data you want.  
  
    -   Use the [Split Data](split-data.md) module with a relative expression or a regular expression to isolate the data you want, and then save it as a dataset.  
  
    > [!NOTE]
    >  If you find that you have loaded more data than you need, you can overwrite the cached dataset by reading a new dataset, and saving it with the same name as the older, larger data.  
  
-   **I get the error, Credentials are required to connect to the OData source. Please refresh and provide credentials to continue. How can I provide credentials?**  
  
     [Import Data](import-data.md) supports only OData endpoints with Anonymous access. If the OData service requires credentials, you cannot use the OData option to get the data.  
  
     However, if the service is on the same domain, authentication can sometimes happen automatically without any user input.  
  
     As a workaround, you can use PowerQuery or PowerPivot to read feed data and then get the data from Excel.  
  
-   **How can I avoid re-loading the same data unnecessarily?**  
  
     If your source data changes, you can refresh the dataset and add new data by re-running [Import Data](import-data.md). However, if you don't want to re-read from the source each time you run the experiment, select the **Use cached results** option to TRUE. When this option is set to TRUE, the module will check whether the experiment has run previously  using the same source and same input options, and if a previous run is found, the data in the cache is used, instead of re-loading the data from the source.  
  
-   **Why do I get an error message  “Type Decimal is not supported”?**  
  
     The `decimal` data type is not supported in Azure Machine Learning.  The reason is that  [Import Data](import-data.md) cannot automatically perform any conversions that would result in a loss of precision.  For more information about supported data types, see [Module Data Types](machine-learning-module-data-types.md).  
  
     As a workaround, you can read the data as a string data type, and then use [Edit Metadata](edit-metadata.md) to convert the decimals to a supported data before reading the data.  
  
-   **Why are some characters in the feed not displayed correctly?**  
  
     Azure Machine Learning supports the UTF-8 encoding. If your source uses another type of encoding, the characters might not be imported correctly.  
  
     As a workaround,  you can save the data to a CSV file in Azure table storage or Azure blob storage. Then, use the option **CSV with encoding** to specify parameters for custom delimiters, the code page, and so forth.  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Data source|List|Data Source Or Sink|Azure Blob Storage|Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, an on-premises SQL Server database, a Hive table, or an OData endpoint.|  
|Data content type|List (subset)|Url Contents|OData|Data format type|  
|Source URL|any|String||URL for Power Query data source|  
|Use cached results|TRUE/FALSE|Boolean|FALSE|description|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with downloaded data|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of inputs are null or empty.|  
|[Error 0029](errors/error-0029.md)|An exception occurs when an invalid URI is passed.|  
|[Error 0030](errors/error-0030.md)|an exception occurs in when it is not possible to download a file.|  
|[Error 0002](errors/error-0002.md)|An exception occurs if one or more parameters could not be parsed or converted from the specified type to the type required by the target method.|  
  
## See Also  
 [Import Data](import-data.md)   
 [Export Data](export-data.md)   
 [Import from Web URL via HTTP](import-from-web-url-via-http.md)   
 [Import from Hive Query](import-from-hive-query.md)   
 [Import from Azure SQL Database](import-from-azure-sql-database.md)   
 [Import from Azure Table](import-from-azure-table.md)   
 [Import from Azure Blob Storage](import-from-azure-blob-storage.md)   
 [Import from On-Premises SQL Server Database](import-from-on-premises-sql-server-database.md)