---
title: "Data Format Conversions | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/16/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d1293c4f-5629-4eef-90a4-097af6945ed6
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Data Format Conversions

This article lists the modules provided in Azure Machine Learning Studio for converting data among various file formats used in machine learning. 

The supported formats include:

+ The **dataset** format used throughout Azure Machine Learning 
+ The **ARFF** format used by [Weka](http://www.cs.waikato.ac.nz/ml/weka/), an open-source Java-based set of machine learning algorithms
+ The **SVM Light** format, which was developed for the [SVMlight](http://svmlight.joachims.org/) framework for machine learning, but can also be used by Vowpal Wabbit
+ The **tab-separated** and **comma-separated** flat file formats supported by most relational databases. These formats are also widely supported by R and Python.  

By converting data to these formats, you can more easily move results and data between different machine learning frameworks or storage mechanisms.

> [!NOTE]
> These data conversion modules only convert the complete dataset to a specified format. If you need to do any casting, truncation, conversion of date-time formats, or other  manipulation of the values, use the modules in this section: [Data Transformation](data-transformation.md), or see the list of [related tasks](#bkmk_Related). 

## Common data conversion scenarios

You would typically use the modules for data conversion if you need to move data from an Azure Machine Learning experiment to another machine learning tool or platform, or if you need to export data from Azure Machine Learning in a format that can be used by a database or other tools. For example:

|Task| Use this|
|----|----|
|An intermediate dataset must be saved for use in Excel, or for import to a database| Use the [CSV](convert-to-csv.md) module or the [TSV](convert-to-tsv.md) module to prepare the data in the correct format. Then, either download the data or save it to Azure storage.|
|You want to re-use data from your experiment in R or Python code|Use the [CSV](convert-to-csv.md) module or the [TSV](convert-to-tsv.md) module to prepare the data. Then, right-click the converted dataset to get the Python code needed to access the dataset. |
|You are porting your experiment and data between Weka and Azure Machine Learning|Use the [ARFF](convert-to-arff.md) module to prepare the data. Then, download the results. |
|You need to prepare data in the SVMLight framework|Use the [Convert to SVMLight](convert-to-svmlight.md) module to prepare the data. Then, download the resulting data.|
|Create data for use with Vowpal Wabbit|Use the [SVMLight](convert-to-svmlight.md) format and then modify the files as described in the topic. Save the file in Azure blob storage to use with a Vowpal Wabbit module in Azure Machine Learning.|
|Data is not in a tabular format|Coerce it to a dataset format by using the [Convert to Dataset](convert-to-dataset.md) module.|
 

## <a name="bkmk_Related"></a>Related tasks

If you need to import data into Azure Machine Learning. or transform data in individual columns, use these modules before performing data conversion:

|Task| Use this|
|----|----|   
|Import data from my computer into Azure Machine Learning|Upload datasets in CSV format as described in [Import your training data into Azure Machine Learning Studio](import-data.md). |
|Import data from a cloud data source, including Hadoop or Azure|Use the [Import Data](import-data.md) module. |
|Save machine learning datasets out to Azure blob storage, a Hadoop cluster, or other cloud-based storage|Use the [Export Data](export-data.md) module.|
|Change the data type of columns; cast columns to a different format or type|In Azure Machine Learning, use these modules: [Edit Metadata](edit-metadata.md), [Apply SQL Transformation](apply-sql-transformation.md). If you are proficient with R or Python, try these modules: [Execute Python Script](execute-python-script.md),  [Execute R Script](execute-r-script.md). |
|Round, group, or normalize numerical data|Use [Apply Math Operation](apply-math-operation.md), [Group Data into Bins](group-data-into-bins.md), or [Normalize Data](normalize-data.md)|
    
  
##  <a name="modules"></a> List of modules  

The **Data Format Conversions** category includes these modules:  
  
|Module|Description|  
|------------|-----------------|  
|[Convert to ARFF](convert-to-arff.md)|Converts data input to the attribute relation file format used by the Weka toolset|  
|[Convert to CSV](convert-to-csv.md)|Converts a dataset to a comma-separated values format|  
|[Convert to Dataset](convert-to-dataset.md)|Converts a data input to the internal Dataset format used by Microsoft Azure Machine Learning|  
|[Convert to SVMLight](convert-to-svmlight.md)|Converts data input to the format used by the SVM-Light framework|  
|[Convert to TSV](convert-to-tsv.md)|Converts data input to the tab-delimited format|  
  
## See also  
 [Data Transformation](data-transformation.md)   
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)