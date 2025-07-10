---
title: "CONCAT"
description: "Returns a string that is the result of concatenating two or more string values. "
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# CONCAT
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

Returns a string that is the result of concatenating two or more string values.

## Syntax

```SQL
CONCAT ( string_value1, string_value2 [, string_valueN ] )
```

## Arguments

**string_value**

 A string value to concatenate to the other values.

## Return Types

nvarchar(max)

## Remarks

CONCAT implicitly converts null values to empty strings. If CONCAT receives arguments with all NULL values, it will return an empty string.

## Examples

```SQL
SELECT
    Make,
    Model,
    CONCAT ( 'Make: ', Make, ', Model: ', Model) AS MakeModel
FROM Input
```

|Make|Model|MakeModel|
|-|-|-|
|Contoso|QRTZX22|Make: Contoso, Model: QRTZX22|

## See Also

- [CONCAT_WS](concat-ws-azure-stream-analytics.md)
- [Substring](substring-azure-stream-analytics.md)