---
title: "SUBSTRING (Azure Stream Analytics)"
description: "Returns part of a character or a text."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# SUBSTRING (Azure Stream Analytics)

Returns part of a character or a text.

## Syntax

```SQL
SUBSTRING ( expression, start, length )
```

> [!NOTE]
> The index/position for the SUBSTRING function is 1 based.

## Arguments

**expression**

Is a character expression or a column of type nvarchar(max).

**start**

Is a bigint expression that specifies where the returned characters start. If start is less than 1, the returned expression will begin at the first character that is specified in expression. In this case, the number of characters that are returned is the largest value of either the sum of start + length- 1 or 0. If start is greater than the number of characters in the value expression, a zero-length expression is returned.

**length**

Is a positive bigint expression that specifies how many characters of the expression will be returned. If length is negative, an error is generated and the statement is terminated. If the sum of start and length is greater than the number of characters in expression, the whole value expression beginning at start is returned.

## Return Types

nvarchar(max)

## Examples

```SQL
SELECT
    'abcdefg' AS x,
    SUBSTRING('abcdefg',2,4) AS substringX
FROM Input
```

|x|substringX|
|-|-|
|abcdefg|bcde|

## See Also

- [LEFT (Azure Stream Analytics)](left-azure-stream-analytics.md)
- [RIGHT (Azure Stream Analytics)](right-azure-stream-analytics.md)
