---
title: "Principal Component Analysis | Microsoft Docs"
ms.custom: ""
ms.date: 04/11/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8be18eb5-ddd8-4d12-8573-7ae10d5f72fb
caps.latest.revision: 13
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Principal Component Analysis
*Computes a set of features with reduced dimensionality for more efficient learning*  
  
 Category: [Data Transformation / Sample and Split](data-transformation-sample-and-split.md)  
  
## Module Overview  
 You can use the **Principal Component Analysis** module to analyze your data and create a reduced feature set that captures all the information contained in the larger dataset.  
  
 The module also creates a transformation that you can apply to new data, to achieve a similar reduction in dimensionality and compression of features, without requiring additional training.  
  
### Understanding Principal Component Analysis  
 Principal Component Analysis is based on the fact that many types of vector-space data are compressible, and that compression can be most efficiently achieved by sampling. As such, Principal Component Analysis (PCA) is a popular technique in machine learning for dimensionality reduction. Added benefits are that PCA can improve data visualization and optimize resource utilization by the learning algorithm.  
  
 The **Principal Component Analysis** module transforms a set of feature columns in the provided dataset into a projection of the feature space that has lower dimensionality. By definition, the transformed data matrices capture the variance in the original data while reducing the effect of noise and minimizing the risk of overfitting. The algorithm uses randomization techniques to identify a feature subspace that captures most of the information in the complete feature matrix.  
  
 For general information about principal component analysis (PCA) see this [Wikipedia article](https://wikipedia.org/wiki/Principal_component_analysis). For information about the PCA approaches used in this module, see these articles:  
  
-   [Finding Structure with Randomness: Probabilistic Algorithms for Constructing Approximate Matrix Decompositions](http://arxiv.org/abs/0909.4061). Halko, Martinsson, and Tropp, 2010.  
  
-   [Combining Structured and Unstructured Randomness in Large Scale PCA](http://arxiv.org/abs/1310.6304)Combining Structured and Unstructured Randomness in Large Scale PCA. Karampatziakis and Mineiro, 2013.  
  
## How to Configure Principal Component Analysis  
  
1.  Add the dataset you want to analyze, and connect it to the input of the module.  
  
     If it is not already clear which columns are features and which are labels, we recommend that you use the [Edit Metadata](edit-metadata.md) module to mark the columns in advance.  
  
2.  Use the Column Selector to choose the columns you want to evaluate.  
  
3.  In **Number of dimensions to reduce to**, type a number to specify how many columns to include in the output dataset. Each column represents a dimension capturing some part of the information in the input columns.  
  
    > [!TIP]
    >  The algorithm used for this module is optimized when the number of reduced dimensions is much smaller than the original dimensions.  
  
     For example, if the source dataset has eight columns and you type `3`, three new columns will be returned that capture the information of the eight selected columns.  
  
     In that case, the columns would be named Col1, Col2, and Col3, and should be considered an approximation of the contents of columns 1-8, rather than being directly derived from particular source columns.  
  
4.  Select the **Normalize dense dataset to zero mean** option if the dataset is dense (contains few missing values) and you want to normalize the values in the columns to a mean of zero before further processing.  
  
     For sparse datasets, the parameter is overridden if selected.  
  
5.  Run the experiment.  
  
6.  The module outputs a reduced set of columns that you can use in creating a model. You can save the output as a new dataset or use it in your experiment.  
  
7.  Optionally, you can save the analysis process as a saved transform, to apply to another dataset using [Apply Transformation](apply-transformation.md). Note that the dataset you apply the transformation to must have the same schema as the original dataset.  
  
## Examples  
 For examples of how Principal Component Analysis is used in machine learning, see these experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Clustering: Find Similar Companies](http://go.microsoft.com/fwlink/?LinkId=525164) sample uses Principal Component Analysis to reduce the number of values from text mining to a manageable number of features.  
  
     Although in this sample PCA is applied using a custom R script, it illustrates how PCA is typically used.  
  
## Technical Notes  
 There are two stages to computation of the lower-dimensional components. The first is to construct a low-dimensional subspace that captures the action of the matrix. The second is to restrict the matrix to the subspace and then compute a standard factorization of the reduced matrix.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Dataset whose dimensions are to be reduced|  
  
##  <a name="parameters"></a> Module Parameters  
  
###  
  
|Name|Type|Range|Optional|Description|Default|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Selected columns|ColumnSelection||Required||Selected columns to apply PCA to|  
|Number of dimensions to reduce to|Integer|>=1|Required||The number of desired dimensions in the reduced dataset|  
|Normalize dense dataset to zero mean|Boolean||Required|true|Indicate whether the input columns will be mean normalized for dense datasets (for sparse data parameter is ignored)|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with reduced dimensions|  
|PCA Transformation|[ITransform interface](itransform-interface.md)|Transformation which when applied to dataset will give new dataset with reduced dimensions|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all exceptions, see [Machine Learning REST API Error Codes](http://msdn.microsoft.com/library/0eccb2eb-27a1-407e-88a9-2092dba847e0).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](errors/error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
  
## See Also  
 [Sample and Split](data-transformation-sample-and-split.md)   
 [Feature Selection](feature-selection-modules.md)