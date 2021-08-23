---
title: "ML Studio (classic): Remove Duplicate Rows - Azure"
description: Learn how to use the Remove Duplicate Rows module to remove potential duplicates from a dataset.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Remove Duplicate Rows

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Removes the duplicate rows from a dataset*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the **Remove Duplicate Rows** module in Machine Learning Studio (classic), to remove potential duplicates from a dataset.

For example, assume your data looks like the following, and represents multiple records for patients. 

| PatientID | Initials| Gender|Age|Admitted|
|----|----|----|----|----|
|1|F.M.| M| 53| Jan|
|2| F.A.M.| M| 53| Jan|
|3| F.A.M.| M| 24| Jan|
|3| F.M.| M| 24| Feb|
|4| F.M.| M| 23| Feb|
| | F.M.| M| 23| |
|5| F.A.M.| M| 53| |

Clearly, this example has multiple columns with potentially duplicate data. Whether they are actually duplicates depends on your knowledge of the data. 

+ For example, you might know that many patients have the same name. You wouldn't eliminate duplicates using any name columns, only the **ID** column. That way, only the rows with duplicate ID values are filtered out, regardless of whether the patients have the same name or not.

+ Alternatively, you might decide to allow duplicates in the ID field, and use some other combination of fileds to find unique records, such as first name, last name, age, and gender.  

To set the criteria for whether a row is duplicate or not, you specify a single column or a set of columns to use as **keys**. Two rows are considered duplicates only when the values in **all** key columns are equal. 

When you run the module, it creates a candidate dataset, and returns a set of rows that have no duplicates across the set of columns you specified.

> [!IMPORTANT]
> The source dataset is not altered; this module creates a new dataset that is filtered to exclude duplicates, based on the criteria you specify.

## How to use Remove Duplicate Rows

1. Add the module to your experiment. You can find the **Remove Duplicate Rows** module under **Data Transformation**, **Manipulation**.  

2. Connect the dataset that you want to check for duplicate rows.

3. In the **Properties** pane, under **Key column selection filter expression**, click **Launch column selector**, to choose columns to use in identifying duplicates.

    In this context, **Key** does not mean a unique identifier. All columns that you select using the Column Selector are designated as **key columns**. All un-selected columns are considered non-key columns. The combination of columns that you select as keys determines the uniqueness of the records. (Think of it as a SQL statement that uses multiple equality joins.)

    Examples:

    + "I want to ensure that IDs are unique": Choose only the ID column.
    + "I want to ensure that the combination of first name, last name, and ID is unique": Select all three columns.

4. Use the **Retain first duplicate row** checkbox to indicate which row to return when duplicates are found:

    + If selected, the first row is returned and others discarded. 
    + If you uncheck this option, the last duplicate row is kept in the results, and others are discarded. 

    See the [Technical notes](#bkmk_Notes) section for information on how missinng values are handled.

5. Run the experiment, or click the module and select **Run Selected**.  

6. To review the results, right-click the module, select **Results dataset**, and click **Visualize**. 

> [!TIP]
> If the results are difficult to understand, or if you want to exclude some columns from consideration, you can remove columns by using the [Select Columns in Dataset](select-columns-in-dataset.md) module.

## Examples  

To see examples of how this module is used, see the [Azure AI Gallery](https://gallery.azure.ai/):  
  
-  [Breast cancer detection](https://go.microsoft.com/fwlink/?LinkId=525726): **Remove Duplicate Rows** is used to consolidate the training and test datasets after adding feature columns. 
  
- [Movie recommendation](https://go.microsoft.com/fwlink/?LinkId=525276): Uses **Remove Duplicate Rows** to ensure that there is only one user _rating_ per movie.  
  
- [Twitter sentiment analysis](https://go.microsoft.com/fwlink/?LinkId=525274): **Remove Duplicate Rows** is applied to only the ID and popularity columns, to ensure that there is only one _ordinal ranking_ value per movie. In other words, a movie cannot be both 1st and 3rd, so a single value is used even if users ranked the movie differently.

##  <a name="bkmk_Notes"></a> Technical notes  

This section contains implementation details, tips, and answers to frequently asked questions.

### Implementation details

The module works by looping through all rows of the input dataset. It collects into a candidate output dataset all rows where the unique combination of key column values appears for the first time.

The column array type is preserved independently of the results of row filtering. You cannot force the array to a particular data type by filtering out invalid values; the column array type is based on all values in the column. This restriction also applies when filtering missing values.  

The algorithm used for comparing data values is hash-forced.

## Missing values

The input dataset might have missing values in non-key columns and key columns. These rules apply to missing values:

+ A missing value is considered a valid value in key columns. Missing values can be present in both key.

+ In a sparse dataset, the missing value is considered equal only if it equals the default representation of a sparse value. 

+ In key columns, a missing value is considered equal to other missing values, but not equal to non-missing values. 

##  Expected input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Key column selection filter expression|any|ColumnSelection||Choose the key columns to use when searching for duplicates.|  
|Retain first duplicate row|any|Boolean|true|Indicate whether to keep the first row of a set of duplicates and discard others. If False, the last duplicate row encountered is kept.|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Filtered dataset|  
  
##  Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of the input datasets are null or empty.|  
|[Error 0020](errors/error-0020.md)|An exception occurs if the number of columns in some of the datasets passed to the module is too small.|  
|[Error 0017](errors/error-0017.md)|An exception occurs if one or more specified columns have a type that is unsupported by the current module.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also  
 [Manipulation](data-transformation-manipulation.md)   
 [A-Z Module List](a-z-module-list.md)
