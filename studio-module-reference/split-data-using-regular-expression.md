---
title: "ML Studio (classic): Split Data using Regular Expression - Azure"
description: Learn how to apply a filter criteria to a text column with the Regular Expression Split option in the Split Data module.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Split Data using Regular Expression

This article describes how to use the **Regular Expression Split** option in the [Split Data](split-data.md) module of Azure Machine Learning Studio (classic). This option is useful when you need to apply a filter criteria to a text column. For example, you might divide your dataset by whether a particular product is mentioned.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

You can use a **regular expression split** on a single text column. You define a regular expression that includes the text column name, and then set conditions that apply to the column, such as "begins with", ""contains", or "does not contain".

For general information about data partitioning for machine learning experiments, see [Split Data](split-data.md) and [Partition and Split](partition-and-sample.md). 

## Related tasks

Other options in the **Split Data** module:

+ [Split data using relative expressions](split-data-using-relative-expression.md): Apply an expression to numeric data. 

+ [Split recommender datasets](split-data-using-recommender-split.md): Divide datasets that are used in recommendation models. The dataset should have three columns: items, users, and ratings 

+ [Split by percentage of dataset](split-data-using-split-rows.md)

##  Use a regular expression to divide a dataset
  
1.  Add the [Split Data](split-data.md) module to your experiment, and connect it as input to the dataset you want to split.  
  
2.  For **Splitting mode**, select **Regular expression split**.

3. In the **Regular expression** box, type a valid regular expression. Some examples are provided [here](#bkmk_RegularExpressionExamples).
  
    The regular expression is applied only to the specified column, which must be a string data type.

    For help composing regular expressions, see the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).

4. Run the experiment, or right-click the module and select **Run selected**.

    Based on the regular expression you provide, the dataset is divided into two sets of rows: rows with values that match the expression and all remaining rows. 

##  <a name="bkmk_RegularExpressionExamples"></a> Examples  

The following examples demonstrate how to divide a dataset using the **Regular Expression** option. 

### Single whole word 

This example puts into the first dataset all rows that contain the text `Gryphon` in the column `Text`, and puts other rows into the second output of **Split Data**:

```text
    \"Text" Gryphon  
```

### Substring

This example looks for the specified string in any position within the second column of the dataset, denoted here by the index value of 1. The match is case-sensitive.

```text
(\1) ^[a-f]
```

The first result dataset contains all rows where the index column begins with one of these characters: `a`, `b`, `c`, `d`, `e`, `f`. All other rows are directed to the second output.

### String match on IP addresses

This example divides some server log data into two categories for analysis: connections behind the firewall and connections with IP addresses outside the firewall. The regular expression is applied to the `IP_Address` field (a **string** data type).

```text
(\IP_Address) ^[10]
```

The first output contains all addresses that begin with `10`.

## See also

 [Sample and Split](data-transformation-sample-and-split.md)    
 [Partition and Sample](partition-and-sample.md)    
