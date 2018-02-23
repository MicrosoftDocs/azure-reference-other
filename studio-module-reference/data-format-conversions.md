---
title: Data Format Conversions | Microsoft Docs
titleSuffix: "Azure Machine Learning Studio"
description: Learn about the modules you can use for data format conversion in Azure Machine Learning.
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
# Data Format Conversions category

This article lists the modules provided in Azure Machine Learning Studio for converting data among various file formats used in machine learning. 

The supported formats include:

- The **dataset** format used throughout Azure Machine Learning.
- The **ARFF** format used by [Weka](http://www.cs.waikato.ac.nz/ml/weka/). Weka is an open-source Java-based set of machine learning algorithms.
- The **SVM Light** format. The SVM Light format was developed for the [SVMlight](http://svmlight.joachims.org/) framework for machine learning. It can also be used by Vowpal Wabbit.
- The **tab-separated (TSV)** and **comma-separated (CSV)** flat file formats that are supported by most relational databases. These formats are also widely supported by R and Python.  

When you convert data to these formats, you can more easily move results and data between different machine learning frameworks or storage mechanisms.

> [!NOTE]
> These data conversion modules only convert the complete dataset to a specified format. If you need to do any casting, truncation, conversion of date-time formats, or other manipulation of the values, use the modules in [Data Transformation](data-transformation.md), or see the list of [related tasks](#bkmk_Related).

## Common data conversion scenarios

You typically use the data conversion modules if you need to move data from an Azure Machine Learning experiment to another machine learning tool or platform. You also can use the modules to export data from Machine Learning in a format that can be used by a database or other tools. For example:

|Task| Use this|
|----|----|
|You need to save an intermediate dataset to use in Excel, or to import to a database.|Use the [CSV](convert-to-csv.md) module or the [TSV](convert-to-tsv.md) module to prepare the data in the correct format. Then, either download the data or save it to Azure Storage.|
|You want to reuse data from your experiment in R or Python code.|Use the [CSV](convert-to-csv.md) module or the [TSV](convert-to-tsv.md) module to prepare the data. Then, right-click the converted dataset to get the Python code that you need to access the dataset. |
|You are porting your experiment and data between Weka and Azure Machine Learning.|Use the [ARFF](convert-to-arff.md) module to prepare the data. Then, download the results. |
|You need to prepare data in the SVMlight framework.|Use the [Convert to SVMLight](convert-to-svmlight.md) module to prepare the data. Then, download the resulting data.|
|Create data to use with Vowpal Wabbit.|Use the [SVMLight](convert-to-svmlight.md) format. Then, modify the files as described in the article. Save the file in Azure Blob storage to use with a Vowpal Wabbit module in Azure Machine Learning.|
|Data is not in a tabular format.|Coerce it to a dataset format by using the [Convert to Dataset](convert-to-dataset.md) module.|
 

## <a name="bkmk_Related"></a>Related tasks

If you need to import data into Azure Machine Learning or transform data in individual columns, use these modules before you perform data conversion:

|Task| Use this|
|----|----|   
|Import data from my computer into Azure Machine Learning.|Upload datasets in CSV format as described in [Import your training data into Azure Machine Learning Studio](import-data.md).|
|Import data from a cloud data source, including Hadoop or Azure.|Use the [Import Data](import-data.md) module.|
|Save machine learning datasets to Azure Blob storage, a Hadoop cluster, or other cloud-based storage.|Use the [Export Data](export-data.md) module.|
|Change the data type of columns or cast columns to a different format or type.|In Azure Machine Learning, use the [Edit Metadata](edit-metadata.md) or [Apply SQL Transformation](apply-sql-transformation.md) modules. If you are proficient with R or Python, try the [Execute Python Script](execute-python-script.md) or [Execute R Script](execute-r-script.md) modules.|
|Round, group, or normalize numerical data.|Use the [Apply Math Operation](apply-math-operation.md), [Group Data into Bins](group-data-into-bins.md), or [Normalize Data](normalize-data.md) modules.|
    
  
##  List of modules  

The Data Format Conversions category includes these modules:    
- [Convert to ARFF](convert-to-arff.md): Converts data input to the attribute relation file format that's used by the Weka toolset.
- [Convert to CSV](convert-to-csv.md): Converts a dataset to a comma-separated values format.
- [Convert to Dataset](convert-to-dataset.md): Converts data input to the internal dataset format that's used by Azure Machine Learning.
- [Convert to SVMLight](convert-to-svmlight.md): Converts data input to the format that's used by the SVMlight framework.
- [Convert to TSV](convert-to-tsv.md): Converts data input to the tab-delimited format.

## Next steps

- Explore the [Data Transformationy](data-transformation.md) category.
- Learn more about [module categories and descriptions](machine-learning-module-descriptions.md).