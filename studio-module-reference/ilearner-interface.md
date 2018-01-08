---
title: "ILearner interface | Microsoft Docs"
ms.custom: ""
ms.date: 06/08/2015
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 48eafe8c-2236-4582-aac9-96a533cc0034
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# ILearner interface
**ILearner interface**  
  
 The `ILearner` interface provides methods and properties that are used to configure and interact with machine learning models. A learner is defined as a set of instructions that perform standardized machine learning tasks. Learners include classification algorithms, clustering algorithms, and regression algorithms.  
  
 For a list of learners provided by Azure Machine Learning, see [Initialize Model](machine-learning-initialize-model.md).  
  
 This interface encapsulates the following functionality:  
  
-   Gets the capabilities of the learner.  These are any general properties of the learner that are not captured by the type signature of the specific learner.  
  
-   Gets or sets the settings of the learner.  The settings are unique to each learner and must be configured once before any query methods can be called on the learner.  
  
##  <a name="also"></a> See Also  
 Reference Machine Learning Studio types  
  
|Type|Description|  
|----------|-----------------|  
|[ICluster interface](icluster-interface.md)|ICluster interface|  
  
## See Also  
 [A-Z Module List](a-z-module-list.md)   
 [Module Parameter Types](machine-learning-module-parameter-types.md)   
 [Module Data Types](machine-learning-module-data-types.md)