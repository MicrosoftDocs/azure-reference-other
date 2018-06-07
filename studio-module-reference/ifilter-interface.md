---
title: "IFilter interface | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 838a91c6-ec59-4ffd-bea2-ff46293801d5
caps.latest.revision: 5
author: rastala
ms.author: roastala
manager: cgronlun
---
# IFilter interface

This article describes `IFilter`, which is the interface for working with digital signal filters in Azure Machine Learning Studio.

The `IFilter` interface provides methods and properties that are used to configure and interact with digital signal filters that have been defined using one of the filter modules in Studio. For more information, see [Filter](data-transformation-filter.md). 

You use the `IFilter` interface to save a filter or apply a predefined filter to data.  

+ Specify a filter to use: its type, coefficients, etc.
+ Apply the filter to input data
+ Generate a `DataTable` of data with filter results

You can interact with `IFilter` only in Studio, or in one of the supported APIs.  

## See also  
 [Module parameter types](machine-learning-module-parameter-types.md)   
 [Module data types](machine-learning-module-data-types.md)