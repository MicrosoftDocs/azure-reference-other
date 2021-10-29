---
title: "TRIM (Azure Stream Analytics)"
description: "Removes the space character from the start and end of a string."
applies_to:
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 10/22/2021
---

# TRIM (Azure Stream Analytics)

Removes the space character `char(32)` from the start and end of a string.

## Syntax

```SQL
TRIM ( string_expression )
```

## Arguments

**string_expression**

Is the string expression to be evaluated. string_expression can be a constant or column of type nvarchar(max).

## Return Types

nvarchar(max)

## Examples

```SQL

SELECT
  TRIM( '      a test    ' ) AS trimmedTest
FROM Input

```

Returns:

|trimmedTest|
|-|
|a test|

## See Also

- [LTRIM](ltrim-azure-stream-analytics.md)
- [RTRIM](rtrim-azure-stream-analytics.md)
- [REPLACE](replace-azure-stream-analytics.md)