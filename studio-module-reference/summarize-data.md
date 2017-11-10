---
title: "Summarize Data | Microsoft Docs"
ms.custom: ""
ms.date: 03/02/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 2c57074f-674f-45de-ad85-d84e4726f04e
caps.latest.revision: 15
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Summarize Data
*Generates a basic descriptive statistics report for the columns in a dataset*  
  
 Category: [Statistical Functions](statistical-functions.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **Summarize Data** module to create a set of standard statistical measures that describe each column in the input table. The module does not return the original dataset. Instead, it generates a row for each column, beginning with the column name and followed by relevant statistics for that column, based on its data type.  
  
 Such reports are useful when you want to understand the characteristics of the complete dataset. For example, you might need to know:  
  
-   How many missing values are there in each column?  
  
-   How many unique categorical values are there in a feature column?  
  
-   What is the mean and standard deviation of the column?  
  
 You can get a partial list of statistics by using the **Visualize** option in any module that outputs a dataset, but the visualization includes only some top number of rows. By outputting the statistics in a tabular dataset, you can use the data in BI reporting tools or provide the values as input to another custom operation in the experiment.  
  
## How to Create Data Summaries  

1. Add the **Summarize Data** module to your experiment. You can find this module in the [Statistical Functions](statistical-functions.md) group in the **experiment items** list in Azure Machine Learning Studio.

2. Connect the dataset for which you want to generate a report.

    If you want to report on only some columns, use the [Select Columns in Dataset](select-columns-in-dataset.md) module to project a subset of columns to work with.

3. No additional parameters are required. By default, the module analyzes all columns that are provided as input, and depending on the type of values in the columns, outputs a relevant set of statistics as described in the [Results](#bkmk_Results) section.

4. Run the experiment, or right-click the module, and select **Run selected**.

### <a name ="bkmk_Results"></a>Results

The report from the module can include the following statistics. Some statistics might not be computed, depending on the column data type. See the [Technical Notes](#bkmk_Notes) section for details.  

|Column name|Description|
|------|------|  
|**Feature**|Name of the column|
|**Count**|Count of all rows|
|**Unique Value Count**|Number of unique values in column|
|**Missing Value Count**|Number of unique values in column|
|**Min**|Lowest value in column|  
|**Max**|Highest value in column|
|**Mean**|Mean of all column values|
|**Mean Deviation**|Mean deviation of column values|
|**1st Quartile**|Value at first quartile|
|**Median**|Median column value|
|**3rd Quartile**|Value at third quartile|
|**Mode**|Mode of column values|
|**Range**|Integer representing the number of values between the maximum and minimum values|
|**Sample Variance**|Variance for column; see Note|
|**Sample Standard Deviation**|Standard deviation for column; see Note|
|**Sample Skewness**|Skewness for column; see Note|
|**Sample Kurtosis**|Kurtosis for column; see Note|
|**P0.5**|0.5% percentile|
|**P1**|1% percentile|
|**P5**|5% percentile|
|**P95**|95% percentile|
|**P99.5**|99.5% percentile |

  

> [!NOTE]
> The module calculates the statistics on the assumption that the statistical instances belong to a representative sample of a population. if you need statistics calculated for the population, use the options in the [Compute Elementary Statistics](compute-elementary-statistics.md) module, which can compute either sample or population statistics. 
  
## Examples  
 For examples of how to use the **Summarize Data** module in an experiment, see these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Download dataset from UCI](http://go.microsoft.com/fwlink/?LinkId=525938) sample reads a dataset in CSV format by using its URL in the UCI Machine Learning Repository, and it generates some basic statistics about the dataset.  
  
-   The [Dataset Processing and Analysis](http://go.microsoft.com/fwlink/?LinkId=525733) sample loads the dataset into the workspace, changes column names, and adds metadata.  
  
-   The [Prediction of student performance](http://go.microsoft.com/fwlink/?LinkId=525727) sample reads data stored in TSV format from Azure Blob storage.  
  
##  <a name="bkmk_Notes"></a> Technical Notes  
  
- For numeric and Boolean columns, you can output the mean, median, mode, and standard deviation. 

- For non-numeric columns, only the values for **Count**, **Unique value count**, and **Missing value count** are computed. For other statistics, a null value is returned.    

-   Columns that contain Boolean values are processed as follows:  
  
    -   When calculating **Min**, a logical AND is applied.  
  
    -   When calculating **Max**, a logical OR is applied.  
  
    -   When computing **Range**, the module first checks whether the number of unique values in the column equals 2.  
  
    -   When computing any statistic that requires floating-point calculations, values of True are treated as 1.0, and values of False are treated as 0.0.  
   
  
##  <a name="ExpectedInputs"></a> Expected Input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|A profile of the input dataset that contains descriptive statistics|  
  
##  <a name="exceptions"></a> Exceptions  
 For a complete list of error messages, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more inputs are null or empty.|  
|[Error 0020](errors/error-0020.md)|Exception occurs if the number of columns in some of the datasets passed to the module is too small.|  
|[Error 0021](errors/error-0021.md)|Exception occurs if the number of rows in some of the datasets passed to the module is too small.|  
  
## See Also  
 [Statistical Functions](statistical-functions.md)   
 [Compute Elementary Statistics](compute-elementary-statistics.md)   
 [descriptive](summarize-data.md)   
 [A-Z Module List](a-z-module-list.md)