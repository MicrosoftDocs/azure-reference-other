---
title: "SUBSTRING (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: bd7921ac-61f4-4d56-a634-47233c14e31a
caps.latest.revision: 7
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# SUBSTRING (Azure Stream Analytics)
  Returns part of a character or a text.  
  
 **Syntax**  
  
```  
SUBSTRING ( expression ,start ,length )  
```  
  
> [!NOTE]  
>  The index/position for the SUBSTRING function is 1 based.  
  
## Arguments  
 **expression**  
  
 Is a character expression or a column of type nvarchar(max).  
  
 **start**  
  
 Is a bigint expression that specifies where the returned characters start. If start is less than 1, the returned expression will begin at the first character that is specified in expression. In this case, the number of characters that are returned is the largest value of either the sum of start + length- 1 or 0. If start is greater than the number of characters in the value expression, a zero-length expression is returned.  
  
 **length**  
  
 Is a positive bigint expression that specifies how many characters of the expression will be returned. If length is negative, an error is generated and the statement is terminated. If the sum of start and length is greater than the number of characters in expression, the whole value expression beginning at start is returned  
  
## Return Types  
 nvarchar(max)  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime,LicensePlate, SUBSTRING ( LicensePlate,1,3 ),  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  