---
title: "ICluster interface | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d54db6b4-fcba-4501-bc60-baa7dadf56e9
caps.latest.revision: 5
author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# ICluster interface

This article describes `ICluster`, which is the interface for trained clustering models that is used in Azure Machine Learning Studio.

The `ICluster` interface provides methods and properties that are used to configure and interact with clustering models. A learner is defined as a set of instructions that perform standardized machine learning tasks. 

The `ICluster` interface provides the following methods and properties for working with clustering models:

+ Gets or sets the feature attributes
+ Trains a clustering model from data
+ Applies a clustering model to new data

You can interact with `ICluster` only in Studio, or in one of the supported APIs.  

For classification or regression models, use the [iLearner](ilearner-interface.md) interface.

## See also
 [Module parameter types](machine-learning-module-parameter-types.md)   
 [Module data types](machine-learning-module-data-types.md)