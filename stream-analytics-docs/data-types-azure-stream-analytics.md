---
title: "Data Types"
description: "Lists the supported data types."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# Data Types
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

Each record has a related data type. A data type describes (and constrains) the set of values that a record of that type can hold or an expression of that type can produce.

Please note that it is records that have a type and not columns. Each record of a column can have a different type. If this will be transparent for most applications, it allows straightforward handling of schema drift scenarios and other unusual typing patterns.

## Supported data types

 Below is the list of data types supported.

|**Data type**|**Description**|
|-|-|
|bigint|Integers in the range -2^63 (-9,223,372,036,854,775,808) to 2^63-1 (9,223,372,036,854,775,807).|
|float|Floating point numbers in the range - 1.79E+308 to -2.23E-308, 0, and 2.23E-308 to 1.79E+308. Floating-point decimal values generally do not have an exact binary representation. Loss of precision can be experienced. This is not specific to Azure Stream Analytics but occurs in all floating-point number implementations.|
|nvarchar(max)|Text values, comprised of Unicode characters. Note: A value other than max is not supported.|
|datetime|Defines a date that is combined with a time of day with fractional seconds (7 digits, 100 nanoseconds precision) that is based on a 24-hour clock and relative to UTC (time zone offset 0).|
|bit|An integer that can take a value of 1, 0, or NULL. This is supported in [compatibility level 1.2](/azure/stream-analytics/stream-analytics-compatibility-level#compatibility-level-12) and above. |
|record|Set of name/value pairs. Values must be of supported data type.|
|array|Ordered collection of values. Values must be of supported data type.|

 You may join on (or compare) a bigint and a float data type. It will work correctly in all cases except for the case of the very large bigint values that cannot be represented.

> [!NOTE]
> When reading bigint datatypes outside the range, Azure Stream Analytics supports, your Stream Analytics job would fail to deserialize the events with the error message: **InputDeserializationError**. You can pre-process the data and convert it to string. One option is using Azure functions to pre-process the data and convert such large integers to string.


## Type conversions

These are the rules governing *data type conversions*:

- Conversion without precision loss during input read and output write operations is implicit and is always successful
- Precision loss and overflow inside output write operations is handled by configured error policy (set to either Drop or Retry)
- Type conversion errors happening during output write operations are handled by the error policy
- Type conversion errors happening during input read operations cause the job to drop the event

A loss of precision may happen in converting values to float. It is not specific to Azure Stream Analytics but to the float data type in general. As such it is not considered an error. In the case where every digit needs to be conserved, the data should be read as string.

## Casting data

There are four functions in the streaming SQL language that are useful for observing and adjusting the data type of your data.

- [CAST](cast-azure-stream-analytics.md) : cast a single column to a given type - will fail the job in case of conversion error
- [TRY_CAST](try-cast-azure-stream-analytics.md) : cast a single column to a given type - errors are let through as NULL. See [input validation](/azure/stream-analytics/input-validation) for how to best use `TRY_CAST`
- [CREATE TABLE](create-table-stream-analytics.md) : define a single explicit schema to an input. Rows with conversion errors are removed from the stream
- [GetType](gettype-azure-stream-analytics.md) : return the type of a column

For most use cases, the recommended option is to use [TRY_CAST](try-cast-azure-stream-analytics.md). This function protects downstream processing by ensuring the output type, while preventing the loss of data by replacing the value in error by NULL. The row is not dropped, and that original value can still be projected in another column.

For strong guarantees, the recommended option is to use [CREATE TABLE](create-table-stream-analytics.md). This approach allows to inform the job of the schema of a given input, with no risk of deviation. The trade-off being that only a single schema can be defined on a given input, and non-compliant rows will be dropped.

If possible, all casting operations should be done explicitly via these functions, rather than implicitly (silently) in other functions. This avoids type mismatches, unexpected behaviors, and insertion errors for strongly typed outputs like SQL databases. See [input validation](/azure/stream-analytics/input-validation) for how to protect the main query logic from such errors.

## Conversion to bit

Values will be converted between float and bit with the following rules:

|From|To|
|-|-|
|(BIT) 1|(FLOAT) 1.0|
|(BIT) 0|(FLOAT) 0.0|
|(BIT) NULL|(FLOAT) NULL|
|(FLOAT) 0.0|(BIT) 0|
|(FLOAT) **any other value** |(BIT) **1**|
|(FLOAT) NULL|(BIT) NULL|

## Type mappings and serialization formats

| Data type  | CSV in  | CSV out  | JSON in  | JSON out  | Avro in  | Avro out  |
|-|-|-|-|-|-|-|
| **bigint**  | string converted to 64 bit signed integer  | 64 bit signed integer converted to string using job culture  | number: integer converted to 64 bit signed integer; <br /><br />Boolean: in [compatibility level 1.1](/azure/stream-analytics/stream-analytics-compatibility-level) and below "false" is converted to 0, "true" is converted to 1  | number: integer  | long and int converted to 64 bit signed integer; <br /><br />Boolean: in [compatibility level 1.1](/azure/stream-analytics/stream-analytics-compatibility-level) and below false is converted to 0, true is converted to 1  | long  |
| **float**  | string converted to 64 bit signed float point number  | 64 bit signed float point number converted to string using job culture  | number: fraction converted to 64 bit signed float point number  | number: fraction  | double and float converted to 64 bit signed float point number    | double  |
| **nvarchar(max)**  | string  | string  | string  | string  | string  | string  |
| **datetime**  | string converted to datetime following ISO 8601 standard  | string using ISO 8601 standard  | string converted to datetime following ISO 8601 standard  | datetime converted to string using ISO 8601 standard  | string converted to datetime following ISO 8601 standard  | datetime converted to string using ISO 8601 standard  |
| **bit** ([compatibility level 1.2](/azure/stream-analytics/stream-analytics-compatibility-level#compatibility-level-12) and above) | string "true", "false", or "null" is converted to integer value 1, 0, or null correspondingly | converted to string "true" or "false" | Boolean: "false" is converted to 0, "true" is converted to 1 | Boolean: boolean value | Boolean: false is converted to 0, true is converted to 1 | boolean |
| **record**  | N/A  | Not supported, "Record" string is outputted  | JSON object  | JSON object  | Avro record type  | Avro record type  |
| **array**  | N/A  | Not supported,  "Array" string is outputted  | JSON object  | JSON object  | Avro record type  | Avro record type  |

> [!NOTE]
> No data type conversion is needed for Parquet.

## Type mapping when writing to structured data stores

| Data type | SQL | Power BI | Azure Cosmos DB | PostgreSQL | Azure Data Explorer |
|-|-|-|-|-|-|
| **bigint** | bigint, int, smallint, tinyint, all string types (ntext, nvarchar, char, …) | yes | numeric: integer | bigint<br /><br />If the column type is smallint or integer, error "incorrect binary data format" will occur. | dynamic, int, long |
| **float** | float, real, decimal, numeric, all string types ( ntext, nvarchar, char, …) | yes | number: fraction | double precision, numeric. Limited to 1.78E+308<br /><br />If the column type is real, error "incorrect binary data format" will occur. | dynamic, real, double |
| **nvarchar(max)** | All string types (ntext, nvarchar, char, uniqueidentifier…) | yes | string | character varying, text | dynamic, string |
| **datetime** | datetime, datetime2, datetimeoffset, all string types ( ntext, nvarchar, char, …) | yes | datetime converted to string using ISO 8601 standard | timestamptz for UTC timestamp, timestamp otherwise | dynamic, string, datetime |
| **bit** ([compatibility level 1.2](/azure/stream-analytics/stream-analytics-compatibility-level#compatibility-level-12) and above) | bigint, int, smallint, tinyint, bit, all string types (ntext, nvarchar, char, …) | yes | boolean: 1 is converted to true, 0 converted to false | bit | dynamic, bool |
| **record** | Not supported,  "Record" string is outputted | Not supported,  "Record" string is outputted | JSON object | Not supported | dynamic, bool, long, datetime, byte array, real, double, string |
| **array** | Not supported,  "Array" string is outputted | Not supported,  "Array" string is outputted | JSON object | Not supported | dynamic, string |
