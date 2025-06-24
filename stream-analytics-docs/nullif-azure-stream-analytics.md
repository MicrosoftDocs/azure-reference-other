---
title: "NULLIF"
description: "Returns a null value if the two specified expressions are equal."

ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024

---

# NULLIF

Returns a null value if the two specified expressions are equal. For example, `SELECT NULLIF(4,4) AS Same, NULLIF(5,7) AS Different ...` returns `NULL` for the first column (4 and 4) because the two input values are the same. The second column returns the first value (5) because the two input values are different.

NULLIF is equivalent to a searched CASE expression in which the two expressions are equal and the resulting expression is NULL.

## Syntax

```SQL
NULLIF ( expression , expression )
```

## Arguments

**expression**

An expression of any type.

## Return Types

Returns the same type as the first expression.

`NULLIF` returns the first expression if the two expressions are not equal. If the expressions are equal, `NULLIF` returns a null value of the type of the first expression.

## Examples

Only project a value when it has changed:

```SQL
SELECT
     sensorId,
     reading,
     NULLIF(
        LAG(reading) OVER (PARTITION BY sensorId LIMIT DURATION(hour, 1)),
        reading
      ) AS previous_reading_if_changed
FROM input
```

## See Also

- [COALESCE](coalesce-azure-stream-analytics.md)
- [NULLIF](nullif-azure-stream-analytics.md)
- [CASE](case-azure-stream-analytics.md)
