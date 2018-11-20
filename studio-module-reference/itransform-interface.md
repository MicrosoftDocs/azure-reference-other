---
title: "ITransform interface | Microsoft Docs"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 444302ce-a1b6-4003-9a64-8a56120be6ce
caps.latest.revision: 5
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