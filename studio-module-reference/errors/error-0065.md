---
title: "Error 0065 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0065-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0065
**Error 0065**  
  
 Exception occurs if Azure blob name is specified incorrectly.  
  
 This error in Azure Machine Learning occurs if the Azure blob name is specified incorrectly.  You will receive the error if:  
  
-   The blob cannot be found in the specified container.  
  
-   The fully qualified name of the blob specified for output in one of the [Learning with Counts](data-transformation-learning-with-counts.md) modules is greater than 512 characters.  
  
-   Only the container was specified as the source in a [Import Data](import-data.md) request when the format was Excel or CSV with encoding; concatenation of the contents of all blobs within a container is not allowed with these formats.  
  
-   A SAS URI does not contain the name of a valid blob.  
  
## Resolution  
 Revisit the module throwing the exception. Verify that the specified blob does exist in the container in the storage account and that permissions allow you to see the blob. Verify that the input is of the form **containername/filename** in the case of Excel or CSV with encoding formats. Verify that a SAS URI contains the name of a valid blob.  
  
|Exception Messages|  
|------------------------|  
|The Azure storage blob is incorrect.|  
|The Azure storage blob name "{0}" is incorrect|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](machine-learning-module-error-codes.md)