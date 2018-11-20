---
title: "Import Count Table | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 12/18/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: db546854-7d3f-40da-9960-8b56ba03ada0
caps.latest.revision: 9
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Import Count Table

*Imports a previously created table of counts*

Category: [Learning with Counts](data-transformation-learning-with-counts.md)

## Module overview

This article describes how to use the **Import Count Table** module in Azure Machine Learning Studio.

The purpose of the **Import Count Table** module is to allow customers who created a table of count-based statistics using an earlier version of Azure Machine Learning to upgrade their experiment. This module merges the existing count tables with new data.

For general information about count tables and how they are used to create features, see [Learning with Counts](data-transformation-learning-with-counts.md).

> [!IMPORTANT]
> This module is provided solely for backward compatibility with experiments that use the [Build Count Table (deprecated)](build-count-table-deprecated.md) and [Count Featurizer (deprecated)](count-featurizer-deprecated.md) modules.We recommend that you upgrade your experiment to use the newer modules, to take advantage of new features. 

For all new experiments, we recommend that you use the following modules:

- [Build Counting Transform](build-counting-transform.md)
- [Modify Count Table Parameters](modify-count-table-parameters.md)
- [Merge Count Transform](merge-count-transform.md)

## How to configure Import Count Table

1. In Azure Machine Learning Studio, open an experiment that contains a count table created using the [Build Count Table (deprecated)](build-count-table-deprecated.md) module.

2. Add the **Import Count Table** module to the experiment.

3. Connect the two outputs of the [Build Count Table (deprecated)](build-count-table-deprecated.md) module to the matching input ports of the **Import Count Table**.

    If you have another dataset of counts that you want to merge with the imported count table, connect it to the rightmost input for the **Import Count Table** module.

4. Use the **Counting type** option to specify where and how the count table is stored:

    - **Dataset**: The data used to build counts is saved as a dataset in Azure Machine Learning Studio.

    - **Blob**: The data used to build counts is stored as a block blob in Windows Azure storage.

    - **MapReduce**: The data used to build counts is stored as a blob in Windows Azure storage.

        This option is typically preferred for very large datasets. To access the counts, you must activate the HDInsight cluster. A MapReduce job is launched to perform the counting. Both of these activities can incur storage and compute costs.

        For more information, see [HDInsight on Azure](http://azure.microsoft.com/services/hdinsight/).

    After specifying the data storage mode, you may need to provide additional connection information for the data, even if you previously used a [Import Data](import-data.md) module in the experiment to access data. That is because the [Count Featurizer (deprecated)](count-featurizer-deprecated.md) module accesses the data storage separately in order to read the data and build the required tables.

5. Use the **Count table type** option to specify the format and storage mode of the table used to store counts.

    - **Dictionary**: Uses a dictionary count table.

        All column values in the selected columns are treated as strings, and are hashed using a bit array of up to 31 bits in size. Therefore, all column values are represented by a non-negative 32-bit integer.

    - **CMSketch**: Uses a table saved in the *count minimum sketch table*.

        With this format, multiple independent hash functions with a smaller range are used to improve memory efficiency and reduce the chance of hash collisions.

    In general, you should use the **Dictionary** option for smaller data sets (<1GB), and use the **CMSketch** option for larger datasets.

6. Run the experiment.

7. When complete, right-click the output of the  **Import Count Table** module, select **Save as Transform**, and type a name for the transformation. When you do this, the merged count tables and any featurization parameters you might have applied are saved in a format that can be applied to a new dataset.

## Examples

Explore examples of count-based featurization using these sample experiments in the [Azure AI Gallery](https://gallery.cortanaintelligence.com/):

- [Flight delay prediction](http://go.microsoft.com/fwlink/?LinkId=525277): Shows how count-based featurization can be useful in a very large dataset.

- [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.cortanaintelligence.com/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2): demonstrates the use of count-based features in a multiclass prediction task.

- [Learning with Counts: Binary classification with NYC taxi data](https://gallery.cortanaintelligence.com/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2): Uses count-based features in a binary classification task.

> [!NOTE]
> These Gallery experiments were all created using the earlier, and now deprecated, version of the [Learning with Counts](data-transformation-learning-with-counts.md) modules. When you open the experiment in Studio, the experiment is automatically upgraded to use the newer modules.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Count metadata|[Data Table](data-table.md)|The metadata of the counts|  
|Count table|[Data Table](data-table.md)|The count table|  
|Counted data set|[Data Table](data-table.md)|The data set used for counting|  

## Module parameters

|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Counting type|CountingType||Required||The counting type|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Counting transform|[ITransform interface](itransform-interface.md)|The counting transform|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0018](errors/error-0018.md)|Exception occurs if input dataset is not valid.|  

For a list of errors specific to Studio modules, see [Machine Learning Error codes](\errors\machine-learning-module-error-codes.md)

For a list of API exceptions, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Learning with Counts](data-transformation-learning-with-counts.md)   
 [Count Featurizer (deprecated)](count-featurizer-deprecated.md)