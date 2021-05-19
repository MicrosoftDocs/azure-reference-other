---
title: "ML Studio (classic): Export to Azure Table - Azure"
description: Learn how to use the Export Data module to export results or intermediate data from a machine learning experiment to an Azure table.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Export to Azure Table

This article describes how to use the **Export to Azure** option in the [Export Data](export-data.md) module in Azure Machine Learning Studio (classic).

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

This option is useful when you want to export results or intermediate data from a machine learning experiment to an Azure table. The Azure table service is a data management service in Azure that can store large amounts of structured, non-relational data. It is a NoSQL data store that accepts authenticated calls from inside and outside Azure.

## How to export data to an Azure table

1. Add the [Export Data](export-data.md) module to your experiment. You can find this module in the [Data Input and Output](data-input-and-output.md) category in Studio (classic).

2. Connect it to the module that produces the data that you want to export to Azure table storage.

3. Specify whether you want to export data to a public shared resource or to a private storage account that requires login credentials, by setting the **Authentication type** option.

    - **Public (SAS URL)**: Choose this option if the account supports access via *SAS URL*. In the **Table SAS URI** field, type or paste the full URI that defines the account and the public blob.

        The SAS URL is a time bound access URL that you can generate by using an Azure storage utility. In a page accessible via SAS URL, data can be stored using only these formats: CSV, TSV, and ARFF.

    - **Account**: Choose this option if your data is in a **private** account. You must also supply credentials including the account name and the key.

4. If you want to export your data to secured, private storage, provide the credentials needed for accessing the account:

    - **Table account name**: Type or paste the name of the account that contains the blob you want to access. For example, if the full URL of the storage account is `https://myshared.table.core.windows.net`, you would type `myshared`.

    - **Table account key**: Paste the access key that is associated with the storage account.

    - **Table name**: Type the name of the specific table that you want to read.

5. Specify which columns to save to the table store, and which columns to use in defining the table schema, by using the column properties.

    - **Partition key**: Choose the column that should be used for partitioning the saved dataset for the table in Azure Storage. Tables in Azure are partitioned to support load balancing across storage nodes. All table entities are organized by partition; therefore, the **PartitionKey** property is required for all table operations.

    - **Azure table row key**: Choose the column that should be used for the **RowKey** property. The RowKey property is a system property that is required for every entity in a table. Along with the **PartitionKey** property, it forms a unique index for every row in the table.

    > [!NOTE]
    > You must use different columns for **RowKey** and **PartitionKey**. Make sure that any column you select for the RowKey or PartitionKey is also included in the list of destination columns, or an error is raised.

    - **Azure table origin columns**: Select any additional columns from the dataset that you want to save to the Azure table. You must also include the columns selected for **PartitionKey** and **RowKey**.

     For more information about tables in Azure Storage, see [Understanding the Table Service Data Model](/rest/api/storageservices/Understanding-the-Table-Service-Data-Model).

6. Specify the names of the columns to write to the table.

    > [!IMPORTANT]
    > You must provide a column name for every column that you output to the table, including the **RowKey**, **PartitionKey**, and all origin columns. 
    > 
    > If the number of column names you provide does not match the number of output columns, an error is raised.
    > 
    > If you type new column names, they must be provided in the order of the column indexes of the source columns.

7. **Azure table write mode**: Indicate how you want the [Export Data](export-data.md) to behave when data already exists in the Azure table.

    - **Insert**: The `Insert Entity` operation inserts a new entity with a unique primary key, which is formed from a combination of the **PartitionKey** and the **RowKey** properties.

    - **Merge**: The `Merge Entity` operation updates an existing entity by updating the entity's properties. This operation does not replace the existing entity.

    - **Replace**: The `Update Entity` operation replaces the contents of the given entity in a table.

    - **InsertOrReplace**: The `InsertOrReplace Entity` operation inserts the entity if the entity does not exist. If the entity exists, it replaces the existing one.

    - **InsertOrMerge**: The `InsertOrMerge Entity` operation inserts the entity if the entity does not exist. If the entity exists, it merges the provided entity properties with the already existing ones.

8. **Use cached results**: Indicate whether you want the data to be refreshed each time the experiment is run.

    If you select this option, the [Export Data](export-data.md) module saves data to the specified table the first time the experiment is run, and thereafter not perform writes, unless there are upstream changes.

    If you deselect this option, the data is written to the destination each time the experiment is run, regardless of whether the data is the same or not.

9. Run the experiment.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Common questions

#### Why did I get an error when writing to an existing Table

Check the schema of the table to make sure the columns names and data types are the same. For example, in Azure table storage, the ID column is expected to be a string.

If you get the error, *Error 0027: The size of passed objects is inconsistent*, verify that the table exists in the specified container. Currently Azure ML can write only to existing tables.

#### Why do I get the error that an existing column cannot be found

If you have not run the experiment, upstream columns are sometimes not detected by the [Export Data](export-data.md). If you make any upstream changes in the experiment, you might need to remove the [Export Data](export-data.md) module and then add and reconfigure it.

#### How can I avoid re-writing the same data unnecessarily

If the data in your experiment changes for any reason, the [Export Data](export-data.md) module will always write the new data.

However, if you are running the experiment with other change that do not affect results, set the **Use cached results** option to TRUE. The module will check whether the experiment has run previously  using the same options, and if a previous result is found, the data will not be written to the Azure table.  

#### Can I export data to a different geographical region

Yes. However, if the storage account is in a different region from the compute node used for the machine learning experiment, data access might be slower. Further, you are charged for data ingress and egress on the subscription.

## Examples

For examples of how to use these machine learning modules, see the [Azure AI Gallery](https://gallery.azure.ai).

## Module parameters

### Public or SAS - Public options

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Table SAS URI|any|String|||  

### Account - Private account options

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Table account name|||||  
|Table account key|any|SecureString|||  

### Storage options

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Table name||String|none||  
|Partition key|any|SecureString|none|Choose the column to use as the key when partitioning the table. If no column is selected, the column name as the partition key for all entries|  
|Azure table row key|any|ColumnPicker|none|Choose the column that contains the unique identifier for table rows. Defaults to a GUID based row key|  
|Azure table origin columns|any|ColumnPicker|none|Specify which columns to include in the table, either by name or by column index|  
|Azure table destination columns|any|String|none|Type the names of the columns to use in the destination table|  
|Azure table write mode|List: Insert,  Merge, Replace, InsertOrReplace, InsertOrMerge|Enum|none||  
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
 [Export to Hive Query](export-to-hive-query.md)
