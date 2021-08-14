---
title: "ML Studio (classic): Split Data using Relative Expression - Azure"
description: Learn how to divide into training and testing datasets using a numerical expression with the the Relative Expression Split option in the Split Data module.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Split a dataset using a relative expression

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes how to use the **Relative Expression Split** option in the [Split Data](split-data.md) module of Machine Learning Studio (classic). This option is helpful when you need to divide a dataset into training and testing datasets using a numerical expression. For example:

+ Age greater than 40 vs. 40 or younger
+ Test score of 60 or higher vs. less than 60
+ Rank value of 1 vs. all other values

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

To divide your data, you choose a single numeric column in your data, and define an expression to use in evaluating each row. The *relative expression* must include the column name, the value, and an operator such as greater than and less than, equal and not equals.

This option divides the dataset into **two** groups.

For general information about data partitioning for machine learning experiments, see [Split Data](split-data.md) and [Partition and Split](partition-and-sample.md). 

## Related tasks

Other options in the **Split Data** module:

+ [Split data using regular expressions](split-data-using-regular-expression.md): Apply a regular expression to  a single text column, and divide the dataset based on the results 

+ [Split recommender datasets](split-data-using-recommender-split.md): Divide datasets that are used in recommendation models. The dataset should have three columns: items, users, and ratings 

+ [Split by percentage of dataset](split-data-using-split-rows.md)

##  Use a relative expression to divide a dataset

1.  Add the [Split Data](split-data.md) module to your experiment in Stuio, and connect it as input to the dataset you want to split.
  
2.  For **Splitting mode**, select **relative expression split**.
  
3. In the **Relational expression** text box, type an expression that performs a numeric comparison operation, on a single column:

    - The column contains numbers of any numeric data type, including date/time data types.

    - The expression can reference a maximum of one column name.

    - Use the ampersand character (&) for the AND operation and use the pipe character (|) for the OR operation.

    - The following operators are supported: `<`, `>`, `<=`, `>=`, `==`, `!=`

    - You cannot group operations by using `(` and `)`.

    For ideas, see the [Examples](#bkmk_RelativeExpressionExamples) section.

4. Run the experiment, or right-click the module and select **Run selected**.

    The expression divides the dataset into two sets of rows: rows with values that meet the condition, and all remaining rows.

    If you need to perform additional split operations, you can either add a second instance of **Split Data*, or use the [Apply SQL Transformation](apply-sql-transformation.md) module and define a CASE statement. 

## <a name="bkmk_RelativeExpressionExamples"></a> Examples of relatve expressions 

The following examples demonstrate how to divide a dataset using the **Relative Expression** option in the **Split Data** module:  

### Using calendar year

A common scenario is to divide a dataset by years. The following expression selects all rows where the values in the column `Year` are greater than `2010`.

```text
\"Year" > 2010
```

The date expression must account for all date parts that are included in the data column, and the format of dates in the data column must be consistent. 

For example, in a date column using the format `mmddyyyy`, the expression should be something like this:

```text
\"Date" > 1/1/2010
```

### Using column indices

The following expression demonstrates how you can use the column index to select all rows in the first column of the dataset that contain values less than or equal to 30, but not equal to 20.

```text
(\0)<=30 & !=20
```

### Compound operation on time values using multiple splits

Suppose you want to split a table of log data, to group queries that run too long. You could use the following relative expression on the column, `Elapsed`, to get the queries that ran over 1 minute.

```text
\"Elapsed" >00:01:00
```

To get the queries with response times under one minute but more than 30 seconds, add another instance of [Split Data](split-data.md) on the right-hand output, and use an expression like this:

```text
\"Elapsed" <:00:01:00 & >00:00:30
```

### Split dataset on date values

The following relative expression divides the dataset by using the date values in the column `dt1`.

```text
\"dt1" > 10-08-2015
```

Rows with a date greater than 10-08-2015 are added to the first (left) output dataset. 

Rows with a date of 10-08-2015 or earlier are added to the second (right) output dataset.  

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Restrictions

The following restrictions apply to relative expressions on a dataset:  

+ Relative expressions can be applied only to numeric data types and date/time data types.
+ Relative expressions can reference a maximum of one column name.
+ Use the ampersand character (&) for the AND operation and the pipe character (|) for the OR operation.
+ The following operators are allowed for relative expressions: `<`, `>`, `<=`, `>=`, `==`, `!=`
+ Grouping operations with parentheses is not supported.

 ## See also  
 
 [Sample and Split](data-transformation-sample-and-split.md)   
 [Partition and Sample](partition-and-sample.md)   
