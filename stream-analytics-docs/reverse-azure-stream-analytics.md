---
title: "REVERSE"
description: "Returns the reverse order of a string value."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# REVERSE

Returns the reverse order of a string value.

## Syntax

```SQL
REVERSE ( expression )
```

## Arguments

**expression**

Is a character expression or a column of type nvarchar(max).

## Return Types

nvarchar(max)

## Examples

```SQL
SELECT
    'abcdefg' AS x,
    REVERSE('abcdefg') AS reversedX
FROM Input
```

|x|reversedX|
|-|-|
|'abcdefg'|'gfedcba'|

