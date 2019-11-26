---
title: "Quantize (deprecated) | Microsoft Docs"
titleSuffix: ML Studio (classic) - Azure
description: Learn how to use the Quantize module to bin numbers.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Quantize (deprecated)

*Puts numerical data into bins*

Category: [Deprecated Modules and Features](deprecated-modules-and-features.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Quantize Module Overview  

This article describes how to use the **Quantize** module in Azure Machine Learning Studio (classic), to bin numbers.

> [!WARNING]
> This module is provided only for backward compatibility with experiments created using the pre-release version of Azure Machine Learning, and has been deprecated. We recommend that you modify your experiments to use the new module, [Group Data into Bins](group-data-into-bins.md).

This module is useful for binning and flattening the distribution of continuous data.

During binning, each input element is mapped to a bin by comparing its value against positions of bin edges. For example, if value is 1.5 and bin edges are 1,2,3, the element would be mapped to bin number 2. Value 0.5 would be mapped to bin number 1 (the underflow bin), and value 3.5 would be mapped to bin number 4 (the overflow bin).

## How to use Quantize

This module is deprecated. For up-to-date information about quantization, see [Group Data into Bins](group-data-into-bins.md).

-   The option **Tag columns as categorical** can be used to control whether the quantized columns become categorical variables.

- To apply different quantization rules to different columns, chain together multiple instances of the **Quantize** module, and in each instance select a subset of columns to quantize.

- The same binning rule is applied to all columns specified in list of columns to quantize. The output mode specifies how the quantized values are returned. Choices include appending input table, overwriting columns in input table, and returning result columns only.

- Input columns must be numeric, and for quantile binning there must be a sufficient range of data points to determine the quantiles. Otherwise an error or NaN result may occur.

##  Technical notes

The bin indices are 1-based. This is the natural convention for quantiles (1st quantile, 2nd quantile, and so on). The only exception is the case when the column to bin is sparse.

All NaNs and missing values are propagated from the input column to the output column. The exception is the case when the module returns quantile indexes. In this case all NaNs are promoted to missing values.

If the column to bin (quantize) is sparse, then the bin index offset (quantile offset) is used when resulting column is populated. The offset is chosen so that sparse 0 always goes to the bin with index 0 (quantile with value 0). As a result, sparse zeros are propagated from input to output column. Notice that processing of dense column always produces a result with a minimum bin index equal to 1 (in other words, the minimum quantile value equals the minimum value in the column). Processing of a sparse column produces a result with variable values for the minimum bin index (minimum quantile value).

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Dataset to be analyzed|  

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Binning mode|any|QuantizationMode|Quantiles|Choose a binning method|  
|Columns to bin|any|ColumnSelection|NumericAll|Choose columns for quantization|  
|Output mode|any|OutputTo||Indicate how quantized columns should be output|  
|Tag columns as categorical|any|Boolean|true|Indicate whether output columns should be tagged as categorical|

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Quantized dataset|[Data Table](data-table.md)|Dataset with quantized columns|  
|Binning function|Function|Function that applies quantization to the dataset|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](errors/error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
|[Error 0011](errors/error-0011.md)|Exception occurs if passed column set argument does not apply to any of dataset columns.|  
|[Error 0021](errors/error-0021.md)|Exception occurs if number of rows in some of the datasets passed to the module is too small.|  
|[Error 0024](errors/error-0024.md)|Exception occurs if dataset does not contain a label column.|  
|[Error 0020](errors/error-0020.md)|Exception occurs if number of columns in some of the datasets passed to the module is too small.|  
|[Error 0038](errors/error-0038.md)|Exception occurs if number of elements expected should be an exact value, but is not.|  
|[Error 0005](errors/error-0005.md)|Exception occurs if parameter is less than a specific value.|  
|[Error 0002](errors/error-0002.md)|Exception occurs if one or more parameters could not be parsed or converted from specified type into required by target method type.|  
|[Error 0019](errors/error-0019.md)|Exception occurs if column is expected to contain sorted values, but it does not.|  
|[Error 0039](errors/error-0039.md)|Exception occurs if operation has failed.|  

## See also

 [Deprecated Modules and Features](deprecated-modules-and-features.md)   
 [A-Z Module List](a-z-module-list.md)
