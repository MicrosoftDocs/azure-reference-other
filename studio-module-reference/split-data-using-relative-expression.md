---
title: "Split Data using Relative Expression | Microsoft Docs"
ms.custom: ""
ms.date: 06/02/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5db11bad-a518-4874-b1a8-b7786c18fc0d
caps.latest.revision: 3
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Split Data using Relative Expression
This topic describes how to use the **Relative Expression Split** option in the [Split Data](split-data.md) module of Azure Machine Learning. Dividing datasets used for training and testing, either randomly or by some criteria, is an important task in many machine learning workflows.

A **relative expression split** lets you divide a dataset by choosing a single numeric column in your data, and then creating an expression that acts as a filter on the column. The *relative expression* must include the column name, the value, and an operator such as greater than and less than, equal and not equals.

For general information about data partitioning for machine learning experiments, see [Split Data](split-data.md) and [Partition and Split](partition-and-sample.md). 

##  <a name="HowRelativeSplit"></a> How to Use Relative Expression Split

1.  Add the [Split Data](split-data.md) module to your experiment, and connect it as input to the dataset you want to split.  
  
2.  For **Splitting mode**, select **relative expression split** .  
  
3. In the **Relational expression** text box, type an expression that performs a numeric comparison operation.  

     The expression divides the dataset into two sets of rows: rows with values that meet the condition, and all remaining rows. The expression can be applied only to the specified column.  
  
4. Run the experiment, or right-click the module and select **Run selected**.

**Notes**

The following restrictions apply to relative expressions on a dataset:  
  
-   Relative expressions can be applied to any columns that contain a numeric data type. Date/time data types are also supported.  
  
-   Relative expressions can reference a maximum of one column name.  
  
-   In relative expressions, use the ampersand character (&) for the AND operation and use the pipe character (&#124;) for the OR operation.  
  
-   The following operators are allowed for relative expressions: \<, >, \<=, >=, ==, !=  
  
-   You cannot group operations by using "(" and ")".  
  
## <a name="bkmk_RelativeExpressionExamples"></a> Examples  

The following examples demonstrate how to divide a dataset using **Relative Expression** mode:  
  
-   A common scenario is to divide a dataset by years. The following expression selects all rows where the values in the column **Year** are greater than 2010.  
  
    ```  
    \"Year" > 2010  
    ```  
    Note that the date expression must account for all date parts that are included in the data column, and that the format of dates in the data column are expected to be consistent. For example, in a date column using the format `mmddyyyy`, the expression must be something like this:
    
    ```
    \"Date" > 1/1/2010
    ```
      
  
-   The following expression demonstrates how you can use the column index to select all rows in the first column of the dataset that contain values less than or equal to 30, but not equal to 20.  
  
    ```  
    (\0)<=30 & !=20  
    ```  
  
-   Suppose you want to split a table of log data, to group queries that run too long. You could use the following relative expression to put in one dataset the queries that ran over 1 minute, and then use another instance of [Split Data](split-data.md) on the right-hand output to extract another set of queries with response times under one minute but more than 30 seconds.  
  
    ```  
    \"Elapsed" >00:01:00   
    ```  
  
    ```  
    \"Elapsed" <:00:01:00 & >00:00:30  
    ```  
  
-   The following relative expression specifies that the dataset should be divided by using the date values in the column dt1. Rows with a date greater than 10-08-2015 are added to the first (left) output dataset. Rows with a date of 10-08-2015 or earlier are added to the second (right) output dataset.  
  
    ```  
    \"dt1" > 10-08-2015  
    ```  

 ## See Also  
   
 [Split Data using Regular Expression](split-data-using-regular-expression.md)   
 [Split Data using Split Rows](split-data-using-split-rows.md)   
 [Split Data using Recommender Split](split-data-using-recommender-split.md)
 
 [Sample and Split](data-transformation-sample-and-split.md)   
 [Partition and Sample](partition-and-sample.md)   
 [A-Z Module List](a-z-module-list.md)   
    