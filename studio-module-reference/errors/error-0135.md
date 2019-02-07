---
title: "Error 0135 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0135  
 Only centroid-based cluster is supported.  
  
## Resolution  
 You might encounter this error message if you have attempted to evaluate a clustering model that is based on a custom clustering algorithm that does not use centroids to initialize the cluster.  
  
 You can use [Evaluate Model](../evaluate-model.md) to evaluate clustering models that are based on the  [K-Means Clustering](../k-means-clustering.md) module. For custom algorithms, use the [Execute R Script](../execute-r-script.md) module to create a custom evaluation script.  
  
|Exception Messages|  
|------------------------|  
|Only centroid-based cluster is supported.|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
