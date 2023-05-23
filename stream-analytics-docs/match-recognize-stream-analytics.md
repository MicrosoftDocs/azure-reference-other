---
title: MATCH_RECOGNIZE (Azure Stream Analytics)
description: Search for a set of events over a data stream in Stream Analytics Query Language.
applies_to: 
  - "Azure"
ms.service: stream-analytics
ms.topic: reference
ms.date: 07/7/2021
---

# MATCH_RECOGNIZE (Stream Analytics)

The MATCH_RECOGNIZE clause is used to search for a set of events over a data stream. This clause enables you to define event patterns using regular expressions and aggregate methods to verify and extract values from the match.

The following example shows the basic structure of a MATCH_RECOGNIZE clause:

```SQL
SELECT *
INTO output FROM input TIMESTAMP BY time
	MATCH_RECOGNIZE (
		LIMIT DURATION (minute, 1)
		PARTITION BY tollBoothId
		MEASURES
			Last(Toyota.LicensePlate) AS toyotaLicensePlate,
			Last(Lexus.LicensePlate) AS lexusLicensePlate
		AFTER MATCH SKIP TO NEXT ROW
		PATTERN (Toyota+ Ford* Lexus+)
		DEFINE
			Toyota AS Toyota.make = 'Toyota',
			Ford AS Ford.make = 'Ford',
			Lexus AS Lexus.make = 'Lexus'
	) AS T
```

MATCH_RECOGNIZE has a matching output of ONE ROW PER MATCH as default, which is the only matching available. This means the match produces a single row result per match and does not return the rows that are matched.
    
## Syntax  
  
```SQL  
SELECT_star_query_definition
MATCH_RECOGNIZE (
	LIMIT DURATION (time_unit, time)
	PARTITION BY column_alias
	MEASURES
		expression AS column_alias [,...n]
	AFTER MATCH SKIP TO NEXT ROW
	PATTERN ( <pattern_group> )
	DEFINE
		pattern_name AS boolean_expression [,…n]
) AS column_alias

<pattern_group> ::=
{
	<pattern_name_modifier> [ | <pattern_group> ]*
}
<pattern_name_modifier> ::=
{
	<pattern_atom> [ <pattern_atom> ]*
}
<pattern_atom> ::=
{
	[ pattern_name | ( <pattern_group> ) ] [ <pattern_modifier> ]?
}
<pattern_name> :: =
{
	name | .
}
<pattern_modifier> ::=
{
	* | + | ?
}
```  
 
## LIMIT DURATION

 The limit duration is used to define a window of time for the pattern to be searched on. The events are ordered by time and TIMESTAMP BY can be used on the SELECT clause to specify time field.

## PARTITION BY

PARTITION BY allows the match to be keyed and partitioned over a column name. A match will happen over every unique key specified by the partition statement. This enables a single query to be matched over all the keys and generate separate matches, one to every key.

## AFTER MATCH SKIP TO NEXT ROW

This skip clause defines that once a pattern is matched starting at event **S**, the next try to match pattern will start at event **S+1**. Matches can overlap in this case as a pattern can contain the start of another pattern inside. This is the only skip clause available.
 
## MEASURES

MEASURES is used to define the projected values from the match using aggregate methods. For example, `LAST(A.id) AS aid` will output the last `id` value that was found over all events that matched pattern named `A` into field name `aid`.

### Classifier function

The classifier function can be used in MEASURES to output pattern names matched to input events. The function returns a list of strings, each with the pattern name that matched an event.

## PATTERN

The pattern defines the regular expression of events to be searched over the data stream. Pattern variables are user- defined and separated by spaces. Modifiers like **+** and **\*** can be used to modify the frequency of a variable when matching events.

### Example

```SQL
PATTERN (A+ (B | C))
```

The pattern on this example defines a variable **A** at least once, followed by a concatenation of either **B** or **C**.

## Pattern Quantifiers

Pattern quantifiers are used to change how a pattern is mapped in the data stream, defining how many times a pattern needs to match to be valid. The following quantifiers are available:

* '*' - Zero or more times
* '+' - One or more times
* '?' – Zero or one time
* '|' - One pattern or another

**Example:**

```SQL
PATTERN (A? B+)
```

This example defines **A** 0 or 1 time followed by **B** at least once.

## DEFINE

DEFINE specifies the rules used to match a pattern variable to an event. The rules are Boolean expressions over aggregated values from the data stream.

```SQL
DEFINE
    A AS Last(A.bigint) > 5,
    B AS Last(A.bigint) < B.bigint
```

This example defines rules **A** and **B** where LAST value of **A** is bigger than 5, and **B** where LAST value of **A** is smaller than the current value of **B**. When not using an aggregate function on DEFINE expression, the current event being evaluated binds to the pattern variable, for example, on **B.bigint** the **B** value comes from the current event being evaluated.

Defined patterns can only be accessed in order, if pattern **A** is defined before pattern **B**, **A** cannot reference **B**.

**Allowed**
```SQL
...
DEFINE
A AS Last(A.value),
B AS Max(A.value) + Max(B.value),
...
```

**Not allowed**
```SQL
...
DEFINE
A AS Last(A.value) + Last(B.Value),
B AS Max(A.value) + Max(B.value),
...
```

## Aggregate Methods

The following aggregate methods can be used in MEASURES and DEFINE:

* Min – The minimum number aggregated so far.
* Max – The maximum number aggregated so far.
* First – The first value aggregated.
* Last – The last value aggregated so far.

**Example:**

Refilling high-pressure tanks is a dangerous process and needs to be monitored closely as increasing pressure on a tank also increases its temperature, pressure needs to increase steadily to give time for the tank to cool down while refilling.

In this example, the developer wants to monitor the refilling of a high-pressure tank as it starts to increase pressure. The tank starts refilling and cannot increase the pressure by its double in less than 3 minutes, otherwise the tank overheats and could cause a catastrophic failure.

The following query could be used to monitor the progress:

```SQL
SELECT *
INTO output FROM input TIMESTAMP BY time
MATCH_RECOGNIZE (
	LIMIT DURATION (minute, 3)
	MEASURES
 		MAX(Dangerous.pressure) as pressure,
		Classifier() as patterns
	AFTER MATCH SKIP TO NEXT ROW
	PATTERN (Normal+ Dangerous+)
	DEFINE
		Normal AS Normal.isFilling = 1,
		Dangerous AS Max(Dangerous.pressure) > 2* Max(Normal.pressure)
) AS T
```

This query matches **Normal** to any event that is filling the tank and in case the pressure is over double of a **Normal** filling within 3 minutes, than an event is fired with the maximum pressure reading for the **Dangerous** pattern.

## Limitations

* Only field values can be used for aggregates. No functions can be called inside an aggregate call.

    **Allowed**
	```SQL 
    ...
    DEFINE
	    A AS Max(A.value) > 5,
    ...
	```

    **Not allowed**
	```SQL
    ...
    DEFINE
	    A AS Max(udf.myUdf(A.value)) > 5,
    ...
	```

* Only a single field can be supplied to an aggregate function as input parameter.

    **Allowed**
	```SQL
    ...
        DEFINE
		    A AS Max(A.value) > 5,
	...    
	```

    **Not allowed**
    ```SQL
	...
	DEFINE
	    A AS Max(A.value1 + A.value2) > 5,
	...
	```

## See also

* [Query Language Elements](query-language-elements-azure-stream-analytics.md)

