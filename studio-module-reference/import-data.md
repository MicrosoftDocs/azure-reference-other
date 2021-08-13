---
title: "ML Studio (classic): Import Data - Azure"
description: Learn how to use the Import Data module to load data into a machine learning experiment from existing cloud data services.  
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"
author: xiaoharper
ms.author: amlstudiodocs

---
# Import Data

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Loads data from external sources on the web; from various forms of cloud-based storage in Azure such as tables, blobs, and SQL  databases; and from on-premises SQL Server databases*

Category: [Data Input and Output](data-input-and-output.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the [Import Data](import-data.md) module in Machine Learning Studio (classic), to load data into a machine learning experiment from existing cloud data services.  

The module now features a wizard to help you choose a storage option and select from among existing subscriptions and accounts to quickly configure all options. Need to edit an existing data connection? No problem; the wizard loads all previous configuration details so that you don't have to start again from scratch. 
  
After you define the data you want and connect to the source, [Import Data](import-data.md) infers the data type of each column based on the values it contains, and loads the data into your Machine Learning Studio (classic) workspace. The output of [Import Data](import-data.md) is a dataset that can be used with any experiment.

> [!IMPORTANT]
> Currently, there are limitations on the types of storage accounts that are supported. For more information, see [Technical Notes](#bkmk_Notes).
  
If your source data changes, you can refresh the dataset and add new data by re-running [Import Data](import-data.md). However, if you don't want to re-read from the source each time you run the experiment, select the **Use cached results** option to TRUE. When this option is selected, the module checks whether the experiment has run previously using the same source and same input options. If a previous run is found, the data in the cache is used, instead of re-loading the data from the source.
 
> [!NOTE]
> This module was previously named **Reader**. If you previously used the **Reader** module in an experiment, it is renamed to [Import Data](import-data.md) when you refresh the experiment.  

### <a name="DataSources"></a> Data sources

The [Import Data](import-data.md) module supports the following data sources. Click the links for detailed instructions and examples of using each data source. 
 
If you are not sure how or where you should store your data, see this guide to common data scenarios in the data science process:  [Scenarios for advanced analytics in Machine Learning](/azure/machine-learning/machine-learning-data-science-plan-sample-scenarios). 

|Data source| Use with|
|-----------|-----------|  
|[Web URL via HTTP](import-from-web-url-via-http.md)|Get data that is hosted on a web URL that uses HTTP and that has been provided in the CSV, TSV, ARFF, or SvmLight formats|  
|[Hive Query](import-from-hive-query.md)|Get data from distributed storage in Hadoop. You specify the data you want by using the HiveQL language|  
|[Azure SQL Database](import-from-azure-sql-database.md)|Get data from Azure SQL Database or from Azure SQL Data Warehouse| 
|[Azure Table](import-from-azure-table.md) |Get data that is stored in the Azure table service|  
|[Import from Azure Blob Storage](import-from-azure-blob-storage.md) |Get data that is stored in the Azure blob service|  
|[Data Feed Providers](import-from-data-feed-providers.md) |Get data exposed as a feed in OData format|  
|[Import from On-Premises SQL Server Database](import-from-on-premises-sql-server-database.md)|Get data from an on-premises SQL Server database using the Microsoft Data Management Gateway|
|[Azure Cosmos DB](import-from-cosmos-db.md)| Get data stored in JSON format in Azure Cosmos DB. |

> [!TIP]
> 
> Need to import data in the JSON format? Both R and Python support REST APIs, so use the [Execute Python Script](execute-python-script.md) or [Execute R Script](execute-r-script.md) modules to parse your data and save it as an Azure ML dataset.  
> 
> Or, use the SQL DB API for CosmosDB, which supports multiple JSON stores, including MongoDB, to read your data using the **Import from Azure Cosmos DB** option. For more information, see [Import from Azure Cosmos DB](import-from-cosmos-db.md). 

## How to use Import Data
 
1. Add the **Import Data** module to your experiment. You can find this module in the **Data Input and Output** category in Studio (classic).

2. Click **Launch Data Import Wizard** to configure the data source using a wizard.

    The wizard gets the account name and credentials, and help you configure other options. If you are editing an existing configuration, it loads the current values first.

3. If you do not want to use the wizard, click **Data source**, and choose the type of cloud-based storage you are reading from. 

    Additional settings depend on the type of storage you choose, and whether the storage is secured or not. You might need to provide the account name, file type, or credentials. Some sources do not require authentication; for others, you might need to know the account name, a key, or container name.

    For details, see the list of [Data sources](#DataSources). 

4. Select the **Use cached results** option if you want to cache the dataset for re-use on successive runs.

    Assuming there have been no other changes to module parameters, the experiment loads the data only the first time the module is run, and thereafter uses a cached version of the dataset.

    Deselect this option if you need to reload the data each time you run the experiment.

5. Run the experiment.

    When [Import Data](import-data.md) loads the data into Studio (classic), it infers the data type of each column based on the values it contains, either numerical or categorical.

    - If a header is present, the header is used to name the columns of the output dataset.

    - If there are no existing column headers in the data, new column names are generated using the format col1, col2,… ,col*n*.

### Results

When import completes, click the output dataset and select **Visualize** to see if the data was imported successfully.

If you want to save the data for re-use, rather than importing a new set of data each time the experiment is run, right-click the output and select **Save as Dataset**. Choose a name for the dataset. The saved dataset preserves the data at the time of saving, and data is not updated when the experiment is re-run, even if the dataset in the experiment changes. This can be handy for taking snapshots of data.

After importing the data, it might need some additional preparations for modeling and analysis:

- Generate statistical summaries of the data, using [Summarize Data](summarize-data.md) or [Compute Elementary Statistics](compute-elementary-statistics.md).

- Use [Edit Metadata](edit-metadata.md) to change column names, to handle a column as a different data type, or to indicate that some columns are labels or features.

- Use [Select Columns in Dataset](select-columns-in-dataset.md) to select a subset of columns to transform or use in modeling. The transformed or removed columns can easily be rejoined to the original dataset by using the [Add Columns](add-columns.md) module or the [Join Data](join-data.md) module.  

- Use [Partition and Sample](partition-and-sample.md) to divide the dataset, perform sampling, or get the top n rows.

- Use [Apply SQL Transformation](apply-sql-transformation.md) to aggregate data, filter, or transform using SQL statements.

- Use these modules to clean up text columns and generate new text features:

  - [Preprocess Text](preprocess-text.md)
  - [Extract N-Gram Features from Text](extract-n-gram-features-from-text.md)
  - [Named Entity Recognition](named-entity-recognition.md)
  - [Execute Python Script](execute-python-script.md), to implement custom NLP based on **nltk**. 

## <a name="bkmk_Notes"></a> Technical notes

This section provides a list of known issues with the **Import Data** module, as well as some general troubleshooting information not specific to a source type.

### Supported account types

Frequently Azure releases new services or new storage types; however, there is typically a delay while support for new account types is implemented in Machine Learning Studio (classic).

- Currently, Machine Learning supports all general purpose storage accounts, except for those using zone-redundant storage (ZRS). 

- Locally redundant storage (LRS) and geo-redundant storage options are supported.

- Block blobs are supported but Append blobs are not.

### Common questions and issues

This section describes some known issues, common questions, and workarounds. 

#### Headers must be single rows

If you are importing from CSV files, be aware that Machine Learning allows a single header row.  You cannot insert multi-line headers.

#### Custom separators supported on import but not export

The **Import Data** module supports importing data that uses alternative column separators, such as the semicolon (;), which is often used in Europe. When you import data from CSV files in external storage, select the **CSV with encodings** option, and pick a supported encoding.

However, you cannot generate alternative separators when you prepare data for export using the [Convert to CSV](convert-to-csv.md) module.

#### Poor column separation on string data containing commas

Just about every character that can be specified as a column separator (tabs, spaces, commas, etc.) can also be found randomly in text fields. Importing text from CSV always requires caution to avoid separating text across unnecessary new columns. It is a common problem in text processing that you have probably encountered and handled in different ways.

Problems can also occur when you try to export a column of string data that contains commas. Machine Learning does not support any special handling or special translation of such data, such as enclosing strings in quotation marks. Also, you cannot use escape characters before a comma to ensure that commas are handled as a literal character. AS a consequence, new fields are created in the output file for each comma that is encountered in the string field.

To avoid problems on export, use the [Preprocess Text](preprocess-text.md) module to remove punctuation characters from string fields.

You can also use custom [R script](execute-r-script.md) or [Python script](execute-python-script.md) to process complex text and ensure that data can be imported or exported correctly.

#### UTF-8 encoding required

Machine Learning requires UTF-8 encoding. If the data you are importing uses a different encoding, or was exported from a data source that uses a different default encoding, various problems might appear in the text. 

For example, the following image contains the same multilanguage dataset exported from Excel and then imported into Machine Learning under four different combinations of file type and encoding.

![Visualization of import encoding](media/aml-encoding-data-problems-all.jpg)

The third example represents data that was lost during while saving from Excel in CSV format, because the correct encoding was not specified at that time. Therefore, if you run into problems, be sure to check not just the file you are importing from, but whether the file was correctly exported from the source.

#### Dataset does not have column names

If the dataset you are importing does not have column names, be sure to specify one of the "no header" options. When you do so, **Import Data** adds default column names using the format Col1, Col2, etc. Later, use [Edit Metadata](edit-metadata.md) to fix the column names.

If you are exporting a dataset to a CSV file, use [Edit Metadata](edit-metadata.md) to add column names before converting or exporting it.

#### Workarounds for unsupported data sources

If you need to get data from a source that is not in the list, there are various workarounds you can try: 

- To upload data from a file on your computer, click **New** in Studio (classic), select **Dataset**, and then select **From Local File**. Locate the file and specify the format (TSV, CSV, etc.). For more information, see [Import training data into Studio (classic)](/azure/machine-learning/classic/import-data).

- Use R or Python.  You can use the [Execute R Script](execute-r-script.md) module with an appropriate R package to get data from other cloud databases.

    The [Execute Python Script](execute-python-script.md) module also lets you read  and convert data from a variety of sources. See these examples from Microsoft data scientists in the Cortana Intelligence Gallery:

    [Convert PDF to Text](https://gallery.azure.ai/Experiment/Convert-PDF-to-TEXT-1)

    [Load non-text file from Azure blob storage](https://gallery.azure.ai/Experiment/Load-non-text-file-from-Azure-Blob-Storage-1)

- Get data from AWS clusters. You can run a query against a generic Hive cluster with WebHCat or HCatalog endpoint enabled. Or publish as a page and read from the Web URL.

- Get data from MongoDB. The data migration utility for Azure Cosmos DB supports a wide variety of sources and formats. For more information and examples, see [Azure Cosmos DB: Data migration tool](/azure/cosmos-db/import-data)

For more ideas and workarounds, see the [Machine Learning forum](https://social.msdn.microsoft.com/forums/azure/home?forum=MachineLearning) or [Azure AI Gallery](https://gallery.azure.ai).  

## Module parameters

Each data source must be configured using different options. This table lists only the options that are common to all data sources.

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Data source|List|DataSource Or Sink|Blob service in Azure Storage|Data source can be HTTP, anonymous HTTPS, a file in the Blob service or Table service, a SQL database in Azure, an Azure SQL Data Warehouse, a Hive table, or an OData endpoint.|  
|Use cached results|TRUE/FALSE|Boolean|FALSE|If TRUE, the module will check whether the experiment has run previously  using the same source and same input options, and if a previous run is found, the data in the cache is used. If FALSE, or if changes are found, data will be reloaded from the source.|  

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
|[Error 0015](errors/error-0015.md)|An exception occurs if the database connection has failed.|  
|[Error 0046](errors/error-0046.md)|An exception occurs when it is not possible to create a directory on specified path.|  
|[Error 0049](errors/error-0049.md)|An exception occurs when it is not possible to parse a file.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Data Input and Output](data-input-and-output.md)   
 [Data Format Conversions](data-format-conversions.md)   
 [Export Data](export-data.md)   
 [A-Z Module List](a-z-module-list.md)
