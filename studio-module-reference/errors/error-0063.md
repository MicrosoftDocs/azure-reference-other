---
title: "Error 0063 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 06/14/2017
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0063  
 This exception is raised when R script evaluation fails with an error.  
  
 This error occurs when you have provided an R script in one of the [R language modules](../r-language-modules.md) in Azure Machine Learning, and the R code contains internal syntax errors. The exception can also occur if you provide the wrong inputs to the R script. 
 
 The error can also occur if the script is too big to execute in the workspace. The maximum script size for the **Execute R Script** module is 1,000 lines or 32KB of work space, whichever is lesser.
  
**Resolution :**

1. In Azure Machine Learning Studio, right-click the module that has the error, and select **View Log**.
2. Examine the standard error log of the module, which contains the stack trace.
    + Lines beginning with [ModuleOutput] indicate output from R.
    + Messages from R marked as **warnings** typically do not cause the experiment to fail.
3. Resolve script issues.  
    + Check for R syntax errors. Check for variables that are defined but never populated.
    + Review the input data and the script to determine if either the data or variables in the script use characters not supported by Azure Machine Learning.
    + Check whether all package dependencies are installed.
    + Check whether your code loads required libraries that are not loaded by default.
    + Check whether the required packages are the correct version.
    + Make sure that any dataset that you want to output is converted to a data frame.  
4.  Resubmit the experiment.


> [!NOTE]
> These topics contains examples of R code that you can use, as well as links to experiments in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com) that use R script.
> + [Execute R Script](../execute-r-script.md)
> + [Create R Model](../create-r-model.md)
  
|Exception Messages|  
|------------------------|  
|Error during evaluation of R script.|  
|The following error occurred during evaluation of R script: ---------- Start of error message from R ---------- {0} ----------- End of error message from R -----------|  
|During evaluation of R script "{1}" the following error occurred: ---------- Start of error message from R ---------- {0} ----------- End of error message from R -----------|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
