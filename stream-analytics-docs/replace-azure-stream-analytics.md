---
title: "REPLACE (Azure Stream Analytics)"
description: Replaces all occurrences of a specified string value with another string value.
ms.service: stream-analytics
ms.topic: reference
ms.date: 11/11/2022
---
# REPLACE (Azure Stream Analytics)

Replaces all occurrences of a specified string value with another string value.

## Syntax

```SQL
REPLACE ( stringExpression, stringPattern, stringReplacement )
```

## Arguments

**stringExpression**

The string expression to be searched.

**stringPattern**

The substring to be found. If *stringPattern* is an empty string, then *stringExpression* is returned.

**stringReplacement**

The replacement string.

## Return Types

Returns NULL if any of the arguments are NULL. Otherwise, returns nvarchar(max).

## Examples

```SQL
SELECT REPLACE(value, pattern, replacement) AS result FROM input
```

|Expression|Result|
|----------|------|
|REPLACE('abcde', 'cd', 'xx')|'abxxe'|
|REPLACE('cdabcd', 'cd', 'x')|'xabx'|
|REPLACE('cd', 'cd', 'xxx')|'xxx'|
|REPLACE('abcde', 'gh', 'xx')|'abcde'|
|REPLACE('abcde', 'cde', '')|'ab'|
|REPLACE('abcde', '', 'xxx')|'abcde'|
|REPLACE('', 'cde', 'xxx')|''|
|REPLACE(NULL, 'cde', 'xxx')|null|
|REPLACE('abcde', NULL, 'xxx')|null|
|REPLACE('abcde', 'cde', NULL)|null|

## See Also

- [TRANSLATE (Azure Stream Analytics)](translate-azure-stream-analytics.md)