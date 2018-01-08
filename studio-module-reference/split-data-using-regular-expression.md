---
title: "Split Data using Regular Expression | Microsoft Docs"
ms.custom: ""
ms.date: 06/02/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c8bc8103-02ce-490a-a299-1db1a50b2e12
caps.latest.revision: 3
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Split Data using Regular Expression
This topic describes how to use the **Regular Expression Split** option in the [Split Data](split-data.md) module of Azure Machine Learning. Dividing datasets used for training and testing, either randomly or by some criteria, is an important task in many machine learning workflows.

Use a **regular expression split** if there is a single text column in your data that you can use to divide the data. You'll define a regular expression that includes the text column name, and then set conditions that apply to the column, such as "begins with", ""contains", or "does not contain".

For general information about data partitioning for machine learning experiments, see [Split Data](split-data.md) and [Partition and Split](partition-and-sample.md). 


##  <a name="HowRegularSplit"></a> How to Use Regular Expression Split
  
1.  Add the [Split Data](split-data.md) module to your experiment, and connect it as input to the dataset you want to split.  
  
2.  For **Splitting mode**, select **Regular expression split** .  

3. In the **Regular expression** box, type a valid regular expression. Some examples are provided [here](#bkmk_RegularExpressionExamples).
  
     Based on the regular expression you provide, the dataset is divided into two sets of rows: rows with values that match the expression and all remaining rows. The regular expression is applied only to the specified column in the dataset. Also, regular expressions can be applied only to columns that contain string data types.  
  
4. Run the experiment, or right-click the module and select **Run selected**.

  
##  <a name="bkmk_RegularExpressionExamples"></a> Examples  

The following examples demonstrate how to divide a dataset using **Regular Expression** mode:  
  
 Using regular expressions to divide the dataset is useful when you need to divide your dataset based on a known value, or part of a value. You can also use it for a variety of preprocessing and filtering tasks.  
  
-   Filter on all rows that contain the text "Gryphon" by applying the following regular expression to a string column:  
  
    ```  
    \"Text" Gryphon  
    ```  
  
     In this example, the substring can be found in any position within the column. The match is case-sensitive.  
  
-   Separate the dataset based on the second column of the dataset, denoted here by the index value of 1. The first result dataset will contains all rows where the index column begins with one of these characters: a, b, c, d, e, f:  
  
    ```  
    (\1) ^[a-f]  
    ```  
  
     Note that the regular expression match is case-sensitive.  
  
-   Assume you want to divide some server log data into two categories for analysis: connections behind the firewall and connections with IP addresses outside the firewall. You can use the following regular expression on the IP_Address field (which is of type string) to put into the first output all addresses that begin with “10.”  
  
    ```  
    (\IP_Address) ^[10]  
    ```  

> [!TIP] 
> For more information about composing regular expressions, see the [MSDN library](https://msdn.microsoft.com/library/kweb790z\(v=vs.110\).aspx), or this Wikipedia article: [Regular Expressions](http://en.wikipedia.org/wiki/Regular_expressions)  

  
## See Also  


 [Split Data using Relative Expression](split-data-using-relative-expression.md)   
 [Split Data using Split Rows](split-data-using-split-rows.md)   
 [Split Data using Recommender Split](split-data-using-recommender-split.md)
 
 [A-Z Module List](a-z-module-list.md)  
 [Sample and Split](data-transformation-sample-and-split.md)    
 [Partition and Sample](partition-and-sample.md)    