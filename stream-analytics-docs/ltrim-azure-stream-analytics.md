---
title: "LTRIM (Azure Stream Analytics)"
description: "Removes the space character from the start a string."
applies_to:
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 10/22/2021
---

# LTRIM (Azure Stream Analytics)

Removes the space character `char(32)` from the start of a string - from the left : LEFT TRIM.

## Syntax

```SQL
LTRIM ( string_expression )
```

## Arguments

**string_expression**

Is the string expression to be evaluated. string_expression can be a constant or column of type nvarchar(max).

## Return Types

nvarchar(max)

## Examples

```SQL

SELECT
  LTRIM( '      Left test' ) AS trimmedTest
FROM Input

```

Returns:

|trimmedTest|
|-|
|Left test|

## See Also

- [TRIM](trim-azure-stream-analytics.md)
- [RTRIM](rtrim-azure-stream-analytics.md)
- [REPLACE](replace-azure-stream-analytics.md)