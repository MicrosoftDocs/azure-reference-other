---
title: "RTRIM (Azure Stream Analytics)"
description: "Removes the space character from the end of a string."
applies_to:
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 10/22/2021
---

# RTRIM (Azure Stream Analytics)

Removes the space character `char(32)` from the end of a string - from the right : RIGHT TRIM.

## Syntax

```SQL
RTRIM ( string_expression )
```

## Arguments

**string_expression**

Is the string expression to be evaluated. string_expression can be a constant or column of type nvarchar(max).

## Return Types

nvarchar(max)

## Examples

```SQL

SELECT
  RTRIM( 'Right test    ' ) AS trimmedTest
FROM Input

```

Returns:

|trimmedTest|
|-|
|Right test|

## See Also

- [TRIM](trim-azure-stream-analytics.md)
- [LTRIM](ltrim-azure-stream-analytics.md)
- [REPLACE](replace-azure-stream-analytics.md)