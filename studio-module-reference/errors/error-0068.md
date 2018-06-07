---
title: "Error 0068 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 06/14/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0068-d185d1509344
caps.latest.revision: 7
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0068  
 Exception occurs if the specified Hive script is not correct.  
  
 This error in Azure Machine Learning occurs if there are syntax errors in a Hive QL script, or if the Hive interpreter encounters an error while executing the query or script.  
  
## Resolution  

The error message from Hive is normally reported back in the Error Log so that you can take action based on the specific error. 

+ Open the module and inspect the query for mistakes.  
+ Verify that the query works correctly outside of Azure Machine Learning by logging in to the Hive console of your Hadoop cluster and running the query.  
+ Try placing comments in your Hive script in a separate line as opposed to mixing executable statements and comments in a single line.  

### Resources

See the following articles for help with Hive queries for machine learning:

+ [Create Hive tables and load data from Azure Blob Storage](https://docs.microsoft.com/azure/machine-learning/machine-learning-data-science-move-hive-tables)
+ [Explore data in tables with Hive queries](https://docs.microsoft.com/azure/machine-learning/machine-learning-data-science-explore-data-hive-tables)
+ [Create features for data in an Hadoop cluster using Hive queries](https://docs.microsoft.com/azure/machine-learning/machine-learning-data-science-create-features-hive)
+ [Hive for SQL Users Cheat Sheet (PDF)](http://hortonworks.com/wp-content/uploads/2013/05/hql_cheat_sheet.pdf)

  
|Exception Messages|  
|------------------------|  
|Hive script is incorrect.|  
|Hive script {0} is not correct.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)