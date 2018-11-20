---
title: "Error 0089 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 08/15/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0089-d185d1509344
caps.latest.revision: 7
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0089  
 Exception occurs when the specified number of classes is less than the actual number of classes in a dataset used for counting.  
  
 This error in Azure Machine Learning occurs when you are creating a count table and the label column contains a different number of classes than you specified in the module parameters.  
  
## Resolution  
 Check your dataset and find out exactly how many distinct values (possible classes) there are in the label column. When you create the count table, you must specify at least this number of classes.  
  
 The count table cannot automatically determine the number of classes available.  
  
 When you create the count table you cannot specify 0 or any number that is less than the actual number of classes in the label column.  
  
|Exception Messages|  
|------------------------|  
|The number of classes is incorrect. Please make sure that the number of classes you specify in the parameter pane is greater than or equal to the number of classes in the label column.|  
|The number of classes specified is '{0}', which is not greater than a label value '{1}' in the data set used to count. Please make sure that the number of classes you specify in the parameter pane is greater than or equal to the number of classes in the label column.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)