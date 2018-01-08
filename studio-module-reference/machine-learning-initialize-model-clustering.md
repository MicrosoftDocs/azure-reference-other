---
title: "Machine Learning - Initialize Model - Clustering | Microsoft Docs"
ms.custom: ""
ms.date: 10/05/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 2b08f216-51b2-4b1c-b4f2-6f9dd1986936
caps.latest.revision: 11
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Machine Learning - Initialize Model - Clustering

  This article introduces the clustering algorithms provided in Azure Machine Learning Studio. 
 
## What is Clustering?

Clustering, in machine learning, is a method of grouping data points into similar clusters. It is also called segmentation. 

Over the years, many clustering algorithms have been developed, but all such algorithms use *features* to find similar items. For example, clustering can be applied in text analysis to group pieces of text that contain common words, where the words are the features.  

Clustering can also be applied to data without any labels or indeed any preconceptions of how the data might be related, to discover new patterns. Hence clustering is often used for exploration of data prior to analysis with other more predictive algorithms. 

A clustering algorithm can be used with either labeled or unlabeled data. 

+ With unlabeled data, the clustering algorithm determines which data points are closest together, and creates clusters around a central point, or centroid. YOu can then use the cluster ID as a sort of temporary label for the group of data.

+ If the data has labels, you can use the label to drive the number of clusters, or use the label as just another feature.

After you have configured the clustering algorithm, you train it on data by using either the [Train Clustering Model](train-clustering-model.md) or [Sweep Clustering](sweep-clustering.md) modules. 

When the model is trained, use if to predict cluster membership for new data points. For example, if you have used clustering to group customers by purchasing behavior, you can use the model to predict the purchasing behavior of new customers.  

## Additional resources
  
 Wondering which algorithm you need for a task? See these topics:  
  
-   [Machine learning algorithm cheat sheet for Azure ML](https://azure.microsoft.com/en-us/documentation/articles/machine-learning-algorithm-cheat-sheet/)  
  
     Provides a graphical decision chart to guide you through the selection process  
  
-   [How to choose Azure Machine Learning algorithms for clustering, classification, or regression](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-choice/)  
  
     Explains in greater detail the different types of machine learning algorithms and how they're used  
  
##  <a name="modules"></a> List of Modules  
 The category for Initialize/Clustering includes the following modules:  
  
|Module|Description|  
|------------|-----------------|  
|[K-Means Clustering](k-means-clustering.md)|Configures and initializes a K-means clustering model|  
  
### Related Tasks

To use a different clustering algorithm, or create  custom clustering model using R, see these topics:  
  
-   [Execute R Script](execute-r-script.md)  
  
-   [Create R Model](create-r-model.md)  
  
## See Also  
 [Regression](machine-learning-initialize-model-regression.md)   
 [Classification](machine-learning-initialize-model-classification.md)    
 [Text Analytics](text-analytics.md)   
 [Image classification using OpenCV](opencv-library-modules.md)