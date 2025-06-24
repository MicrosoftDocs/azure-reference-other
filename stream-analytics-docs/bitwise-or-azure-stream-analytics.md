---
title: "| (Bitwise OR)"
description: "Performs a bitwise logical OR operation between two integer values."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# | (Bitwise OR)
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

Performs a bitwise logical OR operation between two integer values, evaluating each corresponding bit from both expressions.

## Syntax

```SQL
expression | expression
```

## Arguments

**expression**

Is any valid expression of the data types bit or bigint. Expression is treated as a binary number for the bitwise operation.

## Return Types

**bit** if both input values are **bit**.

**bigint** if one or both input values are **bigint**.

## Remarks

The | bitwise operator performs a bitwise logical OR between the two expressions, **taking each corresponding bit for both expressions**. The bits in the result are set to 1 if either or both bits (for the current bit being resolved) in the input expressions have a value of 1; otherwise, the bit in the result is set to 0.

For illustration, the binary representation of 170 is 0000 0000 1010 1010. The binary representation of 75 is 0000 0000 0100 1011. Performing the bitwise AND operation on these two values produces the binary result 0000 0000 1110 1011, which is decimal 235.

```
(170 | 75)
0000 0000 1010 1010
0000 0000 0100 1011
-------------------
0000 0000 1110 1011
```

It is to be noted that casting a FLOAT value to BIGINT, and applying a bitwise operator on it will most often not return the same result as casting it to BIT and applying the same operator:

- First option : 170 | 75.0 => 170 | 75 = 235
- Second option : 170 | 75.0 => 170 | 1 = 171

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
	bit0 | bit0 AS OR00,
	bit0 | bit1 AS OR01,
	bit1 | bit0 AS OR10,
	bit1 | bit1 AS OR11,
	bitN | bit0 AS ORnull
INTO bitOR
FROM MyCTE
```

Returns:

|bit0|bit1|bitN|OR00|OR01|OR10|OR11|ORnull|
|-|-|-|-|-|-|-|-|
|false|true|NULL|false|true|true|true|NULL|

Applying the operator on **bigint** expressions:

```SQL
SELECT
	bigint0,
	bigint1,
	bigintN,
	bigint0 | bigint0 AS OR00,
	bigint0 | bigint1 AS OR01,
	bigint1 | bigint0 AS OR10,
	bigint1 | bigint1 AS OR11,
	bigintN | bigint1 AS ORnull,
	170 | 75 AS ORvalues
INTO bigintOR
FROM MyCTE
```

Returns:

|bigint0|bigint1|bigintN|OR00|OR01|OR10|OR11|ORnull|ORvalues|
|-|-|-|-|-|-|-|-|-|
|0|1|NULL|0|1|1|1|NULL|**235**|

Validating the **output types**:

```SQL
SELECT
	GetType(bit0 | bit0) AS ORtype_bit,
	GetType(bigint0 | bigint0) AS ORtype_bigint,
	GetType(bit0 | bigint0) AS ORtype_mixed
INTO typesOR
FROM MyCTE
```

Returns:

|ORtype_bit|ORtype_bigint|ORtype_mixed|
|-|-|-|
|bit|bigint|bigint|

## See Also

- [Bitwise Operators](bitwise-operators-azure-stream-analytics.md)
- [& (Bitwise AND)](bitwise-and-azure-stream-analytics.md)
- [^ (Bitwise Exclusive OR)](bitwise-xor-azure-stream-analytics.md)
- [~ (Bitwise NOT)&#40;Azure Stream Analytics&#41;](bitwise-not-azure-stream-analytics.md)
- [Data Types Overview](data-types-azure-stream-analytics.md)
- [Conversion Functions](conversion-functions-azure-stream-analytics.md)
- [Built-in Functions](built-in-functions-azure-stream-analytics.md)