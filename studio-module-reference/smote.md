---
title: "SMOTE | Microsoft Docs"
ms.custom: ""
ms.date: 10/06/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9f3fe1c4-520e-49ac-a152-2e104169912a
caps.latest.revision: 22
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# SMOTE
*Increases the number of low incidence examples in a dataset using synthetic minority oversampling*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  
  
## Module Overview  

This article describes how to use the SMOTE module in Azure Machine Learning Studio to increase the number of underepresented cases in a dataset used for machine learning. SMOTE is a better way of increasing the number of rare cases than simply duplicating existing cases.  

 You connect the SMOTE module to a dataset that is *imbalanced*. There are many reasons why a dataset might be imbalanced: the category you are targeting might be very rare in the population, or the data might simply be difficult to collect. Typically, you use SMOTE when the *class* you want to analyze is under-represented. 
  
 The module returns a dataset that contains the original samples, plus an additional number of synthetic minority samples, depending on the percentage you specify.  
  
## How the SMOTE method works  

**SMOTE** stands for *Synthetic Minority Oversampling Technique*. This is a statistical technique for increasing the number of cases in your dataset in a balanced way.  The module works by generating new instances from existing cases that you supply as input. 

The new instances are not just copies of existing cases; instead, the algorithm takes samples of the *feature space* for each target class and its nearest neighbors, and generates new examples that combine features of the target case with features of its neighbors. This approach increases the features available to each class and makes the samples more general.  
  
SMOTE takes the entire dataset as an input, but it increases the percentage of only the minority cases. For example, suppose you have an imbalanced dataset where just 1% of the cases have the target value A (the minority class), and 99% of the cases have the value B. To increase the percentage of minority cases to twice the previous percentage, you would enter 200 for **SMOTE percentage** in the module's properties.  
  
## Examples  

We recommend that you try using **SMOTE** with a small dataset to see how it works.  
  
 The following example uses the Blood Donation dataset available in Azure Machine Learning Studio.  
  
 If you click **Visualize** on the dataset’s output, you can see that, of the 748 rows or cases in the dataset, there are 570 cases (76%) of Class 0, and 178 cases (24%) of class 1. Although this isn’t terribly imbalanced, Class 1 represents the people who donated blood, and thus these rows contain the *feature space* that you want to model. 
 
 To increase the number of cases, you can set the value of **SMOTE percentage**, using multiples of 100, as follows:  
  
||Class 0|Class 1|total|  
|-|-------------|-------------|-----------|  
|Original dataset<br /><br /> (equivalent to **SMOTE percentage** = **0**)|570<br /><br /> 76%|178<br /><br /> 24%|748|  
|**SMOTE percentage** = **100**|570<br /><br /> 62%|356<br /><br /> 38%|926|  
|**SMOTE percentage** = **200**|570<br /><br /> 52%|534<br /><br /> 48%|1104|  
|**SMOTE percentage** = **300**|570<br /><br /> 44%|712<br /><br /> 56%|1282|  
  
> [!WARNING]
>  Increasing the number of cases using SMOTE is not guaranteed to produce more accurate models. You should try experimenting with different percentages, different feature sets, and different numbers of nearest neighbors to see how adding cases influences your model.  
  
## How to Configure SMOTE  
  
1.  Determine which columns in the dataset to use as input.  
  
     Creation of new cases using **SMOTE** is based on **all** the columns that you provide as inputs. You cannot select specific columns, or exclude columns. Therefore, if you want to use a limited feature space for building the new cases, you should use [Select Columns in Dataset](select-columns-in-dataset.md) to select those columns before using **SMOTE**.  
  
2.  Ensure that the column containing the label, or target class, is marked as such.  
  
     If there is no label column, use the [Edit Metadata](edit-metadata.md) module to select the column that contains the class labels, and select **Label** from the **Fields** dropdown list.  
  
3.  SMOTE automatically identifies the minority class in the label column, and then gets all examples for the minority class.  
  
4.  In the **SMOTE percentage** option, type a whole number that indicates the target percentage of minority cases in the output dataset. For example:  
  
    -   You type **0** (%). The SMOTE module returns exactly the same dataset that you provided as input, adding no new minority cases.  
  
         In this dataset, the class proportion has  not changed.  
  
    -   You type **100** (%). The SMOTE module generates new minority cases, adding the same number of minority cases that were in the original dataset.  
  
         Because SMOTE does not increase the number of majority cases, the proportion of cases of each class has  now changed.  
  
    -   You type **200** (%). The module doubles the percentage of minority cases compared to the original dataset.  
  
         This does not result in having twice as many minority cases as before.  Rather, the size of the dataset is increased in such a way that the number of majority cases stays the same, and the number of minority cases is increased till it matches the desired percentage value.  
  
5.  Use the **Number of nearest neighbors** option to determine the size of the feature space that the SMOTE algorithm uses when in building new cases. A *nearest neighbor* is a row of data (a case) that is very similar to some target case. The distance between any two cases is measured by combining the weighted vectors of all features.  
  
     + By increasing the number of nearest neighbors, you get features from more cases.
     + By keeping the number of nearest neighbors low, you use features that are more like those in the original sample.  
  
6.  Run the experiment.  
  
     The output of the module is a dataset containing the original rows plus some number of added rows with minority cases.  
  
## Technical Notes  

+ SMOTE never changes the number of majority cases.  
+ Be sure to use only multiples of 100 for the SMOTE percentage.
  
##  <a name="ExpectedInputs"></a> Expected Input  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Samples|[Data Table](data-table.md)|A dataset of samples|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|SMOTE percentage|>=0|Integer|100|Amount of oversampling in multiples of 100.|  
|Number of nearest neighbors|>=1|Integer|1|The number of nearest neighbors from which to draw features for new cases|  
|Random seed|Any|Integer|0|Seed for the random number generator|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Table|[Data Table](data-table.md)|A [Data Table](data-table.md) containing the original samples plus an additional number of synthetic minority class samples. The number of new samples is (smotePercent/100)*T, where T is the number of minority class samples.|  
  
## See Also  
 [Sample and Split](data-transformation-sample-and-split.md)   
 [A-Z Module List](a-z-module-list.md)