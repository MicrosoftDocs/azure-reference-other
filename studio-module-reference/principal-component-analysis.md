---
title: "ML Studio (classic): Principal Component Analysis - Azure"
description: Learn how to use the Principal Component Analysis module to reduce the dimensionality of your training data.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Principal Component Analysis

*Computes a set of features with reduced dimensionality for more efficient learning*

Category: [Data Transformation / Sample and Split](data-transformation-sample-and-split.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Principal Component Analysis** module in Machine Learning Studio (classic) to reduce the dimensionality of your training data. The module analyzes your data and creates a reduced feature set that captures all the information contained in the dataset, but in a smaller number of features.

The module also creates a transformation that you can apply to new data, to achieve a similar reduction in dimensionality and compression of features, without requiring additional training.

### More about Principal Component Analysis

Principal Component Analysis (PCA) is a popular technique in machine learning. It relies on the fact that many types of vector-space data are compressible, and that compression can be most efficiently achieved by sampling.

Added benefits of PCA are improved data visualization, and optimization of resource use by the learning algorithm.

The **Principal Component Analysis** module in Machine Learning Studio (classic) takes a set of feature columns in the provided dataset, and creates a projection of the feature space that has lower dimensionality. The algorithm uses randomization techniques to identify a feature subspace that captures most of the information in the complete feature matrix. Hence, the transformed data matrices capture the variance in the original data while reducing the effect of noise and minimizing the risk of overfitting.

For general information about principal component analysis (PCA) see this [Wikipedia article](https://wikipedia.org/wiki/Principal_component_analysis). For information about the PCA approaches used in this module, see these articles:

- [Finding Structure with Randomness: Probabilistic Algorithms for Constructing Approximate Matrix Decompositions](https://arxiv.org/abs/0909.4061). Halko, Martinsson, and Tropp, 2010.  

- [Combining Structured and Unstructured Randomness in Large Scale PCA](https://arxiv.org/abs/1310.6304)Combining Structured and Unstructured Randomness in Large Scale PCA. Karampatziakis and Mineiro, 2013.

## How to configure Principal Component Analysis

1. Add the **Principal Component Analysis** module to your experiment. You can find it in under **Data Transformation**, in the **Scale and Reduce** category.

2. Connect the dataset you want to transform, and  choose the feature columns to analyze.

    If it is not already clear which columns are features and which are labels, we recommend that you use the [Edit Metadata](edit-metadata.md) module to mark the columns in advance.

3. **Number of dimensions to reduce to**: Type the desired number of columns in the final output. Each column represents a dimension capturing some part of the information in the input columns.

    For example, if the source dataset has eight columns and you type `3`, three new columns are returned that capture the information of the eight selected columns. The columns are named `Col1`, `Col2`, and `Col3`. These columns do not map directly to the source columns; instead, the columns contain an approximation of the feature space described by the original columns 1-8.

    > [!TIP]
    > The algorithm functions optimally when the number of reduced dimensions is much smaller than the original dimensions.

4. **Normalize dense dataset to zero mean**: Select this option if the dataset is dense, meaning it contains few missing values. If selected, the module normalizes the values in the columns to a mean of zero before any other processing.

    For sparse datasets, this option should not be selected. If a sparse dataset is detected, the parameter is overridden.

5. Run the experiment.

### Results

The module outputs a reduced set of columns that you can use in creating a model. You can save the output as a new dataset or use it in your experiment.

Optionally, you can save the analysis process as a saved transform, to apply to another dataset using [Apply Transformation](apply-transformation.md). 

The dataset you apply the transformation to must have the same schema as the original dataset.

## Examples

For examples of how Principal Component Analysis is used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/):  

- [Clustering: Find Similar Companies](https://go.microsoft.com/fwlink/?LinkId=525164): Uses Principal Component Analysis to reduce the number of values from text mining to a manageable number of features.

    Although in this sample PCA is applied using a custom R script, it illustrates how PCA is typically used.

## Technical notes

There are two stages to computation of the lower-dimensional components. 

- The first is to construct a low-dimensional subspace that captures the action of the matrix.
- The second is to restrict the matrix to the subspace and then compute a standard factorization of the reduced matrix.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Dataset whose dimensions are to be reduced|  

## Module parameters

|Name|Type|Range|Optional|Description|Default|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Selected columns|ColumnSelection||Required||Selected columns to apply PCA to|  
|Number of dimensions to reduce to|Integer|>=1|Required||The number of desired dimensions in the reduced dataset|  
|Normalize dense dataset to zero mean|Boolean||Required|true|Indicate whether the input columns will be mean normalized for dense datasets (for sparse data parameter is ignored)|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with reduced dimensions|  
|PCA Transformation|[ITransform interface](itransform-interface.md)|Transformation which when applied to dataset will give new dataset with reduced dimensions|  

## Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](errors/error-0004.md)|Exception occurs if parameter is less than or equal to specific value.| 

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).
## See also

 [Sample and Split](data-transformation-sample-and-split.md)   
 [Feature Selection](feature-selection-modules.md)
