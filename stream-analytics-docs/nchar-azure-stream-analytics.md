---
title: "NCHAR"
description: "Returns the Unicode character with the specified integer code, as defined by the Unicode standard."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# NCHAR
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

Returns the Unicode character with the specified integer code, as defined by the Unicode standard.

## Syntax

```SQL
NCHAR ( integer_expression )
```

## Arguments

**integer_expression**

Positive integer from 0 through 1114111 (0 through 0x10FFFF). If a value outside this range is specified, NULL is returned.

## Return Types

nvarchar(max)

## Examples

```SQL

SELECT
  NCHAR(33590) AS UnicodeTea_Decimal,
  NCHAR(UNICODE('茶')) AS UnicodeTea_Char
FROM Input

```

Returns:

|UnicodeTea_Decimal|UnicodeTea_Char|
|-|-|
|茶|茶|