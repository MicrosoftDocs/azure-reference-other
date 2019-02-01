---
title: "ITransform interface | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 01/22/2018
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# ITransform interface

This article describes `ITransform`, which is an interface in Azure Machine Learning Studio that stores a predefined transformation, or applies a predefined transformation to data.

The `ITransform` interface provides the following functionality:

+ Lets you save a transformation resulting from the operation of another module
+ Accepts a predefined transformation
+ Accepts an input dataset
+ Returns a `DataTable` containing the transformed data


You can interact with `ITransform` only in Studio, or in one of the supported APIs.

## See also
 [Module parameter types](machine-learning-module-parameter-types.md)   
 [Module data types](machine-learning-module-data-types.md)
