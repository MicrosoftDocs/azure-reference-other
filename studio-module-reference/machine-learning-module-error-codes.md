---
title: "Machine Learning Module Error Codes | Microsoft Docs"
ms.custom: ""
ms.date: 08/15/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-aec7-d185d1509344
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Machine Learning Module Error Codes
This topic lists the errors that might be reported in individual modules in Azure Machine Learning Studio, either when an experiment fails, or when you are editing the properties of the module. To resolve the issue, click the error name in the following table and read about common causes.  
  
 There are two ways to get the full text of an error message in Studio:  
  
-   Click the link, **View Output Log**, in the right pane and scroll to the bottom of the. The detailed error message is generally displayed in the last two lines of the window.  
  
-   Select the module that has the error, and click the red X. Only the pertinent error text is displayed.  
  
 If the error message text is not helpful, please send us information about the context and any desired additions or changes. You can either submit feedback on the error topic, or visit the Azure Machine Learning forum and post a question.  
  
##  <a name="errors"></a> Exceptions List  
  
|Exception|Description|  
|---------------|-----------------|  
|Error 0000|Internal Error|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0002](errors/error-0002.md)|Exception occurs if one or more parameters could not be parsed or converted from specified type into required by target method type.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](errors/error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
|[Error 0005](errors/error-0005.md)|Exception occurs if parameter is less than a specific value.|  
|[Error 0006](errors/error-0006.md)|Exception occurs if parameter is greater than or equal to the specified value.|  
|[Error 0007](errors/error-0007.md)|Exception occurs if parameter is greater than a specific value.|  
|[Error 0008](errors/error-0008.md)|Exception occurs if parameter is not in range.|  
|[Error 0009](errors/error-0009.md)|Exception occurs if Azure storage account name or container name specified incorrectly.|  
|[Error 0010](errors/error-0010.md)|Exception occurs if input datasets have column names that should match but do not.|  
|[Error 0011](errors/error-0011.md)|Exception occurs if passed column set argument does not apply to any of dataset columns.|  
|[Error 0012](errors/error-0012.md)|Exception occurs if instance of class could not be created with passed set of arguments.|  
|[Error 0013](errors/error-0013.md)|Exception occurs if passed to module learner has invalid type.|  
|[Error 0014](errors/error-0014.md)|Exception occurs if amount of column unique values is greater than allowed.|  
|[Error 0015](errors/error-0015.md)|Exception occurs if database connection has failed.|  
|[Error 0016](errors/error-0016.md)|Exception occurs if input datasets passed to the module should have compatible column types but do not.|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  
|[Error 0018](errors/error-0018.md)|Exception occurs if input dataset is not valid.|  
|[Error 0019](errors/error-0019.md)|Exception occurs if column is expected to contain sorted values, but it does not.|  
|[Error 0020](errors/error-0020.md)|Exception occurs if number of columns in some of the datasets passed to the module is too small.|  
|[Error 0021](errors/error-0021.md)|Exception occurs if number of rows in some of the datasets passed to the module is too small.|  
|[Error 0022](errors/error-0022.md)|Exception occurs if number of selected columns in input dataset does not equal to the expected number.|  
|[Error 0023](errors/error-0023.md)|Exception occurs if target column of input dataset is not valid for the current trainer module.|  
|[Error 0024](errors/error-0024.md)|Exception occurs if dataset does not contain a label column.|  
|[Error 0025](errors/error-0025.md)|Exception occurs if dataset does not contain a score column.|  
|[Error 0026](errors/error-0026.md)|Exception occurs if columns with the same name is not allowed.|  
|[Error 0027](errors/error-0027.md)|Exception occurs in case when two objects have to be of the same size but are not.|  
|[Error 0028](errors/error-0028.md)|Exception occurs in the case when column set contains duplicated column names and it is not allowed.|  
|[Error 0029](errors/error-0029.md)|Exception occurs in case when invalid URI is passed.|  
|[Error 0030](errors/error-0030.md)|Exception uccurs in the case when it is not possible to download a file.|  
|[Error 0031](errors/error-0031.md)|Exception occurs if number of columns in column set is less than needed.|  
|[Error 0032](errors/error-0032.md)|Exception occurs if argument is not a number.|  
|[Error 0033](errors/error-0033.md)|Exception occurs if argument is Infinity.|  
|[Error 0034](errors/error-0034.md)|Exception occurs if more than one rating exists for a given user-item pair.|  
|[Error 0035](errors/error-0035.md)|Exception occurs if no features were provided for a given user or item.|  
|[Error 0036](errors/error-0036.md)|Exception occurs if multiple feature vectors were provided for a given user or item.|  
|[Error 0037](errors/error-0037.md)|Exception occurs if multiple label columns are specified and just one is allowed.|  
|[Error 0038](errors/error-0038.md)|Exception occurs if number of elements expected should be an exact value, but is not.|  
|[Error 0039](errors/error-0039.md)|Exception occurs if operation has failed.|  
|[Error 0040](errors/error-0040.md)|Exception occurs when calling a deprecated module.|  
|[Error 0041](errors/error-0041.md)|Exception occurs when calling a deprecated module.|  
|[Error 0042](errors/error-0042.md)|Exception occurs when it is not possible to convert column to another type.|  
|[Error 0043](errors/error-0043.md)|Exception occurs when element type does not explicitly implement Equals.|  
|[Error 0044](errors/error-0044.md)|Exception occurs when it is not possible to derive element type of column from the existing values.|  
|[Error 0045](errors/error-0045.md)|Exception occurs when it is not possible to create a column because of mixed element types in the source.|  
|[Error 0046](errors/error-0046.md)|Exception occurs when it is not possible to create directory on specified path.|  
|[Error 0047](errors/error-0047.md)|Exception occurs if number of feature columns in some of the datasets passed to the module is too small.|  
|[Error 0048](errors/error-0048.md)|Exception occurs in the case when it is not possible to open a file.|  
|[Error 0049](errors/error-0049.md)|Exception occurs in the case when it is not possible to parse a file.|  
|[Error 0050](errors/error-0050.md)|Exception occurs in the case when input and output files are the same.|  
|[Error 0051](errors/error-0051.md)|Exception occurs in the case when several output files are the same.|  
|[Error 0052](errors/error-0052.md)|Exception occurs if Azure storage account key is specified incorrectly.|  
|[Error 0053](errors/error-0053.md)|Exception occurs in the case when there are no user features or items for machbox reccomendations.|  
|[Error 0054](errors/error-0054.md)|Exception occurs if there is too few distinct values in the column to complete operation.|  
|[Error 0055](errors/error-0055.md)|Exception occurs when calling a deprecated module.|  
|[Error 0056](errors/error-0056.md)|Exception occurs if columns are selected in a column picker violates the Selected Columns Category constraint.|  
|[Error 0057](errors/error-0057.md)|Exception occurs when attempting to create a file or blob that already exists.|  
|[Error 0058](errors/error-0058.md)|Exception occurs if dataset does not contain the expected label column.|  
|[Error 0059](errors/error-0059.md)|Exception occurs if a column index specified in a column picker cannot be parsed.|  
|[Error 0060](errors/error-0060.md)|Exception occurs when an out of range column range is specified in a column picker.|  
|[Error 0061](errors/error-0061.md)|Exception occurs when attempting to add a row to a DataTable that has a different number of columns than the table.|  
|[Error 0062](errors/error-0062.md)|Exception occurs when attempting to compare two models with different learner types.|  
|[Error 0063](errors/error-0063.md)|Exception occurs when R script evaluation fails with an error.|  
|[Error 0064](errors/error-0064.md)|Exception occurs if Azure storage account name or storage key is specified incorrectly.|  
|[Error 0065](errors/error-0065.md)|Exception occurs if Azure blob name is specified incorrectly.|  
|[Error 0066](errors/error-0066.md)|Exception occurs if a resource could not be uploaded to an Azure Blob.|  
|[Error 0067](errors/error-0067.md)|Exception occurs if a dataset has a different number of columns than expected.|  
|[Error 0068](errors/error-0068.md)|Exception occurs if the specified Hive script is not correct.|  
|[Error 0069](errors/error-0069.md)|Exception occurs if the specified SQL script is not correct.|  
|[Error 0070](errors/error-0070.md)|Exception occurs when attempting to access non-existent Azure table.|  
|[Error 0071](errors/error-0071.md)|Exception occurs if provided credentials are incorrect.|  
|[Error 0072](errors/error-0072.md)|Exception occurs in the case of connection timeout.|  
|[Error 0073](errors/error-0073.md)|Exception occurs if an error occurs while converting a column to another type.|  
|[Error 0074](errors/error-0074.md)|Exception occurs when the Metadata Editor tries to convert a sparse column to categorical.|  
|[Error 0075](errors/error-0075.md)|Exception occurs when an invalid binning function is used when quantizing a dataset.|  
|[Error 0077](errors/error-0077.md)|Exception occurs when unknown blob file write mode passed.|  
|[Error 0078](errors/error-0078.md)|Exception occurs when the HTTP option for Import Data receives a 3xx status code indicating redirection.|  
|[Error 0079](errors/error-0079.md)|Exception occurs if Azure storage container name is specified incorrectly.|  
|[Error 0080](errors/error-0080.md)|Exception occurs when column with all values missing is not allowed by module.|  
|[Error 0081](errors/error-0081.md)|Exception occurs in PCA module if number of dimensions to reduce to is equal to number of feature columns in input dataset, containing at least one sparse feature column.|  
|[Error 0082](errors/error-0082.md)|Exception occurs when a model cannot be successfully deserialized.|  
|[Error 0083](errors/error-0083.md)|Exception occurs if dataset used for training cannot be used for concrete type of learner.|  
|[Error 0084](errors/error-0084.md)|Exception occurs when scores produced from an R Script are evaluated. This is currently unsupported.|  
|[Error 0085](errors/error-0085.md)|Exception occurs when script evaluation fails with an error.|  
|[Error 0086](errors/error-0086.md)|Exception occurs when a counting transform is invalid.|  
|[Error 0087](errors/error-0087.md)|Exception occurs when an invalid count table type is specified for learning with counts modules.|  
|[Error 0088](errors/error-0088.md)|Exception occurs when an invalid counting type is specified for learning with counts modules.|  
|[Error 0089](errors/error-0089.md)|Exception occurs when the specified number of classes is less than the actual number of classes in a dataset used for counting.|  
|[Error 0090](errors/error-0090.md)|Exception occurs when Hive table creation fails.|  
|[Error 0100](errors/error-0100.md)|Exception occurs when an unsupported language is specified for a custom module.|  
|[Error 0101](errors/error-0101.md)|All port and parameter ID's must be unique.|  
|[Error 0102](errors/error-0102.md)|Thrown when a ZIP file cannot be extracted|  
|[Error 0103](errors/error-0103.md)|Thrown when a ZIP file does not contain any .xml files|  
|[Error 0104](errors/error-0104.md)|Thrown when a module definition file references a script that cannot be located|  
|[Error 0105](errors/error-0105.md)|Thrown when a module definition file defines an unsupported parameter type|  
|[Error 0106](errors/error-0106.md)|Thrown when a module definition file defines an unsupported input type|  
|[Error 0107](errors/error-0107.md)|Thrown when a module definition file defines an unsupported output type|  
|[Error 0108](errors/error-0108.md)|Thrown when a module definition file defines more input or output ports than are supported|  
|[Error 0109](errors/error-0109.md)|Thrown when a module definition file defines a column picker incorrectly|  
|[Error 0110](errors/error-0110.md)|Thrown when a module definition file defines a column picker that references a non-existent input port ID|  
|[Error 0111](errors/error-0111.md)|Thrown when a module definition file defines an invalid property|  
|[Error 0112](errors/error-0112.md)|Thrown when a module definition file cannot be parsed|  
|[Error 0113](errors/error-0113.md)|Thrown when a module definition file contains errors.|  
|[Error 0114](errors/error-0114.md)|Thrown when building a custom module fails.|  
|[Error 0115](errors/error-0115.md)|Thrown when a custom module default script has an unsupported extention.|  
|[Error 0121](errors/error-0121.md)|Thrown when SQL write fails because the table is not writeable|  
|[Error 0122](errors/error-0122.md)|Exception occurs if multiple weight columns are specified and just one is allowed.|  
|[Error 0123](errors/error-0123.md)|Exception occurs if column of vectors is specified to be Label column.|  
|[Error 0124](errors/error-0124.md)|Exception occurs if non-numeric or categorical column is specified to be the weight column.|  
|[Error 0125](errors/error-0125.md)|Thrown when schema for multiple datasets do not match.|  
|[Error 0126](errors/error-0126.md)|Exception occurs if the user specifies a SQL domain that is not supported in Azure ML.|  
|[Error 0127](errors/error-0127.md)|Image pixel size exceeds allowed limit.|  
|[Error 0128](errors/error-0128.md)|Number of conditional probabilities for categorical columns exceeds limit.|  
|[Error 0129](errors/error-0129.md)|Number of columns in the dataset exceeds allowed limit.|  
|[Error 0130](errors/error-0130.md)|Exception occurs when all rows in the training dataset contain missing values.|  
|[Error 0131](errors/error-0131.md)|Exception occurs if one or more datasets in a zip file fails to be unzipped and registered correctly.|  
|[Error 0132](errors/error-0132.md)|No file name was specified for unpacking; multiple files were found in zip file.|  
|[Error 0133](errors/error-0133.md)|The specified file was not found in the zip file.|  
|[Error 0134](errors/error-0134.md)|Exception occurs when label column is missing or has insufficient number of labeled rows.|  
|[Error 0135](errors/error-0135.md)|Only centroid-based cluster is supported.|  
|[Error 0136](errors/error-0136.md)|No file name was returned; unable to process the file as a result.|  
|[Error 0137](errors/error-0137.md)|Azure Storage SDK encountered an error converting between table properties and dataset columns during read or write.|  
|[Error 0138](errors/error-0138.md)|Memory has been exhausted, unable to complete running of module.|  
|[Error 0139](errors/error-0139.md)|Exception occurs when it is not possible to convert column to another type.|  
|[Error 0140](errors/error-0140.md)|Exception occurs if passed column set argument does not contain other columns except label column.|  
|[Error 0141](errors/error-0141.md)|Exception occurs if the number of the selected numerical columns and unique values in the categorical and string columns is too small.|  
|[Error 0142](errors/error-0142.md)|Exception occurs when the system cannot load certificate to authenticate|  
|[Error 0143](errors/error-0143.md)|Can't parse user-provided URL that is supposed to be from GitHub.|  
|[Error 0144](errors/error-0144.md)|User-provided GitHub url is missing the expected part.|  
|[Error 0145](errors/error-0145.md)|Cannot create the replication directory for some reason.|  
|[Error 0146](errors/error-0146.md)|When the user files are unzipped into the local directory, the combined path might be too long.|  
|[Error 0147](errors/error-0147.md)|Could not download stuff from GitHub for some reason|  
|[Error 0148](errors/error-0148.md)|Unauthorized access issues while extracting data or creating directory.|  
|[Error 0149](errors/error-0149.md)|The user file does not exist inside GitHub bundle.|  
|[Error 0150](errors/error-0150.md)|The scripts that come from the user package could not be unzipped, most likely because of the collision with Github files.|  
|[Error 0151](errors/error-0151.md)|There was an error writing to cloud storage. Please check the url.|  
|[Error 0152](errors/error-0152.md)|The Azure cloud type was specified incorrectly in the module context.|  
|[Error 0153](errors/error-0153.md)|The storage end point specified is invalid.|  
|[Error 0154](errors/error-0154.md)|The specified server name could not be resolved|  
|[Error 0155](errors/error-0155.md)|The DocDb Client threw an exception|  
|[Error 0156](errors/error-0156.md)|Bad response for HCatalog Server|  
|[Error 0157](errors/error-0157.md)|There was an error reading from DocumentDB due to inconsistent or different document schemas|  
|[Error 1000](errors/error-1000.md)|Internal library exception.|