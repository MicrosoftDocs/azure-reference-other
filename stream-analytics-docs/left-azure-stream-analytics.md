---
title: "LEFT (Azure Stream Analytics)"
description: "Returns the left part of a character or a text."
applies_to:
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# LEFT (Azure Stream Analytics)

Returns the left part (from the start) of a character string with the specified number of characters.

## Syntax

```SQL
LEFT ( expression , length )
```

## Arguments

**expression**

Is a character expression or a column of type nvarchar(max).

**length**

Is a positive bigint expression that specifies how many characters of the expression will be returned. If length is negative, an error is generated and the statement is terminated. If the sum of start and length is greater than the number of characters in expression, the whole value expression beginning at start is returned.

## Return Types

nvarchar(max)

## Examples

```SQL
SELECT
    'abcdefg' AS x,
    LEFT('abcdefg',2) AS leftX
FROM Input
```

|x|leftX|
|-|-|
|abcdefg|ab|

## See Also

- [RIGHT (Azure Stream Analytics)](right-azure-stream-analytics.md)
- [SUBSTRING (Azure Stream Analytics)](substring-azure-stream-analytics.md)