---
title: "ROUND"
description: "Returns a numeric value, rounded to the specified length or precision."
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# ROUND

Returns a numeric value, rounded to the specified length or precision.

## Syntax  
  
```SQL   
ROUND ( numericExpression, length )
```  
  
## Arguments

**numericExpression**  
  
The numeric expression to be rounded. Must be bigint or float.

**length**

The precision to which *numericExpression* is to be rounded. *length* must be an expression of typ*e bigint. When length is a positive number, *numericExpression* is rounded to the number of decimal positions specified by *length*. When *length* is a negative number, *numericExpression* is rounded on the left side of the decimal point, as specified by *length*.
  
## Return Types  

|numericExpression Type|Return type|
|----------------------|-----------|
|bigint|bigint|
|float|float|

ROUND always returns a value. If length is negative and larger than the number of digits before the decimal point, ROUND returns 0.

## Examples  
  
```SQL  
SELECT ROUND (a, b) AS res FROM input
```  
  
|Expression|Result|
|----------|------|
|ROUND(1, 0)|1|
|ROUND(0, 0)|0|
|ROUND(-1, 0)|-1|
|ROUND(1.0, 0)|1.0|
|ROUND(0.5, 0)|1.0|
|ROUND(-0.5, 0)|-1.0|
|ROUND(1.234, 2)|1.23|
|ROUND(1.234, 10)|1.234|
|ROUND(123.4, -1)|120.0|
|ROUND(123.4, -10)|0.0|
|ROUND(501.0101, -3)|1000.0|
|ROUND(123.9995, 3)|124.0|
