---
title: "SPACE (Azure Stream Analytics)"
description: "Returns a string of repeated spaces."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# SPACE (Azure Stream Analytics)

Returns a string of repeated spaces.

## Syntax

```SQL
SPACE ( integer_expression )
```

## Arguments

**integer_expression**

Is a positive bigint expression that indicates the number of spaces. If integer_expression is negative, a null string is returned.

## Return Types

nvarchar(max)

## Examples

```SQL
SELECT
    RTRIM('LastName  ') + ',' + SPACE(1) +  LTRIM('    FirstName') as FullName
FROM Input
```

|FullName|
|-|
|LastName, FirstName|

## See Also

- [RTRIM (Azure Stream Analytics)](rtrim-azure-stream-analytics.md)
- [LTRIM (Azure Stream Analytics)](ltrim-azure-stream-analytics.md)
