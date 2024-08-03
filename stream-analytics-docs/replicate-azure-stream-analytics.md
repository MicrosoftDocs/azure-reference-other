---
title: "REPLICATE (Azure Stream Analytics)"
description: "Repeats a string value a specified number of times."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# REPLICATE (Azure Stream Analytics)

Repeats a string value a specified number of times.

## Syntax

```SQL
REPLICATE ( expression , integer_expression )
```

## Arguments

**expression**

Is a character expression or a column of type nvarchar(max).

**integer_expression**

Is an expression of type bigint. If integer_expression is negative, NULL is returned.

## Return Types

nvarchar(max)

## Examples

```SQL
SELECT
    ProductLine,
    CONCAT(REPLICATE('0', 4 - LEN(ProductLine), [ProductLine]) AS LineCode
FROM Input
WHERE LEN(ProductLine) = 1
```

`CONCAT` ignore null values, which will prevent loss of values if `LEN(ProductLine)` is over 4 (negative integer_expression make `REPLICATE` returns null).

|ProductLine|LineCode|
|-|-|
|T|0000T|
|1222X|1222X|
|99A|0099A|
|123456789|123456789|

## See Also

- [LEN (Azure Stream Analytics)](len-azure-stream-analytics.md)
- [CONCAT (Azure Stream Analytics)](concat-azure-stream-analytics.md)
