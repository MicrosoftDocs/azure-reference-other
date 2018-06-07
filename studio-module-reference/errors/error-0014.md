---
title: "Error 0014 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 06/14/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0014-d185d1509344
caps.latest.revision: 7
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0014  
 Exception occurs if the count of column unique values is greater than allowed.  
  
 This error occurs when a column contains too many unique values.  For example, you might see this error if you specify that a column be handled as categorical data, but there are too many unique values in the column to allow processing to complete. You might also see this error if there is a mismatch between the number of unique values in two inputs.   
  
## Resolution  

Open the module that generated the error, and identify the columns used as inputs. For some modules, you can right-click the dataset input and select **Visualize** to get statistics on individual columns, including the number of unique values and their distribution.

For columns that you intend to use for grouping or categorization, take steps to reduce the number of unique values in columns. You can do this in different ways, depending on the data type of the column. 

+ For text data, you might be able to use [Preprocess Text](../preprocess-text.md) to collapse similar entries. 
+ For numeric data, you can create a smaller number of bins using [Group Data into Bins](../group-data-into-bins.md), remove or truncate values using [Clip Values](../clip-values.md), or use machine learning methods such as [Principal Component Analysis](../principal-component-analysis.md) or [Learning with Counts](../data-transformation-learning-with-counts.md) to reduce the dimensionality of the data.  

> [!TIP]
> Unable to find a resolution that matches your scenario? You can provide feedback on this topic that includes the name of the module that generated the error, and the data type and cardinality of the column. We will use the information to provide more targeted troubleshooting steps for common scenarios.   
  
|Exception Messages|  
|------------------------|  
|Amount of column unique values is greater than allowed.|  
|Number of unique values in column: "{0}" exceeds tuple count of {1}.|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)