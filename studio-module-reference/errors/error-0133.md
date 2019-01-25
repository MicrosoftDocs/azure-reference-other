---
title: "Error 0133 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.subservice: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0133-d185d1509344
caps.latest.revision: 5
author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0133  
 The specified file was not found in the zip file  
  
 This error is produced when the filename entered in the **Dataset to Unpack** field of the **Property** pane does not match the name of any file found in the .zip file. The most common causes of this error are a typing error or searching the wrong archive file for the file to expand.  
  
## Resolution  
 Revisit the module. If the name of the file you intended to decompress appears in the list of files found, copy the file name and paste it into the **Dataset to Unpack** property box. If you do not see the desired file name in the list, verify that you have the correct .zip file and the correct name for the desired file.  
  
|Exception Messages|  
|------------------------|  
|The specified file was not found int the zip file.|  
|The specified file was not found. Found the following file(s): {0}|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
