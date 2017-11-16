---
title: "Train Clustering Model | Microsoft Docs"
ms.custom: ""
ms.date: 10/06/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bb43c744-f7fa-41d0-ae67-74ae75da3ffd
caps.latest.revision: 14
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlun"
---
# Train Clustering Model
*Trains a clustering model and assigns data from the training set to clusters*  
  
 Category: [Machine Learning / Train](machine-learning-train.md)  
  
##  <a name="Remarks"></a> Module Overview  

This article describes how to use the **Train Clustering Model** module in Azure Machine Learning Studio to train a clustering model.

The module takes an untrained clustering model that you have already configured using the [K-Means Clustering](k-means-clustering.md) module, and trains the model using a labeled or unlabeled data set. The module creates both a trained model that you can use for prediction, and a set of cluster assignments for each case in the training data.  
  
> [!NOTE]
> A clustering model cannnot be trained using the [Train Model](train-model.md) module, which is the generic module for creating machine learning models. That is because [Train Model](train-model.md) works only with supervised learning algorithms. A supervised learning model requires labeled data to train from. 
> 
> In contrast, K-means and other clustering algorithms allow unsupervised learning, meaning that you can let the algorithm learn from new data without necessarily providing it with examples.  
  
## How to Train a Clustering Model  
  
1.  Add the **Train Clustering Model** module to the experiment. You can find the module in Azure Machine Learning Studio, in the [Machine Learning Modules](machine-learning-modules.md) category, under [Train](machine-learning-train.md).  
  
2.  To the left input, connect the [K-Means Clustering](k-means-clustering.md) module, or another custom module that creates a compatible clustering model.  
  
3.  Configure the clustering model.  
  
4.  Attach a training dataset to the right-hand input of **Train Clustering Model**.  
  
5.  In **Column Set**, select the columns from the dataset to use in building clusters. The columns you select should be good features -- avoid using IDs or other columns that have unique values, or columns that have all the same values.

    If a label is available, you can use it as a feature, or leave it out.  
  
6.  **Check for Append or Uncheck for Result Only**:  When this option is selected, the module outputs the training data together with the new cluster label.

    When you deselect this option, only the cluster label is output.

7. Run the experiment, or click the **Train Clustering Model** module and select **Run Selected**.  
  
### Results

+ To view the cluster and their separation in a graph, right-click the **Results dataset** output and select **Visualize**.   

    The graph represents the principal components of the cluster, rather than th eactual values. See [Principal Component Analysis](principal-component-analysis.md) for more information. 
  
+  To view the values in the dataset, add an instance of the [Convert to Dataset](convert-to-dataset.md) module, and connect it to the **Results dataset** output. Run the [Convert to Dataset](convert-to-dataset.md) module to get a copy of the data that you can view or download.

+ To save the trained model for later re-use, right-click the module, select **Trained model**, and click **Save As Trained Model**.

+ To generate scores from the model, use [Assign Data to Clusters](assign-data-to-clusters.md).
  
## Examples  

For an example of how clustering is used in machine learning, see these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Clustering: Find similar Companies](http://go.microsoft.com/fwlink/?LinkId=525164) sample demonstrates how to use clustering on attributes derived from unstructured text.  
  
-   The [Clustering: Color quantization](http://go.microsoft.com/fwlink/?LinkId=525272) sample demonstrates how to use clustering to find related colors and reduce the number of bits used in images.  
  
-   The [Clustering: Group iris data](http://go.microsoft.com/fwlink/?LinkId=526317) sample provides a simple example of clustering based on the iris dataset.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ICluster interface](icluster-interface.md)|Untrained clustering model|  
|Dataset|[Data Table](data-table.md)|Input data source|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Column Set|any|ColumnSelection||Column selection pattern|  
|Check for Append or Uncheck for Result Only|any|Boolean|true|Whether output dataset must contain input dataset appended by assignments column (Checked) or assignments column only (Unchecked)|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ICluster interface](icluster-interface.md)|Trained clustering model|  
|Results dataset|[Data Table](data-table.md)|Input dataset appended by data column of assignments or assignments column only|  
  
##  <a name="exceptions"></a> Exceptions  
 For a complete list of module errors, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
  
## See Also  
 [A-Z Module List](a-z-module-list.md)   
 [Train](machine-learning-train.md)   
 [Assign Data to Clusters](assign-data-to-clusters.md)   
 [K-Means Clustering](k-means-clustering.md)