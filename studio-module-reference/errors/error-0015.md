---
title: "Error 0015 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0015-d185d1509344
caps.latest.revision: 5
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0015  
 Exception occurs if database connection has failed.  
  
 You will receive this error if you enter an incorrect SQL account name, password, database server, or database name, or if a connection with the database cannot be established due to problems with the database or server.  
  
## Resolution  
 Verify that the account name, password, database server, and database have been entered correctly, and that the specified account has the correct level of permissions. Verify that the database is currently accessible.  
  
|Exception Messages|  
|------------------------|  
|Error making database connection.|  
|Error making database connection: {0}.|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)