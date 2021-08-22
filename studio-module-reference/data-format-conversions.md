---
title: "ML Studio (classic): Data Format Conversions - Azure"
description: Learn about the  modules for converting data among various file formats used in machine learning.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Data Format Conversions

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

This article lists the modules provided in Machine Learning Studio (classic) for converting data among various file formats used in machine learning. 

The supported formats include:

- The **dataset** format that's used throughout Machine Learning.
- The **ARFF** format that's used by [Weka](https://www.cs.waikato.ac.nz/ml/weka/). Weka is an open-source Java-based set of machine learning algorithms.
- The **SVMLight** format. The SVMLight format was developed for the [SVMlight](http://svmlight.joachims.org/) framework for machine learning. It can also be used by Vowpal Wabbit.
- The **tab-separated (TSV)** and **comma-separated (CSV)** flat file formats that are supported by most relational databases. These formats are also widely supported by R and Python.  

When you convert data to these formats, you can more easily move results and data between different machine learning frameworks or storage mechanisms.

> [!NOTE]
> These data conversion modules only convert the complete dataset to a specified format. If you need to do any casting, truncation, conversion of date-time formats, or other manipulation of the values, use the modules in [Data Transformation](data-transformation.md), or see the list of [related tasks](#bkmk_Related).

## Common data conversion scenarios

You typically use the data conversion modules if you need to move data from an Machine Learning experiment to another machine learning tool or platform. You also can use the modules to export data from Machine Learning in a format that can be used by a database or other tools. For example:

|Task| Use this|
|----|----|
|You need to save an intermediate dataset to use in Excel, or to import to a database.|Use the [CSV](convert-to-csv.md) module or the [TSV](convert-to-tsv.md) module to prepare the data in the correct format. Then, either download the data or save it to Azure Storage.|
|You want to reuse data from your experiment in R or Python code.|Use the [CSV](convert-to-csv.md) module or the [TSV](convert-to-tsv.md) module to prepare the data. Then, right-click the converted dataset to get the Python code that you need to access the dataset. |
|You are porting your experiment and data between Weka and Machine Learning.|Use the [ARFF](convert-to-arff.md) module to prepare the data. Then, download the results. |
|You need to prepare data in the SVMlight framework.|Use the [Convert to SVMLight](convert-to-svmlight.md) module to prepare the data. Then, download the resulting data.|
|Create data to use with Vowpal Wabbit.|Use the [SVMLight](convert-to-svmlight.md) format. Then, modify the files as described in the article. Save the file in Azure Blob storage to use with a Vowpal Wabbit module in Machine Learning.|
|Data is not in a tabular format.|Coerce it to a dataset format by using the [Convert to Dataset](convert-to-dataset.md) module.|
 

## <a name="bkmk_Related"></a>Related tasks

If you need to import data into Machine Learning or transform data in individual columns, use these modules before you perform data conversion:

|Task| Use this|
|----|----|   
|Import data from my computer into Machine Learning.|Upload datasets in CSV format as described in [Import your training data into Machine Learning Studio (classic)](import-data.md).|
|Import data from a cloud data source, including Hadoop or Azure.|Use the [Import Data](import-data.md) module.|
|Save machine learning datasets to Azure Blob storage, a Hadoop cluster, or other cloud-based storage.|Use the [Export Data](export-data.md) module.|
|Change the data type of columns or cast columns to a different format or type.|In Machine Learning, use the [Edit Metadata](edit-metadata.md) or [Apply SQL Transformation](apply-sql-transformation.md) modules. If you are proficient with R or Python, try the [Execute Python Script](execute-python-script.md) or [Execute R Script](execute-r-script.md) modules.|
|Round, group, or normalize numerical data.|Use the [Apply Math Operation](apply-math-operation.md), [Group Data into Bins](group-data-into-bins.md), or [Normalize Data](normalize-data.md) modules.|
   
  
##  List of modules  

The **Data Format Conversions** category includes these modules:    
- [Convert to ARFF](convert-to-arff.md): Converts data input to the attribute relation file format that's used by the Weka toolset.
- [Convert to CSV](convert-to-csv.md): Converts a dataset to a comma-separated values format.
- [Convert to Dataset](convert-to-dataset.md): Converts data input to the internal dataset format that's used by Machine Learning.
- [Convert to SVMLight](convert-to-svmlight.md): Converts data input to the format that's used by the SVMlight framework.
- [Convert to TSV](convert-to-tsv.md): Converts data input to the tab-delimited format.

## See also

- [Data Transformation](data-transformation.md)
- [Module categories and descriptions](machine-learning-module-descriptions.md)
