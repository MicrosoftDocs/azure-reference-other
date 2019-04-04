---
title: Troubleshoot Studio module errors in Azure Machine Learning
titleSuffix: "Azure Machine Learning Studio"
description: Troubleshoot module exceptions in Azure Machine Learning Studion using error codes
ms.date: 04/10/2019
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Troubleshoot module exceptions in Azure Machine Learning using error codes

Learn about the the error messages and exception codes you might encounter using  modules in Azure Machine Learning Studio. 

To resolve the issue, look for the error in this article to read about common causes. There are two ways to get the full text of an error message in Studio:  
 
- Click the link, **View Output Log**, in the right pane and scroll to the bottom of the. The detailed error message is displayed in the last two lines of the window.  
  
- Select the module that has the error, and click the red X. Only the pertinent error text is displayed.  
  
If the error message text is not helpful, send us information about the context and any desired additions or changes. You can either submit feedback on the error topic, or visit the [Azure Machine Learning STUDIO forum](https://aka.ms/aml-forum-studio) and post a question.  
  
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
|[Error 0014](error-0014.md)|Exception occurs if number of column unique values is greater than allowed.|  
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
|[Error 0026](error-0026.md)|Exception occurs if columns with the same name are not allowed.|  
|[Error 0027](error-0027.md)|Exception occurs in case when two objects have to be of the same size but are not.|  
|[Error 0028](error-0028.md)|Exception occurs in the case when column set contains duplicated column names and it is not allowed.|  
|[Error 0029](error-0029.md)|Exception occurs in case when invalid URI is passed.|  
|[Error 0030](error-0030.md)|Exception occurs in the case when it is not possible to download a file.|  
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
|[Error 0053](error-0053.md)|Exception occurs in the case when there are no user features or items for matchbox recommendations.|  
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






## Error 0070  
 Exception occurs when attempting to access non-existent Azure table.  
  
 This error in Azure Machine Learning occurs when you attempt to access a non-existent Azure table. You will receive this error if you specify a table in Azure storage which does not exist when reading from or writing to Azure Table Storage. This can happen if you mistype the name of the desired table, or you have a mismatch between the target name and the storage type. For example, you intended to read from a table but entered the name of a blob instead.  
  
**Resolution :**
 Revisit the module to verify that the name of the table is correct.  
  
|Exception Messages|  
|------------------------|  
|Azure table does not exist.|  
|Azure table "{0}" does not exist.|  
  
## Error 0071  
 Exception occurs if provided credentials are incorrect.  
  
 This error in Azure Machine Learning occurs if the provided credentials are incorrect.  
  
 You might also receive this error if the module cannot connect to an HDInsight cluster.  
  
**Resolution :**
 Review the inputs to the module and verify the account name and password.  
  
 Check for the following issues that can cause an error:  
  
-   The schema of the dataset does not match the schema of the destination datatable.  
  
-   Column names are missing or misstyped.  
  
-   You are writing to a table that has column names with illegal characters. Ordinarily you can enclose such column names in square brackets , but if that does not work, edit column names to use only letters and underscores (_)  
  
-   Strings that you are trying to write contain single quotation marks  
  
 If you are trying to connect to an HDInsight cluster, verify that the target cluster is accessible with the supplied credentials.  
  
|Exception Messages|  
|------------------------|  
|Incorrect credentials are passed.|  
|Incorrect username "{0}" or password is passed|  
  

## Error 0072  
 Exception occurs in the case of connection timeout.  
  
 This error in Azure Machine Learning occurs when a connection times out. You will receive this error if there are currently connectivity issues with the data source or destination, such as slow internet connectivity, or if the dataset is very large and/or the SQL query to read in the data performs complicated processing.  
  
**Resolution :**
 Determine whether there are currently issues with slow connections to Azure storage or the internet.  
  
|Exception Messages|  
|------------------------|  
|Connection timeout occured.|  
  

## Error 0073  
 Exception occurs if an error occurs while converting a column to another type.  
  
 This error in Azure Machine Learning occurs when it is not possible to convert column to another type.  You will receive this error if a module requires a particular type and it is not possible to convert the column to the new type.  
  
**Resolution :**
 Modify the input dataset so that the column can be converted based on the inner exception.  
  
|Exception Messages|  
|------------------------|  
|Failed to convert column.|  
|Failed to convert column to {0}.|  
  

## Error 0074  
 Exception occurs when the [Edit Metadata](../edit-metadata.md) tries to convert a sparse column to categorical.  
  
 This error in Azure Machine Learning occurs when the [Edit Metadata](../edit-metadata.md) tries to convert a sparse column to categorical.  You will receive this error when trying to convert sparse columns to categorical with the **Make categorical** option.  Azure machine Learning does not support sparse categorical arrays, so the module will fail.  
  
**Resolution :**
 Make the column dense by using [Convert to Dataset](../convert-to-dataset.md) first or do not convert the column to categorical.  
  
|Exception Messages|  
|------------------------|  
|Sparse columns cannot be converted to Categorical.|  
  

## Error 0075  
Exception occurs when an invalid binning function is used when quantizing a dataset.  
  
This error in Azure Machine Learning occurs when you are trying to bin data using an unsupported method, or when the parameter combinations are invalid.  
  
**Resolution :**

Error handling for this event was introduced in an earlier version of Azure Machine Learning that allowed more customization of binning methods. Currently all binning methods are based on a selection from a dropdown list, so technically it should no longer be possible to get this error.

If you get this error when using the [Group Data into Bins](../group-data-into-bins.md) module, consider reporting the issue in the [Azure Machine Learning forum](https://social.msdn.microsoft.com/Forums/en-US/home?forum=MachineLearning), providing the data types, parameter settings, and the exact error message.  
  
|Exception Messages|  
|------------------------|  
|Invalid binning function used.|  
  

## Error 0077  
 Exception occurs when unknown blob file write mode passed.  
  
 This error in Azure Machine Learning occurs if an invalid argument is passed in the specifications for a blob file destination or source.  
  
**Resolution :**
 In almost all modules that import or export data to and from Azure blob storage, parameter values controlling the write mode are assigned by using a dropdown list; therefore, it is not possible to pass an invalid value, and this error should not appear. This error will be deprecated in a later release.  
  
|Exception Messages|  
|------------------------|  
|Unsupported blob write mode.|  
|Unsupported blob write mode: {0}.|  
  

## Error 0078  
 Exception occurs when the HTTP option for [Import Data](../import-data.md) receives a 3xx status code indicating redirection.  
  
 This error in Azure Machine Learning occurs when the HTTP option for [Import Data](../import-data.md) receives a 3xx (301, 302, 304, etc.) status code indicating redirection. You will receive this error if you attempt to connect to an HTTP source that redirects the browser to another page. For security reasons, redirecting websites are not allowed as data sources for Azure Machine Learning.  
  
**Resolution :**
 If the website is a trusted website, enter the redirected URL directly.  
  
|Exception Messages|  
|------------------------|  
|Http redirection not allowed|  
  

## Error 0079  
 Exception occurs if Azure storage container name is specified incorrectly.  
  
 This error in Azure Machine Learning occurs if the Azure storage container name is specified incorrectly. You will receive this error if you have not specified both the container and the blob (file) name using **the Path to blob beginning with container** option when writing to Azure Blob Storage.  
  
**Resolution :**
 Revisit the [Export Data](../export-data.md) module and verify that the specified path to the blob contains both the container and the file name, in the format **container/filename**.  
  
|Exception Messages|  
|------------------------|  
|The Azure storage container name is incorrect.|  
|The Azure storage container name "{0}" is incorrect; a container name of the format container/blob was expected.|  
  

## Error 0080  
 Exception occurs when column with all values missing is not allowed by module.  
  
 This error in Azure Machine Learning is produced when one or more of the columns consumed by the module contains all missing values. For example, if a module is computing aggregate statistics for each column, it cannot operate on a column containing no data. In such cases, module execution is halted with this exception.  
  
**Resolution :**
 Revisit the input dataset and remove any columns that contain all missing values.  
  
|Exception Messages|  
|------------------------|  
|Columns with all values missing are not allowed.|  
|Column {0} has all values missing.|  
  

## Error 0081  
 Exception occurs in PCA module if number of dimensions to reduce to is equal to number of feature columns in input dataset, containing at least one sparse feature column.  
  
 This error in Azure Machine Learning is produced if the following conditions are met: (a) the input dataset has at least one sparse column and (b) the final number of dimensions requested is the same as the number of input dimensions.  
  
**Resolution :**
 Consider reducing the number of dimensions in the output to be fewer than the number of dimensions in the input. This is typical in applications of PCA.  For more information, see [Principal Component Analysis](../principal-component-analysis.md).  
  
|Exception Messages|  
|------------------------|  
|For dataset containing sparse feature columns number of dimensions to reduce to should be less than number of feature columns.|  
 

## Error 0082  
 Exception occurs when a model cannot be successfully deserialized.  
  
 This error in Azure Machine Learning occurs when a saved machine learning model or transform cannot be loaded by a newer version of the Azure Machine Learning runtime as a result of a breaking change.  
  
**Resolution :**
 The training experiment that produced the model or transform must be rerun and the model or transform must be resaved.  
  
|Exception Messages|  
|------------------------|  
|Model could not be deserialized because it is likely serialized with an older serialization format. Please retrain and re-save the model.|  
  

## Error 0083  
 Exception occurs if dataset used for training cannot be used for concrete type of learner.  
  
 This error in Azure Machine Learning is produced when the dataset is incompatible with the learner being trained. For example, the dataset might contain at least one missing value in each row, and as a result, the entire dataset would be skipped during training. In other cases, some machine learning algorithms such as anomaly detection do not expect labels to be present and can throw this exception if labels are present in the dataset.  
  
**Resolution :**
 Consult the documentation of the learner being used to check requirements for the input dataset. Examine the columns to see all required columns are present.  
  
|Exception Messages|  
|------------------------|  
|Dataset used for training is invalid.|  
|{0} contains invalid data for training.|  
|{0} contains invalid data for training. Learner type: {1}.|  
  

## Error 0084  
 Exception occurs when scores produced from an R Script are evaluated. This is currently unsupported.  
  
 This error in Azure Machine Learning occurs if you try to use one of the modules for evaluating a model with output from an R script that contains scores.  
  
**Resolution :**
  
|Exception Messages|  
|------------------------|  
|Evaluating scores produced by R is currently unsupported.|  
  

## Error 0085  
 Exception occurs when script evaluation fails with an error.  
  
 This error in Azure Machine Learning occurs when you are running custom script that contains syntax errors.  
  
**Resolution :**
 Review your code in an external editor and check for errors.  
  
|Exception Messages|  
|------------------------|  
|Error during evaluation of script.|  
|The following error occurred during script evaluation, please view the output log for more information: ---------- Start of error message from {0} interpreter ---------- {1} ---------- End of error message from {0}  interpreter  ----------|  
  

## Error 0086  
 Exception occurs when a counting transform is invalid.  
  
 This error in Azure Machine Learning occurs when you select a transformation based on a count table, but the selected transform is incompatible with the current data, or with the new count table.  
  
**Resolution :**
 The module supports saving the counts and rules that make up the transformation in two different formats. If you are merging count tables, verify that both tables you intend to merge use the same format.  
  
 Also, note that in general, a count-based transform can only be applied to datasets that have the same schema as the dataset on which the transform was originally created.  
  
 For general information, see [Learning with Counts](../data-transformation-learning-with-counts.md). For requirements specific to creating and merging count-based features, see these topics:  
  
-   [Merge Count Transform](../merge-count-transform.md)  
  
-   [Import Count Table](../import-count-table.md)  
  
-   [Modify Count Table Parameters](../modify-count-table-parameters.md)  
  
|Exception Messages|  
|------------------------|  
|Invalid counting transform specified.|  
|The counting transform at input port '{0}' is invalid.|  
|The counting transform at input port '{0}' cannot be merged with the counting transform at input port '{1}'. Please check to verify the metadata used for counting matches.|  
  

## Error 0087  
 Exception occurs when an invalid count table type is specified for learning with counts modules.  
  
 This error in Azure Machine Learning occurs when you try to import an existing count table, but the table is incompatible with the current data, or with the new count table.  
  
**Resolution :**
 There are different formats for saving the counts and rules that make up the transformation. If you are merging count tables, verify that both use the same format.  
  
 Generally, a count-based transform can only be applied to datasets that have the same schema as the dataset on which the transform was originally created.  
  
 For general information, see [Learning with Counts](../data-transformation-learning-with-counts.md). For requirements specific to creating and merging count-based features, see these topics:  
  

## Error 0088  
 Exception occurs when an invalid counting type is specified for learning with counts modules.  
  
 This error in Azure Machine Learning occurs when you try to use a  different counting method than is supported for count-based featurization.  
  
**Resolution :**
 In general, counting methods are chosen from a dropdown list, so you should not see this error.  
  
 For general information, see [Learning with Counts](../data-transformation-learning-with-counts.md). For requirements specific to creating and merging count-based features, see these topics:  
  
-   [Merge Count Transform](../merge-count-transform.md)  
  
-   [Import Count Table](../import-count-table.md)  
  
-   [Modify Count Table Parameters](../modify-count-table-parameters.md)  
  
|Exception Messages|  
|------------------------|  
|Invalid counting type is specified.|  
|The specified counting type '{0}' is not a valid counting type.|  
  

## Error 0089  
 Exception occurs when the specified number of classes is less than the actual number of classes in a dataset used for counting.  
  
 This error in Azure Machine Learning occurs when you are creating a count table and the label column contains a different number of classes than you specified in the module parameters.  
  
**Resolution :**
 Check your dataset and find out exactly how many distinct values (possible classes) there are in the label column. When you create the count table, you must specify at least this number of classes.  
  
 The count table cannot automatically determine the number of classes available.  
  
 When you create the count table you cannot specify 0 or any number that is less than the actual number of classes in the label column.  
  
|Exception Messages|  
|------------------------|  
|The number of classes is incorrect. Please make sure that the number of classes you specify in the parameter pane is greater than or equal to the number of classes in the label column.|  
|The number of classes specified is '{0}', which is not greater than a label value '{1}' in the data set used to count. Please make sure that the number of classes you specify in the parameter pane is greater than or equal to the number of classes in the label column.|  
  

## Error 0090  
 Exception occurs when Hive table creation fails.  
  
 This error in Azure Machine Learning occurs when you are using [Export Data](../export-data.md) or another option to save data to an HDInsight cluster and the specified Hive table cannot be created.  
  
**Resolution :**
 Check the Azure storage account name associated with the cluster and verify that you are using the same account in the module properties.  
  
|Exception Messages|  
|------------------------|  
|The Hive table could not be created. For a HDInsight cluster, please ensure the Azure storage account name associated with cluster is the same as what is passed in through the module parameter.|  
|The Hive table "{0}" could not be created. For a HDInsight cluster, please ensure the Azure storage account name associated with cluster is the same as what is passed in through the module parameter.|  
|The Hive table "{0}" could not be created. For a HDInsight cluster, please ensure the Azure storage account name associated with cluster is "{1}".|  
 

## Error 0100  
 Exception occurs when an unsupported language is specified for a custom module.  
  
 This error in Azure Machine Learning occurs when building a custom module and the name property of the **Language** element in a custom module xml definition file has an invalid value. Currently, the only valid value for this property is `R`. For example:  
  
 `<Language name="R" sourceFile="CustomAddRows.R" entryPoint="CustomAddRows" />`  
  
**Resolution:**
 Verify that the name property of the **Language** element in the custom module xml definition file is set to `R`. Save the file, update the custom module zip package, and try to add the custom module again.  
  
|Exception Messages|  
|------------------------|  
|Unsupported custom module language specified|  
  

## Error 0101  
 All port and parameter IDs must be unique.  
  
 This error in Azure Machine Learning occurs when one or more ports or parameters are assigned the same ID value in a custom module XML definition file.  
  
**Resolution:**
 Check that the ID values across all ports and parameters are unique. Save the xml file, update the custom module zip package, and try to add the custom module again.  
  
|Exception Messages|  
|------------------------|  
|All port and parameter IDs for a module must be unique|  
|Module '{0}' has duplicate port/argument IDs. All port/argument IDs must be unique for a module.|  
  

## Error 0102  
 Thrown when a ZIP file cannot be extracted.  
  
 This error in Azure Machine Learning occurs when you are importing a zipped package with the .zip extension, but the package is either not a zip file, or the file does not use a supported zip format.  
  
**Resolution:**
 Make sure the selected file is a valid .zip file, and that it was compressed by using one of the supported compression algorithms.  
  
 If you get this error when importing datasets in compressed format, verify that all contained files use one of the supported file formats, and are in Unicode format. For more information, see [Unpack Zipped Datasets](../unpack-zipped-datasets.md).  
  
 Try re-adding the desired files to a new compressed zipped folder and try to add the custom module again.  
  
|Exception Messages|  
|------------------------|  
|Given ZIP file is not in the correct format|  


## Error 0103  
 Thrown when a ZIP file does not contain any .xml files  
  
 This error in Azure Machine Learning occurs when the custom module zip package does not contain any module definition (.xml) files. These files need to reside in the root of the zip package (for example, not within a subfolder.)  
  
**Resolution:**
 Verify that one or more xml module definition files are in the root folder of the zip package by extracting it to a temporary folder on your disk drive. Any xml files should be directly in the folder you extracted the zip package to. Make sure when you create the zip package that you do not  select a folder that contains xml files to zip as this will create a sub folder within the zip package with the same name as the folder you selected to zip.  
  
|Exception Messages|  
|------------------------|  
|Given ZIP file does not contain any module definition files (.xml files)|  


## Error 0104  
 Thrown when a module definition file references a script that cannot be located  
  
 This error in Azure Machine Learning is thrown when a custom module xml definition file references a script file in the **Language** element that does not exist in the zip package. The script file path is defined in the **sourceFile** property of the **Language** element. The path to the source file is relative to the root of the zip package (same location as the module xml definition files). If the script file is in a sub folder, the relative path to the script file must be specified. For instance, if all scripts were stored in a **myScripts** folder within the zip package, the **Language** element would have to add this path to the **sourceFile** property as below. For example:  
  
 `<Language name="R" sourceFile="myScripts/CustomAddRows.R" entryPoint="CustomAddRows" />`  
  
**Resolution:**
 Make sure that the value of the **sourceFile** property in the **Language** element of the custom module xml definition is correct and that the source file exists in the correct relative path in the zip package.  
  
|Exception Messages|  
|------------------------|  
|Referenced R script file does not exist.|  
|Referenced R script file '{0}' cannot be found. Ensure that the relative path to the file is correct from the definitions location.|  


## Error 0105  
 This error is displayed when a module definition file contains an unsupported parameter type  
  
 This error in Azure Machine Learning is produced when the you create a custom module xml definition and the type of a parameter or argument in the definition does not match a supported type.  
  
**Resolution:**
 Make sure that the type property of any **Arg** element in the custom module xml definition file is a supported type.  
  
|Exception Messages|  
|------------------------|  
|Unsupported parameter type.|  
|Unsupported parameter type '{0}' specified.|  


## Error 0106  
 Thrown when a module definition file defines an unsupported input type  
  
 This error in Azure Machine Learning is produced when the type of an input port in a custom module XML definition does not match a supported type.  
  
**Resolution:**
 Make sure that the type property of an Input element in the custom module XML definition file is a supported type.  
  
|Exception Messages|  
|------------------------|  
|Unsupported input type.|  
|Unsupported input type '{0}' specified.|  


## Error 0107  
 Thrown when a module definition file defines an unsupported output type  
  
 This error in Azure Machine Learning is produced when the type of an output port in a custom module xml definition does not match a supported type.  
  
**Resolution:**
 Make sure that the type property of an Output element in the custom module xml definition file is a supported type.  
  
|Exception Messages|  
|------------------------|  
|Unsupported output type.|  
|Unsupported output type '{0}' specified.|  


## Error 0108  
 Thrown when a module definition file defines more input or output ports than are supported  
  
 This error in Azure Machine Learning is produced when too many input or output ports are defined in a custom module xml definition.  
  
**Resolution:**
 Makes sure the maximum number of input and output ports defined in the custom module xml definition does not exceed the maximum number of supported ports.  
  
|Exception Messages|  
|------------------------|  
|Exceeded supported number of input or output ports.|  
|Exceeded number of supported '{0}' ports. Maximum allowed number of '{0}' ports is '{1}'.| 

## Error 0109  
 Thrown when a module definition file defines a column picker incorrectly  
  
 This error in Azure Machine Learning is produced when the syntax for a column picker argument contains an error in a custom module xml definition.  
  
**Resolution:**
 This error is produced when the syntax for a column picker argument contains an error in a custom module xml definition.  
  
|Exception Messages|  
|------------------------|  
|Unsupported syntax for column picker.|  
  

## Error 0110  
 Thrown when a module definition file defines a column picker that references a non-existent input port ID  
  
 This error in Azure Machine Learning is produced when the *portId* property within the Properties element of an Arg of type ColumnPicker does not match the ID value of an input port.  
  
**Resolution:**
 Make sure the portId property matches the ID value of an input port defined in the custom module xml definition.  
  
|Exception Messages|  
|------------------------|  
|Column picker references a non-existent input port ID.|  
|Column picker references a non-existent input port ID '{0}'.|  
  

## Error 0111  
 Thrown when a module definition file defines an invalid property  
  
 This error in Azure Machine Learning is produced when an invalid property is assigned to an element in the custom module XML definition.  
  
**Resolution:**
 Make sure the property is supported by the custom module element.  
  
|Exception Messages|  
|------------------------|  
|Property definition is invalid.|  
|Property definition '{0}' is invalid.|  
  

## Error 0112  
 Thrown when a module definition file cannot be parsed  
  
 This error in Azure Machine Learning is produced when there is an error in the xml format that prevents the custom module XML definition from being parsed as a valid XML file.  
  
**Resolution:**
 Ensure that each element is opened and closed correctly. Make sure that there are no errors in the XML formatting.  
  
|Exception Messages|  
|------------------------|  
|Unable to parse module definition file.|  
|Unable to parse module definition file '{0}'.|  
  

## Error 0113  
 Thrown when a module definition file contains errors.  
  
 This error in Azure Machine Learning is produced when the custom module XML definition file can be parsed but contains errors, such as definition of elements not supported by custom modules.  
  
**Resolution:**
 Make sure the custom module definition file defines elements and properties that are supported by custom modules.  
  
|Exception Messages|  
|------------------------|  
|Module definition file contains errors.|  
|Module definition file '{0}' contains errors.|  
|Module definition file '{0}' contains errors. {1}|  
  

## Error 0114  
 Thrown when building a custom module fails.  
  
 This error in Azure Machine Learning is produced when a custom module build fails. This occurs when one or more custom module related errors are encountered while adding the custom module. The additional errors are reported within this error message.  
  
**Resolution:**
 Resolve the errors reported within this exception message.  
  
|Exception Messages|  
|------------------------|  
|Failed to build custom module.|  
|Custom module builds failed with error(s): {0}|  
  

## Error 0115  
 Thrown when a custom module default script has an unsupported extension.  
  
 This error in Azure Machine Learning occurs when you provide a script for a custom module that uses an unknown filename extension.  
  
**Resolution:**
 Verify the file format and filename extension of any script files included in the custom module.  
  
|Exception Messages|  
|------------------------|  
|Unsupported extention for default script.|  
|Unsupported file extention {0} for default script.|  
  

## Error 0121  
 Thrown when SQL writes fails because the table is unwriteable  
  
 This error in Azure Machine Learning is produced when you are using the [Export Data](../export-data.md) module to save results to a table in a SQL database, and the table cannot be written to. Typically, you will see this error if the [Export Data](../export-data.md) module successfully establishes a connection with the SQL Server instance, but is then unable to write the contents of the Azure ML dataset to the table.  
  
**Resolution:**
 - Open the Properties pane of the [Export Data](../export-data.md) module and verify that the database and table names are entered correctly. 
 - Review the schema of the dataset you are exporting, and make sure that the data is compatible with the destination table.
 - Verify that the SQL log in associated with the user name and password has permissions to write to the table. 
 - If the exception contains additional error information from SQL Server, use that information to make corrections.  
  
|Exception Messages|  
|------------------------|  
|Connected to server, unable to write to table.|  
|Unable to write to Sql table: {0}|  


## Error 0122  
 Exception occurs if multiple weight columns are specified and just one is allowed.  
  
 This error in Azure Machine Learning occurs when too many columns have been selected as weight columns.  
  
**Resolution:**
 Review the input dataset and its metadata. Ensure that only one column contains weights.  
  
|Exception Messages|  
|------------------------|  
|Multiple weight columns are specified.|  


## Error 0123  
 Exception occurs if column of vectors is specified to Label column.  
  
 This error in Azure Machine Learning occurs if you use a vector as the label column.  
  
**Resolution:**
 Change the data format of the column if necessary, or choose a different column.  
  
|Exception Messages|  
|------------------------|  
|Column of vectors is specified as Label column.|  


## Error 0124  
 Exception occurs if non-numeric columns are specified to be the weight column.  
  
**Resolution:**
  
|Exception Messages|  
|------------------------|  
|Non-numeric column is specified as the weight column.|  
  


## Error 0125  
 Thrown when schema for multiple datasets does not match.  
  
**Resolution:**
  
|Exception Messages|  
|------------------------|  
|Dataset schema does not match.|  


## Error 0126  
 Exception occurs if the user specifies a SQL domain that is not supported in Azure ML.  
  
 This error is produced when the user specifies a SQL domain that is not supported in Azure Machine Learning. You will receive this error if you are attempting to connect to a database server in a domain that is not whitelisted. Currently, the allowed SQL domains are: ".database.windows.net", ".cloudapp.net", or ".database.secure.windows.net". That is, the server must be an Azure SQL server or a server in a virtual machine on Azure.  
  
**Resolution:**
 Revisit the module. Verify that the SQL database server belongs to one of the accepted domains:  
  
-   .database.windows.net  
  
-   .cloudapp.net  
  
-   .database.secure.windows.net  
  
|Exception Messages|  
|------------------------|  
|Unsupported SQL domain.|  
|The SQL domain {0} is not currently supported in Azure ML|  
  

## Error 0127  
 Image pixel size exceeds allowed limit  
  
 This error occurs if you are reading images from an image dataset for classification and the images are larger than the model can handle.  
  
**Resolution:**
 For more information about the image size and other requirements, see these topics:  
  
-   [Import Images](../import-images.md)  
  
-   [Pretrained Cascade Image Classification](../pretrained-cascade-image-classification.md)  
  
|Exception Messages|  
|------------------------|  
|Image pixel size exceeds allowed limit.|  
|Image pixel size in the file '{0}' exceeds allowed limit: '{1}'|  


## Error 0128  
 Number of conditional probabilities for categorical columns exceeds limit.  
  
**Resolution:**
  
|Exception Messages|  
|------------------------|  
|Number of conditional probabilities for categorical columns exceeds limit.|  
|Number of conditional probabilities for categorical columns exceeds limit. Columns '{0}' and '{1}' are the problematic pair.|  


## Error 0129  
 Number of columns in the dataset exceeds allowed limit.  
  
**Resolution:**
  
|Exception Messages|  
|------------------------|  
|Number of columns in the dataset exceeds allowed limit.|  
|Number of columns in the dataset in '{0}' exceeds allowed.'|  
|Number of columns in the dataset in '{0}' exceeds allowed limit of '{1}'.'|  
|Number of columns in the dataset in '{0}' exceeds allowed '{1}' limit of '{2}'.'|  
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
|The file contains more than one file. Specify the file to expand. The following files were found: {0}|  
  

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
  
 This error occurs when the module that is running requires more memory than is available in the Azure container. This can happen if you are working with a large dataset and the current operation cannot fit into memory.  
  
Resolution:   
 If you are trying to read a large dataset and the operation cannot be completed, downsampling the dataset might help.  
  
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
  
 If the source dataset is valid, you might also check whether some upstream data manipulation or metadata operation has changed the data and removed some values.  
  
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
 The scripts that come from the user package could not be unzipped, most likely because of a collision with GitHub files.  
  
 This error in Azure Machine Learning occurs when a script cannot be extracted, typically when there is an existing file of the same name.  
  
Resolution:
  
|Exception Messages|  
|------------------------|  
|Unable to unzip the bundle; possible name collision with GitHub files.|  
  

## Error 0151  
 There was an error writing to cloud storage. Check the URL.  
  
 This error in Azure Machine Learning occurs when the module tries to write data to cloud storage but the URL is unavailable or invalid.  
  
Resolution: Check the URL and verify that it is writable.  
  
|Exception Messages|  
|------------------------|  
|Error writing to cloud storage (possibly a bad url).|  
|Error writing to cloud storage: {0}. Check the url.|  
  
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
|Detected documents with different schemas. Make sure all documents have the same schema|

## Error 1000  
Internal library exception.  
  
This error is provided to capture otherwise unhandled internal engine errors. Therefore, the cause for this error might be different depending on the module that generated the error.  
  
To get more help, we recommend that you post the detailed message that accompanies the error to the Azure Machine Learning forum, together with a description of the scenario, including the data used as inputs. This feedback will help us to prioritize errors and identify the most important issues for further work.  
  
|Exception Messages|  
|------------------------|  
|Library exception.|  
|Library exception: {0}|  
|{0} library exception: {1}|  
  

## More help  
[Module error codes](machine-learning-module-error-codes.md)

Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
+ [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
+ [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
 