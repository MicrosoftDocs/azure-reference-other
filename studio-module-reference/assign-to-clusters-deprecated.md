---
title: "Assign to Clusters (deprecated) | Microsoft Docs"
ms.custom: ""
ms.date: 09/17/2015
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: eed3ee76-e8aa-46e6-907c-9ca767f5c114
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Assign to Clusters (deprecated)
*Assigns data to clusters using an existing trained clustering model*  
  
 Category: [Deprecated Modules and Features](deprecated-modules-and-features.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **Assign to Clusters** module to generate predictions using a trained clustering model, based on the K-Means clustering algorithm included in Azure Machine Learning.  
  
 The module returns the probable assignment for each new data point, based on the trained model.  
  
> [!NOTE]
>  This module has been deprecated, but is available for compatibility with existing experiments. For new and updated experiments, we recommend that you use [Assign Data to Clusters](assign-data-to-clusters.md).  
  
## How to Use Assign to Clusters  
  
1.  Your workspace should contain a trained clustering model created using either the [K-Means Clustering](k-means-clustering.md) module or a custom clustering algorithm.  
  
     Attach the trained model to the left input port of  
  
2.  Provide an unlabeled data set as input.  
  
     By default, all columns that are used in the input dataset are returned in the results. If you want to use fewer columns when creating cluster predictions, use [Select Columns in Dataset](select-columns-in-dataset.md) to select a subset of the columns.  
  
     However, an error occurs if the dataset provided as input to the **Assign to Clusters** module doesn't contain **all** columns that were used in training the clustering model.  
  
3.  Run the experiment.  
  
4.  The **Assign to Clusters** module returns the *cluster assignments* for each case, in the **Assignments** column appended at the right-hand side of the dataset.  
  
     If you do not want all the columns in the results, select the option to output only the results. For example, when making predictions as part of a web service you might want to return only the ID and the predicted assignment.  
  
### Options  
 ***Column set***  
 Choose the columns from the attached dataset that will be provided as input to the trained clustering model.  
  
 If the original models used eight feature columns to cluster cases, you must provide those same eight columns as input to **Assign to Clusters**.  
  
 ***Check for Append or Uncheck for Result Only***  
 By default, this option is selected. This means that the full input dataset is returned, together with a column indicating the results (cluster assignments).  
  
 If you deselect this option, you can get back just the results, which are useful in the web service or in applications.  
  
## Examples  
  
### Gallery Samples  
 Because this module has been deprecated, there are no examples of this module in the [Model Gallery](https://gallery.cortanaintelligence.com/).  However, the following examples demonstrate how clustering models can be used in Azure Machine Learning.  
  
-   The [Color quantization](http://go.microsoft.com/fwlink/?LinkId=525272) sample uses clustering to group images by color patterns to reduce the number of bits needed to represent each image.  
  
-   The [Clustering: Similar Companies](http://go.microsoft.com/fwlink/?LinkId=525164) sample uses clustering with text extracted from Wikipedia description to find companies in predefined categories.  
  
### Sample Results  
 This table shows some typical results of **Assign to Clusters**. Here, K-means clustering was used to group people in the Adult Census dataset, using these columns: workclass, education, occupation, sex. Then we used the **Assign to Clusters** module to predict which census groups a new data point might belong to, based on similar attributes.  
  
|Age|Workclass|Education|Assignments|  
|---------|---------------|---------------|-----------------|  
|54|Federal-gov|HS-grad|0|  
|43|State-gov|Assoc-voc|1|  
|21||HS-grad||  
|28|Self-emp-not-inc|Bachelors|0|  
  
 The clusters created by the model are 0-based numeric labels. These labels cannot be edited in Azure Machine Learning Studio.  
  
 Note that if there are missing values in any attribute that was used to train the model (such as the preceding case where the workclass value is missing), a cluster assignment is not returned.
  
##  <a name="Notes"></a> Technical Notes  
  
-   If any column names are duplicated when the new column is appended to the dataset, a numeric suffix is added to the name of the new column.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ICluster interface](icluster-interface.md)|Trained clustering model|  
|Dataset|[Data Table](data-table.md)|Input data source|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Column Set|Any|ColumnSelection||Select the columns from the input dataset to map to the clustering model.|  
|Check for Append or Uncheck for Result Only|Any|Boolean|true|Deselect this option if you want to output only the results (cluster assignments).<br /><br /> By default, the column containing the clustering results is appended to the columns of the input dataset .|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|A dataset containing either the results of clustering only, or the input dataset with the assignments column appended|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all module errors, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
  
## See Also  
 [K-Means Clustering](k-means-clustering.md)   
 [Score Model](score-model.md)   
 [Score](machine-learning-score.md)   
 [A-Z Module List](a-z-module-list.md)   
 [Assign Data to Clusters](assign-data-to-clusters.md)