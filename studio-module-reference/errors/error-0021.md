---
title: "Error 0021 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 09/21/2017
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0021  
 Exception occurs if number of rows in some of the datasets passed to the module is too small.  
  
 This error in seen in Azure Machine Learning when there are not enough rows in the dataset to perform the specified operation. For example, you might see this error if the input dataset is empty, or if you are trying to perform an operation that requires some minimum number of row to be valid. Such operations can include (but are not limited to) grouping or classification based on statistical methods, certain types of binning, and learning with counts.  
  
**Resolution:**
 
 + Open the module that returned the error, and check the input dataset and module properties. 
 + Verify that the input dataset is not empty and that there are enough rows of data to meet the requirements described in module help.  
 + If your data is loaded from an external source, make sure that the data source is available and that there is no error or change in the data definition that would cause the import process to get fewer rows.
 + If you are performing an operation on the data upstream of the module that might affect the type of data or the number of values, such as cleaning, splitting, or join operations, check the outputs of those operations to determine the number of rows returned.  


 > [!TIP]
 > Resolution not applicable to your case? You are welcome to send feedback on this article and provide information about the scenario, including the module and the number of rows in the column. We will use this information to provide more detailed troubleshooting steps in future.
  
|Exception Messages|  
|------------------------|  
|Number of rows in input dataset is less than allowed minimum.|  
|Number of rows in input dataset is less than allowed minimum of {0} row(s).|  
|Number of rows in input dataset "{0}" is less than allowed minimum of {1} row(s).|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
