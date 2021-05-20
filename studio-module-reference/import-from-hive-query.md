---
title: "ML Studio (classic): Import from Hive Query - Azure"
description: Learn how to use the Import Data module to get data from Hadoop clusters and HDInsight distributed storage.
ms.date: 07/03/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Import from Hive Query

This article describes how to use the [Import Data](import-data.md) module in Azure Machine Learning Studio (classic), to get data from Hadoop clusters and HDInsight distributed storage.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

Importing data from Hive is particularly useful for loading large datasets, or if you want to pre-process the data using a MapReduce job before loading the data into a machine learning experiment.

> [!IMPORTANT]
> As of July 31, 2018, Microsoft Azure HDInsight version 3.3 was the last version of HDInsight on Windows. If you have any HDInsight clusters on Windows 3.3 or earlier, you must migrate to HDInsight on Linux (HDInsight version 3.5 or later). Please see the [Retired versions](/azure/hdinsight/hdinsight-component-versioning#retired-versions) section for more information on retired versions of HDInsight. Azure Machine Learning Studio (classic) will support [HDInsight on Linux](#support-for-hdinsight-on-linux) in certain scenarios. 

## Support for HDInsight on Linux

Azure Machine Learning Studio (classic) has support for HDInsight on Linux in the following scenarios:

- Hadoop 2.7.3 (HDI 3.6) Blob as default, ADLS secondary
- Spark 2.1.0 (HDI 3.6) Blob as default, ADLS secondary
- Spark 2.2.0 (HDI 3.6) Blob as default, ADLS secondary
- Spark 2.3.0 (HDI 3.6) Blob as default, ADLS secondary

### Known Issues
There are several known issues with using the Import Data module for Hive Queries with HDInsight on Linux:
- Enterprise Security Package is not supported
- [/tmp/hive not writeable](https://www.qumio.com/Blog/Lists/Posts/Post.aspx?ID=38)


## How to import data from Hive queries

### Use the wizard

The module features a new wizard to help you choose a storage option,  select from among existing subscriptions and accounts, and quickly configure all options.

1. Add the **Import Data** module to your experiment. You can find the module in Studio (classic), in the **Data Input and Output** category.

2. Click **Launch Import Data Wizard** and follow the prompts.

3. When configuration is complete, to actually copy the data into your experiment, right-click the module, and select **Run Selected**. 

If you need to edit an existing data connection, the wizard loads all previous configuration details so that you don't have to start again from scratch

### Manually set import properties

The following steps describe how to manually configure the import source.

1. Add the **Import Data** module to your experiment. You can find the module in Studio (classic), in the **Data Input and Output** category.

2. For **Data source**, select **Hive Query**.

3. In the **Hive database query** text box, specify the data you want to read by using HiveQL.

    HiveQL is a SQL-like query language that can also be used to aggregate data and perform data filtering before you add the data to Machine Learning Studio (classic). However, the Hive query must return the data in a tabular format.

    For example, this statement is a valid Hive query:

     `SELECT <column list> FROM table WHERE <expression>;`

4. Click the **HCatalog server URI** text box, and then type the fully qualified name of your cluster.

    For example, if you created a cluster with the name  mycluster001, use this format: `https://mycluster001.azurehdinsight.net`

5. Click the **Hadoop user account name** text box, and paste in the Hadoop user account that you used when you provisioned the cluster.

6. Click the **Hadoop user account password** text box, and type the credentials that you used when you provisioned the cluster.

    For more information about cluster naming and authentication for Hadoop, see [Provision Hadoop clusters in HDInsight](/azure/hdinsight/hdinsight-hadoop-provision-linux-clusters).

7. For **Location of output data**, select the option that indicates where the data is stored. If the data is in the Hadoop distributed file system (HDFS), it must be accessible via the same account and password that you just entered. If the data is in Azure, provide the location and credentials of the storage account.

    - **HDFS**: Type or paste the HDFS server URI. Be sure to use the HDInsight cluster name **without** the `HTTPS://` prefix.

    - **Azure**: For **Azure storage account name**, type the name of the Azure account. For example, if the full URL of the storage account is `https://myshared.blob.core.windows.net`, you would type `myshared`.

    - **Azure storage key**: Copy and paste the key that is provided for accessing the storage account.

    - For **Azure container name**, specify the **default container** for the cluster. See the [Tips](#bkmk_Notes) section for help figuring out which container to use.

8. Select the **Use cached results** options if you don't expect the data to change much, or if you want to avoid reloading the data each time you run the experiment.

    When this is selected, if there are no other changes to module parameters, the experiment loads the data the first time the module is run, and thereafter uses a cached version of the dataset.

    If you want to re-load the dataset on each iteration of the experiment dataset, deselect the **Use cached results** option. Results are also re-loaded when there are changes to the parameters of [Import Data](import-data.md).

9. Run the experiment.

### Results

When complete, click the output dataset and select **Visualize** to see if the data was imported successfully.

If you get errors, check your data for missing values, additional empty columns, or incompatible data types.


## Examples  

For examples of how to configure an HDInsight cluster and use Hive queries in machine learning experiments, see these resources:

- This article provides a detailed walkthrough of how to create a cluster, upload data, and call the data from Studio (classic) using Hive: [Advanced Analytics Process and Technology in Action: Using HDInsight Hadoop clusters](https://azure.microsoft.com/documentation/articles/machine-learning-data-science-process-hive-criteo-walkthrough/).

- This blog by MVP Vesa Tikkanen describes  some issues and workarounds when reading very large files (distributed queries) from an HD cluster on Linux: [Reading Linux HDInsight Hive from Azure ML](https://www.qumio.com/Blog/Lists/Posts/Post.aspx?ID=38)

Although Hive offers superior features for many kinds of data clean-up and pre-processing, after import, you might find these tools useful for preparing the data for modeling:

- Use the [Edit Metadata](edit-metadata.md) and other modules to change column names, specify which columns contain labels and features, and specify the column data type. For examples, see [Dataset Processing](https://go.microsoft.com/fwlink/?LinkId=525733).

- Post-process text data using Python, to remove punctuation, flag parts of speech, and much more. For examples, see [Text Classification](https://gallery.azureml.net/Experiment/f43e79f47d8a4219bf8613d271ea2c45).

- Combine multiple tables from different sources into a single table of training data. For examples, see [Predictive maintenance](https://gallery.azureml.net/Experiment/df7c518dcba7407fb855377339d6589f).

## <a name="bkmk_Notes"></a> Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### How to determine the default container

If you created your cluster by accepting all defaults, a container with the same name as the cluster was created at the same time the cluster was created. That container is the default container for the cluster. However, if you chose the **CUSTOM CREATE** option when creating a cluster, you are given two options for selecting the default container. The first option is to select an existing container. When you do so, that container becomes the default storage container for the cluster.  The second option is **Create default container**. When you use this option, the default container has the same name as the cluster.

### How to call Python scripts from a Hive query

You can use the [Import Data](import-data.md) module to run Hive queries that call Python UDFs to process records.  

For more information, see [Use Python with Hive and Pig in HDInsight](https://azure.microsoft.com/documentation/articles/hdinsight-python/).  

### Avoiding out of memory problems when using Hive to pre-process data

When using Hive queries to extract records from big data sources, sometimes the default configuration of the Hadoop cluster is too limited to support running the MapReduce job. For example, in these [Release Notes](/azure/hdinsight/hdinsight-release-notes) for HDInsight, the default settings are defined as a four-node cluster.

If the requirements of the MapReduce job exceed available capacity, the Hive queries might return an **Out of Memory** error message, which causes the [Import Data](import-data.md) operation to fail. If this happens, you can change the default memory allocation for Hive queries in the [Import Data](import-data.md) module, as shown here:

![Increase memory to maximum allowed on cluster](media/aml-hivequerymemorylimit.png "AML_HiveQueryMemoryLImit")  

In this example, the commands `set mapreduce.map.memory.mb` and `set mapreduce.reduce.memory.mb` are used to increase the amount of memory, to use the maximum allowed in the cluster.

### Common questions

#### How can I avoid re-loading the same data unnecessarily

If your source data changes, you can refresh the dataset and add new data by re-running [Import Data](import-data.md). However, if you don't want to re-read from the source each time you run the experiment, select the **Use cached results** option to TRUE. When this option is set to TRUE, the module will check whether the experiment has run previously  using the same source and same input options, and if a previous run is found, the data in the cache is used, instead of re-loading the data from the source.

#### Can I filter data as it is being read from the source

The [Import Data](import-data.md) module itself does not support filtering as data is being read.

To filter data before reading it into Azure Machine Learning Studio (classic), use a Hive query or a MapReduce job to aggregate and transform the data.

There are also multiple options for filtering data after it has been loaded into Azure Machine Learning Studio (classic):

- Use a custom R script to get only the data you want.
- Use the [Split Data](split-data.md) module with a relative expression or a regular expression to isolate the data you want, and then save it as a dataset.

> [!NOTE]
> If you find that you have loaded more data than you need, you can overwrite the cached dataset by reading a new dataset, and saving it with the same name as the older, larger data.

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Data source|List|Data Source Or Sink|Azure Blob Storage|Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, an on-premises SQL Server database, a Hive table, or an OData endpoint.|  
|Hive database query|any|StreamReader||HQL query|  
|HCatalog server URI|any|String||Templeton endpoint|  
|Hadoop user account name|any|String||Hadoop HDFS/HDInsight username|  
|Hadoop user account password|any|SecureString||Hadoop HDFS/HDInsight password|  
|Location of output data|any|DataLocation|HDFS|Specify HDFS or Azure for outputDir|  
|HDFS server URI|any|String||HDFS rest endpoint|  
|Azure storage account name|any|String||Azure storage account name|  
|Azure storage key|any|SecureString||Azure storage key|  
|Azure container name|any|String||Azure container name|  
|Data content type|List (subset)|Url Contents|OData|Data format type|  
|Source URL|any|String||URL for Power Query data source|  
|Use cached results|TRUE/FALSE|Boolean|FALSE|description|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with downloaded data|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0027](errors/error-0027.md)|An exception occurs when two objects have to be the same size, but they are not.|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of inputs are null or empty.|  
|[Error 0029](errors/error-0029.md)|An exception occurs when an invalid URI is passed.|  
|[Error 0030](errors/error-0030.md)|An exception occurs in when it is not possible to download a file.|  
|[Error 0002](errors/error-0002.md)|An exception occurs if one or more parameters could not be parsed or converted from the specified type to the type required by the target method.|  
|[Error 0009](errors/error-0009.md)|An exception occurs if the Azure storage account name or the container name is specified incorrectly.|  
|[Error 0048](errors/error-0048.md)|An exception occurs when it is not possible to open a file.|  
|[Error 0015](errors/error-0015.md)|An exception occurs if the database connection has failed.|  
|[Error 0046](errors/error-0046.md)|An exception occurs when it is not possible to create a directory on specified path.|  
|[Error 0049](errors/error-0049.md)|An exception occurs when it is not possible to parse a file.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Import Data](import-data.md)   
 [Export Data](export-data.md)   
 [Import from Web URL via HTTP](import-from-web-url-via-http.md)   
 [Import from Azure SQL Database](import-from-azure-sql-database.md)   
 [Import from Azure Table](import-from-azure-table.md)   
 [Import from Azure Blob Storage](import-from-azure-blob-storage.md)   
 [Import from Data Feed Providers](import-from-data-feed-providers.md)   
 [Import from On-Premises SQL Server Database](import-from-on-premises-sql-server-database.md)
