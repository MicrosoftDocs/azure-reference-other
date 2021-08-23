---
title: "ML Studio (classic): IFilter interface - Azure"
description: Learn how to use `IFilter`, which is the interface for working with digital signal filters.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# IFilter interface

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes `IFilter`, which is the interface for working with digital signal filters in Machine Learning Studio (classic).

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

The `IFilter` interface provides methods and properties that are used to configure and interact with digital signal filters that have been defined using one of the filter modules in Studio (classic). For more information, see [Filter](data-transformation-filter.md). 

You use the `IFilter` interface to save a filter or apply a predefined filter to data.  

+ Specify a filter to use: its type, coefficients, etc.
+ Apply the filter to input data
+ Generate a `DataTable` of data with filter results

You can interact with `IFilter` only in Studio (classic), or in one of the supported APIs.  

## See also   
 [Module data types](machine-learning-module-data-types.md)
