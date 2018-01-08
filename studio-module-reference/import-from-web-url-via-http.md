---
title: "Import from Web URL via HTTP | Microsoft Docs"
ms.custom: ""
ms.date: 10/05/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b1e62901-41fb-4839-bacd-c0071c984fc1
caps.latest.revision: 23
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlun"
---
# Import from Web URL via HTTP
This article describes how to use the [Import Data](import-data.md) module in Azure Machine Learning Studio, to read data from a public Web page for use in a machine learning experiment.  
  
The following restrictions apply to data published on a web page:

+ Data must be in one of the supported formats: CSV, TSV, ARFF, or SvmLight. Other data will cause errors.
+ No authentication is required or supported. Data must be publicly available. 

  
##  <a name="HTTP"></a> How to Import Data via HTTP  

There are two ways to get data: use the wizard to set up the data source, or configure it manually.

### Use the Data Import Wizard

1. Add the **Import Data** module to your experiment. You can find the module under **Data Input and Output**.

2. Click **Launch Import Data Wizard** and select Web URL via HTTP.

3. Paste in the URL, and select a data format.

4. When configuration is complete, right-click the module, and select **Run Selected**. 

To edit an existing data connection, start the wizard again. The wizard loads all previous configuration details so that you don't have to start again from scratch

### Manually set properties in the Import Data module

The following steps describe how to manually configure the import source.
  
1.  Add the [Import Data](import-data.md) module to your experiment. You can find this module in the [Data Input and Output](data-input-and-output.md) group in the **experiment items** list in Azure Machine Learning Studio. 
  
2.  For **Data source**, select **Web URL via HTTP**.  
  
3.  For **URL**, type or paste the full URL of the page that contains the data you want to load. 

    The URL should include the site URL and the full path, with file name and extension, to the page that contains the data to load.   

    For example, the following page contains the iris data set from the machine learning repository of the University of California, Irvine:  
  
     `http://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data`  
  
4.  For **Data format**, select one of the supported data formats from the list.  
  
     We recommend that you always check the data beforehand to determine the format. The UC Irvine page uses the CSV format. Other supported data formats are TSV, ARFF, and SvmLight.  
  
5. If the data is in CSV or TSV format, select or deselect the **File has header row** option to indicate whether or not it includes a header row. The header row is used to assign column names.  
  
5.  Select the **Use cached results** options if you don't expect the data to change much, or if you want to avoid reloading the data each time you run the experiment.  
  
     When this option  is selected, the experiment will load the data the first time the module is run, and thereafter use a cached version of the dataset.  
  
     If you want to re-load the dataset on each iteration of the experiment dataset, deselect the **Use cached results** option. Results will also be re-loaded if there are any changes to the parameters of [Import Data](import-data.md).  
  
6.  Run the experiment. 


### Results

When complete, click the output dataset and select **Visualize** to see if the data was imported successfully.  
 
  
##  <a name="Examples"></a> Examples  

See these examples in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com) of machine learning experiments that get data from public web sites:  
  
-   The [Letter Recognition sample](http://go.microsoft.com/fwlink/?LinkId=525737) gets a training dataset from the public machine learning repository hosted by UC Irvine.  
  
-   The [Download UCI Dataset](http://go.microsoft.com/fwlink/?LinkId=525938) sample reads a dataset in the CSV format.  
  
##  <a name="TechnicalNotes"></a> Technical Notes  

This section contains advanced configuration options and answers to commonly asked questions.  
  
-   **How can I filter data as it is being read from the source?**  
  
     That option is not supported with this data source.  After reading it into Azure Machine Learning Studio, you can split the dataset, use sampling, and so forth to get just the rows you want:  
  
    -   Write some simple R code in the [Execute R Script](execute-r-script.md) to get a portion of the data by rows or columns.  
  
    -   Use the [Split Data](split-data.md) module with a relative expression or a regular expression to isolate the data you want.  
  
    -   If you loaded more data than you need, overwrite the cached dataset by reading a new dataset, and saving it with the same name.  
  
-   **How can I avoid re-loading the same data unnecessarily?**  
  
     If your source data changes, you can refresh the dataset and add new data by re-running [Import Data](import-data.md). 
     
     If you don't want to re-read from the source each time you run the experiment, select the **Use cached results** option to TRUE. When this option is set to TRUE, the module will check whether the experiment has run previously  using the same source and same input options, and if a previous run is found, the data in the cache is used, instead of re-loading the data from the source.  
  
-   **Why does [Import Data](import-data.md) add an extra row at the end of my dataset when it finds a trailing new line?**  
  
     If the [Import Data](import-data.md) module encounters a row of data that is followed by an empty line or a trailing new line character, an extra row is added at the end of the table. This new row contains missing values.  
  
     The reason for interpreting a trailing new line as a new row is that [Import Data](import-data.md) cannot determine the difference between an actual empty line and an empty line that is created by the user pressing ENTER at the end of a file.  
  
     Because some machine learning algorithms support missing data and will actually treat this line as a case (which in turn would affect the results), you should use [Clean Missing Data](clean-missing-data.md) to check for missing values (particularly rows that are completely empty), and remove them as needed.  
  
     Before you check for empty rows, you might also want to divide the dataset by using [Split Data](split-data.md). This separates rows with partial missing values, which represent actual missing values in the source data. Use the **Select head N rows** option to read the first part of the dataset into a separate container from the last line.  
  
-   **Why are some characters in my source file not displayed correctly?**  
  
     Azure Machine Learning supports the UTF-8 encoding. If your source file used another type of encoding, the characters might not be imported correctly.  
  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Data source|List|Data Source Or Sink|Azure Blob Storage|Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, an on-premises SQL Server database, a Hive table, or an OData endpoint.|  
|URL|any|String|none|URL for HTTP|  
|Data format|CSV<br /><br /> TSV<br /><br /> ARFF<br /><br /> SvmLight|Data Format|CSV|File type of HTTP source|  
|CSV or TSV has header row|TRUE/FALSE|Boolean|false|Indicates if CSV or TSV file has a header row|  
|Use cached results|TRUE/FALSE|Boolean|FALSE|Module executes only if valid cache does not exist. Otherwise, cached data from previous execution is used.|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with downloaded data|  
  
##  <a name="exceptions"></a> Exceptions  
  
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
  
## See Also  
 [Import Data](import-data.md)   
 [Export Data](export-data.md)   
 [Import from Hive Query](import-from-hive-query.md)   
 [Import from Azure SQL Database](import-from-azure-sql-database.md)   
 [Import from Azure Table](import-from-azure-table.md)   
 [Import from Azure Blob Storage](import-from-azure-blob-storage.md)   
 [Import from Data Feed Providers](import-from-data-feed-providers.md)   
 [Import from On-Premises SQL Server Database](import-from-on-premises-sql-server-database.md)