---
title: "ML Studio (classic): Edit Metadata - Azure"
description: Learn how to use the Edit Metadata module to change metadata that is associated with columns in a dataset.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Edit Metadata
*Edits metadata associated with columns in a dataset*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the [Edit Metadata](edit-metadata.md) module in Machine Learning Studio (classic) to change metadata that is associated with columns in a dataset. The values and the data types in the dataset are not actually altered; what changes is the metadata inside Machine Learning that tells downstream components how to use the column.

Typical metadata changes might include:
  
+ Treating Boolean or numeric columns as categorical values  
  
+ Indicating which column contains the *class* label, or the values you want to categorize or predict  
  
+ Marking columns as features
  
+ Changing date/time values to a numeric value, or vice versa  
  
+ Renaming columns
  
 Use [Edit Metadata](edit-metadata.md) any time you need to modify the definition of a column, typically to meet requirements for a downstream module. For example, some modules can work only with specific data types, or require flags on the columns, such as `IsFeature` or `IsCategorical`.  
  
 After performing the required operation, you can reset the metadata to its original state. 
  
##  How to configure Edit Metadata
  
1.  In Machine Learning Studio (classic), add [Edit Metadata](edit-metadata.md) module to your experiment and connect the dataset you want to update. You can find it under **Data Transformation**, in the **Manipulate** category.
  
2.  Click **Launch the column selector** and choose the column or set of columns to work with. You can choose columns individually, by name or index, or you can choose a group of columns, by type.  

     > [!TIP] 
     > Need help using column indices? See the [Technical Notes](#bkmk_TechnicalNotes) section.
  
3.  Select the **Data type** option if you need to assign a different data type to the selected columns. Changing the data type might be needed for certain operations: for example, if your source dataset has numbers handled as text, you must change them to a numeric data type before using math operations. 

    + The data types supported are `String`, `Integer`, `Floating point`, `Boolean`, `DateTime`, and `TimeSpan`. 

    + If multiple columns are selected, you must apply the metadata changes to **all** selected columns. For example, let's say you choose 2-3 numeric columns. You could change them all to a string data type, and rename them in one operation. However, you can't change one column to a string data type and another column from a float to an integer.
  
    + If you do not specify a new data type, the column metadata is unchanged. 
    
    + Changes of data type affect only the metadata that is associated with the dataset and how the data is handled in downstream operations. The actual column values are not altered unless you perform a different operation (such as rounding) on the column. You can recover the original data type at any time by using [Edit Metadata](edit-metadata.md) to reset the column data type.  

    > [!NOTE]
    > If you change any type of number to the **DateTime** type, leave the **DateTime Format** field blank. Currently, it is not possible to specify the target data format.  
   >  
   >  Machine Learning can convert dates to numbers, or numbers to dates, if the numbers are compatible with one of the supported .NET DateTime objects. For more information, see the [Technical Notes](#bkmk_TechnicalNotes) section.  
      
4.  Select the **Categorical** option to specify that the values in the selected columns should be treated as categories. 

    For example, you might have a column that contains the numbers 0,1 and 2, but know that the numbers actually mean "Smoker", "Non smoker" and "Unknown". In that case, by flagging the column as categorical you can ensure that the values are not used in numeric calculations, only to group data. 
  
5.  Use the **Fields** option if you want to change the way that Machine Learning uses the data in a model.

    + **Feature**: Use this option to flag a column as a feature, for use with modules that operate only on feature columns. By default, all columns are initially treated as features.  
  
    + **Label**: Use this option to mark the label (also known as the predictable attribute, or target variable). Many modules requires that at least one (and only one) label column be present in the dataset. 
    
        In many cases, Machine Learning can infer that a column contains a class label, but by setting this metadata you can ensure that the column is identified correctly. Setting this option does not change data values, only the way that some machine learning algorithms handle the data.
  
    + **Weight**: Use this option with numeric data to indicate that column values represents weights for use in machine learning scoring or training operations. Only one weight column can be present in a dataset, and the column must be numeric.
  
    > [!TIP]
    >  Have data that doesn't fit into these categories?  For example, your dataset might contain values such as unique identifiers that are not useful as variables. Sometimes IDs can cause problems when used in a model. 
    >   
    >  Fortunately "under the covers" Machine Learning keeps all your data, so you don't have to delete such columns from the dataset. When you need to perform operations on some special set of columns, just remove all other columns temporarily by using the [Select Columns in Dataset](select-columns-in-dataset.md) module. Later you can merge the columns back into the dataset by using the [Add Columns](add-columns.md) module.  
  
6. Use the following options to clear previous selections and restore metadata to the default values.  
  
    + **Clear feature**: Use this option to remove the feature flag.  
  
         Because all columns are initially treated as features, for modules that perform mathematical operations, you might need to use this option to prevent numeric columns from being treated as variables.
  
    + **Clear label**: Use this option to remove the **label** metadata from the specified column.  
  
    + **Clear score**: Use this option to remove the **score** metadata from the specified column.  
  
         Currently the ability to explicitly mark a column as a score is not available in Machine Learning. However, some operations result in a column being flagged as a score internally. Also, a custom R module might output score values.
  
    + **Clear weight**: Use this option to remove the **weight** metadata from the specified column.  
  
7.  For **New column names**, type the new name of the selected column or columns.  
  
    + Column names can use only characters that are supported by the UTF-8 encoding. Empty strings, nulls, or names consisting entirely of spaces are not allowed.  
  
    + To rename multiple columns, type the names as a comma-separated list in order of the column indices.  
  
    + All selected columns must be renamed. You cannot omit or skip columns.  
  
    > [!TIP] 
    > If you need to rename multiple columns, you can paste in a comma-delimited string prepared in advance. Or, use the [Execute R Script](execute-r-script.md) or [Apply SQL Transformation](apply-sql-transformation.md) modules.  See the [Technical Notes](#bkmk_TechnicalNotes) section for code and examples.
  
8.  Run the experiment.  
  
## Examples  

 For examples of how [Edit Metadata](edit-metadata.md) is used in preparing data and building models, see the [Azure AI Gallery](https://azure.microsoft.com/documentation/services/machine-learning/models/):  
  
-  [Breast cancer detection](https://go.microsoft.com/fwlink/?LinkId=525726): Column names are changed after joining to datasets. The _Patient ID_ column is also flagged as **categorical** to ensure that it is not used in a calculation, but rather than handled as a string value.  
  
- [Twitter sentiment analysis](https://go.microsoft.com/fwlink/?LinkId=525274): Demonstrates how to use [Edit Metadata](edit-metadata.md) to ensure that columns are treated as features. Later in the experiment, the feature metadata is cleared.  
  
- [Data Processing and analysis](https://go.microsoft.com/fwlink/?LinkId=525733): In this sample, [Edit Metadata](edit-metadata.md) is used to define new column names for data that was loaded from a webpage.  
  
##  <a name="bkmk_TechnicalNotes"></a> Technical notes

This section contains known issues, frequently asked questions, and some examples of common workarounds.

### Known Issues

-   **Custom metadata is not supported.** It is not possible to use custom metadata in Machine Learning or to edit column metadata outside  [Edit Metadata](edit-metadata.md). For example, you cannot add metadata indicating that a column is a unique identifier, or add other descriptive attributes . Machine Learning supports only the metadata attributes that are used within R for working with factors, features, weights, and labels.  
  
-   **Unsupported data types.** The following numeric data types are not supported: Double (decimal) and TimeStamp.  
  
-   **Identifying score columns.** Currently there is no option in [Edit Metadata](edit-metadata.md) to flag a column as containing *scores*. However, you can use the [Execute R Script](execute-r-script.md) module with a script similar to the following  to indicate that a column contains scores:  
  
    ```R
    dataset <- maml.mapInputPort(1)   
    attr(dataset$x, "label.type")= "True Labels"  
    attr(dataset$y, "feature.channel")= "Multiclass Classification Scores"  
    attr(dataset$y, "score.type")= "Assigned Labels"  
    maml.mapOutputPort("dataset");
    ```

+ **Problems with datetime formats.**  The underlying `datetime` data type used by Machine Learning is `POSIXct`.  
  
    If all dates in a column can be parsed by the default parser, the column is imported and treated as string data. 
    
    If you try to convert a column to `DateTime` by using the **Edit Metadata** module and get an error, it means that the date is not in a format that .Net accepts by default.  In this case, we recommend that you use the [Execute R Script](execute-r-script.md) module or the [Apply SQL Transformation](apply-sql-transformation.md) module to transform your column to a format that is accepted by the default parser.  
  
    [DateTime.Parse Method](https://msdn.microsoft.com/library/System.DateTime.Parse%28v=vs.110%29.aspx)  
  
    [Standard Date and Time Format Strings](https://msdn.microsoft.com/library/az4se3k1%28v=vs.110%29.aspx)  
 
### Selecting columns using column indices

In very large datasets, it is not feasible to manually type or select all column names. Using the column index is one shortcut that you can use to specify many columns. This section provides some tips on using column indices.

For example, open the Column Selector, click **WITH RULES**, select **Include** and **column indices**, and then type a range or series of numbers as follows:

+ Type `1-20` to select the first 20 columns
+ Type `5-20` to select a range of columns beginning at 5 and including column 20.
+ Type `1,5,10,15` to select discontinuous columns
+ Type `1-2, 5` to select columns 1, 2 and 5, skipping columns 3 and 4
+ You cannot type an index value that is greater than the number of columns available in the dataset.

The following experiments provide some examples of other methods for selecting and modifying multiple columns:

+ [Binary Classification: Breast Cancer Detection](https://gallery.azure.ai/Experiment/Binary-Classification-Breast-cancer-detection-2): The original data contained many blank columns generated during import from a spreadsheet. The extra columns were removed by specifying columns 1-11 in the **Split Data** module. 

+ [Download dataset from UCI](https://gallery.azure.ai/Experiment/Sample-2-Dataset-Processing-and-Analysis-Auto-Imports-Regression-Dataset-5): Demonstrates how you can provide column names as a list using the **Enter Data Manually** module, and then insert the list into the dataset as headings, using the **Execute R script** module. 

+ [Regex Select Columns](https://gallery.azure.ai/CustomModule/Regex-Select-Columns-1): This experiment provides a custom module that lets you apply a regular expression to column names. You could use this module as an input to **Edit Metadata**.

### Alternate methods for modifying column names

If you have many columns to rename, you can use the **Execute R Script** module, or the **Apply SQL Transformation** module. 

#### Using R script

Data sets used by Machine Learning are passed into this module as a data.frame, meaning that you can use the R `colnames()` function and other related R functions, to list or change column names.

For example, the following code creates a list of new column names, and then applies that list to the input dataset to generate new column headings.

```R
irisdata <- maml.mapInputPort(1);    
newnames <- c("CLASS", "SEPAL  LENGTH", "SEPAL WIDTH", "PETAL LENGTH", "PETAL WIDTH");
colnames(irisdata) = newnames
maml.mapOutputPort("irisdata");
```

The following example uses a regular expression in R to globally replace all instances of the specified string in the column names for `irisdata`:

```R
# Map input dataset to variable
newirisdata <- maml.mapInputPort(1) # class: data.frame
names(newirisdata) <- gsub("col", "iris", names(newirisdata))
maml.mapOutputPort("newirisdata");
```

#### Using SQL

The following example takes a dataset as the input, and then changes the column names using the **AS** keyword.

```sql
SELECT col1 as [C1], 
  col2 as [C2], 
  col3 as [C3], 
  col4 as [C4],
  col5 as [C5] 
FROM t1;
```

##  Expected input  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  Module parameters  

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Column|Any|ColumnSelection||Choose the columns to which your changes should apply.|  
|Data type|List|Metadata editor datatype|Unchanged|Specify the new data type for the column.|  
|Categorical|List|Metadata editor categorical|Unchanged|Indicate if the column should be flagged as categorical.|  
|Fields|List|Metadata editor flag|Unchanged|Specify if the column should be considered a feature or label by learning algorithms.|  
|*New column names*|any|String||Type the new names for the columns.|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with changed metadata|  
  
##  Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of input datasets are null or empty.|  
|[Error 0017](errors/error-0017.md)|An exception occurs if one or more specified columns have a type that is unsupported by the current module.|  
|[Error 0020](errors/error-0020.md)|An exception occurs if the number of columns in some of the datasets that are passed to the module is too small.|  
|[Error 0031](errors/error-0031.md)|An exception occurs if the number of columns in the column set is less than needed.|  
|[Error 0027](errors/error-0027.md)|An exception occurs when two objects have to be of the same size, but they are not.|  
|[Error 0028](errors/error-0028.md)|An exception occurs when the column set contains duplicate column names and it is not allowed.|  
|[Error 0037](errors/error-0037.md)|An exception occurs if multiple label columns are specified and only one is allowed.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also  
 [Manipulation](data-transformation-manipulation.md)   
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)
