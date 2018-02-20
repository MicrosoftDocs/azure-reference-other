---
title: "Error 0022 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 09/16/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0022-d185d1509344
caps.latest.revision: 9
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0022  
 Exception occurs if number of selected columns in input dataset does not equal to the expected number.  
  
 This error in Azure Machine Learning can occur when the downstream module or operation requires a specific number of columns or inputs, and you have provided too few or too many columns or inputs. For example:  
  
-   You need to specify a single label column or key column and accidentally selected multiple columns.  
  
-   You are renaming columns, but provided more or fewer names than there are columns.  
  
-   The number of columns in the source or destination has changed or doesn't match the number of columns used by the module.  
  
-   You have provided a comma-separated list of values for inputs, but the number of values does not match, or multiple inputs are not supported.  
  
## Resolution  
 Revisit the module and check the column selection to ensure that the correct number of columns is selected. Verify the outputs of upstream modules, and the requirements of downstream operations.  
  
 If you used one of the column selection options that can select multiple columns (column indices, all features, all numeric, etc.), validate the exact number of columns returned by the selection.  
  
 If you are trying to specify a comma-separated list of datasets as inputs to [Unpack Zipped Datasets](../unpack-zipped-datasets.md), unpack only one datset at a time. Multiple inputs are not supported.  
  
 Verify that the number or type of upstream columns has not changed.  
  
 If you are using a recommendation dataset to train a model, be aware that the recommender expects a limited number of columns, corresponding to user-item pairs or user-item-rankings. You must remove additional columns before training the model or splitting recommendation datasets. For more information, see [Split Data](../split-data.md).  
  
|Exception Messages|  
|------------------------|  
|Number of selected columns in input dataset does not equal to the expected number.|  
|Number of selected columns in input dataset does not equal to {0}.|  
|Column selection pattern "{0}" provides number of selected columns in input dataset not equal to {1}.|  
|Column selection pattern "{0}" is expected to provide {1} column(s) selected in input dataset, but {2} column(s) is/are actually provided.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)