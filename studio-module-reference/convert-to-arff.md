---
title: "Convert to ARFF | Microsoft Docs"
ms.custom: ""
ms.date: 03/02/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 62d2cece-d832-4a7a-a0bd-f01f03af0960
caps.latest.revision: 22
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Convert to ARFF
*Converts data input to the attribute relation file format used by the Weka toolset*  
  
 Category: [Data Format Conversions](data-format-conversions.md)  
  
## Module Overview  
 You can use the  [Convert to ARFF](convert-to-arff.md) module to convert datasets and results in Azure Machine Learning to the attribute-relation file format used by the Weka toolset. This format is known as ARFF.

The ARFF data specification for Weka supports multiple machine learning tasks, including data preprocessing, classification, and feature selection. In this format, data is organized by entites and their attributes, and is contained in a single text file. You can find details of the Weka file format in the [Technical Notes](#technical-notes) section.

In general, conversion to the Weka file format is required only if you want to use both Azure Machine Learning and Weka, and intend to move your training data back and forth between them. 

For more information about the Weka toolset, see this Wikipedia article: [Weka (machine learning)](https://wikipedia.org/wiki/Weka_(machine_learning))

> [!WARNING]
>  You cannot overwrite an existing ARFF file in Azure Storage.  

## How to Use [Convert to ARFF](convert-to-arff.md)  
 
  
1.  Add the [Convert to ARFF](convert-to-arff.md) module to your experiment. You can find this module in the [Data Format Conversions](data-format-conversions.md) group in the **experiment items** list in Azure Machine Learning Studio. 

2. Connect it to any module that outputs a dataset.   
  
3.  Run the experiment, or click the [Convert to ARFF](convert-to-arff.md) module, and click **Run selected**.  
  
4.  Double-click the output of [Convert to ARFF](convert-to-arff.md), and select the **Download** option to create a copy of the data in a local folder. If you do not specify a folder, a default file name is applied and the file is saved in the local **Downloads** library. 
    
    This format does not support other options, such as export to Python or R code.
    
 
## Examples  
 Although there are no examples specific to these formats, you can see examples of how format conversion is used by exploring these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Color-Based Image Compression](http://go.microsoft.com/fwlink/?LinkId=525272) sample exports the datasets used for each portion of the analysis to files for reproducibility and use on other analytics platforms.  
  
-   The [Cross Validation for Binary Classification sample](http://go.microsoft.com/fwlink/?LinkId=525734) exports the results of cross validation to files so that the results for multiple models can be compared by using a tool such as Excel.  
  
## Technical Notes  

This section provides an example of how a typical dataset would look when converted to to ARFF.

Typically an ARFF data file is comprised of two sections: a **header** that defines the data source and schema, and the **data** section, which contains the actual entities and their attributes.  
  
**Header**  
  
Defines the list of the attributes (in columns) and their data types. 

The header can also contain multiple comment lines that describe the data source or any other notes.  
  
<code>% Source: Iris dataset, UCI   % 0 = Iris-setosa, 1= Iris-virginica   @RELATION iris   @ATTRIBUTE sepal_length  NUMERIC   @ATTRIBUTE sepal_width   NUMERIC   @ATTRIBUTE petal_length  NUMERIC   @ATTRIBUTE petal_width   NUMERIC   @ATTRIBUTE class        {0, 1}</code>
  
> [!TIP] 
> If the dataset you are converting does not have column names, use the [Edit Metadata](edit-metadata.md) module to add column names before using converting to ARFF.  
  
**Data**  
  
The data section consists of comma-separated values, and looks very much like a CSV file without column headings.  
  
<code>@DATA   5.1,3.5,1.4,0.2,0</code>  
  
For additional information about this file format, see the Weka Wiki page: [ARFF (developer version)](http://weka.wikispaces.com/ARFF+%28developer+version%29).  
  
**ARFF version**

Azure Machine Learning Studio saves ARFF files by using the ARFF 3.0 format.  
  

  
##  <a name="ExpectedInputs"></a> Expected Input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|Arff|Output dataset|  
  
## See Also  
 [Data Format Conversions](data-format-conversions.md)   
 [A-Z Module List](a-z-module-list.md)