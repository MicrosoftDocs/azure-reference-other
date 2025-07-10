---
title: "STUFF"
description: "Inserts a string into another string"
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# STUFF
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

Inserts a string into another string. It deletes a specified length of characters in the first string at the start position and then inserts the second string into the first string at the start position.

## Syntax

```SQL
STUFF ( expression, start, length, inserted_expression )
```

> [!NOTE]
> The index/position for the STUFF function is 1 based.

## Arguments

**expression**

Is a character expression or a column of type nvarchar(max).

**start**

Is a bigint expression that specifies where the deletion and insertion starts. If start is less than 1, the returned expression will begin at the first character that is specified in expression. If start is greater than the number of characters in the value expression, a zero-length expression is returned.

**length**

Is a positive bigint expression that specifies how many characters of the expression will be deleted. If length is negative, an error is generated and the statement is terminated. If start + length is greater than the number of characters in expression, all characters are deleted. If length is zero, insertion occurs at start location and no characters are deleted.

## Return Types

nvarchar(max)

## Examples

```SQL
SELECT
    STUFF('abcdef', 2, 3, 'ijklmn') AS Stuffed
FROM Input
```

|Stuffed|
|-|
|aijklmnef|

Which corresponds to:

- Removed 3 characters from position 2 : `bcd`
- Then inserted `ijklmn` at position 2 : `a`+`ijklmn`+`ef`

