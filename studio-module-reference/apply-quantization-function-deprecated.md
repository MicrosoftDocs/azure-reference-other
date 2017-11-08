---
title: "Apply Quantization Function (deprecated) | Microsoft Docs"
ms.custom: ""
ms.date: 07/01/2015
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 77443f05-e1c3-47fc-9167-963b2703936d
caps.latest.revision: 9
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Apply Quantization Function (deprecated)
*Puts data into bins using numeric values from a column*  
  
 Category: [Deprecated Modules and Features](deprecated-modules-and-features.md)  
  
##  <a name="Remarks"></a> Module Overview  
 The **Apply Quantization Function** module applies a predefined function to a dataset you provide as input, and returns a dataset in which each element has been binned according to the specified mode.  
  
 For more information about how to define a quantization function, see [Quantize (deprecated)](quantize-deprecated.md).  
  
> [!NOTE]
>  When you define a quantization function using [Quantize (deprecated)](quantize-deprecated.md), the transformation function implicitly saves the column names and column data types. Therefore, you can apply the quantization function only to matching columns of the same names.  
  
> [!WARNING]
>  This module is provided for backward compatibility with experiments created using the pre-release version of Azure Machine Learning, and will soon be deprecated. We recommend that you modify your experiments to use [Group Data into Bins](group-data-into-bins.md) instead.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
|Binning function|Function|Select a predefined quantization function to apply|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Quantized dataset|[Data Table](data-table.md)|Dataset after quantization is applied|  
  
## See Also  
 [Deprecated Modules and Features](deprecated-modules-and-features.md)   
 [A-Z Module List](a-z-module-list.md)