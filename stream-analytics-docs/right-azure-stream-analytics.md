---
title: "RIGHT"
description: "Returns the right part of a character or a text."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# RIGHT

Returns the right part (from the end) of a character string with the specified number of characters.

## Syntax

```SQL
RIGHT ( expression , length )
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
    RIGHT('abcdefg',2) AS leftX
FROM Input
```

|x|leftX|
|-|-|
|abcdefg|fg|

## See Also

- [LEFT](left-azure-stream-analytics.md)
- [SUBSTRING](substring-azure-stream-analytics.md)