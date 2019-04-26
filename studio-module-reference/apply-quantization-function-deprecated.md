---
title: "Apply Quantization Function (deprecated) | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 01/11/2018
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs 
manager: cgronlun
---
# Apply Quantization Function (deprecated)
*Puts data into bins using numeric values from a column*  
  
 Category: [Deprecated Modules and Features](deprecated-modules-and-features.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview

This article describes how to use the **Apply Quantization Function** module in Azure Machine Learning Studio, to group data into bins.

> [!WARNING]
>  This module is provided for backward compatibility with experiments created using the pre-release version of Azure Machine Learning, and has been deprecated. It is provided for support of older experiments only. We recommend that you modify your experiments to use [Group Data into Bins](group-data-into-bins.md).  

A quantization function applies a predefined function to a dataset you provide as input, and returns a dataset in which each element has been binned according to the specified mode.  

When you define a quantization function, the transformation function implicitly saves the column names and column data types. Therefore, you can apply the quantization function only to matching columns of the same names.  

For more information about how to define a quantization function, see these articles:

+ [Quantize (deprecated)](quantize-deprecated.md)
+ [Group Data into Bins](group-data-into-bins.md)

## Expected inputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
|Binning function|Function|Select a predefined quantization function to apply|  
  
## Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Quantized dataset|[Data Table](data-table.md)|Dataset after quantization is applied|  
  
## See also

 [Deprecated Modules and Features](deprecated-modules-and-features.md)   
 [A-Z Module List](a-z-module-list.md)
