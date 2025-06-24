---
title: "& (Bitwise AND)"
description: "Performs a bitwise logical AND operation between two integer values."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# & (Bitwise AND)

Performs a bitwise logical AND operation between two integer values, evaluating each corresponding bit from both expressions.

## Syntax

```SQL
expression & expression
```

## Arguments

**expression**

Is any valid expression of the data types bit or bigint. Expression is treated as a binary number for the bitwise operation.

## Return Types

**bit** if both input values are **bit**.

**bigint** if one or both input values are **bigint**.

## Remarks

The & bitwise operator performs a bitwise logical AND between the two expressions, **taking each corresponding bit for both expressions**. The bits in the result are set to 1 if and only if both bits (for the current bit being resolved) in the input expressions have a value of 1; otherwise, the bit in the result is set to 0.

For illustration, the binary representation of 170 is 0000 0000 1010 1010. The binary representation of 75 is 0000 0000 0100 1011. Performing the bitwise AND operation on these two values produces the binary result 0000 0000 0000 1010, which is decimal 10.

```
(170 & 75)
0000 0000 1010 1010
0000 0000 0100 1011
-------------------
0000 0000 0000 1010
```

It is to be noted that casting a FLOAT value to BIGINT, and applying a bitwise operator on it will most often not return the same result as casting it to BIT and applying the same operator:

- First option : 170 & 75.0 => 170 & 75 = 10
- Second option : 170 & 75.0 => 170 & 1 = 0

See the [Data Types Overview](data-types-azure-stream-analytics.md) for the rules of conversion to bit.

## Examples

With a common input dataset:

```SQL
WITH MyCTE AS (
	SELECT
		CAST(0 AS BIT) AS bit0,
		CAST(1 AS BIT) AS bit1,
		CAST(NULL AS BIT) AS bitN,
		CAST(0 AS BIGINT) AS bigint0,
		CAST(1 AS BIGINT) AS bigint1,
		CAST(NULL AS BIGINT) AS bigintN
	FROM input
)
```

Applying the operator on **bit** expressions:

```SQL
SELECT
	bit0,
	bit1,
	bitN,
	bit0 & bit0 AS AND00,
	bit0 & bit1 AS AND01,
	bit1 & bit0 AS AND10,
	bit1 & bit1 AS AND11,
	bitN & bit0 AS ANDnull
INTO bitAND
FROM MyCTE
```

Returns:

|bit0|bit1|bitN|AND00|AND01|AND10|AND11|ANDnull|
|-|-|-|-|-|-|-|-|
|false|true|NULL|false|false|false|true|NULL|

Applying the operator on **bigint** expressions:

```SQL
SELECT
	bigint0,
	bigint1,
	bigintN,
	bigint0 & bigint0 AS AND00,
	bigint0 & bigint1 AS AND01,
	bigint1 & bigint0 AS AND10,
	bigint1 & bigint1 AS AND11,
	bigintN & bigint1 AS ANDnull,
    170 & 75 AS ANDvalues
INTO bigintAND
FROM MyCTE
```

Returns:

|bigint0|bigint1|bigintN|AND00|AND01|AND10|AND11|ANDnull|ANDvalues|
|-|-|-|-|-|-|-|-|-|
|0|1|NULL|0|0|0|1|NULL|**10**|

Validating the **output types**:

```SQL
SELECT
    GetType(bit0 & bit0) AS ANDtype_bit,
    GetType(bigint0 & bigint0) AS ANDtype_bigint,
    GetType(bit0 & bigint0) AS ANDtype_mixed
INTO typesAND
FROM MyCTE
```

Returns:

|ANDtype_bit|ANDtype_bigint|ANDtype_mixed|
|-|-|-|
|bit|bigint|bigint|

## See Also

- [Bitwise Operators](bitwise-operators-azure-stream-analytics.md)
- [| (Bitwise OR)](bitwise-or-azure-stream-analytics.md)
- [^ (Bitwise Exclusive OR)](bitwise-xor-azure-stream-analytics.md)
- [~ (Bitwise NOT)&#40;Azure Stream Analytics&#41;](bitwise-not-azure-stream-analytics.md)
- [Data Types Overview](data-types-azure-stream-analytics.md)
- [Conversion Functions](conversion-functions-azure-stream-analytics.md)
- [Built-in Functions](built-in-functions-azure-stream-analytics.md)