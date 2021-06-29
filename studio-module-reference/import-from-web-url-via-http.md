---
title: "ML Studio (classic): Import from Web URL via HTTP - Azure"
description: Learn how to use the Import Data module to read data from a public Web page for use in a machine learning experiment.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Import from Web URL via HTTP

This article describes how to use the [Import Data](import-data.md) module in Machine Learning Studio (classic), to read data from a public Web page for use in a machine learning experiment.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

The following restrictions apply to data published on a web page:

- Data must be in one of the supported formats: CSV, TSV, ARFF, or SvmLight. Other data will cause errors.
- No authentication is required or supported. Data must be publicly available. 

## How to import data via HTTP

There are two ways to get data: use the wizard to set up the data source, or configure it manually.

### Use the Data Import Wizard

1. Add the **Import Data** module to your experiment. You can find the module in Studio (classic), in the **Data Input and Output** category.

2. Click **Launch Import Data Wizard** and select Web URL via HTTP.

3. Paste in the URL, and select a data format.

4. When configuration is complete, right-click the module, and select **Run Selected**.

To edit an existing data connection, start the wizard again. The wizard loads all previous configuration details so that you don't have to start again from scratch

### Manually set properties in the Import Data module

The following steps describe how to manually configure the import source.

1. Add the [Import Data](import-data.md) module to your experiment. You can find the module in Studio (classic), in the **Data Input and Output** category.

2. For **Data source**, select **Web URL via HTTP**.

3. For **URL**, type or paste the full URL of the page that contains the data you want to load.

    The URL should include the site URL and the full path, with file name and extension, to the page that contains the data to load.

    For example, the following page contains the Iris data set from the machine learning repository of the University of California, Irvine:

    `https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data`

4. For **Data format**, select one of the supported data formats from the list.

    We recommend that you always check the data beforehand to determine the format. The UC Irvine page uses the CSV format. Other supported data formats are TSV, ARFF, and SvmLight.

5. If the data is in CSV or TSV format, use the **File has header row** option to indicate whether or not the source data includes a header row. The header row is used to assign column names.

6. Select the **Use cached results** options if you don't expect the data to change much, or if you want to avoid reloading the data each time you run the experiment.

    When this option  is selected, the experiment loads the data the first time the module is run, and thereafter uses a cached version of the dataset.

    If you want to re-load the dataset on each iteration of the experiment dataset, deselect the **Use cached results** option. Results are also re-loaded if there are any changes to the parameters of [Import Data](import-data.md).

7. Run the experiment.

### Results

When complete, click the output dataset and select **Visualize** to see if the data was imported successfully.

## Examples

See these examples in the [Azure AI Gallery](https://gallery.azure.ai) of machine learning experiments that get data from public web sites:

- [Letter Recognition sample](https://go.microsoft.com/fwlink/?LinkId=525737): Gets a training dataset from the public machine learning repository hosted by UC Irvine.

- [Download UCI Dataset](https://go.microsoft.com/fwlink/?LinkId=525938): Reads a dataset in the CSV format.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Common questions

#### Can I filter data as it is being read from the source

No. That option is not supported with this data source.

After reading the data into Machine Learning Studio (classic), you can split the dataset, use sampling, and so forth to get just the rows you want:

- Write some simple R code in the [Execute R Script](execute-r-script.md) to get a portion of the data by rows or columns.

- Use the [Split Data](split-data.md) module with a relative expression or a regular expression to isolate the data you want.

- If you loaded more data than you need, overwrite the cached dataset by reading a new dataset, and saving it with the same name.

#### How can I avoid re-loading the same data unnecessarily

If your source data changes, you can refresh the dataset and add new data by re-running [Import Data](import-data.md).

If you don't want to re-read from the source each time you run the experiment, select the **Use cached results** option to TRUE. When this option is set to TRUE, the module checks whether the experiment has run previously using the same source and same input options. If a previous run is found, the data in the cache is used, instead of re-loading the data from the source.

#### Why was an extra row added at the end of my dataset

If the [Import Data](import-data.md) module encounters a row of data that is followed by an empty line or a trailing new line character, an extra row is added at the end of the table. This new row contains missing values.

The reason for interpreting a trailing new line as a new row is that [Import Data](import-data.md) cannot determine the difference between an actual empty line and an empty line that is created by the user pressing ENTER at the end of a file.

Because some machine learning algorithms support missing data and would thus treat this line as a case (which in turn could affect the results), you should use [Clean Missing Data](clean-missing-data.md) to check for missing values (particularly rows that are completely empty), and remove them as needed.

Before you check for empty rows, you might also want to divide the dataset by using [Split Data](split-data.md). This separates rows with partial missing values, which represent actual missing values in the source data. Use the **Select head N rows** option to read the first part of the dataset into a separate container from the last line.  

#### Why are some characters in my source file not displayed correctly

Machine Learning supports the UTF-8 encoding. If your source file used another type of encoding, the characters might not be imported correctly.

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Data source|List|Data Source Or Sink|Azure Blob Storage|Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, an on-premises SQL Server database, a Hive table, or an OData endpoint.|  
|URL|any|String|none|URL for HTTP|  
|Data format|CSV<br /><br /> TSV<br /><br /> ARFF<br /><br /> SvmLight|Data Format|CSV|File type of HTTP source|  
|CSV or TSV has header row|TRUE/FALSE|Boolean|false|Indicates if CSV or TSV file has a header row|  
|Use cached results|TRUE/FALSE|Boolean|FALSE|Module executes only if valid cache does not exist. Otherwise, cached data from previous execution is used.|  

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
|[Error 0046](errors/error-0046.md)|An exception occurs when it is not possible to create a directory on specified path.|  
|[Error 0049](errors/error-0049.md)|An exception occurs when it is not possible to parse a file.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [Import Data](import-data.md)   
 [Export Data](export-data.md)   
 [Import from Hive Query](import-from-hive-query.md)   
 [Import from Azure SQL Database](import-from-azure-sql-database.md)   
 [Import from Azure Table](import-from-azure-table.md)   
 [Import from Azure Blob Storage](import-from-azure-blob-storage.md)   
 [Import from Data Feed Providers](import-from-data-feed-providers.md)   
 [Import from On-Premises SQL Server Database](import-from-on-premises-sql-server-database.md)
