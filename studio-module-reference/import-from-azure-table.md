---
title: "ML Studio (classic): Import from Azure Table - Azure"
description: Learn how to use the Import Data module to import structured or semi-structured data from Azure tables into a machine learning experiment.  
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Import from Azure Table

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes how to use the [Import Data](import-data.md) module in Machine Learning Studio (classic), to import structured or semi-structured data from Azure tables into a machine learning experiment.  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
 The Azure **table** service is a data management service in Azure that can store large amounts of structured, non-relational data. It is a NoSQL data store that accepts authenticated calls from inside and outside Azure.  
  
 Importing from Azure table storage requires that you choose one of two account types: a storage account that can be accessed by using a SAS URL, or a private storage account that requires login credentials.  

## How to import data from Azure tables

### Use the Data Import Wizard

The module features a new wizard to help you choose a storage option, select from among existing subscriptions and accounts, and quickly configure all options.

1. Add the **Import Data** module to your experiment. You can find the module under **Data Input and Output**.

2. Click **Launch Import Data Wizard** and follow the prompts.

3. When configuration is complete, to actually copy the data into your experiment, right-click the module, and select **Run Selected**. 

If you need to edit an existing data connection, the wizard loads all previous configuration details so that you don't have to start again from scratch

### Manually set properties in the Import Data module

The following steps describe how to manually configure the import source.

1. Add the [Import Data](import-data.md) module to your experiment. You can find this module in the [Data Input and Output](data-input-and-output.md) group in the **experiment items** list in Machine Learning Studio (classic).  

2. For **Data source**, select **Azure Table**.  

3. For **Authentication type**, choose **Public (SAS URL)** if you know that the information has been provided as a public data source. A *SAS URL* is a time bound access URL that you can generate by using an Azure storage utility.  

    Otherwise choose **Account**.

4. If your data is in a **public** blob that can be accessed by using a SAS URL, you do not need additional credentials because the URL string contains all the information that is needed for download and authentication.  

    In the **Table SAS URI** field, type or paste the full URI that defines the account and the public blob.

    > [!NOTE]
    > In a page accessible via SAS URL, data can be stored using only these formats: CSV, TSV, and ARFF.  

5. If your data is in a **private** account, you must supply credentials including the account name and the key.  

    - For **Table account name**, type or paste the name of the account that contains the blob you want to access.  

        For example, if the full URL of the storage account is `https://myshared.table.core.windows.net`, you would type `myshared`.  

    - For **Table account key**, paste the access key that is associated with the storage account.\

        If you don’t know the access key, see the section, “View, copy and regenerate storage access keys” in this article: [About Azure Storage Accounts](https://azure.microsoft.com/documentation/articles/storage-manage-storage-account/).

    - For **Table name**, type the name of the specific table that you want to read.

6. Choose an option that indicates how many rows the [Import Data](import-data.md) should scan. [Import Data](import-data.md) uses the scan to get the list of columns in the data, and to determine what the column data types should be.

    - **TopN**: Scan just the specified number of rows, starting from the top of the dataset.

        By default, 10 rows are scanned, but you can increase or decrease that value by using the **Rows count for TopN** option.

        If the data is homogenous and predictable, select **TopN** and enter a number for N. For large tables, this can result in quicker reading times.

    - **ScanAll**: Scan all rows in the table.

        If the data is structured with sets of properties that vary based on the depth and position of the table, choose the **ScanAll** option to scan all rows. This ensures the integrity of your resulting property and metadata conversion.

7. Indicate whether you want the data to be refreshed each time the experiment is run. If you select the **Use cached results** option (the default) the [Import Data](import-data.md) module will read data form the specified source the first time the experiment is run, and thereafter cache the results. If there are any changes to the parameters of the [Import Data](import-data.md) module, the data is re-loaded.

    If you deselect this option, the data will be read from the source each time the experiment is run, regardless of whether the data is the same or not.

## Examples

For examples of how to use the [Export Data](export-data.md) module, see the [Azure AI Gallery](https://gallery.azure.ai).

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Common questions

#### How can I avoid re-loading the same data unnecessarily?

If your source data changes, you can refresh the dataset and add new data by re-running [Import Data](import-data.md). However, if you don't want to re-read from the source each time you run the experiment, select the **Use cached results** option to TRUE. When this option is set to TRUE, the module checks whether the experiment has run previously using the same source and same input options, and if a previous run is found, the data in the cache is used, instead of re-loading the data from the source.

#### Can I filter data as it is being read from the source?

The [Import Data](import-data.md) module does not support filtering as data is being read. The exception is reading from data feeds, which sometimes allow you to specify a filter condition as part of the feed URL.

However, you can change or filter data after reading it into Machine Learning Studio (classic):

- Use a custom R script to change or filter data.
- Use the [Split Data](split-data.md) module with a relative expression or a regular expression to isolate the data you want, and then save it as a dataset.

> [!NOTE]
> If you find that you have loaded more data than you need, you can overwrite the cached dataset by reading a new dataset, and saving it with the same name as the older, larger data.

#### How does [Import Data](import-data.md) handle data loaded from different geographical regions?

If the blob or table storage account is in a different region from the compute node used for the machine learning experiment, data access might be slower. Further, you are charged for data ingress and egress on the subscription.

#### Why are some characters in my table not displayed correctly?

Machine Learning supports UTF-8 encoding. If your table uses another encoding, the characters might not be imported correctly.

#### Are there any prohibited characters or characters that are changed during import?

If attribute data contains quotation marks or escaped character sequences, they are handled by using the rules for such characters in Microsoft Excel. All other characters are handled by using the following specifications as a guideline: [RFC 4180](https://tools.ietf.org/html/rfc4180).

## Module parameters

|Name|Range|Type|Default|Default|  
|----------|-----------|----------|-------------|-------------|  
|Data source|List|Data Source Or Sink|Azure Blob Storage|Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, an on-premises SQL Server database, a Hive table, or an OData endpoint.|  
|Authentication type|PublicOrSas<br /><br /> Account|tableAuthType|Account|Specify whether the data is in a public container accessible via SAS URL, or is in a private storage account that requires authentication for access.|  

### Public or SAS - Public storage options

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Table URI|any|String|||  
|Rows to scan for property names via SAS|integer||||  
|Rows count for TopN via SAS|||||  

### Account - Private storage options

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Table account name|||||  
|Table account key|any|SecureString|||  
|Table name|any||||  
|Rows to scan for property names|TopN<br /><br /> ScanAll||||  
|Rows count for TopN|any|integer|||  

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
|[Error 0009](errors/error-0009.md)|An exception occurs if the Azure storage account name or the container name is specified incorrectly.|  
|[Error 0048](errors/error-0048.md)|An exception occurs when it is not possible to open a file.|  
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
 [Import from Azure Blob Storage](import-from-azure-blob-storage.md)   
 [Import from Data Feed Providers](import-from-data-feed-providers.md)   
 [Import from On-Premises SQL Server Database](import-from-on-premises-sql-server-database.md)
