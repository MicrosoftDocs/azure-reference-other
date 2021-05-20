---
title: "ML Studio (classic): Normalize Data - Azure"
description: Learn how to use the Normalize Data module to transform a dataset through *normalization*.
ms.custom: "formulas"
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Normalize Data

*Rescales numeric data to constrain dataset values to a standard range*

Category: [Data Transformation / Scale and Reduce](data-transformation-scale-and-reduce.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Normalize Data** module in Azure Machine Learning Studio (classic), to transform a dataset through *normalization*.

Normalization is a technique often applied as part of data preparation for machine learning. The goal of normalization is to change the values of numeric columns in the dataset to use a common scale, without distorting differences in the ranges of values or losing information. Normalization is also required for some algorithms to model the data correctly.

For example, assume your input dataset contains one column with values ranging from 0 to 1, and another column with values ranging from 10,000 to 100,000. The great difference in the *scale* of the numbers could cause problems when you attempt to combine the values as features during modeling.

*Normalization* avoids these problems by creating new values that maintain the general distribution and ratios in the source data, while keeping values within a scale applied across all numeric columns used in the model.

This module offers several options for transforming numeric data:

- You can change all values to a 0-1 scale, or transform the values by representing them as percentile ranks rather than absolute values.
- You can apply normalization to a single column, or to multiple columns in the same dataset.
- If you need to repeat the experiment, or apply the same normalization steps to other data, you can save the steps as a normalization transform, and apply it to other datasets that have the same schema.

> [!WARNING]
> Some algorithms require that data be normalized before training a model. Other algorithms perform their own data scaling or normalization. Therefore, when you choose a machine learning algorithm to use in building a predictive model, be sure to review the data requirements of the algorithm before applying normalization to the training data.

## <a name = "bkmk_HowTo"></a> How to configure Normalize Data

You can apply only one normalization method at a time using this module. Therefore, the same normalization method is applied to all columns that you select. To use different normalization methods, use a second instance of **Normalize Data**.

1. Add the **Normalize Data** module to your experiment. You can find the module in Azure Machine Learning Studio (classic), under **Data Transformation**, in the **Scale and Reduce** category.

2. Connect a dataset that contains at least one column of all numbers.

3. Use the Column Selector to choose the numeric columns to normalize. If you don't choose individual columns, by default **all** numeric type columns in the input are included, and the same normalization process is applied to all selected columns. 

    This can lead to strange results if you include numeric columns that shouldn't be normalized! Always check the columns carefully.

    If no numeric columns are detected, check the column metadata to verify that the data type of the column is a supported numeric type.

    > [!TIP]
    > To ensure that columns of a specific type are provided as input, try using the [Select Columns in Dataset](select-columns-in-dataset.md) module before **Normalize Data**.

4. **Use 0 for constant columns when checked**:  Select this option when any numeric column contains a single unchanging value. This ensures that such columns are not used in normalization operations.

5. From the **Transformation method** dropdown list, choose a single mathematical functions to apply to all selected columns. 
  
    - **Zscore**: Converts all values to a z-score.
    
      The values in the column are transformed using the following formula:  
  
      ![normalization using z&#45;scores](media/aml-normalization-z-score.png "AML_normalization-z-score")  
  
      Mean and standard deviation are computed for each column separately. Population standard deviation is used.
  
    - **MinMax**: The min-max normalizer linearly rescales every feature to the [0,1] interval.
    
      Rescaling to the [0,1] interval is done by shifting the values of each feature so that the minimal value is 0, and then dividing by the new maximal value (which is the difference between the original maximal and minimal values).
      
      The values in the column are transformed using the following formula:  
  
      ![normalization using the min&#45;max function](media/aml-normalization-minmax.png "AML_normalization-minmax")  
  
    - **Logistic**: The values in the column are transformed using the following formula:

      ![formula for normalization by logistic function](media/aml-normalization-logistic.png "AML_normalization-logistic")  
  
    - **LogNormal**: This option converts all values to a lognormal scale.
  
      The values in the column are transformed using the following formula:
  
      ![formula log&#45;normal distribution](media/aml-normalization-lognormal.png "AML_normalization-lognormal")
    
      Here μ and σ are the parameters of the distribution, computed empirically from the data as maximum likelihood estimates, for each column separately.  
  
    - **TanH**: All values are converted to a hyperbolic tangent.
    
      The values in the column are transformed using the following formula:
    
      ![normalization using the tanh function](media/aml-normalization-tanh.png "AML_normalization-tanh")

6. Run the experiment, or double-click the **Normalize Data** module and select **Run Selected**. 

### Results

The **Normalize Data** module generates two outputs:

- To view the transformed values, right-click the module, select **Transformed dataset**, and click **Visualize**.

    By default, values are transformed in place. If you want to compare the transformed values to the original values, use the [Add Columns](add-columns.md) module to recombine the datasets and view the columns side-by-side.

- To save the transformation so that you can apply the same normalization method to another similar dataset, right-click the module, select **Transformation function**, and click **Save as Transform**.

    You can then load the saved transformations from the **Transforms** group of the left navigation pane and apply it to a dataset with the same schema by using [Apply Transformation](apply-transformation.md).  

## Examples

For examples of how normalization is used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/):  

- [Credit risk prediction](https://go.microsoft.com/fwlink/?LinkId=525270): In this sample, normalization is applied to all numeric data except the class column, the credit risk score. This example uses the **tanh** transformation, which converts all numeric features to values within a range of 0-1.

## Technical notes

This module supports only the standard normalization methods listed in the [How to](#bkmk_HowTo) section, and does not support matrix normalization or other complex transforms.

If you need to create a custom normalization method, you can use the [Execute R Script](execute-r-script.md) or [Execute Python Script](execute-python-script.md) modules to compute and apply the transformation.

### Algorithms that apply normalization

Normalizing features so that they use a common scale is a general requirement for many machine learning algorithms.

- In linear classification algorithms, instances are viewed as vectors in multi-dimensional space. Since the range of values of raw data varies widely, some objective functions do not work properly without normalization. For example, if one of the features has a broad range of values, the distances between points is governed by this particular feature.

    Therefore, numeric features should be normalized so that each feature contributes approximately proportionately to the final distance. This can provide significant speedup and accuracy benefits.

- When using the **Logistic Regression** and **Averaged Perceptron** algorithms, by default, features are normalized before training.

### Further reading and resources

If you are unsure which type of normalization suits your data, see these resources:

- [Recommend Modules for My Data](https://gallery.azure.ai/Experiment/Recommend-Modules-for-My-Data-1): This custom module by a member of the Azure ML team evaluates your dataset and recommends steps for cleaning and scaling data.

- [Feature scaling](https://en.wikipedia.org/wiki/Feature_scaling): This article in Wikipedia explains the basic methods used for normalizing numeric data.

- [Data Preparation for Data Mining](https://dl.acm.org/citation.cfm?id=299577) covers many data preparation steps in depth. See Chapter 7 for a discussion of data normalization. 

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Transformation method|any|TransformationMethods|ZScore|Choose the mathematical method used for scaling|  
|Columns to transform|any|ColumnSelection|NumericAll|Select all columns to which the selected transformation should be applied|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Transformed dataset|[Data Table](data-table.md)|Transformed dataset|  
|Transformation function|[ITransform interface](itransform-interface.md)|Definition of the transformation function, which can be applied to other datasets|  

## Exceptions
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  
|[Error 0020](errors/error-0020.md)|Exception occurs if number of columns in some of the datasets passed to the module is too small.|  
|[Error 0021](errors/error-0021.md)|Exception occurs if number of rows in some of the datasets passed to the module is too small.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [Scale and Reduce](data-transformation-scale-and-reduce.md)   
