---
title: "ML Studio (classic): Import from Azure Blob Storage - Azure"
description: Learn how to use the Import Data module to read data from Azure Blob Storage, so that you can use the data in a machine learning experiment.  
ms.date: 09/28/2020
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: likebupt
ms.author: amlstudiodocs

---
# Import from Azure Blob Storage

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This topic describes how to use the [Import Data](import-data.md) module in Machine Learning Studio (classic), to read data from Azure Blob Storage, so that you can use the data in a machine learning experiment.  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

The Azure Blob Service is for storing large amounts of data, including binary data. Azure blobs can be accessed from anywhere, by using either HTTP or HTTPS. Authentication might be required depending on the type of blob storage. 

- Public blobs can be accessed by anyone, or by users who have a SAS URL.
- Private blobs require a login and credentials.

Importing from blob storage requires that data be stored in blobs that use the **block blob** format. The files stored in the blob must use either comma-separated ( CSV) or tab-separated (TSV) formats. When you read the file, the records and any applicable attribute headings are loaded as rows into memory as a dataset.
> [!NOTE]
> Import data module does not support connecting to Azure Blob Storage account if "Secure Transfer Required" option is enabled. 

For other restrictions on the types of blob storage supported for use with Machine Learning, see the [Technical notes](#bkmk_Notes) section.

> [!TIP]
> Need to import data in a format that's not supported? You can use Python or R. See this sample in the Azure AI Gallery: [Load non-text file from Azure Blob Storage](https://gallery.azure.ai/Experiment/Load-non-text-file-from-Azure-Blob-Storage-1) 

## How to import data from Azure blobs

We strongly recommend that you profile your data before importing, to make sure that the schema is as expected. The import process scans some number of head rows to determine the schema, but later rows might contain extra columns, or data that cause errors.

### Use the Data Import Wizard

The module features a new wizard to help you choose a storage option, select from among existing subscriptions and accounts, and quickly configure all options.

1. Add the **Import Data** module to your experiment. You can find the module in Studio (classic), in the **Data Input and Output** category.

2. Click **Launch Import Data Wizard** and follow the prompts.

3. When configuration is complete, to actually copy the data into your experiment, right-click the module, and select **Run Selected**. 

If you need to edit an existing data connection, the wizard loads all previous configuration details so that you don't have to start again from scratch.

### Manually set properties in the Import Data module

The following steps describe how to manually configure the import source.

1. Add the **Import Data** module to your experiment. You can find this module in Studio (classic), in the [Data Input and Output](data-input-and-output.md) category.

2. For **Data source**, select **Azure Blob Storage**.

3. For **Authentication type**, choose **Public (SAS URL)** if you know that the information has been provided as a public data source. A SAS URL is a time-bound URL for public access that you can generate by using an Azure storage utility.

    Otherwise choose **Account**.

4. If your data is in a **public** blob that can be accessed by using a SAS URL, you do not need additional credentials because the URL string contains all the information that is needed for download and authentication.

    In the **URI** field, type or paste the full URI that defines the account and the public blob.

    > [!NOTE]
    > In a page accessible via SAS URL, data can be stored using only these formats: CSV, TSV, and ARFF.

5. If your data is in a **private** account, you must supply credentials including the account name and the key.

    - For **Account name**, type or paste the name of the account that contains the blob you want to access.

        For example, if the full URL of the storage account is `https://myshared.blob.core.windows.net`, you would type `myshared`.

    - For **Account key**, paste the storage access key that is associated with the account.

        If you don’t know the access key, see the section, “Manage your Azure storage accounts” in this article: [About Azure Storage Accounts](/azure/storage/storage-create-storage-account).

6. For **Path to container, directory, or blob**, type the name of the specific blob that you want to retrieve.

    For example, if you uploaded a file named **data01.csv** to the container **trainingdata** in an account named **mymldata**, the full URL for the file would be: `https://mymldata.blob.core.windows.net/trainingdata/data01.txt`.

    Therefore, in the field  **Path to container, directory, or blob**, you would type: `trainingdata/data01.csv`

    To import multiple files, you can use the wildcard characters `*` (asterisk) or `?` (question mark).

    For example, assuming the container `trainingdata` contains multiple files of a compatible format, you could use the following specification to read all the files starting with `data`, and concatenate them into a single dataset:

    `trainingdata/data*.csv`

    You cannot use wildcards in container names. If you need to import files from multiple containers, use a separate instance of the **Import Data** module for each container, and then merge the datasets using the [Add Rows](add-rows.md) module.

    > [!NOTE]
    > If you have selected the option, **Use cached results**, any changes that you make to the files in the container do not trigger a refresh of the data in the experiment.

7. For **Blob file format**, select an option that indicates the format of the data that is stored in the blob, so that Machine Learning can process the data appropriately. The following formats are supported:

    - **CSV**: Comma-separated values (CSV) is the default storage format for exporting and importing files in Machine Learning. If the data already contains a header row, be sure to select the option, **File has header row**, or the header will be treated as a data row.

        For more information about the CSV format used in Machine Learning, see [Convert to CSV](convert-to-csv.md

    - **TSV**: Tab-separated values (TSV) is a format used by many machine learning tools. If the data already contains a header row, be sure to select the option, **File has header row**, or the header will be treated as a data row.

        For more information about the TSV format used in Machine Learning, see [Convert to TSV](convert-to-tsv.md).

    - **ARFF**: This format supports importing files in the format used by the Weka toolset. For more information, see [Convert to ARFF](convert-to-arff.md).

    - **CSV with a specified encoding**: Use this option for CSV files that might have been prepared using a different field separator, or if the source might have used a different character encoding than UTF-8. This format is not supported for files stored in a SAS URL.

    - **Excel**: Use this option to read data from Excel workbooks stored in Azure Blob Storage. The Excel format is not supported for files stored in a SAS URL.

8. For CSV files with special encodings, set these additional options to control proper import of the characters:

    - **Comma delimiter format**: Choose from a list of common characters used as field separators, including the comma `,` tab character, and semicolon `;`.

    - **Encoding format**: Choose the character encoding used by the file you want to read. See the [Technical notes](#bkmk_Notes) section for a list of supported encodings.

    - **File has header row**: Select this option if the data already contains a header row. Otherwise, the header is imported as a data row.

9. For Excel files, after specifying the account and container where the Excel file is stored, you must indicate the Excel format and range or table name, using these options:

    - **Excel data format**: Indicate whether the data is in an Excel worksheet range, or in an Excel table.

    - **Excel sheet or embedded table**: If you select the **Excel sheet** option, specify the name of the worksheet (the tab name) or a table embedded in the workbook. All data from the sheet is read; you cannot specify a range of cells. If you select the **Excel table** option, you must get the table name and not the sheet name, even if there is only one  table on a sheet. To view the table name, click inside the table and then view the **Table Name** property in the **Table Tools** tab.

10. Run the experiment.

## Examples

To learn how to use data from Azure Blob Storage in machine learning experiments, see the [Azure Gallery](https://gallery.azure.ai):

- [News Categorization sample](https://go.microsoft.com/fwlink/?LinkId=525167): Loads and then combines multiple datasets from Azure Blob Storage.

- [Student Performance sample](https://go.microsoft.com/fwlink/?LinkId=525727): Reads data that is stored in the TSV format from Azure Blob Storage.

## <a name="bkmk_Notes"></a> Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Common questions

#### Is there any way of automating data import?

There are a variety of ways to get new data and use it to regularly update an experiment. Much depends on where the source data originates, and the tools you prefer for data movement. see these articles for some ideas.

- [Cheat sheet: automated data pipeline for Machine Learning](/azure/machine-learning/machine-learning-automated-data-pipeline-cheat-sheet)

- [Use SSIS to move data to Blob storage](/azure/machine-learning/machine-learning-data-science-move-data-to-azure-blob-using-ssis)

- [Retrain experiments programmatically](/azure/machine-learning/classic/retrain-machine-learning-model)

Automating the execution of the experiment generally requires creation of a web service, which can then be triggered by  a task scheduler, PowerShell, or other custom code.

#### Why did I get an error when I tried to read input data from an existing blob?

There are several possible issues:

- The blob uses an unsupported format
- The account itself was created using an option that is not yet supported by Machine Learning.

**Unsupported format**: When reading from Azure Blob Storage, currently Machine Learning requires that the blob use the *block blob* format, which lets you upload large blobs efficiently. For example, if you upload a CSV file to blob storage, the file would be stored as  a block blob. However, when you create a blob file programmatically, you might be generating a different type of blob, such as the AppendBlob type, which is not supported.

As a workaround, we recommend that you use the **block blob** type.

> [!IMPORTANT]
> After the blob has been created, the type cannot be changed.

For more information, see [Understanding Block Blobs, Append Blobs, and Page Blobs](/rest/api/storageservices/understanding-block-blobs--append-blobs--and-page-blobs).

**Unsupported account type**: The import and export modules can read and write data only from Azure storage accounts that were created using the Classic deployment model. In other words, the new Azure Blob Storage account type that offers a hot and cool storage access tiers is not yet supported.  Generally, any Azure storage accounts that you might have created before this service option became available should not have been affected.

If you need to create a new account for use with Machine Learning, select **Classic** for the **Deployment model**, or use **Resource manager** and for **Account kind**, select **General purpose** rather than **Blob storage**.

#### How can I avoid re-loading the same data unnecessarily?

If your source data changes, you can refresh the dataset and add new data by re-running [Import Data](import-data.md). However, if you don't want to re-read from the source each time you run the experiment, select the **Use cached results** option to TRUE. When this option is set to TRUE, the module will check whether the experiment has run previously  using the same source and same input options, and if a previous run is found, the data in the cache is used, instead of re-loading the data from the source.

#### Can I filter data as it is being read from the source?

The **Import Data** module does not support filtering as data is being read.

After you have loaded the data into Machine Learning Studio (classic), you can modify the data with these tools:

- Use a custom R script to filter or transform data.

- Use the [Split Data](split-data.md) module with a relative expression or a regular expression to isolate the data you want, and then save it as a dataset.

If you find that you have loaded more data than you need, you can overwrite the dataset by reading a new dataset and specify that it be saved with the same name as the older, larger data.

#### Why does the import process add an extra row at the end of my dataset when it finds a trailing new line?

If the **Import Data** module encounters a row of data that is followed by an empty line or a trailing new line character, an extra row containing missing values is added at the end of the table.

The reason for interpreting a trailing new line as a new row is that **Import Data** cannot determine the difference between an actual empty line and an empty line that is created by the user pressing ENTER at the end of a file.

Because some machine learning algorithms support missing data and would thus treat this line as a case (which in turn could affect the results), you should use [Clean Missing Data](clean-missing-data.md) to check for missing values, and remove them as needed.

Before you check for empty rows, you might also want to separate the final empty row from other rows with partial missing values, which might represent actual missing values in the source data. To do this, you can divide the dataset by using [Split Data](split-data.md). Select the **Select head N rows** option to read all rows but the  final row.  

#### What happens if you import data loaded from different geographical regions?


If the blob or table storage account is in a different region from the compute node used for the machine learning experiment, data access might be slower. Further, you are charged for data ingress and egress on the subscription.  

#### Why are some characters in my source file not displayed correctly in the header?

Machine Learning generally supports UTF-8 encoding. If your source file uses another type of encoding, the characters might not be imported correctly.  

If you have trouble loading data correctly, try using the option **CSV with encoding** and specify parameters for custom delimiters, the code page, and so forth.  
  
#### Are there any prohibited characters or characters that are changed during import?

If attribute data contains quotation marks or escaped character sequences, they are handled by using the rules for such characters in Microsoft Excel. All other characters are handled by using the following specifications as a guideline: [RFC 4180](https://tools.ietf.org/html/rfc4180).  

#### I need to import a very large file. What is the recommended method?

The size limit for uploading local datasets directly to Machine Learning is 1.98 GB. With very large files, adding the dataset to your experiment account can take a long time to complete. 

- Estimate 10 minutes or more per GB of data. 
- To optimize performance, use a storage account in the same region that Azure ML service uses.

To upload larger files, up to 10 GB, there are several approaches:

- **Use a zipped file.** You can upload datasets to Azure ML Studio (classic) in zipped format, and then use the [Unpack Zipped Datasets](unpack-zipped-datasets.md) module to unpack and save the dataset. Zipped datasets can also be unpacked using the [Execute R Script](execute-r-script.md) module but performance might be limited.

- **Use a fast Azure utility such as AzCopy.** Stage the data to Microsoft Azure Blob Storage using   a utility such as [AzCopy](https://azure.microsoft.com/documentation/articles/storage-use-azcopy/). Then, use the [Import Data](import-data.md) module to import data from blob storage to Studio (classic).

    For example, the following code shows the AzCopy syntax for writing to blob storage.

    ```text
    cd "C:\Program Files (x86)\Microsoft SDKs\Azure\AzCopy"
    .\AzCopy.exe /Source:C:\LocalFolder /Dest:https://mystorage.blob.core.windows.net/mycontainer /DestKey:MyStorageAccountKey /Pattern:myfile.csv
    ```

#### I imported a CSV file using a specified encoding but the text is not displayed  correctly when I use the option to visualize. Why?

For uploaded datasets, Machine Learning generally supports only UTF-8. However, the **Import Data** module supports additional encoding formats. Therefore, after you have imported a file using one of these formats, you might find that the characters are not displaying correctly. The solution is to convert the encoding to UTF-8 using one of these methods: 

- Save the imported data as a dataset. (Using a saved dataset instead of the CSV data also might improve performance.)

- If you are using the dataset in the [Execute R Script](execute-r-script.md) module, you can enforce the correct coding using script such as this:

    ```R
    dataset <- maml.mapInputPort(1)
    Encoding(dataset$city) <- "UTF-8"
    maml.mapOutputPort("dataset")
    ```

    You can then use **Visualize** on the output of the Execute R Script module and verify that characters are displayed correctly.

#### What options do I have for importing text files? The CSV is not appropriate for my data.

Processing and cleaning unstructured text to fit neatly in columns is always a challenge. However, if  you need to import columns of text data, the TSV format often presents fewer difficulties, though you still need to check for excess tab characters in advance.

We recommend that you review the [Text Classification template](https://gallery.azure.ai/Collection/Text-Classification-Template-1), in the [Azure AI Gallery](https://gallery.azure.ai/), to see an example of text ingestion and processing in Machine Learning Studio (classic).

###  Custom encoding for CSV files  

Early versions of the **Import Data** module did not support some kinds of valid CSV files. For example, data exported from Excel sometimes contained characters that prevented the file from parsing correctly.

To support a wider possible range of delimiters and character formats, **Import Data** now supports choosing the delimiter and encoding format. If you use the **CSV with encoding** option, the result is a more robust and efficient parsing of the CSV file.

You can use the following character encodings:

|Type|Encoding|  
|----------|--------------|  
|Unicode|Unicode (UTF-8)<br /><br /> Unicode<br /><br /> Unicode (UTF-32)<br /><br /> Unicode (UTF-7)|  
|CJYK|Chinese Traditional (Big5)<br /><br /> Chinese Simplified (GB2312)<br /><br /> Chinese Simplified (Mac)<br /><br /> Chinese Simplified (GB2312-80)<br /><br /> Chinese Simplified (ISO-2022)<br /><br /> Chinese Simplified (GB18030)<br /><br /> Japanese (JIS)<br /><br /> Korean (ISO)<br /><br /> Korean (Mac)|  
|Other|Western European (Windows)<br /><br /> Western European (ISO)<br /><br /> Hebrew (ISO-Visual)<br /><br /> US ASCII|  

> [!TIP]
> After the CSV import is complete, we recommend that you save imported files as a dataset to ensure that the imported data uses the UTF-8 encoding in your experiment.

### Data type inference in CSV and TSV formats

When the **Import Data** module loads data from a CSV or TSV file in Azure Blob Storage, a type guesser looks for categorical or numerical data in the source file, and represents the discovered type in the metadata for the new dataset.  

However, you can override the results of the type guesser by editing the column attributes in the [Edit Metadata](edit-metadata.md) module after the data has been loaded.

## Module parameters

### General options

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Data source|List|Data Source Or Sink|Azure Blob Storage|Data source can be HTTP, FTP, anonymous HTTPS or FTPS, a file in Azure BLOB storage, an Azure table, an Azure SQL Database, an on-premises SQL Server database, a Hive table, or an OData endpoint.|  
|Authentication type|PublicOrSas/Account|String|Account|Specify whether the data is in a public container accessible via SAS URL, or is in a private storage account that requires authentication for access.|  
|Use cached results|TRUE/FALSE|Boolean|FALSE|Select to avoid loading data between runs|  

### Public or SAS - Public storage options

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|URI|any|String|none|HDFS rest endpoint|  
|File format|ARFF, CSV, or TSV|String|CSV|Select one of the supported formats|  
|URI has header row|Boolean|TRUE/FALSE|TRUE|True if the file contains a header row; if False, the first row of data is used as the column headings|  

### Account - Private storage options

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Account name|any|String|none|Type the name of the storage account|  
|Account key|any|SecureString|none|Paste the account key|  
|Path to container, directory, or blob|any|String|N/A|Type the container or directory name|  
|Blob file format|ARFF, CSV, or TSV|String|CSV|Select one of the supported formats|  
|File has header row|any|String|True|Azure storage account name|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with imported data|  

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
 [Import from Web URL via HTTP](import-from-web-url-via-http.md)   
 [Import from Hive Query](import-from-hive-query.md)   
 [Import from Azure SQL Database](import-from-azure-sql-database.md)   
 [Import from Azure Table](import-from-azure-table.md)   
 [Import from Data Feed Providers](import-from-data-feed-providers.md)   
 [Import from On-Premises SQL Server Database](import-from-on-premises-sql-server-database.md)
