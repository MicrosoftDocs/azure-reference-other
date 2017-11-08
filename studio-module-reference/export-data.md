---
title: "Export Data | Microsoft Docs"
ms.custom: ""
ms.date: 04/25/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 7a391181-b6a7-4ad4-b82d-e419c0d6522c
caps.latest.revision: 39
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlun"
---
# Export Data
*Writes a dataset to various forms of cloud-based storage in Azure, such as tables, blobs, and Azure SQL databases*  
  
 Category: [Data Input and Output](data-input-and-output.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the [Export Data](export-data.md) module to save results, intermediate data, and working data from your experiments into cloud storage destinations outside Azure Machine Learning Studio.  

  
 [Export Data](export-data.md) supports saving your data to the following cloud data services:  
  
-   **Hive Query**. Write data to a Hive table in an HDInsight Hadoop cluster.  
  
-   **Azure SQL Database**. Save data to Azure SQL Database or to Azure SQL Data Warehouse.  
  
-   **Azure Table**. Save data to the table storage service in Azure. Table storage is good for storing large amounts of data. It provides a tabular format that is scalable, inexpensive, and highly available.  
  
-   **Azure Blob Storage**. Saves data to the Blob service in Azure. This option is useful for images, unstructured text, or binary data. Data in the Blob service can be shared publicly or saved in secured application data stores.  
  
### Related Tasks

+ **Download data:** If you need to download your data so that you can open it in Excel or another application, you can use a module such as [Convert to CSV](convert-to-csv.md) or [Convert to TSV](convert-to-tsv.md) to prepare the data in a particular format, and then download the data. 

  You can download the results of any module that outputs a dataset by right-clicking the output and selecting **Download dataset**. By default, the data is exported in CSV format. 

+ **Download a module definition or experiment graph:** A new PowerShell ibrary is available that lets you download the complete metadata for your experiment, or the details for a particular module. The PowerShell for Azure Machine Learning library is in beta, but has these and many other useful cmdlets:
    + *Get-AmlExperiment* lists all the experiments in a workspace.
    + *Export-AmlExperimentGraph* exports a definition of the complete experiment to a JSON file.
    + *Download-AmlExperimentNodeOutput* lets you extract the information provided on the output ports of any module.
    
    For more information, see [PowerShell Module for Azure Machine Learning Studio](https://github.com/hning86/azuremlps).
  
## How to Configure [Export Data](export-data.md)  
  
1.  For **Data destination**, select the type of cloud storage where you'll save your data. 

    What you select here will change many of the following options, and if you change this option later, any entries you might have made will be reset. So be sure to choose this option first. 
  
2.  Configure any options required to access the specified storage account. Depending on the storage type and whether the account is secured, you might need to provide the account name, file type, access key, or container name. For sources that do not require authentication, generally it is sufficient to know the URL.  
  
     The following topics provide examples, and configuration details for each storage type:  
  
    -   [Export to Hive Query](export-to-hive-query.md)  
  
    -   [Export to Azure SQL Database](export-to-azure-sql-database.md)  
  
    -   [Export to Azure Table](export-to-azure-table.md)  
  
    -   [Export to Azure Blob Storage](export-to-azure-blob-storage.md)  
  
3.  Select the option, **Use cached results**, if you want to avoid rewriting the results each time you run the experiment. 
    
      + If you deselect this option, the results will be written to storage each time the experiment is run, regardless of whether the output data has changed.
  
     + If you select this option, [Export Data](export-data.md) will generate new results only when there is an upstream change that would affect the results.  
  
4.  Run the experiment.  
  
 Not sure how or where you should store your data? See this guide to common data scenarios in the data science process:  [Scenarios for advanced analytics in Azure Machine Learning](https://azure.microsoft.com/documentation/articles/machine-learning-data-science-plan-sample-scenarios/)  
  
## Example  
 For examples of how to use the [Export Data](export-data.md) module, see these experiments in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com):  
  
-   This  sample uses [Export Data](export-data.md) to save intermediate results and then uses [Import Data](import-data.md) to get them from storage for later steps in the experiment.  
  
     [Text Classification](http://gallery.cortanaintelligence.com/Experiment/f43e79f47d8a4219bf8613d271ea2c45)  
  
-   The Retail Forecasting template illustrates a machine learning task based on data stored in Azure SQL Database. It demonstrates several useful techniques such as how to create an Azure SQL database for machine learning, using the Azure SQL database to pass datasets between experiments in different accounts, saving and combining forecasts.  
  
     [http://gallery.cortanaintelligence.com/Experiment/Retail-Forecasting-Step-1-of-6-data-preprocessing-5](http://gallery.cortanaintelligence.com/Experiment/Retail-Forecasting-Step-1-of-6-data-preprocessing-5)  
  
-   This article demonstrates how you can use a SQL Server database hosted in an Azure VM as a source for storing training data and the predictions generated by the experiment. It also illustrates how relational database can be used for feature engineering and feature selection.  
  
     [Build and deploy a machine learning model using SQL Server on an Azure VM](../../team-data-science-process/sql-walkthrough.md)  
  
-   This article shows how you can create a machine learning model using data in Azure SQL Data Warehouse:  
  
     [How to use Azure ML with Azure SQL Data Warehouse](https://blogs.technet.microsoft.com/machinelearning/2016/03/08/how-to-use-azure-ml-with-azure-sql-data-warehouse/)  
  
## Technical Notes  

 - This module was previously named **Writer**. If you previously used the **Writer** module in an experiment, it will be renamed to [Export Data](export-data.md) when you refresh the experiment.  
  
-   Not all modules produce output that is compatible with [Export Data](export-data.md) destinations. For example, [Export Data](export-data.md) cannot save a dataset that has been converted to the SVMLight format.  [Export Data](export-data.md) supports these formats: 

    + dataset (Azure ML internal format)
    + .NET DataTable
    + CSV with or without headers
    + TSV with or without headers  
  
-   When you select Azure Table as the location to output your data, occasionally there might be an error when writing to the specified table, and instead the data is written to a blob. If this error happens and later you are unable to read from a table, try using an Azure storage utility to check the blobs in the specified container in your storage account.  
  
-   The ability to save a blob into a specified Hive table is not working. If you need to write intermediate results, avoid using a Hive table in HDInsight, and use blob storage or table storage instead.  
  
-   Currently, if you select HDFS as the location to save output data, this error message is returned: “Microsoft.Analytics.Exceptions.ErrorMapping+ModuleException.”  
  
##  <a name="ExpectedInputs"></a> Expected Input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|The dataset to be written.|  
  
##  <a name="parameters"></a> Module Parameter  
 This table lists parameters that apply to all [Export Data](export-data.md) options. Other parameters are dynamic and change depending on the data destination you select.  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Please specify data destination|List|DataSourceOrSink|Blob service in Azure Storage|Indicate whether the data destination is a file in the [Blob service](export-to-azure-blob-storage.md), a file in the [Table service](export-to-azure-table.md), a [SQL database](export-to-azure-sql-database.md) in Azure, or a [Hive table](export-to-hive-query.md).|  
|Use cached results|TRUE/FALSE|Boolean|FALSE|Select this option to avoid rewriting results unnecessarily. If anything changes upstream in the experiment, [Export Data](export-data.md) will always execute and write new results. However if nothing has changed, and you have selected this option, [Export Data](export-data.md) will not execute in order to avoid rewriting the same results.|  
  
##  <a name="exceptions"></a> Exceptions  
  
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
  
## See Also  
 [Import Data](import-data.md)   
 [Data Input and Output](data-input-and-output.md)   
 [Data Transformation](data-transformation.md)   
 [Comparing Azure Table Storage and Azure SQL Database](https://msdn.microsoft.com/subscriptions/administration/jj553018.aspx)   
 [A-Z Module List](a-z-module-list.md)