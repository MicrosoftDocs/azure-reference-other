---
title: "Error 0024 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 06/14/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0024-d185d1509344
caps.latest.revision: 8
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0024  
Exception occurs if dataset does not contain a label column.  

 This error in Azure Machine Learning occurs when the module requires a label column and the dataset does not have a label column. For example, evaluation of a scored dataset usually requires that a label column be present to compute accuracy metrics.  
 
It can also happen that a label column is present in the dataset, but not detected correctly by Azure Machine Learning.
  
## Resolution  

+ Open the module that generated the error, and determine if a label column is present. The name or data type of the column doesn't matter, as long as the column contains a single outcome (or dependent variable) that you are trying to predict. If you are not sure which column has the label, look for a generic name such as  *Class* or *Target*. 
+  If the dataset does not include a label column, it is possible that the label column was explicitly or accidentally removed upstream. It could also be that the dataset is not the output of an upstream scoring module.
+ To explicitly mark the column as the label column, add the [Edit Metadata](../edit-metadata.md) module and connect the dataset. Select only the label column, and select **Label** from the **Fields** dropdown list. 
+ If the wrong column is chosen as the label, you can select **Clear label** from the **Fields** to fix the metadata on the column. 
  
|Exception Messages|  
|------------------------|  
|There is no label column in dataset.|  
|There is no label column in "{0}".|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)