---
title: "ML Studio (classic): Export Data - Azure"
description: Learn how to use the Export Data module to save results, intermediate data, and working data from your experiments into cloud storage destinations.
ms.date: 09/28/2020
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: likebupt
ms.author: amlstudiodocs

---
# Export Data

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Writes a dataset to various forms of cloud-based storage in Azure, such as tables, blobs, and Azure SQL databases*

Category: [Data Input and Output](data-input-and-output.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the  [Export Data](export-data.md) module in Machine Learning Studio (classic), to save results, intermediate data, and working data from your experiments into cloud storage destinations outside Machine Learning Studio (classic).

This module supports exporting or saving your data to the following cloud data services:

- [Export to Hive Query](export-to-hive-query.md): Write data to a Hive table in an HDInsight Hadoop cluster.

- [Export to Azure SQL Database](export-to-azure-sql-database.md): Save data to Azure SQL Database or to Azure SQL Data Warehouse.

- [Export to Azure Table](export-to-azure-table.md): Save data to the table storage service in Azure. Table storage is good for storing large amounts of data. It provides a tabular format that is scalable, inexpensive, and highly available.

- [Export to Azure Blob Storage](export-to-azure-blob-storage.md): Saves data to the Blob service in Azure. This option is useful for images, unstructured text, or binary data. Data in the Blob service can be shared publicly or saved in secured application data stores.
> [!NOTE]
> Export data module does not support connecting to Azure Blob storage account if "Secure Transfer Required" option is enabled. 

### Related tasks

- **Download data:** To download your data so that you can open it in Excel or another application, use a module such as [Convert to CSV](convert-to-csv.md) or [Convert to TSV](convert-to-tsv.md) to prepare the data in a particular format, and then download the data.

- You can download the results of any module that outputs a dataset by right-clicking the output and selecting **Download dataset**. By default, the data is exported in CSV format.

- **Download a module definition or experiment graph:** A new PowerShell library lets you download the complete metadata for your experiment, or the details for a particular module. The PowerShell for Machine Learning library is an experimental release, but has many useful cmdlets:

  - `Get-AmlExperiment` lists all the experiments in a workspace.
  - `Export-AmlExperimentGraph` exports a definition of the complete experiment to a JSON file.
  - `Download-AmlExperimentNodeOutput` lets you extract the information provided on the output ports of any module.

    For more information, see [PowerShell Module for Machine Learning Studio (classic)](https://github.com/hning86/azuremlps).
  
## How to configure Export Data

1. Add the **Export Data** module to your experiment in Studio (classic). You can find this module in the **Input and Output** category.

2. Connect **Export Data** to the module that contain the data you want to export.

3. Double-click **Export Data** to open the **Properties** pane.

4. For **Data destination**, select the type of cloud storage where you'll save your data. If you make any changes to this option, all other properties are reset. So be sure to choose this option first!

5. Provide an account name and authentication method required to access the specified storage account.

    Depending on the storage type and whether the account is secured, you might need to provide the account name, file type, access key, or container name. For sources that do not require authentication, generally it is sufficient to know the URL.

    For examples of each type, see the following topics:

    - [Export to Hive Query](export-to-hive-query.md)

    - [Export to Azure SQL Database](export-to-azure-sql-database.md)

    - [Export to Azure Table](export-to-azure-table.md)

    - [Export to Azure Blob Storage](export-to-azure-blob-storage.md)

6. The option, **Use cached results**, lets you repeat the experiment without rewriting the same results each time.

    If you deselect this option, results are written to storage each time the experiment is run, regardless of whether the output data has changed.

    If you select this option, [Export Data](export-data.md) uses cached data, if available. New results are generated only when there is an upstream change that would affect the results.

7. Run the experiment.

## Examples

For examples of how to use the [Export Data](export-data.md) module, see the [Azure AI Gallery](https://gallery.azure.ai):

- [Text Classification](https://gallery.azure.ai/Experiment/f43e79f47d8a4219bf8613d271ea2c45): This  sample uses [Export Data](export-data.md) to save intermediate results and then uses [Import Data](import-data.md) to get them from storage for later steps in the experiment.

- [Retail Forecasting Step 1 of 6 - data preprocessing](https://gallery.azure.ai/Experiment/Retail-Forecasting-Step-1-of-6-data-preprocessing-5): The retail forecasting template illustrates a machine learning task based on data stored in Azure SQL Database. It demonstrates several useful techniques such as how to create an Azure SQL database for machine learning, using the Azure SQL database to pass datasets between experiments in different accounts, saving and combining forecasts.

- [Build and deploy a machine learning model using SQL Server on an Azure VM](/azure/machine-learning/team-data-science-process/sql-walkthrough): This article demonstrates how you can use a SQL Server database hosted in an Azure VM as a source for storing training data and the predictions generated by the experiment. It also illustrates how relational database can be used for feature engineering and feature selection.

- [How to use Azure ML with Azure SQL Data Warehouse](https://blogs.technet.microsoft.com/machinelearning/2016/03/08/how-to-use-azure-ml-with-azure-sql-data-warehouse/): This article shows how you can create a machine learning model using data in Azure SQL Data Warehouse.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.


### Implementation details

- This module was previously named **Writer**. If you have an existing experiment that uses the **Writer** module, the module is renamed to [Export Data](export-data.md) when you refresh the experiment.

- Not all modules produce output that is compatible with [Export Data](export-data.md) destinations. For example, [Export Data](export-data.md) cannot save a dataset that has been converted to the SVMLight format.  [Export Data](export-data.md) supports these formats:

  - Dataset (Azure ML internal format)
  - .NET DataTable
  - CSV with or without headers
  - TSV with or without headers

### Known issues

- When you select Azure Table as the location to output your data, occasionally there might be an error when writing to the specified table. When this happens, the data might be written to a blob instead.

    If this error happens and later you are unable to read from the expected table, try using an Azure storage utility to check the blobs in the specified container in your storage account.

- Currently, you cannot save a blob into a specified Hive table. If you need to write intermediate results, avoid using a Hive table in HDInsight, and use blob storage or table storage instead.

- Currently, if you select HDFS as the location to save output data, this error message is returned: “Microsoft.Analytics.Exceptions.ErrorMapping+ModuleException.”

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|The dataset to be written.|  

## Module parameters

This table lists parameters that apply to all [Export Data](export-data.md) options. Other parameters are dynamic and change depending on the data destination you select. 

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Please specify data destination|List|DataSourceOrSink|Blob service in Azure Storage|Indicate whether the data destination is a file in the [Blob service](export-to-azure-blob-storage.md), a file in the [Table service](export-to-azure-table.md), a [SQL database](export-to-azure-sql-database.md) in Azure, or a [Hive table](export-to-hive-query.md).|  
|Use cached results|TRUE/FALSE|Boolean|FALSE|Select this option to avoid rewriting results unnecessarily. If anything changes upstream in the experiment, [Export Data](export-data.md) will always execute and write new results. However if nothing has changed, and you have selected this option, [Export Data](export-data.md) will not execute in order to avoid rewriting the same results.| 

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0057](errors/error-0057.md)|An exception occurs when attempting to create a file or blob that already exists.|  
|[Error 0001](errors/error-0001.md)|An exception occurs if one or more specified columns of the dataset couldn't be found.|  
|[Error 0027](errors/error-0027.md)|An exception occurs when two objects have to be of the same size, but they are not.|  
|[Error 0079](errors/error-0079.md)|An exception occurs if the container name in Azure Storage is specified incorrectly.|  
|[Error 0052](errors/error-0052.md)|An exception occurs if the storage access key for the Azure account is specified incorrectly.|  
|[Error 0064](errors/error-0064.md)|An exception occurs if account name or storage access key for the Azure account is specified incorrectly.|  
|[Error 0071](errors/error-0071.md)|An exception occurs if the provided credentials are incorrect.|  
|[Error 0018](errors/error-0018.md)|An exception occurs if the input dataset is not valid.|  
|[Error 0029](errors/error-0029.md)|An exception occurs when an invalid URI is passed.|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more inputs are null or empty.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [Import Data](import-data.md)   
 [Data Input and Output](data-input-and-output.md)   
 [Data Transformation](data-transformation.md)   
 [Comparing Azure Table Storage and Azure SQL Database](https://msdn.microsoft.com/subscriptions/administration/jj553018.aspx)   
 [A-Z Module List](a-z-module-list.md)
