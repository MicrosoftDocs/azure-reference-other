---
title: "ML Studio (classic): Enter Data Manually - Azure"
description: Learn how to use the Enter Data Manually module to create a small dataset by typing values. The dataset can have multiple columns.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Enter Data Manually

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Enables entering and editing small datasets by typing values*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the [Enter Data Manually](enter-data-manually.md) module in Machine Learning Studio (classic), to create a small dataset by typing values. The dataset can have multiple columns.
  
This module can be helpful in scenarios such as these:  
  
- Generating a small set of values for testing  
  
- Creating a short list of labels

- Entering values for use in [Apply Math Operation](apply-math-operation.md)

- Specifying replacement values for use in [Replace Discrete Values](replace-discrete-values.md)  
  
- Typing a list of column names to insert in a dataset

## How to use Enter Data Manually 
  
1.  Add the [Enter Data Manually](enter-data-manually.md) module to your experiment. You can find this module in the [Data Input and Output](data-input-and-output.md) category in Machine Learning Studio (classic). 
  
2.  For **DataFormat**, select one of the following options. These options determine how the data that you provide should be parsed. The requirements for each format differ greatly, so be sure to read the related topics.  
  
    -   **ARFF**. The attribute-relation file format, used by Weka. For more information, see [Convert to ARFF](convert-to-arff.md).  
  
    -   **CSV**. Comma-separated values format. For more information, see [Convert to CSV](convert-to-csv.md).  
  
    -   **SVMLight**. A format used by Vowpal Wabbit and other machine learning frameworks. For more information, see [Convert to SVMLight](convert-to-svmlight.md).  
  
    -   **TSV**. Tab-separated values format. For more information, see [Convert to TSV](convert-to-tsv.md).  

     If you choose a format and do not provide data that meets the format specifications, a run-time error occurs.
  
3.  Click inside the **Data** text box to start entering data. The following formats require special attention:  
  
    - **CSV**:  To create multiple columns, paste in comma-separated text, or type multiple columns using commas between fields.
  
        If you select the **HasHeader** option, you can use the first row of values as the column heading.  
  
        If you deselect this option, the columns names, Col1, Col2 and so forth are used. You can add or change columns names later using [Edit Metadata](edit-metadata.md).  
  
    - **TSV**: To create multiple columns, paste in tab-separated text, or type multiple columns using tabs between fields.  
  
        If you select the **HasHeader** option, you can use the first row of values as the column heading.  
  
        If you deselect this option, the columns names, Col1, Col2 and so forth are used. You can add or change columns names later using [Edit Metadata](edit-metadata.md).  
  
    -   **ARFF**:  Paste in an existing ARFF format file. If you are typing values directly, be sure to add the optional header and required attribute fields at the  beginning of the data. 
    
        For example, the following header and attribute rows could be added to a simple list. The column heading would be `SampleText`.
    
        ```text
        % Title: SampleText.ARFF  
        % Source: Enter Data module  
        @ATTRIBUTE SampleText STRING  
        @DATA  
        \<type first data row here>  
        ```

    -   **SVMLight**: Type or paste in values using the SVMLight format.  
  
        For example, the following sample represents the first couple lines of the Blood Donation dataset, in SVMight format:  
  
        ```text  
        # features are [Recency], [Frequency], [Monetary], [Time]  
        1 1:2 2:50 3:12500 4:98   
        1 1:0 2:13 3:3250 4:28   
        ```  
  
        When you run the [Enter Data Manually](enter-data-manually.md) module, these lines are converted to a dataset of columns and index values as follows:  
  
        |Col1|Col2|Col3|Col4|Labels|  
        |-|-|-|-|-|  
        |0.00016|0.004|0.999961|0.00784|1|  
        |0|0.004|0.999955|0.008615|1|  
  
4.  Press ENTER after each row, to start a new line.  
  
     **Be sure to press ENTER after the final row.** 
     
     If you press ENTER multiple times to add multiple empty trailing rows, the final empty row is removed trimmed, but other empty rows are treated as missing values.  
  
     If you create rows with missing values, you can always filter them out later.  
  
5.  Right-click the module and select **Run selected** to parse the data and load it into your workspace as a dataset.  
  
     To view the dataset, click the output port and select **Visualize**.  
  
## Examples

For examples of how this module is used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/):  
  
- [Download Data sample](https://go.microsoft.com/fwlink/?LinkId=525938): Gets data from the UCI Machine Learning repository and then uses [Enter Data Manually](enter-data-manually.md) to create column names. Sample R code is also provided, which you can use to merge the entered rows with the dataset.  
  
##  Technical notes  

This section contains implementation details, tips, and answers to frequently asked questions.

-   Regardless of the saved format, data that you enter is implicitly converted to the dataset ([Data Table](data-table.md)) format for use in experiments. However, data is not persisted as a saved dataset unless you explicitly choose the **Save as Dataset** option.  
  
     If you do not save the data in [Enter Data Manually](enter-data-manually.md) as a dataset, it is removed from the workspace cache when you end the session. However, you can run the experiment again to make the data available.  
  
-   If you combine the data from [Enter Data Manually](enter-data-manually.md) with another dataset, the combined dataset cannot have two columns with the same name. If there are duplicate column names, a numeric suffix is appended to the column from the right dataset to make the column names unique.  
  
     For example, assume that you have two instances of [Enter Data Manually](enter-data-manually.md) that contain the column **TestData**, and use the [Add Columns](add-columns.md) module to merge them. The column from the left instance of [Enter Data Manually](enter-data-manually.md) would remain as **TestData**, and the column from the right instance of [Enter Data Manually](enter-data-manually.md) would be renamed **TestData (2)**.  
  
## See also  
 [Data Input and Output](data-input-and-output.md)   
 [A-Z Module List](a-z-module-list.md)
