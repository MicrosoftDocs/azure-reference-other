---
title: "Assign to Clusters (deprecated) | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/16/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: eed3ee76-e8aa-46e6-907c-9ca767f5c114
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Assign to Clusters (deprecated)

*Assigns data to clusters using an existing trained clustering model*  
  
 Category: [Deprecated Modules and Features](deprecated-modules-and-features.md)  

## Module overview  

This article describes how to use the **Assign to Clusters** module in Azure Machine Learning Studio, to generate predictions using a trained clustering model, based on the K-Means clustering algorithm included in Studio.

The module returns the probable assignment for each new data point, based on the trained model.  

> [!NOTE]
>  This module has been deprecated, and is available solely for compatibility with existing experiments. For new and updated experiments, we recommend that you use [Assign Data to Clusters](assign-data-to-clusters.md).

## How to use Assign to Clusters  

Use of this module requires that you have already configured a clustering model in Studio using the [K-Means Clustering](k-means-clustering.md) module.
  
1. Add the **Assign to Clusters** module to your experiment, and attach the trained model to the left input port.
  
2.  Provide an unlabeled data set as input.  
  
     By default, all columns that are used in the input dataset are returned in the results. If you want to use fewer columns when creating cluster predictions, use [Select Columns in Dataset](select-columns-in-dataset.md) to select a subset of the columns.  
  
     However, an error occurs if the dataset provided as input to the **Assign to Clusters** module doesn't contain **all** columns that were used in training the clustering model.  

3. For **Column set**, open the column selector and choose the columns that should be used as input to the trained clustering model.
  
    If the original models used eight feature columns to cluster cases, you must provide those same eight columns as input to **Assign to Clusters**.  
  
4. Leave the **Check for Append or Uncheck for Result Only** option selected if you want to add the cluster assignments to the input dataset.

    Deselect this option if you want just the results (cluster assignments).  This is the likely option when running in a web service.
  
5.  Run the experiment.  

### Results

The **Assign to Clusters** module returns the *cluster assignments* for each case, in the **Assignments** column appended at the right-hand side of the dataset.

If you do not want all the columns in the results, change the output option to get only the results. For example, when making predictions as part of a web service you might want to return only the predicted assignment.

The following table shows the typical results of **Assign to Clusters**. 

In this example, K-means clustering was used to group people in the **Adult Census** dataset, using these columns: `workclass`, `education`, `occupation`, `sex`. The **Assign to Clusters** module was used to predict the census group for a new person, based on these attributes.

|Age|Workclass|Education|Assignments|  
|---------|---------------|---------------|-----------------|  
|54|Federal-gov|HS-grad|0|  
|43|State-gov|Assoc-voc|1|  
|21||HS-grad||  
|28|Self-emp-not-inc|Bachelors|0|  

> [!IMPORTANT]
> If there are missing values in any attribute that was used to train the model (such as the preceding case where the workclass value is missing), a cluster assignment is not returned.

## Examples  
  
Because this module has been deprecated, there are no examples of this module in the [Azure AI Gallery](https://gallery.cortanaintelligence.com/).  

To see examples of updated clustering models, see these experiments:
  
- [Color quantization](http://go.microsoft.com/fwlink/?LinkId=525272): Uses clustering to group images by color patterns to reduce the number of bits needed to represent each image.  
  
- [Clustering: Similar Companies](http://go.microsoft.com/fwlink/?LinkId=525164): Uses clustering with text extracted from Wikipedia description to find companies in predefined categories.  
  
##  Technical notes

-   If any column names are duplicated when the new column is appended to the dataset, a numeric suffix is added to the name of the new column.  

- The clusters created by the model are 0-based numeric labels. These labels cannot be edited in Azure Machine Learning Studio.

## Expected inputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ICluster interface](icluster-interface.md)|Trained clustering model|  
|Dataset|[Data Table](data-table.md)|Input data source|  
  
## Module parameters  

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Column Set|Any|ColumnSelection||Select the columns from the input dataset to map to the clustering model.|  
|Check for Append or Uncheck for Result Only|Any|Boolean|true|Deselect this option if you want to output only the results (cluster assignments).<br /><br /> By default, the column containing the clustering results is appended to the columns of the input dataset .|  
  
## Outputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|A dataset containing either the results of clustering only, or the input dataset with the assignments column appended|  
  
## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

For a list of errors specific to Studio modules, see [Machine Learning Error codes](\errors\machine-learning-module-error-codes.md)

For a list of API exceptions, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes). 

## See also
 
 [K-Means Clustering](k-means-clustering.md)   
 [Score Model](score-model.md)   
 [Score](machine-learning-score.md)   
 [A-Z Module List](a-z-module-list.md)   
 [Assign Data to Clusters](assign-data-to-clusters.md)