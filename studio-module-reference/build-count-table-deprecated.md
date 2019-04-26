---
title: "Build Count Table (deprecated) | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Build Count Table (deprecated)

*Builds a count table that can be used to create count-based features.*

Category: [Learning with Counts](data-transformation-learning-with-counts.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Build Count Table** module in Azure Machine Learning Studio, to analyze training data and create a *count table*, which contains the joint distribution of all feature columns given a specified label column.

The table of counts is used as an input to the [Count Featurizer (deprecated)](count-featurizer-deprecated.md) module. From the count-based information, the **Count Featurizer** module creates a new set of features, which is more compact than the original training data, but which captures all the most useful information.

> [!IMPORTANT]
> This module and related modules have been deprecated. The older versions are provided solely to support existing experiments that use previous modules for count-based featurization. We recommend that you upgrade your experiment to use the newer modules, to take advantage of new features.

For all new experiments, we recommend that you use the following modules:

- [Build Counting Transform](build-counting-transform.md)
- [Modify Count Table Parameters](modify-count-table-parameters.md)
- [Merge Count Transform](merge-count-transform.md)

## How to use Build Count Table

This module has been deprecated.

You can find updated instructions for how to build a count table here:

- [Build Counting Transform](build-counting-transform.md)

We recommend that you use the following modules to upgrade an existing count table to a count transformation, which is more easily applied and updated.

- [Import Count Table](import-count-table.md)
- [Export Count Table](export-count-table.md)

## Examples

Explore examples of count-based featurization using these sample experiments in the [Azure AI Gallery](https://gallery.cortanaintelligence.com/):

- [Flight delay prediction](http://go.microsoft.com/fwlink/?LinkId=525277): Shows how count-based featurization can be useful in a very large dataset.

- [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.cortanaintelligence.com/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2): Demonstrates the use of count-based features in a multiclass prediction task.

- [Learning with Counts: Binary classification with NYC taxi data](https://gallery.cortanaintelligence.com/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2): Uses count-based features in a binary classification task.

> [!NOTE]
> 
> These experiments were all created using the earlier, and now deprecated, version of the [Learning with Counts](data-transformation-learning-with-counts.md) modules. When you open the experiment in Studio, the experiment is automatically upgraded to use the newer modules.

## Technical notes

In statistical learning theory, a classification problem can be formulated as the problem of finding an estimate of a target function from labelled data drawn from an unknown fixed distribution. In fact, if there is a way to know the exact joint distribution of the features of the data and the label, you can readily estimate the target function, given a metric for evaluating the estimates. Therefore, if all combinations of all columns of the dataset are used to build the count table, the generated count table must completely describe the distribution of the label values over the training data.

However, if there are *N* columns in the training data, then there are *2^N* choices of joint columns to count, which becomes an enormous number when *N* is large.

Therefore, in practice, you typically choose a small subset of joint columns to build the count table, and use the count table to compute additional features, which can be used to train classifiers such as a decision tree or a neural network.

For any subset of selected columns in the training data, and for each row of the data, you can look up values in the count table to generate any combination of the following features:

- Total counts per label class

- Log of the odds ratio (log odds) for each label class

- A flag indicating whether the total counts of the appearance of the row is too low for sufficient statistical significance

These additional features can be used in combination with the other original columns of the training data, or you can replace some of the original data columns with the count featurized columns.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|*Input data*|[Data Table](data-table.md)|The data to count.|  

## Module parameters

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

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Count metadata|[Data Table](data-table.md)|The metadata of counts.|  
|Count table|[Data Table](data-table.md)|The count table.|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

For a list of errors specific to Studio modules, see [Machine Learning Error codes](/errors/machine-learning-module-error-codes.md)

For a list of API exceptions, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes).

## See also

 [Learning with Counts](data-transformation-learning-with-counts.md)   
 [Count Featurizer (deprecated)](count-featurizer-deprecated.md)
