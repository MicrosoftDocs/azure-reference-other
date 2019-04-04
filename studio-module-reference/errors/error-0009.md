---
title: "Error 0009 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 10/05/2017
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0009  
 Exception occurs when the Azure storage account name or container name is specified incorrectly.  
  
This error occurs in Azure Machine Learning Studio when you specify parameters for an Azure storage account, but the name or password cannot be resolved. Errors on passwords or account names can happen for many reasons:
 
 + The account is the wrong type. Some new account types are not supported for use with Machine Learning Studio. See [Import Data](../import-data.md) for details.
 + You misstyped the account name
 + The account no longer exists
 + The password for the storage account is wrong or has changed
 + You didn't specify the container name, or the container does not exist
 + You didn't fully specify the file path (path to the blob)
   
**Resolution :**

Such problems often occur when you try to manually enter the account name, password, or container path. We recommend that you use the new wizard for the [Import Data](../import-data.md) module, which helps you look up and check names.

You should also check whether the account, container, or blob has been deleted. Use another Azure storage utility to verify that the account name and password have been entered correctly, and that the container exists. 

Some newer account types are not supported by Azure Machine Learning. For example, the new "hot" or "cold" storage types cannot be used for machine learning. Both classic storage accounts and storage accounts created as "General purpose" work fine.

If the complete path to a blob was specified, verify that the path is specified as **container/blobname**, and that both the container and the blob exist in the account.  
  
 The path should not contain a leading slash. For example **/container/blob** is incorrect and should be entered as **container/blob**.  

### Resources

See this article for an explanation of the different storage options that are supported: [Import data into Azure Machine Learning Studio from various online data sources with the Import Data module](https://docs.microsoft.com/azure/machine-learning/machine-learning-import-data-from-online-sources)

### Sample experiments

See these experiments in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/) for examples of how to connect to different data sources:

+ Input data from various sources:  This lab provides a visual guide to using many of the Azure ML data sources: [AzureML experiments and data interaction](https://gallery.cortanaintelligence.com/Tutorial/3-AzureML-Experiments-and-Data-Interaction-1)

+ Azure Cosmos DB: [Reading data from Azure Cosmos DB in Azure Machine Learning](https://gallery.cortanaintelligence.com/Experiment/Reading-data-from-Azure-DocumentDB-in-Azure-Machine-Learning-1)

+ Azure blob storage and Azure SQL Database: [Twitter Stream Analysis with Azure Machine Learning](https://gallery.cortanaintelligence.com/Tutorial/Twitter-Stream-Analysis-with-Azure-Machine-Learning)

+ Import otherwise unreadable data using Python: [Load non-text file from Azure Blob storage](https://gallery.cortanaintelligence.com/Experiment/Load-non-text-file-from-Azure-Blob-Storage-1)

  
|Exception Messages|  
|------------------------|  
|The Azure storage account name or container name is incorrect.|  
|The Azure storage account name "{0}" or container name "{1}" is incorrect; a container name of the format container/blob was expected.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  

 [Module error codes](machine-learning-module-error-codes.md)
