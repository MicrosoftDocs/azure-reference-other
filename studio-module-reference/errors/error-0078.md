---
title: "Error 0078 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0078-d185d1509344
caps.latest.revision: 7
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0078
**Error 0078**  
  
 Exception occurs when the HTTP option for [Import Data](import-data.md) receives a 3xx status code indicating redirection.  
  
 This error in Azure Machine Learning occurs when the HTTP option for [Import Data](import-data.md) receives a 3xx (301, 302, 304, etc.) status code indicating redirection. You will receive this error if you attempt to connect to an HTTP source that redirects the browser to another page. For security reasons, redirecting websites are not allowed as data sources for Azure Machine Learning.  
  
## Resolution  
 If the website is a trusted website, enter the redirected URL directly.  
  
|Exception Messages|  
|------------------------|  
|Http redirection not allowed|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](machine-learning-module-error-codes.md)