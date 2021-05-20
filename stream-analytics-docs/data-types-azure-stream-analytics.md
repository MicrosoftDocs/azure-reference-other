---
title: "Data Types (Azure Stream Analytics)"
description: "Lists the data types supported by Azure Stream Analytics."
applies_to: 
  - "Azure"

ms.service: stream-analytics
ms.topic: reference
ms.date: 05/17/2018
---

# Data Types (Azure Stream Analytics)
  In Azure Stream Analytics, each column or scalar expression has a related data type. A data type describes (and constrains) the set of values that a column of that type can hold or an expression of that type can produce.  
 
## Supported data types

 Below is the list of data types supported.  
  
|**Data type**|**Description**|
|-|-|  
|bigint|Integers in the range -2^63 (-9,223,372,036,854,775,808) to 2^63-1 (9,223,372,036,854,775,807).|  
|float|Floating point numbers in the range - 1.79E+308 to -2.23E-308, 0, and 2.23E-308 to 1.79E+308.|  
|nvarchar(max)|Text values, comprised of Unicode characters. Note: A value other than max is not supported.|  
|datetime|Defines a date that is combined with a time of day with fractional seconds that is based on a 24-hour clock and relative to UTC (time zone offset 0).|  
|bit|An integer that can take a value of 1, 0, or NULL. This is supported in [compatibility level 1.2](/azure/stream-analytics/stream-analytics-compatibility-level#compatibility-level-12) and above. |
|record|Set of name/value pairs. Values must be of supported data type.|  
|array|Ordered collection of values. Values must be of supported data type.|  
  
 You may join on (or compare) a bigint and a float data type. It will work correctly in all cases except for the case of the very large bigint values that cannot be represented.  
  
## Type conversions
 
These are the rules governing *data type conversions*:  
- Conversion without precision loss during input read and output write operations is implicit and is always successful  
- Precision loss and overflow inside output write operations is handled by configured error policy (set to either Drop or Retry)  
- Type conversion errors happening during output write operations are handled by the error policy  
- Type conversion errors happening during input read operations cause the job to drop the event

## Casting data
There are three functions in the streaming SQL language that are useful for observing and adjusting the data type of your data.
- [CAST](cast-azure-stream-analytics.md)
- [TRY_CAST](try-cast-azure-stream-analytics.md)
- [GetType](gettype-azure-stream-analytics.md)
  

## Type mappings and serialization formats:
| Data type  | CSV in  | CSV out  | JSON in  | JSON out  | Avro in  | Avro out  |
|---|---|---|---|---|---|---|
| **bigint**  | string converted to 64 bit signed integer  | 64 bit signed integer converted to string using job culture  | number: integer converted to 64 bit signed integer; <br /><br />Boolean: in [compatibility level 1.1](/azure/stream-analytics/stream-analytics-compatibility-level) and below "false" is converted to 0, "true" is converted to 1  | number: integer  | long and int converted to 64 bit signed integer; <br /><br />Boolean: in [compatibility level 1.1](/azure/stream-analytics/stream-analytics-compatibility-level) and below false is converted to 0, true is converted to 1  | long  |
| **float**  | string converted to 64 bit signed float point number  | 64 bit signed float point number converted to string using job culture  | number: fraction converted to 64 bit signed float point number  | number: fraction  | double and float converted to 64 bit signed float point number    | double  |
| **nvarchar(max)**  | string  | string  | string  | string  | string  | string  |
| **datetime**  | string converted to datetime following ISO 8601 standard  | string using ISO 8601 standard  | string converted to datetime following ISO 8601 standard  | datetime converted to string using ISO 8601 standard  | string converted to datetime following ISO 8601 standard  | datetime converted to string using ISO 8601 standard  |
| **bit** ([compatibility level 1.2](/azure/stream-analytics/stream-analytics-compatibility-level#compatibility-level-12) and above) | string "true", "false", or "null" is converted to integer value 1, 0, or null correspondingly | converted to string "true" or "false" | Boolean: "false" is converted to 0, "true" is converted to 1 | Boolean: boolean value | Boolean: false is converted to 0, true is converted to 1 | boolean |
| **record**  | N/A  | Not supported, "Record" string is outputted  | JSON object  | JSON object  | Avro record type  | Avro record type  |
| **array**  | N/A  | Not supported,  "Array" string is outputted  | JSON object  | JSON object  | Avro record type  | Avro record type  |

> [!NOTE]
> No data type conversion is needed for Parquet.
 
## Type mapping when writing to structured data stores:
| Data type | SQL | Power BI | Document DB |
|---------------|-----------------------------------------------------------------------------|---------------------------------------------|------------------------------------------------------|
| **bigint** | bigint, int, smallint, tinyint, all string types (ntext, nvarchar, char, …) | yes | numeric: integer |
| **float** | float, real, decimal, numeric, all string types ( ntext, nvarchar, char, …) | yes | number: fraction |
| **nvarchar(max)** | All string types (ntext, nvarchar, char, uniqueidentifier…) | yes | string |
| **datetime** | datetime, datetime2, datetimeoffset, all string types ( ntext, nvarchar, char, …) | yes | datetime converted to string using ISO 8601 standard |
| **bit** ([compatibility level 1.2](/azure/stream-analytics/stream-analytics-compatibility-level#compatibility-level-12) and above) | bigint, int, smallint, tinyint, bit, all string types (ntext, nvarchar, char, …) | yes | boolean: 1 is converted to true, 0 converted to false |
| **record** | Not supported,  "Record" string is outputted | Not supported,  "Record" string is outputted | JSON object |
| **array** | Not supported,  "Array" string is outputted | Not supported,  "Array" string is outputted | JSON object |
