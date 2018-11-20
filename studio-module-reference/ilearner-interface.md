---
title: "ILearner interface | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 48eafe8c-2236-4582-aac9-96a533cc0034
caps.latest.revision: 6
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# ILearner interface

This article describes `iLearner`, which is the interface for trained models that is used in Azure Machine Learning Studio.

The `ILearner` interface provides methods and properties that are used to configure and interact with machine learning models. A learner is defined as a set of instructions that perform standardized machine learning tasks. Learners include classification algorithms, clustering algorithms, and regression algorithms.

You can interact with `iLearner` only in Studio, or in one of the supported APIs.

Studio uses this interface for the following functionality:

+ Determines whether a model has the correct format.
+ Gets the capabilities of the learner. These are any general properties of the learner that are not captured by the type signature of the specific learner.
+ Gets or sets the settings of the learner.The settings are unique to each learner and must be configured once before any query methods can be called on the learner.

For a list of learners provided by Azure Machine Learning Studio, see [Initialize Model](machine-learning-initialize-model.md).  

> [!NOTE]
> The [ICluster interface](icluster-interface.md) is also available, for clustering models only.

## See also

 [Module parameter types](machine-learning-module-parameter-types.md)   
 [Module data types](machine-learning-module-data-types.md)