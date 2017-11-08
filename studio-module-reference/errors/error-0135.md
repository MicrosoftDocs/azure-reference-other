---
title: "Error 0135 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0135-d185d1509344
caps.latest.revision: 7
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0135
**Error 0135**  
  
 Only centroid-based cluster is supported.  
  
## Resolution  
 You might encounter this error message if you have attempted to evaluate a clustering model that is based on a custom clustering algorithm that does not use centroids to initialize the cluster.  
  
 You can use [Evaluate Model](evaluate-model.md) to evaluate clustering models that are based on the  [K-Means Clustering](k-means-clustering.md) module. For custom algorithms, use the [Execute R Script](execute-r-script.md) module to create a custom evaluation script.  
  
|Exception Messages|  
|------------------------|  
|Only centroid-based cluster is supported.|  
  
## See Also  
 [Module Error Codes](machine-learning-module-error-codes.md)