---
title: "Error 0104 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0104-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0104
**Error 0104**  
  
 Thrown when a module definition file references a script that cannot be located  
  
 This error in Azure Machine Learning is thrown when a custom module xml definition file references a script file in the **Language** element that does not exist in the zip package. The script file path is defined in the **sourceFile** property of the **Language** element. The path to the source file is relative to the root of the zip package (same location as the module xml definition files). If the script file is in a sub folder, the relative path to the script file must be specified. For instance, if all scripts were stored in a **myScripts** folder within the zip package, the **Language** element would have to add this path to the **sourceFile** property as below. For example:  
  
 `<Language name="R" sourceFile="myScripts/CustomAddRows.R" entryPoint="CustomAddRows" />`  
  
## Resolution  
 Make sure that the value of the **sourceFile** property in the **Language** element of the custom module xml definition is correct and that the source file exists in the correct relative path in the zip package.  
  
|Exception Messages|  
|------------------------|  
|Referenced R script file does not exist.|  
|Referenced R script file '{0}' can not be found. Ensure that the relative path to the file is correct from the definitions location.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)