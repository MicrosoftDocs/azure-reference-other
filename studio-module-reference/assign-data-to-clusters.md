---
title: "ML Studio (classic): Assign Data to Clusters - Azure"
description: Learn how to use the Assign Data to Clusters module to generate predictions using a clustering model that was trained using the K-Means clustering module.

ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs 
manager: cgronlun
---
# Assign Data to Clusters

*Assigns data to clusters using an existing trained clustering model*  

Category: [Score](machine-learning-score.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview  

This article describes how to use the [Assign Data to Clusters](assign-data-to-clusters.md) module in Machine Learning Studio (classic), to generate predictions using a clustering model that was trained using the K-Means clustering algorithm.

The module returns a dataset that contains the probable assignments for each new data point. It also creates a PCA (Principal Component Analysis) graph to help you visualize the dimensionality of the clusters.

> [!WARNING]
> This module replaces the Assign to Clusters (deprecated) module, which is available only for support of older experiments.

## How to use Assign Data to Clusters
  
1.  In Machine Learning Studio (classic), locate a previously trained clustering model. You can create and train a clustering model by using either of these methods:  
  
    - Configure the K-means algorithm using the [K-Means Clustering](k-means-clustering.md) module, and then train the model using a dataset and the [Train Clustering Model](train-clustering-model.md) module.  
  
    - Configure a range of options for the K-means algorithm using [K-Means Clustering](k-means-clustering.md) and then train the model using the [Sweep Clustering](sweep-clustering.md) module.
  
    You can also add an existing trained clustering model from the **Saved Models** group in your workspace.

2. Attach the trained model to the left input port of [Assign Data to Clusters](assign-data-to-clusters.md).  

3. Attach a new dataset as input. In this dataset, labels are optional. Generally, clustering is an unsupervised learning method so it is not expected that you will know categories in advance.

    However, the input columns must be the same as the columns that were used in training the clustering model, or an error occurs.

    > [!TIP]
    > To reduce the number of columns output from cluster predictions, use [Select Columns in Dataset](select-columns-in-dataset.md), and select a subset of the columns. 
    
4. Leave the option **Check for Append or Uncheck for Result Only** selected if you want the results to contain the full input dataset, together with a column indicating the results (cluster assignments).
  
    If you deselect this option, you get back just the results. This might be useful when creating predictions as part of a web service.
  
5.  Run the experiment.  
  
### Results

The [Assign Data to Clusters](assign-data-to-clusters.md) module returns two types of results on the **Results dataset** output:
  
+ To see the separation of clusters in the model, click the output of the module and select **Visualize**

    This command displays a Principal Component Analysis (PCA) graph that maps the collection of values in each cluster to two component axes.
    
    + The first component axis is the combined set of features that captures the most variance in the model. It  is plotted on the x-axis (**Principal Component 1**). 
    + The next component axis represents some combined set of features  that is orthogonal to the first component and that adds the next most information to the chart. It is plotted on the y-axis (**Principal Component 2**). 

    From the graph, you can see the separation between the clusters, and how the clusters are distributed along the axes that represent the principal components.
  
+ To view the table of results for each case in the input data, attach the [Convert to Dataset](convert-to-dataset.md) module, and visualize the results in  Studio (classic).  
  
    This dataset contains the *cluster assignments* for each case, and a distance metric that gives you some indication of how close this particular case is to the center of the cluster.  
  
    |Output column name|Description|  
    |------------------------|-----------------|  
    |Assignments|A 0-based index that indicates which cluster the data point was assigned to.|  
    |DistancesToClusterCenter no. *n*|For each data point, this value indicates the distance from the data point to the center of the assigned cluster, and the distance to other clusters.<br /><br /> The metric used to calculate distance is determined when you configure the K-means clustering model.|  
  
## Expected inputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ICluster interface](icluster-interface.md)|Trained clustering model|  
|Dataset|[Data Table](data-table.md)|Input data source|  
  
## Module parameters  

|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Append or Result Only|||Required|TRUE|Indicate whether the output dataset should contain the input dataset as well as the results, or the results only|  
|Specify parameter sweeping mode|Sweep Methods|List:Entire grid&#124;Random sweep|Required|Random sweep|Sweep entire grid on parameter space, or sweep with using a limited number of sample runs|  
  
## Outputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Input dataset appended by data column of assignments or assignments column only|  

## Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
  
## See also

 [K-Means Clustering](k-means-clustering.md)   
 [Score](machine-learning-score.md)   
