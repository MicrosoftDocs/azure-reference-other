---
title: "ML Studio (classic): Group Categorical Values - Azure"
description: Learn how to use the Group Categorical Values module to create an in-place lookup table.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Group Categorical Values

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Groups data from multiple categories into a new category*

 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Group Categorical Values** module in Machine Learning Studio (classic), to create an in-place lookup table.

The typical use for grouping categorical values is to merge multiple string values into a single new level. For example, you might assign individual postal codes in a region to a single regional code, or group multiple products under one category.

To use this module, you type the lookup values you want to use, and map existing values to the replacement values. You can create groupings only for categorical columns, not to  columns of numeric type or columns designated as labels or features.

Any column values that are not explicitly mapped to a new level are assigned to a default level. For example, if you did not map all the individual postal codes, they would be grouped in a level for unmapped values, which you might name **Unknown**.

> [!NOTE]
>  
> A maximum of 20 new levels can be created, including the default level. If you need more values, or need to define mappings dynamically, we recommend that you use custom R script in the [Execute R Script](execute-r-script.md) module. Or, use SQL statements in the [Apply SQL Transformation](apply-sql-transformation.md) module.

## How to use Group Categorical Values

We recommend that you prepare the list of existing values, and the new categories, beforehand. For each category, you should prepare a new category name, and a comma-separated list of values to include in the category.

1. Add the **Group Categorical Values** module to your experiment. You can find the module under **Data Transformation**, **Manipulation**.

2. Connect a dataset that has the values you want to transform.

3. In the **Properties** pane of  **Group Categorical Values**, use the Column Selector to choose the column that has the levels you want to reduce.

    + We recommend that you click **BEGIN WITH** and **NO COLUMNS** to start, and then add columns by name. Otherwise too many columns might be added as candidates, leading to an error.

    + The column must be a categorical column. If it is not, add [Edit Metadata](edit-metadata.md) upstream, and change the column type.

    + Be sure to remove from the input any columns to which string replacement should not be applied.

4. For **Output mode**, indicate whether you want to output just the new levels, or append the changes to see the original column, with the replacements side by side.

    The default, **ResultOnly**, shows only the new values. The **Inplace** option replaces the existing column values with the new levels.

5. For **Default level name**, type a string value to use as the replacement for all values that are not explicitly mapped. You might use something such as "Unknown" or "Default".

    > [!NOTE]
    > 
    > This default level value is applied to all values that cannot be mapped. If you accidentally included columns that you did not intend to map, the value would be applied to all values in the columns. Therefore, check that column selection is accurate before processing.

6. For **New number of levels**, type a number that indicates the total number of new categories (levels), including the default level for unmapped values.

7. For **Name of new level 1**, provide the new group name for the first category.

8. In the text box that immediately follows, **Comma-separated list of old levels to map to new level 1**, type or paste an exhaustive list of all values to map to the new level. Wildcard characters and regular expressions are not allowed.

9. Continue to type new level names and type or paste values that should be mapped to the new level.

    We recommend that you save your list of values in a separate file as you are working. If you change the number of levels, any strings that you previously typed are removed, and you must start over.

    However, if you are editing a module that was previously saved, you can revert to the original settings.

10. Run the experiment.

### Results

To view the results, right-click the **Group Categorical Values** module, select **Results dataset**, and click **Visualize**.

## Examples

For examples of machine learning in action, see the [Azure AI Gallery](https://gallery.azure.ai/). 

You can also try this module for yourself, by using a small dataset with some string variables that can be easily grouped, such as the **Automobile price** dataset that is provided in Machine Learning Studio (classic).

Let's assume that you want to group cars in the Automobile price dataset by engine size, using the number of cylinders. Rather than lots of different engine sizes, you will create the new levels, "big", "small", and "other" as follows:

+ Big engines: six cylinders or larger
+ Small engines: two or four cylinders
+ Other:  anything else

1. Add the **Select Columns in Dataset** module, and select only the `num-of-cylinders` column.
2. Add the **Edit Metadata** module, and change the `num-of-cylinders` column to **Categorical**.
3. Add the **Group Categorical Values** module and connect the modified dataset.
4. For **Default level name**, type `other`. You don't need to provide values for this level.
5. For **Name of new level 1**, type `big`. In the list of old levels to map to level 1, paste in `six, eight, twelve`. 
6. For **Name of new level 2**, type `small`. For the mapped values, paste in `two, four`.
7. Run the experiment.
8. When you **Visualize** the results, you realize that the original dataset had some odd engine sizes that you didn't account for, such as `five` and `three`. All such items are mapped to the `other` level.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

+ You might encounter the error message, “Column with name "\<columnname>" is not in an allowed category.”

    This message indicates that the column you selected is not a categorical column. You can mark the column as `Categorical` by using [Edit Metadata](edit-metadata.md), or select a different column that contains appropriate category values.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Data to group|  
  
## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Selected columns|any|ColumnSelection|CategoricalAll|Select the columns that will be grouped.|  
|Output mode|any|OutputTo|ResultOnly|Specify how the category labels should be output.|  
|Default level name|any|String||Indicate the default level to use if no mappings match.|  
|New number of levels|List|Number of groups||Specify the number of levels after values have been grouped, including the default level.|  

## Output

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Grouped data|  

## See also

 [Manipulation](data-transformation-manipulation.md)   
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)
