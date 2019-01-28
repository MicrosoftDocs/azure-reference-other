---
title: "Error 0132 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0132  
 No file name was specified for unpacking; multiple files were found in zip file.  
  
 This error is produced when no file name was specified for unpacking; multiple files were found in zip file. You will receive this error if the .zip file contains more than one compressed file, but you did not specify a file for extraction in the **Dataset to Unpack** text box, in the **Property** pane of the module. Currently, only one file can be extracted each time the module is run.  
  
## Resolution  
 The error message provides a list of the files found in the .zip file. Copy the name of the desired file and paste it into the **Dataset to Unpack** text box.  
  
|Exception Messages|  
|------------------------|  
|Zip file contains multiple files; you must specify the file to expand.|  
|The file contains more than one file. Please specify the file to expand. The following files were found: {0}|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
