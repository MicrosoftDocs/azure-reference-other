---
title: "CHARINDEX (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-04-22"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: ef239dd8-5b03-44c2-8d3f-3937262ab714
caps.latest.revision: 8
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# CHARINDEX (Azure Stream Analytics)
  Searches an expression for another expression and returns its starting position if found.  
  
 **Syntax**  
  
```  
CHARINDEX ( expressionToFind ,expressionToSearch [ , start_location ] )  
```  
  
> [!NOTE]  
>  The index/position for the CHARINDEX function is 1 based.  
  
## Arguments  
 **expressionToFind**  
  
 Is a character expression that contains the sequence to be found.  
  
 **expressionToSearch**  
  
 Is a character expression to be searched.  
  
 **start_location**  
  
 Is a bigint expression at which the search starts. If start_location is not specified, is a negative number, or is 0, the search starts at the beginning of expressionToSearch.  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime, CHARINDEX ( 'us', Model), Model  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
## Remarks  
 If expressionToFind is not found within expressionToSearch, CHARINDEX returns 0.  
  
  