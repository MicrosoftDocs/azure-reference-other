---
title: "ML Studio (classic): Build Counting Transform - Azure"
description: Learn how to use the Build Counting Transform module to build a *count table* as well as a set of *count-based features* that can be used in a predictive model.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Build Counting Transform

*Creates a transformation that turns count tables into features, so that you can apply the transformation to multiple datasets*

Category: [Learning with Counts](data-transformation-learning-with-counts.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Build Counting Transform** module in Azure Machine Learning Studio (classic), to analyze training data. From this data, the module builds a *count table* as well as a set of *count-based features* that can be used in a predictive model.

A count table contains the joint distribution of all feature columns, given a specified label column. Such statistics are useful in determining which columns have the most information value. *Count-based featurization* is useful because such features are more compact than the original training data, but capture all the most useful information. You can use the module parameters to customize how the counts are transformed into the new set of count-based features.

After generating counts and transforming them into features, you can save the process as a transformation for re-use on related data. You can also modify the set of features without having to generate a new set of counts, or merge the counts and features with another set of counts and features.

The ability to re-use and re-apply count-based features is useful in scenarios such as these:

+ New data becomes available to improve the coverage or balance of your dataset.
+ Your original counts and features were based on a very large dataset that you don’t want to re-process. By merging the counts you can update with new data.
+ You want to ensure that the same set of count-based features is applied to all datasets that you are using in your experiment.

## How to configure Build Counting Transform

You can create a count-based feature transformation directly from a dataset, and re-run it each time you run an experiment. Or, you can generate a set of counts, and then merge it with new data to create an updated count table.

+ [Create count-based features from a dataset](#bkmk_CreateCounts)  

    Start here if you have not created counts before. You use the **Build Counting Transform** module to create count tables and automatically generate a set of features.

    This process creates a feature transformation that you can apply to a dataset, using the [Apply Transformation](apply-transformation.md) module.

+ [Merge counts and features from multiple datasets](#bkmk_MergeCounts)

    If you have already generated a count table from a previous dataset, generate counts on just the new data, or import an existing count table created in an earlier version of Azure Machine Learning. Then, merge the two sets of count tables

    This process creates a new feature transformation that you can apply to a dataset, using the [Apply Transformation](apply-transformation.md) module.

### <a name="bkmk_CreateCounts"></a> Create count-based features from a dataset

1. In Azure Machine Learning Studio (classic), add the **Build Counting Transform** module to your experiment. You can find the module under **Data Transformation**, in the category **Learning with Counts**.

2. Connect the dataset you want to use as the basis for our count-based features.

3. Use the **Number of classes** option to specify the number of values in your label column.

    + For any binary classification problem, type `2`.
    + For a classification problem with more than two possible outputs, you must specify in advance the exact number of classes to count. If you enter a number that is less than the actual number of classes, the module will return an error.
    + If your dataset contains multiple class values and the class label values are non-sequential, you must use [Edit Metadata](edit-metadata.md) to specify that the column contains categorical values.

4. For the option, **The bits of hash function**, indicate how many bits to use when hashing the values.

    It is generally safe to accept the defaults, unless you know that there are many values to count and a higher bit count might be needed.

5. In **The seed of hash function**, you can optionally specify a value to seed the hashing function. Setting a seed manually is typically done when you want to ensure that hashing results are deterministic across runs of the same experiment.

6. Use the **Module type** option to indicate the type of data that you will be counting, based on the storage mode:

    + **Dataset**: Choose this option if you are counting data that is saved as a dataset in Azure Machine Learning Studio (classic).

    + **Blob**: Choose this option if your source data used to build counts is stored as a block blob in Windows Azure storage.

    + **MapReduce**: Choose this option if you want to call Map/Reduce functions to process the data.

        To use this option, the new data must be provided  as a blob in Windows Azure storage, and you must have access to a deployed HDInsight cluster. When you run the experiment, a Map/Reduce job is launched in the cluster to perform the counting.

        For very large datasets, we recommend that you use this option whenever possible. Although you might incur additional costs for using the HDInsight service, computation over large datasets might be faster in HDInsight.

         For more information, see [https://azure.microsoft.com/services/hdinsight/](https://azure.microsoft.com/services/hdinsight/).

7. After specifying the data storage mode, provide any additional connection information for the data that is required:

    + If you are using data from Hadoop or blob storage, provide the cluster location and credentials.
    + If you previously used a [Import Data](import-data.md) module in the experiment to access data, you must re-enter the account name and your credentials. The **Build Counting Transform** module accesses the data storage separately in order to read the data and build the required tables.

8. For **Label column or index**, select  one column as the label column.

    A label column is required. The column must already be marked as a label or an error is raised.

9. Use the option, **Select columns to count**, and select the columns for which to generate counts.

    In general, the best candidates are high-dimensional columns, together with any other columns that are correlated with those columns.

10. Use the **Count table type** option to specify the format used for storing the count table.

    + **Dictionary**: Creates a dictionary count table. All column values in the selected columns are treated as strings, and are hashed using a bit array of up to 31 bits in size. Therefore, all column values are represented by a non-negative 32-bit integer.

        In general, you should use this option for smaller data sets (less than 1 GB), and use the **CMSketch** option for larger datasets.

        After selecting this option, configure the number of bits used by the hashing function, and set a seed for initializing the hash function.

    + **CMSketch**:  Creates a *count minimum sketch table*. With this option, multiple independent hash functions with a smaller range are used to improve memory efficiency and reduce the chance of hash collisions.  The parameters for hashing bit size and hashing seed have no effect on this option.

11. Run the experiment.

    The module creates a *featurization transform* that you can use as input to the [Apply Transformation](apply-transformation.md) module. The output of the [Apply Transformation](apply-transformation.md) module is a transformed dataset that can be used to train a model.

    Optionally, you can save the transform if you want to merge the set of count-based features with another set of count-based features. For more information, see [Merge Count Transform](merge-count-transform.md).

### <a name="bkmk_MergeCounts"></a> Merge counts and features from multiple datasets

1. In Azure Machine Learning Studio (classic), add the **Build Counting Transform** module to your experiment, and connect the dataset that contains the new data you want to add.

2. Use the **Module type** option to indicate the source of the new data. You can merge data from different sources.

    + **Dataset**: Choose this option if the new data is provided as a dataset in Azure Machine Learning Studio (classic).

    + **Blob**: Choose this option if the new data is provided as a block blob in Windows Azure storage.

    + **MapReduce**: Choose this option if you want to call Map/Reduce functions to process the data.

        To use this option, the new data must be provided  as a blob in Windows Azure storage, and you must have access to a deployed HDInsight cluster. When you run the experiment, a Map/Reduce job will be launched in the cluster to perform the counting.

         For more information, see [https://azure.microsoft.com/services/hdinsight/](https://azure.microsoft.com/services/hdinsight)

3. After specifying the data storage mode, provide any additional connection information for the new data:

    + If you are using data from Hadoop or blob storage, provide the cluster location and credentials.

    + If you previously used a [Import Data](import-data.md) module in the experiment to access data, you must re-enter the account name and your credentials. The reason is that the **Build Counting Transform** module accesses the data storage separately in order to read the data and build the required tables.

4. When merging counts, the following options must be exactly the same in both counts tables:

    + **Number of classes**
    + **The bits of hash function**
    + **The seed of hash function**
    + **Select columns to count**

     The label column can be different, as long as it contains the same number of classes.

5. Use the **Count table type** option to specify the format and destination for the  updated count table.

    > [!TIP]
    > The format of the two count tables that you intend to merge must be the same.
    > In other words, if you saved an earlier count table using the **Dictionary** format you cannot merge it with counts saved using the **CMSketch** format.

6. Run the experiment.

    The module creates a *featurization transform* that you can use as input to the [Apply Transformation](apply-transformation.md) module. The output of the [Apply Transformation](apply-transformation.md) module is a transformed dataset that can be used to train a model.

7. To merge this set of counts with an existing set of count-based features, see [Merge Count Transform](merge-count-transform.md).

## Examples

See these articles for more information about the counts algorithm and the efficacy of count-based modeling compared to other methods.

+ [Using Azure ML to Build Click-through Prediction Models](https://go.microsoft.com/fwlink/?LinkId=699305)
+ [Big Learning Made Easy with Counts!](https://blogs.technet.microsoft.com/machinelearning/2015/02/17/big-learning-made-easy-with-counts/)

The following experiments in the [Azure AI Gallery](https://gallery.azure.ai/) demonstrate how to use count-based learning to build various predictive models:

+ [Learning With Counts - Binary Classification](https://gallery.azure.ai/Experiment/Learning-with-Counts-Binary-Classification-2)
+ [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.azure.ai/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2)
+ [Learning with Counts: Binary classification with NYC taxi data](https://gallery.azure.ai/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2)

## Module parameters

The following parameters are used with all options:

|Name|Type|Range|Optional|Default|Description|  
|----------|------------|----------|-----------|--------------|-----------------| 
|Number of classes|Integer|>=2|Required|2|The number of classes for the label.|  
|The bits of hash function|Integer|[12;31]|Required|20|The number of bits of the range of hash function.|  
|The seed of hash function|Integer|any|Required|1|The seed for the hash function.|  
|Module type| | |Required|Dataset|The type of module to use when generating the count table.|  
|Count table type|CountTableType|select from list|Required|Dictionary|Specify the format of the count table.|  

The following options apply when selecting the **blob** option.

|Name|Type|Range|Optional|Default|Description|  
|----------|------------|----------|-----------|--------------|-----------------| 
|Blob name|String|any|Required||The name of the input blob. Do not include container name.|  
|Account name|String|any|Required||The name of the storage account.|  
|Account key|SecureString|any|Required||The key of the storage account.|  
|Container name|String|any|Required||The Azure blob container that contains the input blob.|  
|Count columns|String|any|Required||The one-based indexes of groups of columns to perform counting.|  
|Label column|Integer|>=1|Required|1|The one-based index of the label column.|  
|Blob format| |any| Required|CSV|The blob text file format.|  

The following parameters apply when using **MapReduce** to generate counts:

|Name|Type|Range|Optional|Default|Description|  
|----------|------------|----------|-----------|--------------|-----------------|
|Default storage account name|String|any|Required|none  |The name of the storage account containing the input blob.|
|Default storage account key|SecureString|any|Required|none|The key of the storage account containing the input blob.|
|Default container name |String|any|Required|none|The name of the blob container to write the count table.|
|Cluster URI|String|any|Required|none|The URI to the HDInsight Hadoop cluster.|
|Username|String|any|Required|none|The username to login to the HDInsight Hadoop cluster.| 

The following parameters define the format of the count table:

|Name|Type|Range|Optional|Default|Description|  
|----------|------------|----------|-----------|--------------|-----------------| 
|Count table type|CountTableType| List|Required|Dictionary|Type of the count table.|  
|Label column index or name|ColumnSelection| |Required if count table saved as Dataset|none|Select the label column.|  
|Select columns to count|ColumnSelection| |Required if count table saved as Dataset||Select columns for counting. These columns are considered as categorical features.|  
|Depth of CM sketch table|Integer|>=1|Required if count table uses CMSketch format|4|The depth of the CM sketch table, which equals the number of hash functions.|  
|Width of CM sketch table|Integer|[1;31]|Required if count table uses CMSketch format|20|The width of the CM sketch table, which is the number of bits of the range of hash function.|  
|Label column index or namecolumn|ColumnSelection| |Required if count table saved as Dataset||Selects the label column.|  
|Select columns to count|ColumnSelection| |Required if count table saved as Dataset||Selects columns for counting. These columns are considered as categorical features.|  
|Count table type|  |  |Required if count table saved as Dataset|Dictionary|Specifies the type of the count table.|  
|Depth of CM sketch table|Integer|>=1|Required if count table saved as CMSketch|4|The CM sketch table depth, which equals the number of hash functions.|  
|Width of CM sketch table|Integer|[1;31]|Required if count table saved as CMSketch|20|The CM sketch table width, which is the number of bits of the range of hash function.|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Counting transform|[ITransform interface](itransform-interface.md)|The counting transform.|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](errors/error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
|[Error 0005](errors/error-0005.md)|Exception occurs if parameter is less than a specific value.|  
|[Error 0007](errors/error-0007.md)|Exception occurs if parameter is greater than a specific value.|  
|[Error 0009](errors/error-0009.md)|Exception occurs if Azure storage account name or container name specified incorrectly.|  
|[Error 0065](errors/error-0065.md)|Exception occurs if Azure blob name is specified incorrectly.|  
|[Error 0011](errors/error-0011.md)|Exception occurs if passed column set argument does not apply to any of dataset columns.|  
|[Error 0049](errors/error-0049.md)|Exception occurs in the case when it is not possible to parse a file.|  
|[Error 1000](errors/error-1000.md)|Internal library exception.|  
|[Error 0059](errors/error-0059.md)|Exception occurs if a column index specified in a column picker cannot be parsed.|  
|[Error 0060](errors/error-0060.md)|Exception occurs when an out of range column range is specified in a column picker.|  
|[Error 0089](errors/error-0089.md)|Exception occurs when the specified number of classes is less than the actual number of classes in a dataset used for counting.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Learning with Counts](data-transformation-learning-with-counts.md)
