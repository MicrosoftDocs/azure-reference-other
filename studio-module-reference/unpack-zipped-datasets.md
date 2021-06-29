---
title: "ML Studio (classic): Unpack Zipped Datasets - Azure"
description: Learn how to use the Unpack Zipped Datasets module to upload data and script files in compressed format, then unzip them for use in an experiment.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Unpack Zipped Datasets
*Unpacks datasets from a zip package in user storage*  
  
 Category: [Data Input and Output](data-input-and-output.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview

This article describes how to use the **Unpack Zipped Datasets** module in Machine Learning Studio (classic), to upload data and script files in compressed format, and then unzip them for use in an experiment.

The purpose of this module is to reduce data transfer times when working with very large datasets by saving and uploading your data files in a compressed format. Generally, zipping files is a good option when your dataset is so large that you want to use compression for the upload, to minimize upload time and associated costs.

The module takes as input a dataset in your workspace. The dataset must have been uploaded in a compressed format. The module then decompresses the dataset and adds the data to your workspace.

## How to use Unpack Zipped Datasets

This section describes how to prepare your data and then unzip it in Machine Learning Studio (classic). 

### Step 1. Prepare files

Before uploading your file, make sure that the data in the file can be used in Machine Learning:

+ Ensure that the data in the file uses UTF-8 encoding.

    If the file is small enough, you can open it in Notepad and then save the file in the desired encoding. Many other text editors offer similar functionality.  For CSV files, you can use Excel's **Save As** or **Export** commands to specify a file format and encoding.  

+ Verify that the data files use a supported **format**, such as CSV, TSV, ARFF, or SVMLight.  

+ Compress the data by adding the data file to a .ZIP or .GZ format archive file. Other archive types are not supported. 

+ Remove password protection. If any of the files or the compressed folder itself has been encrypted or password-protected, you must unlock or decrypt the file before you upload it. The module cannot detect encrypted data types and does not support dialog boxes for password entry from arbitrary clients.  

### Step 2. Upload dataset to your workspace

Next, upload the zipped dataset to your experiment workspace.  
  
1.  Click **NEW**, select **DATASET**, and select **FROM LOCAL FILE**.

3. Locate the zipped file to upload. When you select the file, the type should automatically be set to **Zip file (.zip)**.  
  
### Step 3. Add zipped dataset to experiment

After the dataset has uploaded completely, add it to your experiment in zipped format.

1. In the left-hand navigation pane of Machine Learning Studio (classic), select **Saved Datasets**, and then expand **My Datasets**. 

2. Locate the zipped dataset that you just uploaded, and drag it to the experiment canvas.

### Step 4. Unpack dataset

The final step is to unpack the dataset.

1.  Connect the zipped dataset to the input of the **Unpack Zipped Datasets** module.  
  
2.  In **Dataset to Unpack**, type the name of a single dataset to unpack.  
  
    -   If you saved a worksheet with the name **Sheet1** as an Excel CSV file named **Test.csv**, the name of the dataset would be **Test.csv**, not **Sheet1**.  
      
    -   The name that you type in the **Dataset to Unpack** text box must be exactly the same as the name of the original file **before** it was compressed, including the file name extension. For example, if you want to unpack a dataset based on the text file **Users.txt**, type **Users.txt**, not **Users**.  
  
    -   If you put multiple files into one compressed folder, you must unpack one dataset at a time.  
  
    > [!TIP]
    >  If you leave the property blank, the module gets the file name from the zipped file, assuming the compressed archive file contains only one source file. If the compressed archive contains multiple files, a run-time error is raised.
  
3.  For **Dataset file format**, specify the original format of the dataset: that is, the format before it was zipped.  
  
     You can upload and unzip datasets that were created using any of these formats: CSV, ARFF, TSV, SvmLight.  
  
     If this property is left empty, the module identifies the dataset using the source file name.
  
4.  Select the option, **File has header row**, if the original dataset had a header row.  Otherwise the first row of data is used as the header. If this is not what you want, add a header prior to input. 
  
     This option applies only to .CSV and .TSV files.  
  
    > [!NOTE]
    >  If you change the format of the file, this option is reset.  
  
5. If the file is compressed, use the **Compression file format** option to specify the algorithm that was used to compress or expand the file.  
  
     Currently the .ZIP and GZ (or Gzip) formats are supported.  
  
6. Run the experiment.  

### Results
  
+ To verify that the data was imported correctly, right-click the **Unpacked Zipped Datasets** module, and select **Visualize** .  
  
+ To change the name of the dataset, right-click the **Unpacked Zipped Datasets** module, and select **Save as Dataset**. At this point you can type a different name. 

    This option is handy if you are unpacking multiple datasets from a single ZIP file.  
  
## Examples

To demonstrate how this module works, we created a sample .ZIP file containing four different CSV files. All files were saved from Excel. 
 
 |File name |Description|
 |----|----|
 |names-uni.csv| Unicode file with column headings|
 |names-utf.csv| UTF-8 file with column headings|
 |nonames-uni.csv| Unicode file with no column headings|
 |nonames-utf8.csv| UTF-8 file with no column headings|

The entire zipped file was uploaded, and then the **Unpack Zipped Datasets** module was run four times to extract each of the four files, using these settings:

1. **Dataset to unpack** = names-uni.csv, **File has header row** = TRUE
2. **Dataset to unpack** = names-utf8.csv, **File has header row** = TRUE
3. **Dataset to unpack** = nonames-uni.csv, **File has header row** = FALSE
4. **Dataset to unpack** = nonames-utf8.csv, **File has header row** = FALSE  

The results were as expected:

| File name | Upload result|
|----|----|
|names-uni.csv|Error 0049: Error while parsing the file. File is not Unicode (UTF-8) encoded|
 |names-utf8.csv| Success. Uses original column names from source file.|
 |nonames-uni.csv| Error 0049: Error while parsing the file. File is not Unicode (UTF-8) encoded|
 |nonames-utf8.csv| Success. Column names Col1, col2, ...col*n* are automatically added to the dataset.|

> [!NOTE]
> If you use the option, **File has header row** = TRUE, and the source file actually does not have a column heading, the first row of data is used as the column heading.
 
## Technical notes

You cannot use this module to unpack zipped R packages into your workspace. R packages must be uploaded and consumed as zipped files.

For more information about how to work with zipped R packages, see [Execute R Script](execute-r-script.md).  

> [!NOTE]  
> Confused about the difference between UTF-8 and Unicode? See this Wikipedia article: [What is UTF-8](https://wikipedia.org/wiki/UTF-8)
 
##  Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Compression file format|Zip<br /><br /> Gzip|compression rule|Zip|Compression algorithm used to compress or expand the file.|  
|Dataset to Unpack|Any|String|none|Name of  dataset to register with Azure ML Studio (classic). If the name of a dataset is not specified, the name is obtained from the file name in the zipped file.|  
|Dataset file format|CSV<br /><br /> TSV<br /><br /> ARFF<br /><br /> SVMLIGHT|File format|CSV|File format of the dataset in the zipped file|  
|File has header row|TRUE/FALSE|Boolean|False|Set to **True** only if the CSV/TSV file has a header row| 
##  Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|Zip|Zipped file containing datasets|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Output dataset|  
  
## See also  

[Data Input and Output](data-input-and-output.md)
