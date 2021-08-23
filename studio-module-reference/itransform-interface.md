---
title: "ML Studio (classic): ITransform interface - Azure"
description: Learn how to use `ITransform`, which is an interface that stores a predefined transformation, or applies a predefined transformation to data.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# ITransform interface

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes `ITransform`, which is an interface in Machine Learning Studio (classic) that stores a predefined transformation, or applies a predefined transformation to data.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

The `ITransform` interface provides the following functionality:

+ Lets you save a transformation resulting from the operation of another module
+ Accepts a predefined transformation
+ Accepts an input dataset
+ Returns a `DataTable` containing the transformed data


You can interact with `ITransform` only in Studio (classic), or in one of the supported APIs.

## See also
 [Module data types](machine-learning-module-data-types.md)
