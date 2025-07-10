---
title: "Bitwise operators"
description: "Lists the Bitwise Operators supported by Azure Stream Analytics."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# Bitwise Operators
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

Bitwise operators perform bit manipulations between two expressions of any of the data types of the integer data type category.

## Overview

Bitwise operators convert two integer values to binary bits, perform the AND, OR, XOR, or NOT operation on each bit, producing a result. Then converts the result to an integer.   
For example, the integer 170 converts to binary 1010 1010.
The integer 75 converts to binary 0100 1011.

|operator|bitwise math|
|---- |---- |
|AND <br> If bits at any location are both 1, the result is 1. |1010 1010 = 170 <br>0100 1011 =  75 <br>-----------------  <br> 0000 1010 =  10 |
|OR <br> If either bit at any location is 1, the result is 1. |1010 1010 = 170 <br>0100 1011 =  75 <br>-----------------  <br> 1110 1011 = 235|
|NOT  <br> Reverses the bit value at every bit location. |1010 1010 = 170 <br>----------------- <br>  0101 0101 =   85 |

Stream Analytics Query Language provides the following bitwise operators:

:::row:::
    :::column:::
        [& (Bitwise AND)](bitwise-and-azure-stream-analytics.md)
    :::column-end:::
    :::column:::
        [| (Bitwise OR)](bitwise-or-azure-stream-analytics.md)
    :::column-end:::
    :::column:::
        [^ (Bitwise Exclusive OR)](bitwise-xor-azure-stream-analytics.md)
    :::column-end:::
    :::column:::
        [~ (Bitwise NOT)](bitwise-not-azure-stream-analytics.md)
    :::column-end:::
:::row-end:::

## See Also

- [Data Types Overview](data-types-azure-stream-analytics.md)
- [Conversion Functions](conversion-functions-azure-stream-analytics.md)
- [Built-in Functions](built-in-functions-azure-stream-analytics.md)
