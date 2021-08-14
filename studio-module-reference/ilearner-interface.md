---
title: "ML Studio (classic): ILearner interface - Azure"
description: Learn how to use the `iLearner` interface with its methods and properties to configure and interact with machine learning models.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# ILearner interface

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes `iLearner`, which is the interface for trained models that is used in Machine Learning Studio (classic).

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

The `ILearner` interface provides methods and properties that are used to configure and interact with machine learning models. A learner is defined as a set of instructions that perform standardized machine learning tasks. Learners include classification algorithms, clustering algorithms, and regression algorithms.

You can interact with `iLearner` only in Studio (classic), or in one of the supported APIs.

Studio (classic) uses this interface for the following functionality:

+ Determines whether a model has the correct format.
+ Gets the capabilities of the learner. These are any general properties of the learner that are not captured by the type signature of the specific learner.
+ Gets or sets the settings of the learner.The settings are unique to each learner and must be configured once before any query methods can be called on the learner.

For a list of learners provided by Machine Learning Studio (classic), see [Initialize Model](machine-learning-initialize-model.md).  

> [!NOTE]
> The [ICluster interface](icluster-interface.md) is also available, for clustering models only.

## See also  
 [Module data types](machine-learning-module-data-types.md)
