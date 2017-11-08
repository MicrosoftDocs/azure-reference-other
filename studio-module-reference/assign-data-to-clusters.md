---
title: "Assign Data to Clusters | Microsoft Docs"
ms.custom: ""
ms.date: 06/27/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 20a0683a-07f9-4a08-a89b-44b3bbaae382
caps.latest.revision: 13
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Assign Data to Clusters
*Assigns data to clusters using an existing trained clustering model*  
  
 Category: [Score](machine-learning-score.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the [Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md) module to generate predictions using a trained clustering model, based on the K-Means clustering algorithm included in Azure Machine Learning.  
  
 The module returns a dataset that contains the probable assignments for each new data point. It also creates a PCA graph to help you visualize the dimensionality of the clusters.  
  
> [!WARNING]
>  This module replaces the [Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md) module, which is still available for support of older experiments.  
  
## How to Use [Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md)  
  
1.  Your workspace should contain a trained clustering model. You can create and train a clustering model by using either of these methods:  
  
    -   Configure the K-means algorithm using the [K-Means Clustering](k-means-clustering.md) module, and then train the model using a dataset and the [Train Clustering Model](train-clustering-model.md) module.  
  
    -   Configure a range of options for the K-means algorithm using [K-Means Clustering](k-means-clustering.md) and then train the model using the [Sweep Clustering](sweep-clustering.md) module.  
  
    -   Add an existing trained clustering model from the **Saved Models** group in your workspace.  
  
2.  Attach the trained model to the left input port of [Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md).  
  
3.  Attach a new dataset as input.  
  
     Labels are optional in the dataset. Generally, clustering is an unsupervised learning method so it is not expected that you will know categories in advance.  
  
     By default, all columns in the input dataset are returned in the results. If you want to use fewer columns when creating cluster predictions, use [Select Columns in Dataset](select-columns-in-dataset.md) to select a subset of the columns. However, the input columns must be the same as the columns that were used in training the clustering model, or an error will occur.  
  
4.  Leave the option **Check for Append or Uncheck for Result Only** selected if you want the results to contain the full input dataset, together with a column indicating the results (cluster assignments).  
  
     If you deselect this option, you get back just the results. This might be useful when creating predictions as part of a web service.  
  
5.  Run the experiment.  
  
6.  The [Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md) module returns two types of results on the **Results dataset** output:  
  
    -   Click the output of the module and select **Visualize** to view a *PCA graph* or *Principal Components Graph*.  
  
         In a PCA graph, the collection of values in each cluster is mapped to two component axes: the first component axis is the combined set of features that captures the most variance in the model, and is plotted on the x-axis (**Principal Component 1**). The next component axis represents some combined set of features  that is orthogonal to the first component and that adds the next most information to the chart, plotted on the y-axis (**Principal Component 2**). From this graph, you can see the maximum separation that can be attained between the clusters, and how all clusters are distributed along the axes that represent the principal distinguishing components.  
  
    -   To view the table of results for each case in the input data, you can attach the [Convert to Dataset](convert-to-dataset.md) module to view the results in Machine Learning Studio.  
  
         The results dataset contains the *cluster assignments* for each case, and a distance metric that gives you some indication of how close this particular case is to the center of the cluster.  
  
        |Output column name|Description|  
        |------------------------|-----------------|  
        |Assignments|A 0-based index that indicates which cluster the data point was assigned to.|  
        |DistancesToClusterCenter no. *n*|For each data point, this value indicates the distance from the data point to the center of the assigned cluster, and the distance to other clusters.<br /><br /> The metric used to calculate distance is determined when you configure the K-means clustering model.|  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ICluster interface](icluster-interface.md)|Trained clustering model|  
|Dataset|[Data Table](data-table.md)|Input data source|  
  
##  <a name="parameters"></a> Module Parameters  
  
###  
  
|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Append or Result Only|||Required|TRUE|Indicate whether the output dataset should contain the input dataset as well as the results, or the results only|  
|Specify parameter sweeping mode|Sweep Methods|List:Entire grid&#124;Random sweep|Required|Random sweep|Sweep entire grid on parameter space, or sweep with using a limited number of sample runs|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Input dataset appended by data column of assignments or assignments column only|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
  
## See Also  
 [K-Means Clustering](k-means-clustering.md)   
 [Score](machine-learning-score.md)   
 [Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md)