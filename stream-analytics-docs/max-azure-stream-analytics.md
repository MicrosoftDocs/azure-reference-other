---
title: "MAX"
description: "Returns the maximum value in the expression.  "
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# MAX

Returns the maximum value in the expression.

## Syntax

```SQL
-- Aggregate Function Syntax
MAX ( expression )

-- Analytic Function Syntax
MAX ( expression ) OVER ([<PARTITION BY clause>] <LIMIT DURATION clause> [<WHEN clause>])
```

## Arguments

**expression**

Is a constant, column name, or function, and any combination of arithmetic operators. Aggregate functions and subqueries are not permitted.

MAX can be used with Bit, Bigint, Datetime and Float columns.

MAX can also be used with NVARCHAR(MAX) with the following behavior:

- If the column was not explicitly cast to NVARCHAR(MAX), then MAX will try to implicitly cast it to FLOAT. Type mismatches will result in errors.
- If the column was explicitly cast to NVARCHAR(MAX) by using [CAST](cast-azure-stream-analytics.md) or [TRY_CAST](try-cast-azure-stream-analytics.md), then the maximal string value will be returned.

**OVER ([\<PARTITION BY clause> \<LIMIT DURATION clause> [\<WHEN clause>]]**

Determines the group of rows over which MAX is applied. The PARTITION BY clause specifies that the rows with the same partition key will be grouped together. The LIMIT DURATION clause specifies how much history is included in the group. The WHEN clause specifies a boolean condition for the rows to be included in the group. See [OVER clause](over-azure-stream-analytics.md) for more details on the usage.

## Return Types

Returns a value same as expression.

## Examples

With the aggregate syntax, we will reduce the number of rows. Here we select the maximum fare at each Toll every hour:

```SQL
SELECT
  TollId,
  System.Timestamp() AS WindowEnd,
  MAX(Toll) AS MaxFare
FROM Input TIMESTAMP BY EntryTime
GROUP BY
  TollId,
  TumblingWindow(hour,1)
```

With the analytics syntax, we maintain the input cardinality. Here for every vehicle going through the toll, we compare the current fare to the maximum over the last hour:

```SQL
SELECT
  TollId,
  System.Timestamp() AS PassageTime,
  LicensePlate,
  Toll AS Fare,
  MAX (Toll) OVER (PARTITION BY VehicleClass LIMIT DURATION(hour,1)) AS MaximumFareOverLastHour
FROM Input TIMESTAMP BY EntryTime
```

## See Also

- [MIN](min-azure-stream-analytics.md)
- [GROUP BY clause](group-by-azure-stream-analytics.md)
- [OVER clause](over-azure-stream-analytics.md)
