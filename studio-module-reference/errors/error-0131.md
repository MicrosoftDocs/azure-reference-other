---
title: "Error 0131 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0131-d185d1509344
caps.latest.revision: 5
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0131
**Error 0131**  
  
 Exception occurs if one or more datasets in a zip file fails to be unzipped and registered correctly  
  
 This error is produced when one or more datasets in a zip file fails to be unzipped and read correctly. You will receive this error if the unpacking fails because the zip file itself or one of the files in it is corrupt, or there is a system error while trying to unpack and expand a file.  
  
## Resolution  
 Use the details provided in the error message to determine how to proceed.  
  
|Exception Messages|  
|------------------------|  
|Upload zipped datasets failed|  
|Zipped dataset {0} failed with the following message: {1}|  
|Zipped dataset {0} failed with a {1} exception with message: {2}|  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)