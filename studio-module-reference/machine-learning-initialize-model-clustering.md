---
title: 'ML Studio (classic): Initialize Clustering Models - Azure'
description: Description of the modules in Machine Learning Studio (classic) that support creation of clustering models.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
---
# Clustering modules

This article describes the modules in Machine Learning Studio (classic) that support creation of clustering models. 



[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## What is clustering?

Clustering, in machine learning, is a method of grouping data points into similar clusters. It is also called _segmentation_. 

Over the years, many clustering algorithms have been developed. Almost all clustering algorithms use the features of individual items to find similar items. For example, you might apply clustering to find similar people by demographics. You might use clustering with text analysis to group sentences with similar topics or sentiment.  

Clustering is called a non-supervised learning technique because it can be used in unlabeled data. Indeed, clustering is a useful first step for discovering new patterns, and requires little prior knowledge about how the data might be structured or how items are related. Clustering is often used for exploration of data prior to analysis with other more predictive algorithms. 

### How to create a clustering model

In Machine Learning Studio (classic), you can use clustering with either labeled or unlabeled data. 

+ In unlabeled data, the clustering algorithm determines which data points are closest together, and creates clusters around a central point, or centroid. You can then use the cluster ID as a temporary label for the group of data.

+ If the data has labels, you can use the label to drive the number of clusters, or use the label as just another feature.

After you have configured the clustering algorithm, you train it on data by using either the [Train Clustering Model](train-clustering-model.md) or [Sweep Clustering](sweep-clustering.md) modules. 

When the model is trained, use it to predict cluster membership for new data points. For example, if you have used clustering to group customers by purchasing behavior, you can use the model to predict the purchasing behavior of new customers.
  
##  List of modules  

The clustering category includes this module:

+ [K-Means Clustering](k-means-clustering.md): Configures and initializes a K-means clustering model.  

### Related tasks

To use a different clustering algorithm, or create a custom clustering model by using R, see these topics:  
  
-   [Execute R Script](execute-r-script.md)  
  
-   [Create R Model](create-r-model.md)  

## Examples

For examples of clustering in action, see the [Azure AI Gallery](https://gallery.azure.ai/).

See these articles for help choosing an algorithm:  

-   [Machine learning algorithm cheat sheet for Machine Learning Studio (classic)](/azure/machine-learning/studio/algorithm-cheat-sheet)  
  
     Provides a graphical decision chart to guide you through the selection process.  
  
-   [How to choose Machine Learning algorithms for clustering, classification, or regression](/azure/machine-learning/studio/algorithm-choice)  
  
     Explains in greater detail the different types of machine learning algorithms, and how they're used.  

## See also  
- [Regression](machine-learning-initialize-model-regression.md)   
- [Classification](machine-learning-initialize-model-classification.md)    
- [Text Analytics](text-analytics.md)   
- [Image classification using OpenCV](opencv-library-modules.md)
