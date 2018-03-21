---
title: "Error 0103 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0103-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0103  
 Thrown when a ZIP file does not contain any .xml files  
  
 This error in Azure Machine Learning occurs when the custom module zip package does not contain any module definition (.xml) files. These files need to reside in the root of the zip package (e.g. not within a subfolder.)  
  
## Resolution  
 Verify that one or more xml module definition files are in the root folder of the zip package by extracting it to a temporary folder on your disk drive. Any xml files should be directly in the folder you extracted the zip package to. Make sure when you create the zip package that you do not simply select a folder that contains xml files to zip as this will create a sub folder within the zip package with the same name as the folder you selected to zip.  
  
|Exception Messages|  
|------------------------|  
|Given ZIP file does not contain any module definition files (.xml files)|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)