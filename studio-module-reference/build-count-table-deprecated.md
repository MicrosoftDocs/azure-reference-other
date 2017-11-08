---
title: "Build Count Table (deprecated) | Microsoft Docs"
ms.custom: ""
ms.date: 07/01/2015
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 166586ff-5bba-46a9-b469-20179f179b6c
caps.latest.revision: 12
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Build Count Table (deprecated)
*Builds a count table that can be used to create count-based features.*  
  
 Category: [Learning with Counts](data-transformation-learning-with-counts.md)  
  
## Module Overview  
 You can use the **Build Count Table** module to analyze training data and create a *count table*, which contains the joint distribution of all feature columns given a specified label column.  
  
 You provide this table of counts as an input to the [Count Featurizer (deprecated)](count-featurizer-deprecated.md) module, which uses the count-based information to create a set of features that is more compact than the original training data, but which captures all the most useful information.  
  
 You can generate a new count table from a dataset each time you run your experiment, or you can write the table to blob storage or a Hive table, and then update or reuse the table in other experiments or with other data. Updating or reusing the data is useful in scenarios such as these:  
  
-   When new data becomes available to further enhance the model, you can create a new count table and merge it with previously created counts table to improve the joint distributions.  
  
-   If you generate a set of counts that reflects the expected distribution of data in the real world domain, you can reuse that table when scoring new models, to ensure that features reflect the real world, rather than risk overfitting your model on a small and possibly skewed subset of data.  
  
> [!WARNING]
>  This module has been deprecated.  
>   
>  For new experiments, we recommend that you use the following modules:  
>   
>  -   [Build Counting Transform](build-counting-transform.md)  
> -   [Modify Count Table Parameters](modify-count-table-parameters.md)  
> -   [Merge Count Transform](merge-count-transform.md)  
>   
>  For backward compatibility with existing experiments, the following modules can help you update an existing count table, or change the count table to a new count transformation.  
>   
>  -   [Import Count Table](import-count-table.md)  
> -   [Export Count Table](export-count-table.md)  
  
## Examples  
 You can see how this module is used by exploring these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [flight delay prediction](http://go.microsoft.com/fwlink/?LinkId=525277) sample demonstrates the use of count-based featurization over a very large dataset.  
  
## Technical Notes  
 In statistical learning theory, a classification problem can be formulated as the problem of finding an estimate of a target function from labelled data drawn from an unknown fixed distribution. In fact, if there is a way to know the exact joint distribution of the features of the data and the label, you can readily estimate the target function, given a metric for evaluating the estimates. Therefore, if all combinations of all columns of the dataset are used to build the count table, the generated count table must completely describe the distribution of the label values over the training data.  
  
 However, if there are *N* columns in the training data, then there are *2^N* choices of joint columns to count, which becomes an enormous number when *N* is large.  
  
 Therefore, in practice, you will typically choose a small subset of joint columns to build the count table, and use the count table to compute additional features, which can be used to train classifiers such as a decision tree or a neural network.  
  
 For any subset of selected columns in the training data, and for each row of the data, you can look up values in the count table to generate any combination of the following features:  
  
-   Total counts per label class  
  
-   Log of the odds ratio (log odds) for each label class  
  
-   A flag indicating whether the total counts of the appearance of the row is too low for sufficient statistical significance  
  
 These additional features can be used in combination with the other original columns of the training data, or you can replace some of the original data columns with the count featurized columns.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|*Input data*|[Data Table](data-table.md)|The data to count.|  
  
##  <a name="parameters"></a> Module Parameters  
  
###  
  
|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Account key|SecureString||countingType:Blob||The key of the storage account used for the count table.|  
|Account name|String||countingType:Blob||The name of the storage account used for the count table.|  
|Blob format|BlobFormat||countingType:Blob|CSV|Specify the format of the blob file used for the counts table.|  
|Blob format|BlobFormat||countingType:MapReduce|CSV|The blob text file format.|  
|Blob name|String||countingType:Blob||The name of the Azure blob where the count table is stored.|  
|Cluster URI|String||countingType:MapReduce||The URI to the HDInsight Hadoop cluster to perform MapReduce counting for MapReduce counting.|  
|Container name|String||countingType:Blob||The name of the blob container where the count table will be saved.|  
|Count columns|String||countingType:Blob||A list of the columns to perform counting on, specified as a comma-separated list of column indices. Column indexes are 1-based.|  
|Count columns|String||countingType:MapReduce||The one-based indices of groups of columns to perform counting for MapReduce counting.|  
|Count table type|CountTableType||countingType:Blob|Dictionary|Specify the type of count table to use: Dictionary or CMSketch.|  
|Count table type|CountTableType||countingType:MapReduce|Dictionary|Specify the type of count table to use: Dictionary or CMSketch.|  
|Default container name|String||countingType:MapReduce||The name of the blob container to write the count table for MapReduce counting.|  
|Default storage account key|SecureString||countingType:MapReduce||The key of the storage account containing the input blob for MapReduce counting.|  
|Default storage account name|String||countingType:MapReduce||The name of the storage account containing the input blob for MapReduce counting.|  
|Depth of CM sketch table|Integer|>=1|azureCountTableType:CMSketch|4|If you choose the CMSketch format for the count table, specify the depth of the CM sketch table.|  
|Depth of CM sketch table|Integer|>=1|dataCountTableType:CMSketch|4|If you choose the CMSketch format for the count table, specify the depth of the CM sketch table.|  
|Input blob name|String||countingType:MapReduce||The name of the blob that contains the data to be counted using MapReduce counting.|  
|Input data container|HadoopInputContainer||countingType:MapReduce|Default container|The container that contains the blob with input for MapReduce counting.|  
|Label column|Integer|>=1|countingType:Blob|1|The index of the label column. Column indexes are 1-based.|  
|Label column|Integer|>=1|countingType:MapReduce|1|The index of the label column. Column indexes are 1-based.|  
|Label column index or name|ColumnSelection||countingType:Dataset||Select the column that contains the label for the dataset.|  
|Module type|CountingType||Required|Dataset|Specify where the counts table will be created and stored.|  
|Number of classes|Integer|>=2|Required|2|The number of classes for the label.|  
|Output blob path|string||countingType:MapReduce||The output blob path for the count table for MapReduce counting.|  
|Password|SecureString||countingType:MapReduce||The password to login to the HDInsight Hadoop cluster for MapReduce counting.|  
|Select columns to count|ColumnSelection||countingType:Dataset||Select columns for counting.|  
|The bits of hash function|Integer|[12;31]|Required|20|Number of bits used for the hash function|  
|The seed of hash function|Integer||Required|1|Specify a seed to use when initializing the hash function.|  
|The URI to the input blob container|String||hadoopInputContainer:ExternalContainer||The URI to the input blob container. The container should have public read access.|  
|Username|String||countingType:MapReduce||The username to login to the HDInsight Hadoop cluster for MapReduce counting.|  
|Width of CM sketch table|Integer|[1;31]|azureCountTableType:CMSketch|20|If you choose the CMSketch format for the count table, specify the width of the CM sketch table.|  
|Width of CM sketch table|Integer|[1;31]|dataCountTableType:CMSketch|20|If you choose the CMSketch format for the count table, specify the width of the CM sketch table.|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Count metadata|[Data Table](data-table.md)|The metadata of counts.|  
|Count table|[Data Table](data-table.md)|The count table.|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all exceptions, see [Machine Learning REST API Error Codes](http://msdn.microsoft.com/library/0eccb2eb-27a1-407e-88a9-2092dba847e0).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
  
## See Also  
 [Learning with Counts](data-transformation-learning-with-counts.md)   
 [Count Featurizer (deprecated)](count-featurizer-deprecated.md)