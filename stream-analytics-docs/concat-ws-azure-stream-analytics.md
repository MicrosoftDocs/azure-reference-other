---
title: "CONCAT_WS (Azure Stream Analytics)"
description: "Returns a string that is the result of concatenating two or more string values with a specified delimiter."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# CONCAT_WS (Azure Stream Analytics)

This function returns a string resulting from the concatenation, or joining, of two or more string values in an end-to-end manner. It separates those concatenated string values with the delimiter specified in the first function argument. `CONCAT_WS` indicates concatenate with separator.

## Syntax

```SQL
CONCAT_WS ( separator, string_value1, string_value2 [, string_valueN ] )
```

## Arguments

**separator**

A string value to separate the other values.

**string_value**

A string value to concatenate to the other values.

## Return Types

nvarchar(max)

## Remarks

CONCAT_WS ignores null values during concatenation, and does not add the separator between null values. If CONCAT_WS receives arguments with all NULL values, it will return an empty string.

## Examples

```SQL
SELECT
    address1,
    address2,
    city,
    stateCode,
    zipCode,
    country,
    CONCAT_WS(', ',address1, address2, city, stateCode, zipCode, country) AS fullAddress
FROM Input

```

|address1|address2|city|zipCode|stateCode|country|fullAddress|
|-|-|-|-|-|-|-|
|1 Microsoft Way|null|Redmond|WA|98052|null|1 Microsoft Way, Redmond, WA, 98052|

## See Also

- [CONCAT (Azure Stream Analytics)](concat-azure-stream-analytics.md)
- [Substring (Azure Stream Analytics)](substring-azure-stream-analytics.md)