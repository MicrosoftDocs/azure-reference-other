---
title: "TRANSLATE"
description: "Returns a string after some specified characters are replaced by others."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# TRANSLATE
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

Returns the string provided as a first argument after some characters specified in the second argument are translated into a destination set of characters specified in the third argument.

The behavior of the `TRANSLATE` function is similar to using multiple `REPLACE` functions.

## Syntax

```SQL
TRANSLATE ( expression, replaced_characters, translations)
```

> [!NOTE]
> The index/position for the TRANSLATE function is 1 based.

## Arguments

**expression**

Is a character expression or a column of type nvarchar(max).

**replaced_characters**

Is a character expression or a column of type nvarchar(max). It contains the list of characters to be replaced.

**translations**

Is a character expression or a column of type nvarchar(max) of the same length as replaced_characters. It contains the replacement characters.

## Return Types

nvarchar(max)

## Remarks

`TRANSLATE` will return an error if characters and translations expressions have different lengths. `TRANSLATE` will return NULL if any of the arguments are NULL.

The behavior of the `TRANSLATE` function is similar to using multiple REPLACE functions. `TRANSLATE` does not, however, replace any individual character in inputString more than once. A single value in the characters parameter, can replace multiple characters in expression. This is dissimilar to the behavior of multiple `REPLACE` functions, as each function call would replace all relevant characters, even if they had been replaced by a previous nested `REPLACE` function call.

## Examples

**Replace square and curly braces with regular braces**

```SQL
SELECT
    x,
    TRANSLATE(x, '[]{}', '()()') AS translatedX
FROM Input
```

|x|translatedX|
|-|-|
|2*[3+4]/{7-2}|2*(3+4)/(7-2)|

**Convert GeoJSON points into WKT**

```SQL
SELECT
    xPoint,
    TRANSLATE(xPoint, '[,]', '( )') xPoint2Coordinates,
    xCoordinates,
    TRANSLATE(xPoint, '[,]', '( )') xCoordinates2Point
FROM Input
```

|xPoint|xPoint2Coordinates|xCoordinates|xCoordinates2Point|
|-|-|-|-|
|(137.4 72.3)|[137.4,72.3]|[137.4,72.3]|(137.4 72.3)|

## See Also

- [REPLACE](replace-azure-stream-analytics.md)
