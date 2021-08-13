---
title: "ML Studio (classic): Import Count Table - Azure"
description: Learn how to use the Import Count Table module to merge existing count tables with new data.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Import Count Table

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Imports a previously created table of counts*

Category: [Learning with Counts](data-transformation-learning-with-counts.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Import Count Table** module in Machine Learning Studio (classic).

The purpose of the **Import Count Table** module is to allow customers who created a table of count-based statistics using an earlier version of Machine Learning to upgrade their experiment. This module merges the existing count tables with new data.

For general information about count tables and how they are used to create features, see [Learning with Counts](data-transformation-learning-with-counts.md).

> [!IMPORTANT]
> This module is provided solely for backward compatibility with experiments that use the deprecated Build Count Table and deprecated Count Featurizer modules. We recommend that you upgrade your experiment to use the newer modules, to take advantage of new features. 

For all new experiments, we recommend that you use the following modules:

- [Build Counting Transform](build-counting-transform.md)
- [Modify Count Table Parameters](modify-count-table-parameters.md)
- [Merge Count Transform](merge-count-transform.md)

## How to configure Import Count Table

1. In Machine Learning Studio (classic), open an experiment that contains a count table created using the deprecated Build Count Table module.

2. Add the **Import Count Table** module to the experiment.

3. Connect the two outputs of the Build Count Table (deprecated) module to the matching input ports of the **Import Count Table**.

    If you have another dataset of counts that you want to merge with the imported count table, connect it to the rightmost input for the **Import Count Table** module.

4. Use the **Counting type** option to specify where and how the count table is stored:

    - **Dataset**: The data used to build counts is saved as a dataset in Machine Learning Studio (classic).

    - **Blob**: The data used to build counts is stored as a block blob in Windows Azure storage.

    - **MapReduce**: The data used to build counts is stored as a blob in Windows Azure storage.

        This option is typically preferred for very large datasets. To access the counts, you must activate the HDInsight cluster. A MapReduce job is launched to perform the counting. Both of these activities can incur storage and compute costs.

        For more information, see [HDInsight on Azure](https://azure.microsoft.com/services/hdinsight/).

    After specifying the data storage mode, you may need to provide additional connection information for the data, even if you previously used a [Import Data](import-data.md) module in the experiment to access data. That is because the Count Featurizer (deprecated) module accesses the data storage separately in order to read the data and build the required tables.

5. Use the **Count table type** option to specify the format and storage mode of the table used to store counts.

    - **Dictionary**: Uses a dictionary count table.

        All column values in the selected columns are treated as strings, and are hashed using a bit array of up to 31 bits in size. Therefore, all column values are represented by a non-negative 32-bit integer.

    - **CMSketch**: Uses a table saved in the *count minimum sketch table*.

        With this format, multiple independent hash functions with a smaller range are used to improve memory efficiency and reduce the chance of hash collisions.

    In general, you should use the **Dictionary** option for smaller data sets (<1GB), and use the **CMSketch** option for larger datasets.

6. Run the experiment.

7. When complete, right-click the output of the  **Import Count Table** module, select **Save as Transform**, and type a name for the transformation. When you do this, the merged count tables and any featurization parameters you might have applied are saved in a format that can be applied to a new dataset.

## Examples

Explore examples of count-based featurization using these sample experiments in the [Azure AI Gallery](https://gallery.azure.ai/):

- [Flight delay prediction](https://gallery.azure.ai/Experiment/Binary-Classification-Flight-delay-prediction-3): Shows how count-based featurization can be useful in a very large dataset.

- [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.azure.ai/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2): demonstrates the use of count-based features in a multiclass prediction task.

- [Learning with Counts: Binary classification with NYC taxi data](https://gallery.azure.ai/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2): Uses count-based features in a binary classification task.

> [!NOTE]
> These Gallery experiments were all created using the earlier, and now deprecated, version of the [Learning with Counts](data-transformation-learning-with-counts.md) modules. When you open the experiment in Studio (classic), the experiment is automatically upgraded to use the newer modules.

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

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Learning with Counts](data-transformation-learning-with-counts.md)   
