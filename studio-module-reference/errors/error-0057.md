---
title: "Error 0057 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 06/14/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0057-d185d1509344
caps.latest.revision: 7
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0057  
 Exception occurs when attempting to create a file or blob that already exists.  
  
 This exception occurs when you are using the [Export Data](../export-data.md) module or other module to save  results of an experiment in Azure Machine Learning to Azure blob storage, but you attempt to create a file or blob that already exists.   
  
## Resolution  
 
 You will receive this error only if you previously set the property **Azure blob storage write mode** to **Error**. By design, this module raises an error if you attempt to write a dataset to a blob that already exists.
 
 - Open the module properties and change the property **Azure blob storage write mode** to **Overwrite**.
 - Alternatively, you can type the name of a different destination blob or file and be sure to specify a blob that does not already exist.  
  
|Exception Messages|  
|------------------------|  
|File or Blob already exists.|  
|File or Blob "{0}" already exists.|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)