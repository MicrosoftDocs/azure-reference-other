---
title: "ML Studio (classic): Export to Hive Query - Azure"
description: Learn how to use the Export Data module to save your machine learning experiment data to a Hadoop cluster or HDInsight distributed storage.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Export to Hive Query

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

This article describes how to use the **Export data to Hive** option in the [Export Data](export-data.md) module in Machine Learning Studio (classic). This option is useful when you are working with very large datasets, and want to save your machine learning experiment data to a Hadoop cluster or HDInsight distributed storage. You might also want to export intermediate results or other data to Hadoop so that you can process it using a MapReduce job.

## How to export data to Hive

1. Add the [Export Data](export-data.md) module to your experiment. You can find this module in the [Data Input and Output](data-input-and-output.md) category in Machine Learning Studio (classic).

    Connect the module to the dataset you want to export.

2. For **Data source**, select **Hive Query**.

3. For **Hive table name** type the name of the Hive table in which to store the dataset.

4. In the **HCatalog server URI** text box, type the fully qualified name of your cluster.

    For example, if you created a cluster with the name `mycluster001`, use this format:

    `https://mycluster001.azurehdinsight.net`

5. In the **Hadoop user account name** text box, paste in the Hadoop user account that you used when you provisioned the cluster.

6. In the **Hadoop user account password** text box, type the credentials that you used when you provisioned the cluster.

7. For **Location of output data**, select the option that indicates where the data should be stored: HDFS, or Azure.

    If the data is in the Hadoop distributed file system (HDFS), it must be accessible via the same account and password that you just entered.

    If the data is in Azure, provide the location and credentials of the storage account.

8. If you selected the **HDFS** option, for **HDFS server URI**, specify the HDInsight cluster name without the `https://` prefix.

9. If you selected the **Azure** option, provide the storage account name, and the credentials the module can use to connect to storage.

    - **Azure storage account name**: Type the name of the Azure account. For example, if the full URL of the storage account is `https://myshared.blob.core.windows.net`, you would type `myshared`.

    - **Azure storage key**: Copy and paste the key that is provided for accessing the storage account.

    - **Azure container name**: Specify the **default container** for the cluster. For tips son how to figure out the default container, see the [Technical notes](#TechnicalNotes) section.

10. **Use cached results**:  Select this option if you want to avoid rewriting the Hive table each time you run the experiment. If there are no other changes to module parameters, the experiment writes the Hive table only the first time the module is run, or when there are changes to the data.

    If you want to write the Hive table each time the experiment is run, deselect the **Use cached results** option.

11. Run the experiment.

## Examples

For examples of how to use the [Export Data](export-data.md) module, see the [Azure AI Gallery](https://gallery.azure.ai).

+ [Advanced Analytics Process and Technology in Action: Using HDInsight Hadoop clusters](/azure/machine-learning/team-data-science-process/hive-criteo-walkthrough): This article provides a detailed walkthrough of how to create a cluster, upload data, and call the data from Studio (classic) using Hive.

## <a name="TechnicalNotes"></a> Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Common questions

#### How to avoid out of memory problems when writing large datasets

Sometimes the default configuration of the Hadoop cluster is too limited to support running the MapReduce job. For example, in these [Release Notes](/azure/hdinsight/hdinsight-release-notes) for HDInsight, the default settings are defined as a four-node cluster.

If the requirements of the MapReduce job exceed available capacity, the Hive queries might return an **Out of Memory** error message, which causes the [Export Data](export-data.md) operation to fail. If this happens, you can change the default memory allocation for Hive queries.

#### How to avoid re-loading the same data unnecessarily

If you don't want to recreate the Hive table each time you run the experiment, select the **Use cached results** option to TRUE. When this option is set to TRUE, the module will check whether the experiment has run previously, and if a previous run is found, the write operation is not performed.

### Usage tips

It can be hard to figure out the default container for the cluster. Here are some tips:

+ If you created your cluster by using the default settings, a container with the same name was created at the same time that the cluster was created. That container is the default container for the cluster.

+ If you created the cluster by using the **CUSTOM CREATE** option, you were given two options for selecting the default container.

    **Existing container**: If you selected an existing container, that container is the default storage container for the cluster.

    **Create default container**: If you selected this option, a container with the same name as the cluster was created, and you should specify that container name as the default container for the cluster.

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Data source|List|Data Source Or Sink|Azure Blob Storage|Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, a Hive table or an OData endpoint.|  
|Hive table name|any|String|none|Name of table in Hive|  
|HCatalog server URI|any|String|none|Templeton endpoint|  
|Hadoop user account name|any|String|none|Hadoop HDFS/HDInsight username|  
|Hadoop user account password|any|SecureString|none|Hadoop HDFS/HDInsight password|  
|Location of output data|any|DataLocation|HDFS|Specify HDFS or Azure for outputDir|  
|HDFS server URI|any|String|none|HDFS rest endpoint|  
|Azure storage account name|any|String|none|Azure storage account name|  
|Azure storage key|any|SecureString|none|Azure storage key|  
|Azure container name|any|String|none|Azure container name|  
|Use cached results|TRUE/FALSE|Boolean|FALSE|Module only executes if valid cache does not exist; otherwise use cached data from prior execution.|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0027](errors/error-0027.md)|An exception occurs when two objects have to be the same size, but they are not.|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of inputs are null or empty.|  
|[Error 0029](errors/error-0029.md)|An exception occurs when an invalid URI is passed.|  
|[Error 0030](errors/error-0030.md)|an exception occurs in when it is not possible to download a file.|  
|[Error 0002](errors/error-0002.md)|An exception occurs if one or more parameters could not be parsed or converted from the specified type to the type required by the target method.|  
|[Error 0009](errors/error-0009.md)|An exception occurs if the Azure storage account name or the container name is specified incorrectly.|  
|[Error 0048](errors/error-0048.md)|An exception occurs when it is not possible to open a file.|  
|[Error 0046](errors/error-0046.md)|An exception occurs when it is not possible to create a directory on specified path.|  
|[Error 0049](errors/error-0049.md)|An exception occurs when it is not possible to parse a file.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Import Data](import-data.md)   
 [Export Data](export-data.md)   
 [Export to Azure SQL Database](export-to-azure-sql-database.md)   
 [Export to Azure Blob Storage](export-to-azure-blob-storage.md)   
 [Export to Azure Table](export-to-azure-table.md)
