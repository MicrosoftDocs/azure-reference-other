---
title: "~ (Bitwise NOT) (Azure Stream Analytics)"
description: "Performs a bitwise logical NOT operation on an integer value."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# ~ (Bitwise NOT) (Azure Stream Analytics)

Performs a bitwise logical NOT operation on an integer value.

## Syntax

```SQL
~ expression
```

## Arguments

**expression**

Is any valid expression of the data types bit or bigint. Expression is treated as a binary number for the bitwise operation.

## Return Types

**bit** if the input value is **bit**.

**bigint** if the input value is **bigint**.

## Remarks

The ~ bitwise operator performs a bitwise logical NOT on the expression, taking each bit in turn. If expression has a value of 0, the bits in the result set are set to 1; otherwise, the bit in the result is cleared to a value of 0. In other words, ones are changed to zeros and zeros are changed to ones.

For illustration, the binary representation of 170 is 0000 0000 1010 1010. Performing the bitwise NOT operation on this value produces the binary result 1111 1111 0101 0101, which is decimal -171.

```
(~170)
0000 0000 1010 1010
-------------------
1111 1111 0101 0101
```

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
	~ bit0 AS NOT0,
	~ bit1 AS NOT1,
	~ bitN AS NOTnull
INTO bitNOT
FROM MyCTE
```

Returns:

|bit0|bit1|bitN|NOT0|NOT1|NOTnull|
|-|-|-|-|-|-|
|false|true|NULL|true|false|NULL|

Applying the operator on **bigint** expressions:

```SQL
SELECT
	bigint0,
	bigint1,
	bigintN,
	~ bigint0 AS NOT0,
	~ bigint1 AS NOT1,
	~ bigintN AS NOTnull,
	~ 170 AS NOT170
INTO bigintNOT
FROM MyCTE
```

Returns:

|bit0|bit1|bitN|NOT0|NOT1|NOTnull|NOT170|
|-|-|-|-|-|-|-|
|0|1|NULL|-1|-2|NULL|**-171**|

Validating the **output types**:

```SQL
SELECT
	GetType(~ bit0) AS NOTtype_bit,
	GetType(~ bigint0) AS NOTtype_bigint
INTO typesNOT
FROM MyCTE
```

Returns:

|NOTtype_bit|NOTtype_bigint|
|-|-|
|bit|bigint|

## See Also

- [Bitwise Operators &#40;Azure Stream Analytics&#41;](bitwise-operators-azure-stream-analytics.md)
- [& (Bitwise AND)&#40;Azure Stream Analytics&#41;](bitwise-and-azure-stream-analytics.md)
- [| (Bitwise OR) &#40;Azure Stream Analytics&#41;](bitwise-or-azure-stream-analytics.md)
- [^ (Bitwise Exclusive OR) &#40;Azure Stream Analytics&#41;](bitwise-xor-azure-stream-analytics.md)
- [Data Types Overview &#40;Azure Stream Analytics&#41;](data-types-azure-stream-analytics.md)
- [Conversion Functions &#40;Azure Stream Analytics&#41;](conversion-functions-azure-stream-analytics.md)
- [Built-in Functions &#40;Azure Stream Analytics&#41;](built-in-functions-azure-stream-analytics.md)