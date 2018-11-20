---
title: "Train Clustering Model | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/17/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bb43c744-f7fa-41d0-ae67-74ae75da3ffd
caps.latest.revision: 14
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Train Clustering Model
*Trains a clustering model and assigns data from the training set to clusters*  
  
 Category: [Machine Learning / Train](machine-learning-train.md)  
  
## Module overview  

This article describes how to use the **Train Clustering Model** module in Azure Machine Learning Studio, to train a clustering model.

The module takes an untrained clustering model that you have already configured using the [K-Means Clustering](k-means-clustering.md) module, and trains the model using a labeled or unlabeled data set. The module creates both a trained model that you can use for prediction, and a set of cluster assignments for each case in the training data.

> [!NOTE]
> A clustering model cannnot be trained using the [Train Model](train-model.md) module, which is the generic module for creating machine learning models. That is because [Train Model](train-model.md) works only with supervised learning algorithms. K-means and other clustering algorithms allow unsupervised learning, meaning that the algorithm can learn from unlabeled data.  
  
## How to use Train Clustering Model  
  
1.  Add the **Train Clustering Model** module to your experiment in Studio. You can find the module under [Machine Learning Modules](machine-learning-modules.md), in the [Train](machine-learning-train.md) category.  
  
2. Add the [K-Means Clustering](k-means-clustering.md) module, or another custom module that creates a compatible clustering model, and set the parameters of the clustering model.  
    
3.  Attach a training dataset to the right-hand input of **Train Clustering Model**.
  
5.  In **Column Set**, select the columns from the dataset to use in building clusters. Be sure to select columns that make good features: for example, avoid using IDs or other columns that have unique values, or columns that have all the same values.

    If a label is available, you can either use it as a feature, or leave it out.  
  
6. Select the option, **Check for Append or Uncheck for Result Only**, if you want to output the training data together with the new cluster label.

    If you deselect this option, only the cluster assignments are output. 

7. Run the experiment, or click the **Train Clustering Model** module and select **Run Selected**.  
  
### Results

After training has completed:

+ To view the cluster and their separation in a graph, right-click the **Results dataset** output and select **Visualize**.   

    The graph represents the principal components of the cluster, rather than the actual values. See [Principal Component Analysis](principal-component-analysis.md) for more information. 
  
+  To view the values in the dataset, add an instance of the [Convert to Dataset](convert-to-dataset.md) module, and connect it to the **Results dataset** output. Run the [Convert to Dataset](convert-to-dataset.md) module to get a copy of the data that you can view or download.

+ To save the trained model for later re-use, right-click the module, select **Trained model**, and click **Save As Trained Model**.

+ To generate scores from the model, use [Assign Data to Clusters](assign-data-to-clusters.md).

## Examples  

For an example of how clustering is used in machine learning, see the [Azure AI Gallery](https://gallery.cortanaintelligence.com/):  
  
- [Clustering: Find similar Companies](http://go.microsoft.com/fwlink/?LinkId=525164): Demonstrates how to use clustering on attributes derived from unstructured text.  
  
- [Clustering: Color quantization](http://go.microsoft.com/fwlink/?LinkId=525272): Demonstrates how to use clustering to find related colors and reduce the number of bits used in images.
  
- [Clustering: Group iris data](http://go.microsoft.com/fwlink/?LinkId=526317): Provides a simple example of clustering based on the iris dataset.  
  
##  Expected inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ICluster interface](icluster-interface.md)|Untrained clustering model|  
|Dataset|[Data Table](data-table.md)|Input data source|  
  
##  Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Column Set|any|ColumnSelection||Column selection pattern|  
|Check for Append or Uncheck for Result Only|any|Boolean|true|Whether output dataset must contain input dataset appended by assignments column (Checked) or assignments column only (Unchecked)|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ICluster interface](icluster-interface.md)|Trained clustering model|  
|Results dataset|[Data Table](data-table.md)|Input dataset appended by data column of assignments or assignments column only|  
  
##  Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

For a list of errors specific to Studio modules, see [Machine Learning Error codes](\errors\machine-learning-module-error-codes.md)

For a list of API exceptions, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes). 

## See also  
 [A-Z Module List](a-z-module-list.md)   
 [Train](machine-learning-train.md)   
 [Assign Data to Clusters](assign-data-to-clusters.md)   
 [K-Means Clustering](k-means-clustering.md)