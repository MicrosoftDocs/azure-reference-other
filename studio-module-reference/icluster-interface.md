---
title: "ML Studio (classic): ICluster interface - Azure"
description: Learn how to use `ICluster`, which is the interface for trained clustering models.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# ICluster interface

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes `ICluster`, which is the interface for trained clustering models that is used in Machine Learning Studio (classic).

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

The `ICluster` interface provides methods and properties that are used to configure and interact with clustering models. A learner is defined as a set of instructions that perform standardized machine learning tasks. 

The `ICluster` interface provides the following methods and properties for working with clustering models:

+ Gets or sets the feature attributes
+ Trains a clustering model from data
+ Applies a clustering model to new data

You can interact with `ICluster` only in Studio (classic), or in one of the supported APIs.  

For classification or regression models, use the [iLearner](ilearner-interface.md) interface.

## See also
 [Module data types](machine-learning-module-data-types.md)
