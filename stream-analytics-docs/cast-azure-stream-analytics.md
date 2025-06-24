---
title: CAST
description: Converts an expression of one data type to another within the supported types in Stream Analytics Query Language.
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# CAST

Converts an expression of one data type to another within the supported [data types](data-types-azure-stream-analytics.md) in Stream Analytics Query Language.

If the conversion cannot be performed, the function fails and causes the job to stop. For example, the clause `CAST ('this is a string' AS bigint)` results in a job failure since the input string cannot be converted into the `bigint` data type. To avoid type cast failures, use [TRY_CAST](try-cast-azure-stream-analytics.md) function instead.

> [!NOTE]
> To compare the different options available for type conversion, see [casting data](data-types-azure-stream-analytics.md#casting-data)

## Syntax

```SQL
CAST ( expression AS data_type)

```

## Arguments
 **expression**

 Is any valid expression.

 **data_type**

 Is the target [data type](data-types-azure-stream-analytics.md) supported by Stream Analytics Query Language.

## Return Types
 Returns expression translated to data_type.

## Remark

See the [data types](data-types-azure-stream-analytics.md) article for more information about special cases.
## Examples

```SQL

SELECT TollId, EntryTime, LicensePlate, State, Make
FROM Input TIMESTAMP BY EntryTime
WHERE CAST( TollId AS bigint) > 2

```

## See also
For more information on Stream Analytics data types, see:
- [Data types](data-types-azure-stream-analytics.md)
- [TRY_CAST](try-cast-azure-stream-analytics.md)
- [Parsing JSON and AVRO data](/azure/stream-analytics/stream-analytics-parsing-json)
