---
title: "Error 0090 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0090  
 Exception occurs when Hive table creation fails.  
  
 This error in Azure Machine Learning occurs when you are using [Export Data](../export-data.md) or another option to save data to an HDInsight cluster and the specified Hive table cannot be created.  
  
## Resolution  
 Check the Azure storage account name associated with the cluster and verify that you are using the same account in the module properties.  
  
|Exception Messages|  
|------------------------|  
|The Hive table could not be created. For a HDInsight cluster, please ensure the Azure storage account name associated with cluster is the same as what is passed in through the module parameter.|  
|The Hive table "{0}" could not be created. For a HDInsight cluster, please ensure the Azure storage account name associated with cluster is the same as what is passed in through the module parameter.|  
|The Hive table "{0}" could not be created. For a HDInsight cluster, please ensure the Azure storage account name associated with cluster is "{1}".|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
