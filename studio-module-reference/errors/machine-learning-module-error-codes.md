---
title: "Machine learning module error codes | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 08/15/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-aec7-d185d1509344
caps.latest.revision: 17
author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Machine learning module error codes
This topic lists the errors that might be reported in individual modules in Azure Machine Learning Studio, either when an experiment fails, or when you are editing the properties of the module. To resolve the issue, click the error name in the following table and read about common causes.  
  
 There are two ways to get the full text of an error message in Studio:  
  
-   Click the link, **View Output Log**, in the right pane and scroll to the bottom of the. The detailed error message is generally displayed in the last two lines of the window.  
  
-   Select the module that has the error, and click the red X. Only the pertinent error text is displayed.  
  
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
|[Error 0130](error-0130.md)|Exception occurs when all rows in the training dataset contain missing values.|  
|[Error 0131](error-0131.md)|Exception occurs if one or more datasets in a zip file fails to be unzipped and registered correctly.|  
|[Error 0132](error-0132.md)|No file name was specified for unpacking; multiple files were found in zip file.|  
|[Error 0133](error-0133.md)|The specified file was not found in the zip file.|  
|[Error 0134](error-0134.md)|Exception occurs when label column is missing or has insufficient number of labeled rows.|  
|[Error 0135](error-0135.md)|Only centroid-based cluster is supported.|  
|[Error 0136](error-0136.md)|No file name was returned; unable to process the file as a result.|  
|[Error 0137](error-0137.md)|Azure Storage SDK encountered an error converting between table properties and dataset columns during read or write.|  
|[Error 0138](error-0138.md)|Memory has been exhausted, unable to complete running of module.|  
|[Error 0139](error-0139.md)|Exception occurs when it is not possible to convert column to another type.|  
|[Error 0140](error-0140.md)|Exception occurs if passed column set argument does not contain other columns except label column.|  
|[Error 0141](error-0141.md)|Exception occurs if the number of the selected numerical columns and unique values in the categorical and string columns is too small.|  
|[Error 0142](error-0142.md)|Exception occurs when the system cannot load certificate to authenticate.|  
|[Error 0143](error-0143.md)|Can't parse user-provided URL that is supposed to be from GitHub|  
|[Error 0144](error-0144.md)|User-provided GitHub url is missing the expected part.|  
|[Error 0145](error-0145.md)|Cannot create the replication directory for some reason|  
|[Error 0146](error-0146.md)|When the user files are unzipped into the local directory, the combined path might be too long.|  
|[Error 0147](error-0147.md)|Could not download stuff from GitHub for some reason|  
|[Error 0148](error-0148.md)|Unauthorized access issues while extracting data or creating directory|  
|[Error 0149](error-0149.md)|The user file does not exist inside GitHub bundle.|  
|[Error 0150](error-0150.md)|The scripts that come from the user package could not be unzipped, most likely because of the collision with Github files.|  
|[Error 0151](error-0151.md)|There was an error writing to cloud storage. Please check the url.|  
|[Error 0152](error-0152.md)|The Azure cloud type was specified incorrectly in the module context.|  
|[Error 0153](error-0153.md)|The storage end point specified is invalid.|  
|[Error 0154](error-0154.md)|The specified server name could not be resolved.|  
|[Error 0155](error-0155.md)|The DocDb Client threw an exception.|  
|[Error 0156](error-0156.md)|Bad response for HCatalog Server|  
|[Error 0157](error-0157.md)|There was an error reading from Azure Cosmos DB due to inconsistent or different document schemas.|  
|[Error 1000](error-1000.md)|Internal library exception|