---
title: "UNICODE (Azure Stream Analytics)"
description: "Returns the integer value, as defined by the Unicode standard, for the first character of the input expression."
applies_to:
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 06/03/2021
---

# UNICODE (Azure Stream Analytics)

Returns the integer value, as defined by the Unicode standard, for the first character of the input expression.

## Syntax

```SQL
UNICODE ( character_expression )
```

## Arguments

**character_expression**

Is a nvarchar expression to be evaluated. If more than one character is provided, only the first one is considered.

## Return Types

bigint

## Examples

```SQL

SELECT
  UNICODE('茶') AS UnicodeTea
FROM Input

```

Returns:

|UnicodeTea|
|-|
|33590|
