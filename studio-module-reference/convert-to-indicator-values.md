---
title: "Convert to Indicator Values | Microsoft Docs"
ms.custom: ""
ms.date: 06/30/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6ea59c36-f283-410e-b34c-edfabfac39b0
caps.latest.revision: 18
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Convert to Indicator Values
*Converts categorical values in columns to indicator values*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  
  
## Module Overview  
 
This article describes how to use the [Convert to Indicator Values](convert-to-indicator-values.md) module in Azure Machine Learning Studio. The purpose of this module is to convert columns that contain categorical values into a series of binary indicator columns that can more easily be used as features in a machine learning model.  
  
 For example, suppose you have a column with scores that indicate whether a server has a high, medium or low probability of failure.  
  
|Server ID|Failure score|  
|---------------|-------------------|  
|10301|Low|  
|10302|Medium|  
|10303|High|  
  
 You can use [Convert to Indicator Values](convert-to-indicator-values.md) to convert the single column of labels into multiple columns of this pattern:  
  
|Server ID|Failure score - Low|Failure score - Medium|Failure score - High|  
|---------------|--------------------------|-----------------------------|---------------------------|  
|10301|1|0|0|  
|10302|0|1|0|  
|10303|0|0|1|  
  
 Here is how the conversion works:  
  
-   In the **Failure score** column that describes risk, there are only three possible values (High, Medium, and Low), and no missing values. Therefore exactly three new columns are created.  
  
-   The new indicator columns are named based on the column headings and values of the source column, using this pattern: *\<source column>- \<data value>*.  
  
-   There should be a 1 in exactly one indicator column, and 0 in all other indicator columns. That is because each server can have only one risk rating.  
  
 You can now use the three indicator columns as features and analyze their correlation with other properties that are associated with different risk level.  
  
## How to Configure [Convert to Indicator Values](convert-to-indicator-values.md)  
  
1.  Add the [Convert to Indicator Values](convert-to-indicator-values.md) module to your Azure Machine Learning experiment, and connect it to the datset containing the columns you want to convert.

    You can find this module in the **Data Transformations** category, under **Manipulation**.

2. Use the **Column Selector** to choose one or more categorical columns.  
  
     To ensure that the columns you select are categorical, use [Edit Metadata](edit-metadata.md) before [Convert to Indicator Values](convert-to-indicator-values.md) in your experiment, to mark the target column as categorical.  
  
2.  Select the **Overwrite categorical columns** option if you want to output **only** the new Boolean columns.  
  
     By default, this option is off, which lets you see the categorical column that is the source, together with the related indicator columns.  
  
    > [!TIP]
    >  If you choose the option to overwrite, the source column is not actually deleted or modified. Instead, the new columns are generated and presented in the output dataset, and the source column remains available in the workspace. 
    > If you need to see the original data, you can use the [Add Columns](add-columns.md) module at any time to add the source column back in.  
  
## Examples  
 
 You can see examples of how this module is used by exploring these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   In the [Breast cancer detection](http://go.microsoft.com/fwlink/?LinkId=525726) sample, patients are binned into groups based on patient ID numbers, and then **Indicator Values** is used to flag which group the patient belongs to. Later, the group indicators are used when scoring models.  
  
-   In the [Direct marketing](http://go.microsoft.com/fwlink/?LinkId=525168) sample, probabilities are compared to a constant by using [Apply Math Operation](apply-math-operation.md), and the Yes/No values that indicate whether the score was above or below the constant are turned into new indicator columns.  
  
-   In the [Network intrusion detection](http://go.microsoft.com/fwlink/?LinkId=525724) sample, log data is loaded from Azure storage. The class variable (which describes, for example, if an attack is a rootkit or buffer overflow) is converted to a categorical column and then expanded to multiple indicator values.  
  
## Technical Notes  
  
-   Only columns that are marked as categorical can be converted to indicator columns. If you see this error, it is likely that one of the columns you selected is not categorical:  
  
     Error 0056: Column with name  \<column name> is not in an allowed category.  
  
     By default most string columns are handled as string features, so you must explicitly mark them as categorical using [Edit Metadata](edit-metadata.md).  
  
-   An error will be displayed if you do not select at least one categorical column.  
  
-   There is no limit on the number of columns that you can convert to indicator columns. However, because each column of values can yield multiple indicator columns, you might want to convert and review just a few columns at a time.  
  
-   If the column contains missing values, a separate indicator column is created for the missing category, with this name: *\<source column>- Missing*  
  
-   If the column that you convert to indicator values contains numbers, they must be marked as categorical like any other feature column. After you have done so, the numbers are treated as discrete values. For example, if you have a numeric column with MPG values ranging from 25 to 30, a new indicator column would be created for each discrete value:  
  
    |Make|Highway mpg -25|Highway mpg -26|Highway mpg -27|Highway mpg -28|Highway mpg -29|Highway mpg -30|  
    |----------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|  
    |Alfa Romeo|0|0|0|0|0|1|  
  
     To avoid getting a huge number of indicator columns, we recommend that you first check the number of values in the column, and bin or quantize the data appropriately.  
  
##  <a name="ExpectedInputs"></a> Expected Input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Dataset with categorical columns|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Categorical columns to convert|Any|ColumnSelection||Select categorical columns to convert to indicator matrices.|  
|Overwrite categorical columns|Any|Boolean|false|If True, overwrite the selected categorical columns; otherwise, append the resulting indicator matrices to the dataset.|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with categorical columns converted to indicator matrices.|  
  
## See Also  
 [Manipulation](data-transformation-manipulation.md)   
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)