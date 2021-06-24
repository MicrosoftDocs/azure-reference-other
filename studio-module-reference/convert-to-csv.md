---
title: "ML Studio (classic): Convert to CSV - Azure"
description: Learn how to use the Convert to CSV module to convert a dataset into a CSV format that can be downloaded, exported, or shared with R or Python script modules.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Convert to CSV
*Converts data input to a comma-separated values format*  
  
 Category: [Data Format Conversions](data-format-conversions.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview
 
This article describes how to use the [Convert to CSV](convert-to-csv.md) module in Machine Learning Studio (classic), to convert a dataset from Azure ML into a CSV format that can be downloaded, exported, or shared with R or Python script modules.

### More about the CSV format 

The CSV format, which stands for "comma-separated values", is a file format used by many external machine learning tools. Although the native dataset format used by Machine Learning is based on the .NET datatable and thus can be read by .NET libraries, CSV is a common interchange format when working with open-source languages such as R or Python.

Even if you do most of your work in Machine Learning Studio (classic), there are times when you might find it handy to convert your dataset to CSV to use in external tools. For example:

+ Download the CSV file to open it with Excel, or import it into a relational database.  
+ Save the CSV file to cloud storage and connect to it from Power BI to create visualizations.  
+ Use the CSV format to prepare data for use in R and Python. Just right-click the output of the module to generate the code needed to access the data directly from Python or a Jupyter notebook. 

When you convert a dataset to CSV, the file is saved in your Azure ML workspace. You can use an Azure storage utility to open and use the file directly, or you can right-click the module output and download the CSV file to your computer, or use it in R or Python code.  

## How to configure Convert to CSV

1.  Add the [Convert to CSV](convert-to-csv.md) module to your experiment. You can find this module in the [Data Format Conversions](data-format-conversions.md) group in Studio (classic). 

2. Connect it to any module that outputs a dataset.   
  
3.  Run the experiment, or click the [Convert to CSV](convert-to-csv.md) module, and click **Run selected**.

### Results
  
Double-click the output of [Convert to CSV](convert-to-csv.md), and select one of these options.  

 + **Download**: Immediately opens a copy of the data in CSV format that you can save to a local folder. If you do not specify a folder, a default file name is applied and the CSV file is saved in the local **Downloads** library.

    If you select **Download dataset**, you must indicate whether you want to open the dataset, or save it to a local file.  

    If you select **Open**, the dataset is loaded using the application that is associated by default with .CSV files: for example, Microsoft Excel.  

     If you select **Download dataset**, by default, the file is saved with the name of the module plus a GUID representing the workspace ID. However, you can select the **Save As** option during download and change the file name or location.

 + **Save as Dataset**: Saves the CSV file back to the Azure ML workspace as a separate dataset.

 + **Generate Data Access Code**: Azure ML generates two sets of code for you to access the data, either by using Python or by using R. To access the data, copy the code snippet into your application.

 + **Open in a new Notebook**: A new Jupyter notebook is created for you and code inserted for reading the data from your workspace, using the language of your choice: Python 2, Python 3, or R with Microsoft R Open. 
 
     For example, if you choose the R option, sample R code is provided that loads the CSV file into a data frame and displays the first few rows using the `head` function.


## Technical notes  

This section contains implementation details, tips, and answers to frequently asked questions.

### Requirements of the CSV format

The CSV file format is a popular format supported by many machine learning frameworks. The format is variously referred to "comma-separated values" or "character-separated values."  
 
A CSV file stores tabular data (numbers and text) in plain text form. A CSV file consists of any number of records, separated by line breaks of some kind. Each record consists of fields, separated by a literal comma. In some regions, the separator might be a semi-colon. 

Typically, all records have an identical number of fields, and missing values are represented as nulls or empty strings.  

> [!TIP]
> You can easily export data from Excel, Access, or a relational database into CSV files, to use in Machine Learning. Although file names typically have the .CSV extension, Machine Learning does not require that this filename extension be present if you want to import the data as CSV. You can import XLSX, TXT, and other files as CSV. 
> However, the fields in the file must be formatted as described in the preceding section, and the file must use the UTF-8 encoding.

### Common questions and issues 

This section describes some known issues, common questions, and workarounds specific to the **Convert to CSV** module. 

#### Headers must be single rows
  
The CSV file format used in Machine Learning supports a single header row.  You cannot insert multi-line headers.

#### Custom separators supported on import but not export

The [Convert to CSV](convert-to-csv.md) module does not support generating alternative column separators, such as the semicolon (;), which is often used in Europe. 

However, when you import data from CSV files in external storage, you can specify alternative separators. In the [Import Data](import-data.md) module, select the **CSV with encodings** option, and pick a supported encoding.  

#### Inaccurate column separation on string data containing commas
  
It is a common problem in text processing that just about every character that can be specified as a column separator (tabs, spaces, commas, etc.) can also be found randomly in text fields. Importing text from CSV always requires caution to avoid separating text across unnecessary new columns. 

When you try to export a column of string data that contains commas, you might run into problems as well. Machine Learning does not support any special handling or special translation of such data, such as enclosing strings in quotation marks. Also, you cannot use escape characters before a comma to ensure that commas are handled as a literal character. 

Therefore, new fields are created in the output file for each comma that is encountered in the string field. To avoid this problem, there are several workarounds:

- Use the [Preprocess Text](preprocess-text.md) module to remove punctuation characters from string fields.

- Use custom [R script](execute-r-script.md) or [Python script](execute-python-script.md) to process text and ensure that data can be exported correctly.   

**UTF-8 encoding required**

The [Convert to CSV](convert-to-csv.md) module supports only UTF-8 character encoding.  If you need to export data using a different encoding, you can try using the [Execute R Script](execute-r-script.md) or [Execute Python Script](execute-python-script.md) modules to generate custom output.

+ [Encodings and R](https://developer.r-project.org/Encodings_and_R.html)

+ [Python standard encodings](https://docs.python.org/2.4/lib/standard-encodings.html)

#### Dataset does not have column names

If the dataset you are exporting to a CSV file does not have column names, we recommend that you use [Edit Metadata](edit-metadata.md) to add column names before converting it. You cannot add column names as part of the conversion or export process.  

#### SYLK: File format is not valid

If the first column of the dataset that you convert to CSV has the name **ID**, you might get the following error when you try to open the file in Excel:  
  
"SYLK: File format is not valid."  
  
To avoid this error, you must rename the column. For more information, see [https://support.microsoft.com/kb/215591](https://www.betaarchive.com/wiki/index.php/Microsoft_KB_Archive/215591)  

#### I need help with importing from CSV

For importing, don't use the **Export to CSV** module. Instead, use the [Import Data](import-data.md) module.

For general information about importing from CSV, see these resources:

+ [Import your training data into Machine Learning Studio (classic) from various data sources](import-data.md)
+ [AzureML Experiments and Data Interaction](https://gallery.azure.ai/Tutorial/3-AzureML-Experiments-and-Data-Interaction-1): Demonstrates various data sources and how to work with them in Studio (classic).

##  Expected inputs
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|GenericCsv|Output dataset|  
  
## See also  
 [Data Format Conversions](data-format-conversions.md)   
 [A-Z Module List](a-z-module-list.md)
