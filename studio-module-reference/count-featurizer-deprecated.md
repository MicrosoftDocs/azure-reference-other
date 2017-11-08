---
title: "Count Featurizer (deprecated) | Microsoft Docs"
ms.custom: ""
ms.date: 07/01/2015
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 217741b5-730a-4c4b-839c-93c9cbb80ae7
caps.latest.revision: 11
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Count Featurizer (deprecated)
*Creates a set of features based on a counts table*  
  
 Category: [Learning with Counts](data-transformation-learning-with-counts.md)  
  
## Module Overview  
 You can use the **Count Featurizer** module to create features from a previously generated count table. Creating features from counts is an efficient way of summarizing useful information about the distribution of data and labels in a set of training data.  
  
 This method of creating features from raw data is particularly useful in large data sets with high-cardinality features.  For example, in fraud detection, count tables can be used to collect information about the user ID, product and transaction and all the possible combinations over terabytes of data.  Count tables can also be useful in improving accuracy on small data sets.  
  
 You generate the count tables using the [Build Count Table (deprecated)](build-count-table-deprecated.md) module together with a training dataset, and then use **Count Featurizer** to create a ranked set of features that can be used with any of the [machine learning modules](machine-learning-initialize-model.md) as an input for training.  
  
 You can also enhance your count-based features by:  
  
-   Generating a count table, saving it, and then updating it with new data.  
  
-   Creating a master count table over time, which can be applied to multiple models.  
  
-   Saving  featurization steps for reuse with other data sets.  
  
> [!WARNING]
>  This module has been deprecated.  
>   
>  For new experiments, we recommend that you use the following modules:  
>   
>  -   [Build Count Transform](count-featurizer-deprecated.md)  
> -   [Modify Count Table Parameters](modify-count-table-parameters.md)  
> -   [Merge Count Transform](merge-count-transform.md)  
>   
>  For backward compatibility with existing experiments, the following modules can help you update an existing count table, or change the count table to a new count transformation.  
>   
>  -   [Import Count Table](import-count-table.md)  
> -   [Export Count Table](export-count-table.md)  
  
## How to Configure Count Featurizer  
  
1.  Create a table of counts using the [Build Count Table (deprecated)](build-count-table-deprecated.md) module.  
  
2.  Connect the output of the [Build Count Table (deprecated)](build-count-table-deprecated.md) module to the leftmost input port of **Count Featurizer**.  
  
3.  Connect a training data set to the middle input port of **Count Featurizer**.  
  
     It need not be the same training dataset that was used for [Build Count Table (deprecated)](build-count-table-deprecated.md), but you must select the same number of columns and they must have the same data type and values.  
  
4.  Set additional options using the parameters in the following table.  
  
### Options  
 *Select counted columns*  
 Select the columns in the count table that you created using [Build Count Table (deprecated)](build-count-table-deprecated.md).  You can select any subset of the columns used in the [Build Count Table (deprecated)](build-count-table-deprecated.md) module.  
  
 *Select columns to featurize*  
 Select the columns in the input dataset that you want to featurize by using the data from the count table.  You must select the same number of columns that you selected in the previous option, *Select counted columns*.  
  
> [!NOTE]
>  The columns you select must have the same type and structure as the columns you used to build the count table.  
  
 *Garbage bin threshold*  
 Type a value to use as the garbage bin threshold. This value specifies the minimum number of occurrences that must be found for each value, in order for counts to be used.  
  
 If the frequency of the value is less than the garbage bin threshold, the value-label pair is not counted.  
  
> [!TIP]
>  If you are using a small dataset and you are counting and training on the same data, a good starting value is 1.  
  
 *Additional prior pseudo examples*  
 Specify some n number of additional pseudo examples to include. The pseudo examples are generated based on the prior distribution.  
  
 *Laplacian noise scale*  
 Type a positive floating-point value that represents the scale used for introducing noise sampled from a Laplacian distribution.  
  
 It is statistically safe to count and train on the same data set if you set the Laplacian noise scale parameter. In other words, by setting a scale value, some acceptable level of noise is incorporated into the model, so the model is less likely to be affected by unseen values in data.  
  
 *Output features include*  
 Choose the count-based features that you want to include in the module output.  
  
-   **CountsOnly**.   Creates features using counts.  
  
-   **LogOddsOnly**.   Creates features using the log of the odds ratio.  
  
-   **BothCountsAndLogOdds**.   Creates features using both counts and log odds.  
  
 *Ignore back off column*  
 Select this option if you want to ignore the `IsBackOff` column in the output when creating features  
  
## Examples  
 You can see examples of how this module is used by exploring these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [flight delay prediction](http://go.microsoft.com/fwlink/?LinkId=525277) sample demonstrates the use of count-based featurization over a very large dataset.  
  
## Technical Notes  
 It is statistically safe to count and train on the same data set if you set the Laplacian noise scale parameter.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Count metadata|[Data Table](data-table.md)|The metadata of the counts.|  
|Count table|[Data Table](data-table.md)|The count table.|  
|Input dataset|[Data Table](data-table.md)|The data set to be featurized.|  
  
##  <a name="parameters"></a> Module Parameters  
  
###  
  
|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Additional prior pseudo examples|Float|>=0.0f|Required|42.0f|Provide additional pseudo examples following prior distribution, to include with the counts.|  
|Garbage bin threshold|Float|>=0.0f|Required|10.0f|Specify the threshold under which a column value will be featurized against the garbage bin.|  
|Ignore back off column|Boolean||Required|false|Indicate whether the IsBackOff column should be ignored when creating results.|  
|Laplacian noise scale|Float|>=0.0f|Required|0.0f|Specify a scale to apply when introducing noise sampled from Laplacian distribution.|  
|Output features include|OutputFeatureType||Required|BothCountsAndLogOdds|Select the features to include in the output.|  
|Select columns to featurize|ColumnSelection||Required||Select the columns to featurize. This must be a subset of the counted columns.|  
|Select counted columns|ColumnSelection||Required||Select the columns that have been used to build count table.|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Featured data|[Data Table](data-table.md)|The featured data.|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all exceptions, see [Machine Learning REST API Error Codes](http://msdn.microsoft.com/library/0eccb2eb-27a1-407e-88a9-2092dba847e0).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
  
## See Also  
 [Learning with Counts](data-transformation-learning-with-counts.md)   
 [Build Count Table (deprecated)](build-count-table-deprecated.md)