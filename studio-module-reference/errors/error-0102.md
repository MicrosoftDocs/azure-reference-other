---
title: "Error 0102 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 09/16/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0102  
 Thrown when a ZIP file cannot be extracted.  
  
 This error in Azure Machine Learning occurs when you are importing a zipped package with the .zip extension, but the package is either not a zip file, or the file does not use a supported zip format.  
  
**Resolution :**
 Make sure the selected file is a valid .zip file, and that it was compressed by using one of the supported compression algorithms.  
  
 If you get this error when importing datasets in compressed format, verify that all contained files use one of the supported file formats, and are in Unicode format. For more information, see [Unpack Zipped Datasets](../unpack-zipped-datasets.md).  
  
 Try re-adding the desired files to a new compressed zipped folder and try to add the custom module again.  
  
|Exception Messages|  
|------------------------|  
|Given ZIP file is not in the correct format|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
