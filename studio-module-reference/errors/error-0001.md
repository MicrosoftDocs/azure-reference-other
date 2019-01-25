---
title: "Error 0001 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.subservice: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0001-d185d1509344
caps.latest.revision: 6
author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0001  
 Exception occurs if one or more specified columns of data set couldn't be found.  
  
 You will receive this error if a column selection is made for a module, but the selected column(s) do not exist in the input data set. This may occur if you have manually typed in a column name or if the column selector has provided a suggested column that did not exist in your dataset when you ran the experiment.  
  
## Resolution  
 Revisit the module throwing this exception and validate that the column name or names are correct and that all referenced columns do exist.  
  
|Exception Messages|  
|------------------------|  
|One or more specified columns were not found|  
|Column with name or index "{0}" not found|  
|Column with name or index "{0}" does not exist in "{1}"|  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
