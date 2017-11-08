---
title: "Enter Data Manually | Microsoft Docs"
ms.custom: ""
ms.date: 02/23/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 4fbef0ab-2c8e-4a25-b5c4-7be76eac33d6
caps.latest.revision: 21
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Enter Data Manually
*Enables entering and editing small datasets by typing values*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the [Enter Data Manually](enter-data-manually.md) module to create a small, single-column dataset by typing values, rather than loading data from a source in Azure Machine Learning Studio or from a local file.  
  
 This can be helpful in scenarios such as:  
  
-   Generating a short list of values for testing  
  
-   Creating a shorter list of labels for use with the [Group Categorical Values](group-categorical-values.md) or [Execute R Script](execute-r-script.md) modules  
  
-   Entering values for use in [Apply Math Operation](apply-math-operation.md) or replacement values for use in [Replace Discrete Values](replace-discrete-values.md)  
  
-   Typing a list of column names to insert in a dataset  
  
## How to Manually Create New Data for Use in Experiments  
  
1.  Add the [Enter Data Manually](enter-data-manually.md) module to your experiment. You can find this module in the [Data Input and Output](data-input-and-output.md) group in the **experiment items** list in Azure Machine Learning Studio. 
  
2.  For **DataFormat**, select one of the following options:  
  
    -   **ARFF**. The attribute-relation file format, used by Weka. For more information, see [Convert to ARFF](convert-to-arff.md).  
  
    -   **CSV**. Comma-separated values format. For more information, see [Convert to CSV](convert-to-csv.md).  
  
    -   **SVMLight**. A format used by Vowpal Wabbit and other machine learning frameworks. For more information, see [Convert to SVMLight](convert-to-svmlight.md).  
  
    -   **TSV**. Tab-separated values format. For more information, see [Convert to TSV](convert-to-tsv.md).  
  
     These options  determine  how data that you provide will be parsed. For example, if you choose the ARFF format, you must provide your data in a format that meets the ARFF specifications, or a run-time error will occur.  
  
     The requirements for each format differ greatly, so be sure to read the related topics.  
  
3.  Click inside the **Data** text box to start entering data.  Note that the following formats require special considerations:  
  
    -   **CSV**  
  
         To create multiple columns,  paste in comma-separated text, or   type multiple columns using commas between fields.  
  
         If you select the **HasHeader** option, you can use the first row of values as the column heading.  
  
         If you deselect this option, the columns names, Col1, Col2 and so forth are used. You can add or change columns names later using [Edit Metadata](edit-metadata.md).  
  
    -   **TSV**  
  
         To create multiple columns,  paste in tab-separated text, or   type multiple columns using tabs between fields.  
  
         If you select the **HasHeader** option, you can use the first row of values as the column heading.  
  
         If you deselect this option, the columns names, Col1, Col2 and so forth are used. You can add or change columns names later using [Edit Metadata](edit-metadata.md).  
  
    -   **ARFF**  
  
         Paste in an existing ARFF format file.  
  
         If you are typing values directly, be sure to add the optional header and required attribute fields at the  beginning of the data. For example, the following header and attribute rows could be added to a simple list. The column heading would be  SampleText.  
  
         % Title: SampleTextARFF  
  
         % Source: Enter Data module  
  
         @ATTRIBUTE SampleText STRING  
  
         @DATA  
  
         \<type first data row here>  
  
    -   **SVMLight**  
  
         Type of paste in values using the SVMLight format.  
  
         For example, the following sample represents the first couple lines of the Blood Donation dataset, in SVMight format:  
  
        ```  
        # features are [Recency], [Frequency], [Monetary], [Time]  
        1 1:2 2:50 3:12500 4:98   
        1 1:0 2:13 3:3250 4:28   
        ```  
  
         If you run the [Enter Data Manually](enter-data-manually.md) module, these lines are converted to a dataset of columns and index values as follows:  
  
        ||||||  
        |-|-|-|-|-|  
        |Col1|Col2|Col3|Col4|Labels|  
        |0.00016|0.004|0.999961|0.00784|1|  
        |0|0.004|0.999955|0.008615|1|  
  
4.  Press ENTER after each row, to start a new line.  
  
     Be sure to press ENTER after the final row. If you press ENTER multiple times to add multiple empty trailing rows, the final empty row will be trimmed, but other empty rows will be treated as missing values.  
  
     You can enter rows with missing values, and then go back and edit the rows to add values later.  
  
5.  Right-click the module and select **Run selected** to parse the data and load it into your workspace as a dataset.  
  
     You can view the dataset by clicking the output port and selecting **Visualize**.  
  
## Examples  
 For examples of how this module is used in machine learning, see this sample experiment in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Download Data sample](http://go.microsoft.com/fwlink/?LinkId=525938) gets data from the UCI Machine Learning repository and then uses [Enter Data Manually](enter-data-manually.md) to create column names.  
  
     Sample R code is also provided, which you can use to merge the entered rows with the dataset.  
  
##  <a name="Notes"></a> Technical Notes  
  
-   Regardless of the saved format, data that you enter is implicitly converted to the dataset ([Data Table](data-table.md)) format for use in experiments. However, data is not persisted as a saved dataset unless you explicitly choose the **Save as Dataset** option.  
  
     If you do not save the data in [Enter Data Manually](enter-data-manually.md) as a dataset, it will be removed from the workspace cache when you end the session. However, you can run the experiment again to make the data available.  
  
-   If you combine the data from [Enter Data Manually](enter-data-manually.md) with another dataset, the combined dataset cannot have two columns with the same name. If there are duplicate column names, a numeric suffix is appended to the column from the right dataset to make the column names unique.  
  
     For example, assume that you have two instances of [Enter Data Manually](enter-data-manually.md) that contain the column **TestData**, and use the [Add Columns](add-columns.md) module to merge them. The column from the left instance of [Enter Data Manually](enter-data-manually.md) would remain as **TestData**, and the column from the right instance of [Enter Data Manually](enter-data-manually.md) would be renamed **TestData (2)**.  
  
## See Also  
 [Data Input and Output](data-input-and-output.md)   
 [A-Z Module List](a-z-module-list.md)