---
title: "ML Studio (classic): Select Columns in Dataset - Azure"
description: Learn how to use the Select Columns in Dataset module to choose a subset of columns to use in downstream operations. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Select Columns in Dataset

*Selects columns to include or exclude from a dataset in an operation*

Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the [Select Columns in Dataset](select-columns-in-dataset.md) module in Azure Machine Learning Studio (classic), to choose a subset of columns to use in downstream operations. The module does not physically remove the columns from the source dataset; instead, it creates a subset of columns, much like a database *view* or *projection*.

This module is particularly useful when you need to limit the columns available for a downstream operation, or if you want to reduce the size of the dataset by removing unneeded columns.

The columns in the dataset are output in the same order as in the original data, even if you specify them in a different order.

## How to use Select Columns in Dataset

This module has no parameters. You use the column selector to choose the columns to include or exclude.

### Choose columns by name

There are multiple options in the module for choosing columns by name: 

+ Filter and search

    Click the **BY NAME** option.

    If you have connected a dataset that is already populated, a list of available columns should appear. If no columns appear, you might need to run upstream modules to view the column list.

    To filter the list, type in the search box. For example, if you type the letter `w` in the search box, the list is filtered to show the column names that contain the letter `w`.

    Select columns and click the right arrow button to move the selected columns to the list in the right-hand pane.

    + To select a continuous range of column names, press **Shift + Click**.
    + To add individual columns to the selection, press **Ctrl + Click**.

    Click the checkmark button to save and close.

+ Use names in combination with other rules

    Click the **WITH RULES** option.
    
    Choose a rule, such as showing columns of a specific data type.

    Then, click individual columns of that type by name, to add them to the selection list.

+ Type or paste a comma-separated list of column names

    If your dataset is very wide, it might be easier to use indexes or generated lists of names, rather than selecting columns individually. Assuming you have prepared the list in advance:

    1. Click the **WITH RULES** option. 
    2. Select **No columns**, select  **Include**, and then click inside the text box with the red exclamation mark. 
    3. Paste in or type a comma-separated list of previously validated column names. You cannot save the module if any column has an invalid name, so be sure to check the names beforehand.
    
    You can also use this method to specify a list of columns using their index values. See the [Examples](#bkmk_scenarios) section for tips on how to work with column indices.

### Choose by type

If you use the **WITH RULES** option, you can apply multiple conditions on the column selections. For example, you might need to get only feature columns of a numeric data type.

The **BEGIN WITH** option determines your starting point and is very important for understanding the results. 

+ If you select the **ALL COLUMNS** option, all columns are added to the list. Then, you must use the **Exclude** option to *remove* columns that meet certain conditions. 

    For example, you might start with all columns and then remove columns by name, or by type.

+ If you select the **NO COLUMNS** option, the list of columns starts out empty. You then specify conditions to *add* columns to the list. 

    If you apply multiple rules, each condition is **additive**. For example, say you start with no columns, and then add a rule to get all numeric columns. In the Automobile price dataset, that results in 16 columns. Then, you click the **+** sign to add a new condition, and select **Include all features**. The resulting dataset includes all the numeric columns, plus all the feature columns, including some string feature columns.

### Choose by column index

The column index refers to the order of the column within the original dataset.

+ Columns are numbered sequentially starting at 1.  
+ To get a range of columns, use a hyphen. 
+ Open-ended specifications such as `1-` or `-3` are not allowed.
+ Duplicate index values (or column names) are not allowed, and might result in an error.

For example, assuming your dataset has at least eight columns, you could paste in any of the following examples to return multiple non-contiguous columns: 

+ `8,1-4,6`
+ `1,3-8`
+ `1,3-6,4` 

the final example does not result in an error; however, it returns a single instance of column `4`.

For additional tips on working with column indices, see the [Examples](#bkmk_scenarios) section.

### <a name ="bkmk_changeorder"></a>Change order of columns

The option **Allow duplicates and preserve column order in selection** starts with an empty list, and adds columns that you specify by name or by index. Unlike other options, which always return columns in their "natural order", this option outputs the columns in the order that you name or list them. 

For example, in a dataset with the columns Col1, Col2, Col3, and Col4, you could reverse the order of the columns and leave out column 2, by specifying either of the following lists:

+ `Col4, Col3, Col1`
+ `4,3,1`


## Examples  

For examples of how to use [Select Columns in Dataset](select-columns-in-dataset.md), see these sample experiments in the [Model Gallery](https://gallery.azure.ai/):  
  
-   The [Breast cancer detection](https://go.microsoft.com/fwlink/?LinkId=525726) sample uses [Select Columns in Dataset](select-columns-in-dataset.md) to remove a trailing empty column, remove a column with duplicate data, and to project training and test sets.  
  
-   In the [Flight delay prediction](https://go.microsoft.com/fwlink/?LinkId=525725) sample, [Select Columns in Dataset](select-columns-in-dataset.md) is used to exclude all string columns and to exclude columns by name.  
  
-   In the [Prediction of student performance](https://go.microsoft.com/fwlink/?LinkId=525727) sample, [Select Columns in Dataset](select-columns-in-dataset.md) is used to get all temporal features, and to exclude multiple columns.  
  
-   In the [Compare Regressors](https://go.microsoft.com/fwlink/?LinkId=525731) sample, [Select Columns in Dataset](select-columns-in-dataset.md) is used to exclude the column, **num-of-doors**, because it is the wrong data type for the math operation that follows.  

### <a name ="bkmk_scenarios"></a>Common scenarios for column selection 
  
The following examples describe some typical ways that users apply  [Select Columns in Dataset](select-columns-in-dataset.md) in machine learning, and provides some tips for how to select the columns:  
  
-   **I want to remove text columns from the dataset so I can apply a math operation to all numeric columns.**  
  
     Many operations require that only numeric columns be present in the dataset. You can temporarily remove columns that would cause an error, by excluding text and excluding categorical columns (numbers that represent discrete categories).  
  
    1.  Click **Launch column selector**.  
  
    2.  For **Begin With**, select **All columns**.  
  
    3.  Select the **Exclude** option, select **column type**, and then select **String**.  
  
    4.  Click the plus sign (+) to add a new condition.  
  
    5.  Select the **Exclude** option, select **column type**, and then select **Categorical**.  
  
-   **I need to apply feature selection to only the categorical feature columns.**  
  
     If you need to separate columns of a similar type, you can apply multiple conditions. For example, features can be either categorical or numeric, but some feature selection modules do not allow non-numeric fields, so you first have to get features, and then add a condition to get just the numeric features.  
  
    1.  Click **Launch column selector**.  
  
    2.  For **Begin With**, select **No columns**.  
  
    3.  Select the **Include** option, and select **all features**.  
  
    4.  Click the plus sign (+) to add a new condition.  
  
    5.  Select the **Include** option,  select **column type**, and then select **Categorical**.  
  
-   **I need to apply a different normalization operation to different numeric columns.**  
  
     Before applying mathematical operations, you might need to separate integers from floating point numbers, and so forth. To do this use the data types and apply multiple conditions.  
  
    1.  Click **Launch column selector**.  
  
    2.  For **Begin With**, select **No columns**.  
  
    3.  Select the **Include** option, select **column type**, and then select **Numeric**.  
  
    4.  Click the plus sign (+) to add a new condition.  
  
    5.  Select the **Include** option, select **column type**, and then select the numeric type that is incompatible with the downstream operation.  
  
-   **There are too many columns to choose using the selector.**  
  
     Often, after importing a dataset, you find that it has a lot of columns that aren't needed for modeling. However, you want to preserve them for output later, or for identifying cases. You can do this by splitting the dataset into two parts (metadata, and columns used for modeling) and later recombine columns as needed, by using [Add Columns](add-columns.md).  
  
    1.  Click **Launch column selector**.  
  
    2.  For **Begin With**, select **No columns**.  
  
    3.  Select the **Include** option, select **column type**, and then select **Feature**.  
  
    4.  Click the plus sign (+) to add a new condition.  
  
    5.  Select the **Include** option, select **column type**, and then select **Label**.  
  
    6.  Repeat these steps, but start with all columns, and then exclude feature and label columns to create a dataset of only the metadata.  
  
-   **I don't know the index values for the columns I need.**  
  
     If there are just a few columns in your dataset, you can use the **Visualize** option to see the first 100 rows and then figure out which column is index 1, 2, and so forth. 
     
     - The indexes in Azure Machine Learning start at 1, so the first column is always 1.  
     
     - To get the index of the last column, look at the two lists of columns in the Column Selector: AVAILABLE COLUMNS and SELECTED COLUMNS. The gray bar beneath the column list displays the count of columns in each list. Thus, if 24 columns are available and two columns are selected, there are a total of 26 columns, and the index of the final column is 26.
  
    Another option for extracting the schema of your dataset is to use the [Execute R Script](execute-r-script.md) module to get the column names with index numbers. 
    
    1. Connect your dataset to the **Execute R Script** module. 
    2. In the module, type a script like the following to output the column names. The line starting with `myindex` generates a sequence that represents the indexes in order. 
  
        ```R
        dataset1 <- maml.mapInputPort(1) # class: data.frame
        mycolnames <-names(dataset1);
        myindex <- seq(from = 1, to = length(mycolnames), by=1);
        outdata <- as.data.frame(cbind(myindex, mycolnames));
        maml.mapOutputPort("outdata"); 
        ```
  
    Results on Automobile price dataset
      
    |myindex|mycolnames|
    |----|----|
    |1 |symboling|  
    |2 |normalized-losses|  
    |3 |make |

  
## Technical notes  

If you are familiar with relational databases, this module creates a *projection* of the data;  hence the original name, **Project Columns**. In database terms, a projection is a function, such as a Transact-SQL or LINQ statement, that takes a data in tabular format as input and produces a related output.

In relational algebra, a projection is a unary operation, which is written as a set of attribute names. The result of a projection is the set of those attributes, with other attributes discarded.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Select columns|any|ColumnSelection||Select columns to keep in the projected dataset.|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Output dataset|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](errors/error-0001.md)|An exception occurs if one or more specified columns of the dataset couldn't be found.|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more input datasets are null or empty.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).

## See also

 [Manipulation](data-transformation-manipulation.md)   
 
