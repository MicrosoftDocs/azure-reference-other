---
title: "Import Count Table | Microsoft Docs"
ms.custom: ""
ms.date: 10/11/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: db546854-7d3f-40da-9960-8b56ba03ada0
caps.latest.revision: 9
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Import Count Table
*Imports a previously created table of counts*  
  
 Category: [Learning with Counts](data-transformation-learning-with-counts.md)  
  
## Module Overview  
 The **Import Count Table** module is provided for backward compatibility with experiments that use the [Build Count Table (deprecated)](build-count-table-deprecated.md) and [Count Featurizer (deprecated)](count-featurizer-deprecated.md) modules.  
  
 By using **Import Count Table**, you can re-use a count table that was created in an older experiment, and merge the count tables with new data, or change the way that features are created.  
  
 For general information about count tables and how they are used to create features, see [Learning with Counts](data-transformation-learning-with-counts.md).  
  
## How to Configure Import Count Table  
  
1.  Open an experiment in which you created a count table using the [Build Count Table (deprecated)](build-count-table-deprecated.md) module.  
  
2.  Add the **Import Count Table** module to the experiment.  
  
3.  Connect the two outputs of the [Build Count Table (deprecated)](build-count-table-deprecated.md) module to the matching input ports of the **Import Count Table**.  
  
     If you have another dataset of counts that you want to merge with the imported count table, connect it to the rightmost input port of the **Import Count Table** module.  
  
4.  Use the **Counting type** option to specify where and how the count table is stored:  
  
    -   **Dataset** The data used to build counts is saved as a dataset in Azure Machine Learning Studio.  
  
    -   **Blob** The data used to build counts is stored as a block blob in Windows Azure storage.  
  
    -   **MapReduce** The data used to build counts is stored as a blob in Windows Azure storage.  
  
         This option is typically preferred for very large datasets. To access the counts, you must activate the HDInsight cluster. A MapReduce job is launched to perform the counting. Note that both of these activities can incur storage and compute costs.  
  
         For more information, see [http://azure.microsoft.com/services/hdinsight/](http://azure.microsoft.com/services/hdinsight/).  
  
     After specifying the data storage mode, you may need to provide additional connection information for the data, even if you previously used a [Import Data](import-data.md) module in the experiment to access data. That is because the [Count Featurizer (deprecated)](count-featurizer-deprecated.md) module accesses the data storage separately in order to read the data and build the required tables.  
  
5.  Use the **Count table type** option to specify the format and storage mode of the table used to store counts.  
  
    -   **Dictionary**.    Uses a dictionary count table.  
  
         All column values in the selected columns are treated as strings, and are hashed using a bit array of up to 31 bits in size. Therefore, all column values are represented by a non-negative 32-bit integer.  
  
    -   **CMSketch**.     Uses a table saved in the *count minimum sketch table*.  
  
         With this format, multiple independent hash functions with a smaller range are used to improve memory efficiency and reduce the chance of hash collisions.  
  
     In general, you should use the **Dictionary** option for smaller data sets (<1GB), and use the **CMSketch** option for larger datasets.  
  
6.  Run the experiment.  
  
     When complete, right-click the output of the  **Import Count Table** module, select **Save as Transform**, and type a name for the transformation. When you do this, the merged count tables and any featurization parameters you might have applied are saved in a format that can be applied to a new dataset.  
  
 For more information about how to apply a counting transformation to dataset to use in building a model, see these topics:  
  
## Examples  
 You can see how this module is used by exploring these sample experiments in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Learning with Counts: Binary Classification](https://gallery.azureml.net/Experiment/Learning-with-Counts-Binary-Classification-2) sample demonstrates how to use the **Learning with Counts** modules to generate features from columns of categorical values for a binary classification model.  
  
-   The [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.azureml.net/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2) sample demonstrates how to use the learning with counts modules for performing multiclass classification on the publicly available NYC taxi dataset.  
  
-   The [Learning with Counts: Binary classification with NYC taxi data](https://gallery.azureml.net/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2) sample demonstrates how to use the learning with counts modules for performing binary classification on the publicly available NYC taxi dataset.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Count metadata|[Data Table](data-table.md)|The metadata of the counts|  
|Count table|[Data Table](data-table.md)|The count table|  
|Counted data set|[Data Table](data-table.md)|The data set used for counting|  
  
##  <a name="parameters"></a> Module Parameters  
  
###  
  
|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Counting type|CountingType||Required||The counting type|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Counting transform|[ITransform interface](itransform-interface.md)|The counting transform|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0018](errors/error-0018.md)|Exception occurs if input dataset is not valid.|  
  
## See Also  
 [Learning with Counts](data-transformation-learning-with-counts.md)   
 [Count Featurizer (deprecated)](count-featurizer-deprecated.md)