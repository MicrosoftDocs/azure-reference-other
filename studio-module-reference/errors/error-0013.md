---
title: "Error 0013 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 09/21/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0013-d185d1509344
caps.latest.revision: 7
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0013  
 Exception occurs if the learner passed to the module is an invalid type.  
  
 This error occurs whenever a trained model is incompatible with the connected scoring module. For example, connecting the output of [Train Matchbox Recommender](../train-matchbox-recommender.md) to [Score Model](../score-model.md) (instead of [Score Matchbox Recommender](../score-matchbox-recommender.md)) will generate this error when the experiment is run.  
  
## Resolution  

Determine the type of learner that is produced by the training module, and determine the scoring module that is appropriate for the learner. 

If the model was trained using any of the specialized training modules, connect the trained model only to the corresponding specialized scoring module. 


|Model type|Training module| Scoring module|
|----|----|----|
|any classifier|[Train Model](../train-model.md) or [Tune Model Hyperparameters](../tune-model-hyperparameters.md)|[Score Model](../score-model.md)|
|any regression model|[Train Model](../train-model.md) or [Tune Model Hyperparameters](../tune-model-hyperparameters.md)|[Score Model](../score-model.md)|
| clustering models| [Train Clustering Model](../train-clustering-model.md) or [Sweep Clustering](../sweep-clustering.md)| [Assign Data to Clusters](../assign-data-to-clusters.md)|
| anomaly detection - One-Class SVM | [Train Anomaly Detection Model](../train-anomaly-detection-model.md) |[Score Model](../score-model.md)|
| anomaly detection - PCA |[Train Model](../train-model.md) or [Tune Model Hyperparameters](../tune-model-hyperparameters.md)|[Score Model](../score-model.md) </br> Some additional steps are required to evaluate the model. |
| anomaly detection - time series|  [Time Series Anomaly Detection](../time-series-anomaly-detection.md) |Model trains from data and generates scores. The module does not create a trained learner and no additional scoring is required. |
| recommendation model| [Train Matchbox Recommender](../train-matchbox-recommender.md) | [Score Matchbox Recommender](../score-matchbox-recommender.md) |
| image classification | [Pretrained Cascade Image Classification](../pretrained-cascade-image-classification.md) | [Score Model](../score-model.md) |
|Vowpal Wabbit models| [Train Vowpal Wabbit Version 7-4 Model](../train-vowpal-wabbit-version-7-4-model.md) | [Score Vowpal Wabbit Version 7-4 Model](../score-vowpal-wabbit-version-7-4-model.md) |   
|Vowpal Wabbit models| [Train Vowpal Wabbit Version 7-10 Model](../train-vowpal-wabbit-version-7-10-model.md) | [Score Vowpal Wabbit Version 7-10 Model](../score-vowpal-wabbit-version-7-10-model.md) |
|Vowpal Wabbit models| [Train Vowpal Wabbit Version 8 Model](../score-vowpal-wabbit-version-8-model.md) | [Score Vowpal Wabbit Version 8 Model](../score-vowpal-wabbit-version-8-model.md) |
  
|Exception Messages|  
|------------------------|  
|Learner of invalid type is passed.|  
|Learner "{0}" has invalid type.|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)