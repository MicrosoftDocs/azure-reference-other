---
title: "Error 0058 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0058-d185d1509344
caps.latest.revision: 9
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0058  
 This error in Azure Machine Learning occurs if the dataset does not contain the expected label column.  
  
 This exception can also occur when the label column provided does not match the data or datatype expected by the learner, or has the wrong values. For example, this exception is produced when using a real-valued label column when training a binary classifier.  
  
## Resolution  
 The resolution depends on the learner or trainer that you are using, and the data types of  the columns in your dataset. First, verify the requirements of the machine learning algorithm or training module.  
  
 Revisit the input dataset. Verify that the column you expect to be treated as the label has the right data type for the model you are creating.  
  
 Check inputs for missing values and eliminate or replace them if necessary.  
  
 If necessary, add the [Edit Metadata](../edit-metadata.md) module and ensure that the label column is marked as a label.  
  
|Exception Messages|  
|------------------------|  
|The label column is not as expected|  
|The label column is not as expected in "{0}".|  
|The label column "{0}" is not expected in "{1}".|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
