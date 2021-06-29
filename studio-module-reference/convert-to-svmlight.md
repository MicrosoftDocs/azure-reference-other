---
title: "ML Studio (classic): Convert to SVMLight - Azure"
description: Learn how to use the Convert to SVMLight module to convert your datasets to the format that is used by SVMLight.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Convert to SVMLight
*Converts data input to the format used by the SVM-Light framework*  
  
 Category: [Data Format Conversions](data-format-conversions.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  
 
This article describes how to use the [Convert to SVMLight](convert-to-svmlight.md) module in Machine Learning Studio (classic), to convert your datasets to the format that is used by SVMLight. 

The SVM-Light framework was developed by researchers at Cornell University. The SVM-Light library implements Vapnik's Support Vector Machine, but the format has been adopted elsewhere and can be used for many machine learning tasks, including classification and regression.  
  
For more information, see [SVMLight Support Vector Machine](http://svmlight.joachims.org/).  
  
## How to configure Convert to SVMLight  

The conversion to SVMLight format entails converting each case into a row of data that begins with the label, followed by feature-value pairs expressed as colon-separated numbers. The conversion process **does not** automatically identify the correct columns, so it is important that you prepare the columns in your dataset before attempting conversion. For more information, see [Preparing Data for Conversion](#bkmk_PreparingData). 
    
1. Add the [Convert to SVMLight](convert-to-svmlight.md) module to your experiment. You can find this module in the [Data Format Conversions](data-format-conversions.md) category in Machine Learning Studio (classic). 

2. Connect the dataset or output that you want to convert to SVMLight format.

3. Run the experiment.

4. Right-click the output of the module, select **Download**, and save the data to a local file for modification or for reuse with a program that supports SVMLight.

### <a name="bkmk_PreparingData"></a>Preparing data for conversion

To illustrate the conversion process, this example uses the **Blood Donor** dataset in Studio (classic). 

This sample dataset has the following format, in tabular form.  
  
|Recency|Frequency|Monetary|Time|Class|  
|-|-|-|-|-|  
|2|50|12500|98|1|  
|0|13|3250|28|1|  
|1|1|4000|35|1|  
|2|20|5000|45|1|  
 |1|24|6000|77|0|  
  
Note that the label column, named [Class] in this dataset, is the last column in the table. However, if you convert the dataset to SVMLight without first indicating that which column contains the label, the first column, [Recency], is used as the label, and the [Class] column is treated as a feature:  
  
<code>2 1:50 2:12500 3:98 4:1</code>  
<code>0 1:13 2:3250 3:28 4:1</code>   
<code>1 1:16 2:4000 3:35 4:1</code>  
  
To make sure the labels are generated correctly at the beginning of the row for each case, you must add two instances of the [Edit Metadata](edit-metadata.md) module.  
  
1. In the first instance of **Edit Metadata**, select the label column ([Class]) and for **Fields**, select **Label**.  
  
2. In the second instance of **Edit Metadata**, select all feature columns that you need in the converted file ([Recency], [Frequency], [Monetary], [Time]) and for **Fields**, select **Features**.  
  
After the columns have been identified correctly, you can run the **Convert to SVMLight** module. After conversion, the first few rows of the Blood Donor dataset now have this format: 

- The label value precedes each entry, followed by the values for [Recency], [Frequency], [Monetary], and [Time], identified as features 1, 2, 3 and 4 respectively.  
  
- The label value of 0 in the fifth row has been converted to -1. This is because SVMLight supports only binary classification labels.   
  
<code>1 1:2 2:50 3:12500 4:98</code>   
<code>1 1:0 2:13 3:3250 4:28</code>   
<code>1 1:1 2:16 3:4000 4:35</code>  
<code>1 1:2 2:20 3:5000 4:45</code>   
<code>-1 1:1 2:24 3:6000 4:77</code>   

You can't directly use this text data for models in Azure ML, or visualize it. However, you can download it to a local share. 

While you have the file open, we recommend that you add a comment line, prefaced by <code>#</code>, so that you can add notes about the source or the original feature column names. 

To use an SVMLight file in Vowpal Wabbit, and make additional modifications as described here: [Conversion to Vowpal Wabbit Format](#bkmk_VWConvert). When the file is ready, upload it to Azure blob storage, and call it directly from one of the Vowpal Wabbit modules.

## Examples  

There are no examples in the [Azure AI Gallery](https://gallery.azure.ai/): that are specific to this format.
  
## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Usage tips

The executables provided in the SVM-Light framework require both an *example file* and a *model file*. However, this module creates only the example file. You must create the model file separately by using the SVMLight libraries.  
  
The example file is the file that contains the training examples.  
  
-   **Optional header**  
  
     The first lines can contain comments. Comments must be prefixed with the number sign (#).  
  
     The file format output by **Convert to SVMLight** does not create headers. You can edit the file to add comments, a list of column names, and so forth.  
  
-   **Training data**  
  
     Each case is on its own row. A case consists of a target value followed by a series of indices and the associated feature values.  
  
     The response value must be 1 or -1 for classification, or a number for regression.  
  
     The target value and each of the index-value pairs are separated by a space.  
  
### Training data example

The following table shows how the values in the columns of the Two-Class Iris dataset are converted to a representation in which each column is represented by an index, followed by a colon, and then the value in that column:  
  
|Iris Dataset|Iris Dataset Converted to SVMLight|  
|------------------|----------------------------------------|  
|1 6.3 2.9 5.6 1.8|1 1:6.3 2:2.9 3:5.6 4:1.8|  
|0 4.8 3.4 1.6 0.2|-1 1:4.8 2:3.4 3:1.6 4:0.2|  
|1 7.2 3.2 6 1.8|1 1:7.2 2:3.2 3:6 4:1.8|  
  
 Note that the names of the feature columns are lost in the conversion.  
  
### <a name ="bkmk_VWConvert"></a>Using SVMLight to prepare a Vowpal Wabbit file
  
The SVMLight format is similar to the format used by Vowpal Wabbit. To change the SVMLight output file to a format usable for training a Vowpal Wabbit model, just add a pipe symbol between the label and the list of features.  
  
For example, compare these lines of input:  
  
**Vowpal Wabbit format, including optional comment**  
  
<code># features are [Recency], [Frequency], [Monetary], [Time]</code>  
<code>1 &#124; 1:2 2:50 3:12500 4:98</code>   
<code>1 &#124; 1:0 2:13 3:3250 4:28</code> 
  
**SVMLight format, including optional comment**  
  
<code># features are [Recency], [Frequency], [Monetary], [Time]</code>  
<code>1 1:2 2:50 3:12500 4:98</code>   
<code>1 1:0 2:13 3:3250 4:28</code>  
  
##  Expected inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|SvmLight|Output dataset|  
  
## See also  
 [Data Format Conversions](data-format-conversions.md)   
 [A-Z Module List](a-z-module-list.md)
