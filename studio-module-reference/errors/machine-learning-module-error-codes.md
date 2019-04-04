---
title: "Machine learning module error codes | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 01/22/2018
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Machine learning module error codes

This topic lists some of the errors that are reported from modules in Azure Machine Learning Studio, either when an experiment fails, or when you are editing the properties of the module. 

## Error resolution

To resolve the issue, click the error name in the following table and read about common causes. There are two ways to get the full text of an error message in Studio:  
  
- Click the link, **View Output Log**, in the right pane and scroll to the bottom of the. The detailed error message is generally displayed in the last two lines of the window.  
  
- Select the module that has the error, and click the red X. Only the pertinent error text is displayed.  
  
 If the error message text is not helpful, please send us information about the context and any desired additions or changes. You can either submit feedback on the error topic, or visit the Azure Machine Learning forum and post a question.  
  
###  <a name="errors"></a> Exceptions list  
  
|Exception|Description|  
|---------------|-----------------|  
|Error 0000|Internal Error|  
|[Error 0001](error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0002](error-0002.md)|Exception occurs if one or more parameters could not be parsed or converted from specified type into required by target method type.|  
|[Error 0003](error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
|[Error 0005](error-0005.md)|Exception occurs if parameter is less than a specific value.|  
|[Error 0006](error-0006.md)|Exception occurs if parameter is greater than or equal to the specified value.|  
|[Error 0007](error-0007.md)|Exception occurs if parameter is greater than a specific value.|  
|[Error 0008](error-0008.md)|Exception occurs if parameter is not in range.|  
|[Error 0009](error-0009.md)|Exception occurs if Azure storage account name or container name specified incorrectly.|  
|[Error 0010](error-0010.md)|Exception occurs if input datasets have column names that should match but do not.|  
|[Error 0011](error-0011.md)|Exception occurs if passed column set argument does not apply to any of dataset columns.|  
|[Error 0012](error-0012.md)|Exception occurs if instance of class could not be created with passed set of arguments.|  
|[Error 0013](error-0013.md)|Exception occurs if passed to module learner has invalid type.|  
|[Error 0014](error-0014.md)|Exception occurs if amount of column unique values is greater than allowed.|  
|[Error 0015](error-0015.md)|Exception occurs if database connection has failed.|  
|[Error 0016](error-0016.md)|Exception occurs if input datasets passed to the module should have compatible column types but do not.|  
|[Error 0017](error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  
|[Error 0018](error-0018.md)|Exception occurs if input dataset is not valid.|  
|[Error 0019](error-0019.md)|Exception occurs if column is expected to contain sorted values, but it does not.|  
|[Error 0020](error-0020.md)|Exception occurs if number of columns in some of the datasets passed to the module is too small.|  
|[Error 0021](error-0021.md)|Exception occurs if number of rows in some of the datasets passed to the module is too small.|  
|[Error 0022](error-0022.md)|Exception occurs if number of selected columns in input dataset does not equal to the expected number.|  
|[Error 0023](error-0023.md)|Exception occurs if target column of input dataset is not valid for the current trainer module.|  
|[Error 0024](error-0024.md)|Exception occurs if dataset does not contain a label column.|  
|[Error 0025](error-0025.md)|Exception occurs if dataset does not contain a score column.|  
|[Error 0026](error-0026.md)|Exception occurs if columns with the same name is not allowed.|  
|[Error 0027](error-0027.md)|Exception occurs in case when two objects have to be of the same size but are not.|  
|[Error 0028](error-0028.md)|Exception occurs in the case when column set contains duplicated column names and it is not allowed.|  
|[Error 0029](error-0029.md)|Exception occurs in case when invalid URI is passed.|  
|[Error 0030](error-0030.md)|Exception uccurs in the case when it is not possible to download a file.|  
|[Error 0031](error-0031.md)|Exception occurs if number of columns in column set is less than needed.|  
|[Error 0032](error-0032.md)|Exception occurs if argument is not a number.|  
|[Error 0033](error-0033.md)|Exception occurs if argument is Infinity.|  
|[Error 0034](error-0034.md)|Exception occurs if more than one rating exists for a given user-item pair.|  
|[Error 0035](error-0035.md)|Exception occurs if no features were provided for a given user or item.|  
|[Error 0036](error-0036.md)|Exception occurs if multiple feature vectors were provided for a given user or item.|  
|[Error 0037](error-0037.md)|Exception occurs if multiple label columns are specified and just one is allowed.|  
|[Error 0038](error-0038.md)|Exception occurs if number of elements expected should be an exact value, but is not.|  
|[Error 0039](error-0039.md)|Exception occurs if operation has failed.|  
|[Error 0040](error-0040.md)|Exception occurs when calling a deprecated module.|  
|[Error 0041](error-0041.md)|Exception occurs when calling a deprecated module.|  
|[Error 0042](error-0042.md)|Exception occurs when it is not possible to convert column to another type.|  
|[Error 0043](error-0043.md)|Exception occurs when element type does not explicitly implement Equals.|  
|[Error 0044](error-0044.md)|Exception occurs when it is not possible to derive element type of column from the existing values.|  
|[Error 0045](error-0045.md)|Exception occurs when it is not possible to create a column because of mixed element types in the source.|  
|[Error 0046](error-0046.md)|Exception occurs when it is not possible to create directory on specified path.|  
|[Error 0047](error-0047.md)|Exception occurs if number of feature columns in some of the datasets passed to the module is too small.|  
|[Error 0048](error-0048.md)|Exception occurs in the case when it is not possible to open a file.|  
|[Error 0049](error-0049.md)|Exception occurs in the case when it is not possible to parse a file.|  
|[Error 0050](error-0050.md)|Exception occurs in the case when input and output files are the same.|  
|[Error 0051](error-0051.md)|Exception occurs in the case when several output files are the same.|  
|[Error 0052](error-0052.md)|Exception occurs if Azure storage account key is specified incorrectly.|  
|[Error 0053](error-0053.md)|Exception occurs in the case when there are no user features or items for machbox reccomendations.|  
|[Error 0054](error-0054.md)|Exception occurs if there is too few distinct values in the column to complete operation.|  
|[Error 0055](error-0055.md)|Exception occurs when calling a deprecated module.|  
|[Error 0056](error-0056.md)|Exception occurs if columns are selected in a column picker violates the Selected Columns Category constraint.|  
|[Error 0057](error-0057.md)|Exception occurs when attempting to create a file or blob that already exists.|  
|[Error 0058](error-0058.md)|Exception occurs if dataset does not contain the expected label column.|  
|[Error 0059](error-0059.md)|Exception occurs if a column index specified in a column picker cannot be parsed.|  
|[Error 0060](error-0060.md)|Exception occurs when an out of range column range is specified in a column picker.|  
|[Error 0061](error-0061.md)|Exception occurs when attempting to add a row to a DataTable that has a different number of columns than the table.|  
|[Error 0062](error-0062.md)|Exception occurs when attempting to compare two models with different learner types.|  
|[Error 0063](error-0063.md)|Exception occurs when R script evaluation fails with an error.|  
|[Error 0064](error-0064.md)|Exception occurs if Azure storage account name or storage key is specified incorrectly.|  
|[Error 0065](error-0065.md)|Exception occurs if Azure blob name is specified incorrectly.|  
|[Error 0066](error-0066.md)|Exception occurs if a resource could not be uploaded to an Azure Blob.|  
|[Error 0067](error-0067.md)|Exception occurs if a dataset has a different number of columns than expected.|  
|[Error 0068](error-0068.md)|Exception occurs if the specified Hive script is not correct.|  
|[Error 0069](error-0069.md)|Exception occurs if the specified SQL script is not correct.|  
|[Error 0070](error-0070.md)|Exception occurs when attempting to access non-existent Azure table.|  
|[Error 0071](error-0071.md)|Exception occurs if provided credentials are incorrect.|  
|[Error 0072](error-0072.md)|Exception occurs in the case of connection timeout.|  
|[Error 0073](error-0073.md)|Exception occurs if an error occurs while converting a column to another type.|  
|[Error 0074](error-0074.md)|Exception occurs when the Metadata Editor tries to convert a sparse column to categorical.|  
|[Error 0075](error-0075.md)|Exception occurs when an invalid binning function is used when quantizing a dataset.|  
|[Error 0077](error-0077.md)|Exception occurs when unknown blob file write mode passed.|  
|[Error 0078](error-0078.md)|Exception occurs when the HTTP option for Import Data receives a 3xx status code indicating redirection.|  
|[Error 0079](error-0079.md)|Exception occurs if Azure storage container name is specified incorrectly.|  
|[Error 0080](error-0080.md)|Exception occurs when column with all values missing is not allowed by module.|  
|[Error 0081](error-0081.md)|Exception occurs in PCA module if number of dimensions to reduce to is equal to number of feature columns in input dataset, containing at least one sparse feature column.|  
|[Error 0082](error-0082.md)|Exception occurs when a model cannot be successfully deserialized.|  
|[Error 0083](error-0083.md)|Exception occurs if dataset used for training cannot be used for concrete type of learner.|  
|[Error 0084](error-0084.md)|Exception occurs when scores produced from an R Script are evaluated. This is currently unsupported.|  
|[Error 0085](error-0085.md)|Exception occurs when script evaluation fails with an error.|  
|[Error 0086](error-0086.md)|Exception occurs when a counting transform is invalid.|  
|[Error 0087](error-0087.md)|Exception occurs when an invalid count table type is specified for learning with counts modules.|  
|[Error 0088](error-0088.md)|Exception occurs when an invalid counting type is specified for learning with counts modules.|  
|[Error 0089](error-0089.md)|Exception occurs when the specified number of classes is less than the actual number of classes in a dataset used for counting.|  
|[Error 0090](error-0090.md)|Exception occurs when Hive table creation fails.|  
|[Error 0100](error-0100.md)|Exception occurs when an unsupported language is specified for a custom module.|  
|[Error 0101](error-0101.md)|All port and parameter ID's must be unique.|  
|[Error 0102](error-0102.md)|Thrown when a ZIP file cannot be extracted|  
|[Error 0103](error-0103.md)|Thrown when a ZIP file does not contain any .xml files|  
|[Error 0104](error-0104.md)|Thrown when a module definition file references a script that cannot be located|  
|[Error 0105](error-0105.md)|Thrown when a module definition file defines an unsupported parameter type|  
|[Error 0106](error-0106.md)|Thrown when a module definition file defines an unsupported input type|  
|[Error 0107](error-0107.md)|Thrown when a module definition file defines an unsupported output type|  
|[Error 0108](error-0108.md)|Thrown when a module definition file defines more input or output ports than are supported|  
|[Error 0109](error-0109.md)|Thrown when a module definition file defines a column picker incorrectly|  
|[Error 0110](error-0110.md)|Thrown when a module definition file defines a column picker that references a non-existent input port ID|  
|[Error 0111](error-0111.md)|Thrown when a module definition file defines an invalid property|  
|[Error 0112](error-0112.md)|Thrown when a module definition file cannot be parsed|  
|[Error 0113](error-0113.md)|Thrown when a module definition file contains errors|  
|[Error 0114](error-0114.md)|Thrown when building a custom module fails|  
|[Error 0115](error-0115.md)|Thrown when a custom module default script has an unsupported extension|  
|[Error 0121](error-0121.md)|Thrown when SQL write fails because the table is not writeable|  
|[Error 0122](error-0122.md)|Exception occurs if multiple weight columns are specified and just one is allowed.|  
|[Error 0123](error-0123.md)|Exception occurs if column of vectors is specified to be Label column.|  
|[Error 0124](error-0124.md)|Exception occurs if non-numeric or categorical column is specified to be the weight column.|  
|[Error 0125](error-0125.md)|Thrown when schema for multiple datasets do not match.|  
|[Error 0126](error-0126.md)|Exception occurs if the user specifies a SQL domain that is not supported in Azure ML.|  
|[Error 0127](error-0127.md)|Image pixel size exceeds allowed limit.|  
|[Error 0128](error-0128.md)|Number of conditional probabilities for categorical columns exceeds limit.|  
|[Error 0129](error-0129.md)|Number of columns in the dataset exceeds allowed limit.|  


## Error 0130  
 Exception occurs when all rows in the training dataset contain missing values.  
  
 This occurs when some column in the training dataset is empty.  
  
Resolution:   
 Use the [Clean Missing Data](../clean-missing-data.md) module to remove columns with all missing values.  
  
|Exception Messages|  
|------------------------|  
|All rows in training dataset contain missing values.  Consider using the Clean Missing Data module to remove missing values.|  
 

## Error 0131  
 Exception occurs if one or more datasets in a zip file fails to be unzipped and registered correctly  
  
 This error is produced when one or more datasets in a zip file fails to be unzipped and read correctly. You will receive this error if the unpacking fails because the zip file itself or one of the files in it is corrupt, or there is a system error while trying to unpack and expand a file.  
  
Resolution:   
 Use the details provided in the error message to determine how to proceed.  
  
|Exception Messages|  
|------------------------|  
|Upload zipped datasets failed|  
|Zipped dataset {0} failed with the following message: {1}|  
|Zipped dataset {0} failed with a {1} exception with message: {2}|  
  

## Error 0132  
 No file name was specified for unpacking; multiple files were found in zip file.  
  
 This error is produced when no file name was specified for unpacking; multiple files were found in zip file. You will receive this error if the .zip file contains more than one compressed file, but you did not specify a file for extraction in the **Dataset to Unpack** text box, in the **Property** pane of the module. Currently, only one file can be extracted each time the module is run.  
  
Resolution:   
 The error message provides a list of the files found in the .zip file. Copy the name of the desired file and paste it into the **Dataset to Unpack** text box.  
  
|Exception Messages|  
|------------------------|  
|Zip file contains multiple files; you must specify the file to expand.|  
|The file contains more than one file. Please specify the file to expand. The following files were found: {0}|  
  

## Error 0133  
 The specified file was not found in the zip file  
  
 This error is produced when the filename entered in the **Dataset to Unpack** field of the **Property** pane does not match the name of any file found in the .zip file. The most common causes of this error are a typing error or searching the wrong archive file for the file to expand.  
  
Resolution:   
 Revisit the module. If the name of the file you intended to decompress appears in the list of files found, copy the file name and paste it into the **Dataset to Unpack** property box. If you do not see the desired file name in the list, verify that you have the correct .zip file and the correct name for the desired file.  
  
|Exception Messages|  
|------------------------|  
|The specified file was not found int the zip file.|  
|The specified file was not found. Found the following file(s): {0}|  
  

## Error 0134
Exception occurs when label column is missing or has insufficient number of labeled rows.  
  
This error occurs when the module requires a label column, but you did not include one in the column selection, or the label column is missing too many values.

This error can also occur when a previous operation changes the dataset such that insufficient rows are available to a downstream operation. For example, suppose you use an expression in the **Partition and Sample** module to divide a dataset by values. If no matches are found for your expression, one of the datasets resulting from the partition would be empty.

Resolution: 

 If you include a label column in the column selection but it isn’t recognized, use the [Edit Metadata](../edit-metadata.md) module to mark it as a label column.
  
 Use the [Summarize Data](../summarize-data.md) module to generate a report that shows how many values are missing in each column. Then, you can use the [Clean Missing Data](../clean-missing-data.md) module to remove rows with missing values in the label column. 

 Check your input datasets to make sure that they contain valid data, and enough rows to satisfy the requirements of the operation. Many algorithms will generate an error message if they require some minimum number rows of data, but the data contains only a few rows, or only a header.
  
|Exception Messages|
|------------------------|
|Exception occurs when label column is missing or has insufficient number of labeled rows.|  
|Exception occurs when label column is missing or has less than {0} labeled rows|  
  

## Error 0135  
 Only centroid-based cluster is supported.  
  
Resolution:   
 You might encounter this error message if you have attempted to evaluate a clustering model that is based on a custom clustering algorithm that does not use centroids to initialize the cluster.  
  
 You can use [Evaluate Model](../evaluate-model.md) to evaluate clustering models that are based on the  [K-Means Clustering](../k-means-clustering.md) module. For custom algorithms, use the [Execute R Script](../execute-r-script.md) module to create a custom evaluation script.  
  
|Exception Messages|  
|------------------------|  
|Only centroid-based cluster is supported.|  
  

## Error 0136  
 No file name was returned; unable to process the file as a result.  
  
Resolution:   
  
|Exception Messages|  
|------------------------|  
|No file name was returned; unable to process the file as a result.|  
  

## Error 0137  
 Azure Storage SDK encountered an error converting between table properties and dataset columns during read or write.  
  
Resolution:   
  
|Exception Messages|  
|------------------------|  
|Conversion error between Azure table storage property and dataset column.|  
|Conversion error between Azure table storage property and dataset column. Additional information: {0}|  

## Error 0138  
 Memory has been exhausted, unable to complete running of module. Downsampling the dataset may help to alleviate the problem.  
  
 This error occurs when the module that is running requires more memory than is available in the Azure container. This can happen if you are working with a very large dataset and the current operation cannot fit into memory.  
  
Resolution:   
 If you are trying to read a very large dataset and the operation cannot be completed, downsampling the dataset might help.  
  
 If you use the visualizations on datasets to check the cardinality of columns, only some rows are sampled. To get a full report, use [Summarize Data](../summarize-data.md). You can also use the [Apply SQL Transformation](../apply-sql-transformation.md) to check for the number of unique values in each column.  
  
 Sometimes transient loads can lead to this error. Machine support also changes over time. See the [Azure Machine Learning FAQ](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/) for  a description of supported data size.  
  
 Try using [Principal Component Analysis](../principal-component-analysis.md) or one of the provided feature selection methods to reduce your dataset to a smaller set of more feature-rich columns: [Feature Selection](../feature-selection-modules.md)  
  
|Exception Messages|  
|------------------------|  
|Memory has been exhausted, unable to complete running of module.|  
  

## Error 0139  
 Exception occurs when it is not possible to convert a column to another type.  
  
 This error in Azure Machine Learning occurs when you try to convert a column to a different data type, but that type is not supported by the current operation or by the module.  
  
 The error might also appear when a module tries to implicitly convert data to meet requirements of the current module, but the conversion is not possible.  
  
Resolution:   

1. Review your input data and determine the exact data type of the column that you want to use, and the data type of the column that is producing the error. Sometimes you might think the data type is correct, but find that an upstream operation has modified the data type or usage of a column. Use the [Edit Metadata](../edit-metadata.md) module to reset column metadata to its original state. 
2. Look at the module help page to verify the requirements for the specified operation. Determine which data types are supported by the current module, and what range of values is supported. 
3. If values need to be truncated, rounded, or outliers removed, use the [Apply Math Operation](../apply-math-operation.md) or [Clip Values](../clip-values.md) modules to make corrections.
4. Consider whether it is possible to convert or cast the column to a different data type. The following modules all provide considerable flexibility and power for modifying data: 
  
   + [Apply SQL Transformation](../apply-sql-transformation.md)
   + [Execute R Script](../execute-r-script.md)
   + [Execute Python Script](../execute-python-script.md).  

> [!NOTE]
> Still not working? Consider providing additional feedback on the problem, to help us develop better troubleshooting guidance. Just submit feedback on this page and provide the name of the module that generated the error, and the data type conversion that failed.
  
|Exception Messages|  
|------------------------|  
|Not allowed conversion.|  
|Could not convert: {0}.|  
|Could not convert: {0}, on row {1}.|  
|Could not convert column of type {0} to column of type {1} on row {2}.|  
|Could not convert column "{2}" of type {0} to column of type {1} on row {3}.|  
|Could not convert column "{2}" of type {0} to column "{3}" of type {1} on row {4}.| 

## Error 0140  
 Exception occurs if passed column set argument does not contain other columns except label column.  
  
 This error occurs if you connected a dataset to a module that requires multiple columns, including features, but you have provided only the label column.  
  
Resolution:   
 Choose at least one feature column to include in the dataset.  
  
|Exception Messages|  
|------------------------|  
|Specified column set does not contain other columns except label column.|  
  

## Error 0141  
 Exception occurs if the number of the selected numerical columns and unique values in the categorical and string columns is too small.  
  
 This error in Azure Machine Learning occurs when there are not enough unique values in the selected column to perform the operation.  
  
Resolution:   
 Some operations perform statistical operations on feature and categorical columns, and if there are not enough values, the operation might fail or return an invalid result. Check your dataset to see how many values there are in the fature and label columns, and determine whether the operation you are trying to perform is statistically valid.  
  
 If the source dataset is valid, you might also check whether some upstream data maniipulation or metadata operation has changed the data and removed some values.  
  
 If upstream operations include splitting, sampling, or resampling, verify that the outputs contain the expected number of rows and values.  
  
|Exception Messages|  
|------------------------|  
|The number of the selected numerical columns and unique values in the categorical and string columns is too small.|  
|The total number of the selected numerical columns and unique values in the categorical and string columns (currently {0}) should be at least {1}|  
  

## Error 0142  
 Exception occurs when the system cannot load certificate to authenticate.  
  
Resolution:   
  
|Exception Messages|  
|------------------------|  
|The certificate cannot be loaded.|  
|The certificate {0} cannot be loaded. Its thumbprint is {1}.|  
  

## Error 0143  
 Can't parse user-provided URL that is supposed to be from GitHub.  
  
 This error in Azure Machine Learning occurs when you specify an invalid URL and the module requires a valid GitHub URL.  
  
Resolution:   
 Verify that the URL refers to a valid GitHub repository. Other site types are not supported.  
  
|Exception Messages|  
|------------------------|  
|URL is not from github.com.|  
|URL is not from github.com: {0}|  

## Error 0144  
 User-provided GitHub url is missing the expected part.  
  
 This error in Azure Machine Learning occurs when you specify a GitHub file source using an invalid URL format.  
  
Resolution:   
 Check that the URL of the GitHub repository is valid and ends with \blob\ or \tree\\.  
  
|Exception Messages|  
|------------------------|  
|Cannot parse GitHub URL.|  
|Cannot parse GitHub URL (expecting '\blob\\' or '\tree\\' after the repository name): {0}|  

## Error 0145  
 Cannot create the replication directory for some reason.  
  
 This error in Azure Machine Learning occurs when the module fails to create the specified directory.  
  
Resolution:   
  
|Exception Messages|  
|------------------------|  
|Cannot create replication directory.|  
  

## Error 0146  
 When the user files are unzipped into the local directory, the combined path might be too long.  
  
 This error in Azure Machine Learning occurs when you are extracting files but some file names are too long when unzipped.  
  
Resolution:   
 Edit the file names such that combined path and file name is no longer than 248 characters.  
  
|Exception Messages|  
|------------------------|  
|Replication path is longer than 248 characters, shorten the script name or path.|  

## Error 0147  
 Could not download stuff from GitHub for some reason  
  
 This error in Azure Machine Learning occurs when you cannot read or download the specified files from GitHub.  
  
Resolution:   
 The issue might be temporary; you might try accessing the files at another time. Or verify that you have the necessary permissions and that the source is valid.  
  
|Exception Messages|  
|------------------------|  
|GitHub access error.|  
|GitHub access error. {0}|  
  

## Error 0148  
 Unauthorized access issues while extracting data or creating directory.  
  
 This error in Azure Machine Learning occurs when you are trying to create a directory or read data from storage but do not have the necessary permissions.  
  
Resolution:   
  
|Exception Messages|  
|------------------------|  
|Unauthorized access exception while extracting data.|  
  

## Error 0149  
 The user file does not exist inside GitHub bundle.  
  
 This error in Azure Machine Learning occurs when the specified file cannot be found.  
  
Resolution: 
  
|Exception Messages|  
|------------------------|  
|GitHub file is not found.|  
|GitHub file is not found.: {0}|  
  

## Error 0150  
 The scripts that come from the user package could not be unzipped, most likely because of a collision with Github files.  
  
 This error in Azure Machine Learning occurs when a script cannot be extracted, typically when there is an existing file of the same name.  
  
Resolution:
  
|Exception Messages|  
|------------------------|  
|Unable to unzip the bundle; possible name collision with GitHub files.|  
  

## Error 0151  
 There was an error writing to cloud storage. Please check the URL.  
  
 This error in Azure Machine Learning occurs when the module tries to write data to cloud storage but the URL is unavailable or invalid.  
  
Resolution: Check the URL and verify that it is writable.  
  
|Exception Messages|  
|------------------------|  
|Error writing to cloud storage (possibly a bad url).|  
|Error writing to cloud storage: {0}. Please check the url.|  
  
## Error 0152  
 The Azure cloud type was specified incorrectly in the module context.  
  
|Exception messages|  
|------------------------|  
|Bad Azure Cloud Type|  
|Bad Azure Cloud Type: {0}|  
  
## Error 0153  
 The storage end point specified is invalid.  
  
|Exception Messages|  
|------------------------|  
|Bad Azure Cloud Type|  
|Bad Storage End Point: {0}|  

## Error 0154  
 The specified server name could not be resolved  
  
|Exception Messages|  
|------------------------|  
|The specified server name could not be resolved|  
|The specified server {0}.documents.azure.com could not be resolved|

## Error 0155  
 The DocDb Client threw an exception  
  
|Exception Messages|  
|------------------------|  
|The DocDb Client threw an exception|  
|DocDb Client: {0}|

## Error 0156  
 Bad response for HCatalog Server.  
  
|Exception Messages|  
|------------------------|  
|Bad response for HCatalog Server. Check that all services are running.|  
|Bad response for HCatalog Server. Check that all services are running. Error details: {0}|

## Error 0157  
 There was an error reading from Azure Cosmos DB due to inconsistent or different document schemas. Reader requires all documents to have the same schema.  
  
|Exception Messages|  
|------------------------|  
|Detected documents with different schemas. Please make sure all documents have the same schema|

## Error 1000  
Internal library exception.  
  
This error is provided to capture otherwise unhandled internal engine errors. Therefore, the cause for this error might be very different depending on the module that generated the error.  
  
To get more help, we recommend that you post the detailed message that accompanies the error to the Azure Machine Learning forum, together with a description of the scenario, including the data used as inputs. This feedback will help us to prioritize errors and identify the most important issues for further work.  
  
|Exception Messages|  
|------------------------|  
|Library exception.|  
|Library exception: {0}|  
|{0} library exception: {1}|  
  

## More help  
[Module error codes](../machine-learning-module-error-codes.md)

Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
+ [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
+ [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
 