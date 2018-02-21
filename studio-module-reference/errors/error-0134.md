---
title: "Error 0134 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 12/11/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0134-d185d1509344
caps.latest.revision: 5
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0134

**Error 0134**  
  
Exception occurs when label column is missing or has insufficient number of labeled rows.  
  
This error occurs when the module requires a label column, but you did not include one in the column selection, or the label column is missing too many values.

This error can also occur when a previous operation changes the dataset such that insufficient rows are available to a downstream operation. For example, suppose you use an expression in the **Partition and Sample** module to divide a dataset by values. If no matches are found for your expression, one of the datasets resulting from the partition would be empty.

## Resolution

 If you include a label column in the column selection but it isn’t recognized, use the [Edit Metadata](../edit-metadata.md) module to mark it as a label column.
  
 Use the [Summarize Data](../summarize-data.md) module to generate a report that shows how many values are missing in each column. Then, you can use the [Clean Missing Data](../clean-missing-data.md) module to remove rows with missing values in the label column. 

 Check your input datasets to make sure that they contain valid data, and enough rows to satisfy the requirements of the operation. Many algorithms will generate an error message if they require some minimum number rows of data, but the data contains only a few rows, or only a header.
  
|Exception Messages|
|------------------------|
|Exception occurs when label column is missing or has insufficient number of labeled rows.|  
|Exception occurs when label column is missing or has less than {0} labeled rows|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)