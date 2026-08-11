---
title: "JSON_PARSE"
description: "Converts a JSON-formatted string into a record for use in Azure Stream Analytics and Microsoft Fabric Eventstream queries."
author: spelluru
ms.author: spelluru
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/11/2026
ai-usage: ai-assisted
---

<!-- markdownlint-disable-next-line MD025 -->
# JSON_PARSE

:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

`JSON_PARSE` converts a JSON-formatted string into a record that you can access and query. Use this function when an event contains a nested JSON object serialized as a string, such as the `data` property in a Fabric Eventstream change event.

## Why use JSON_PARSE

Many streaming scenarios, particularly Eventstream integrations, contain events where a property is a JSON document serialized as a string. During event deserialization, these nested payloads are treated as strings, so you can't directly access their properties as JSON objects. Use `JSON_PARSE` to convert string-encoded JSON into a structured record whose properties you can access and query.

## Syntax

```sql
JSON_PARSE ( jsonString )
```

## Arguments

| Name | Type | Description |
| --- | --- | --- |
| `jsonString` | `nvarchar(max)` | A valid JSON object serialized as a string. |

## Return type

Returns the parsed JSON object as a value of type `record`.

## Error handling

`JSON_PARSE` is a non-throwing function. If parsing can't be completed, the function returns `NULL` instead of failing query execution. `JSON_PARSE` returns `NULL` when:

- The input expression isn't a supported string value.
- The supplied string isn't valid JSON.
- Another JSON conversion failure occurs.

## Examples

The examples use the following input event. The `old` and `current` properties contain JSON objects serialized as strings.

```json
{
  "eventrow": {
    "old": "{\"SalesOrderID\":\"65191\",\"SalesOrderDetailID\":\"89090\"}",
    "current": "{\"SalesOrderID\":\"65191\",\"SalesOrderDetailID\":\"89090\",\"ProductName\":\"Touring-2000 Blue, 54\"}"
  }
}
```

### Parse a nested JSON string

The following query converts the JSON string in `eventrow.old` into a record:

```sql
SELECT
    JSON_PARSE(eventrow.old) AS ParsedOldRow
INTO Output
FROM Input
```

### Access properties in a parsed record

The following query parses `eventrow.current` and accesses properties in the returned record by using dot notation:

```sql
WITH ParsedEvents AS
(
    SELECT JSON_PARSE(eventrow.current) AS ParsedCurrent
    FROM Input
)
SELECT
    ParsedCurrent.SalesOrderID,
    ParsedCurrent.ProductName
FROM ParsedEvents
```

## Related content

- [String functions](string-functions-azure-stream-analytics.md)
- [Stream SQL change events to an eventstream](/fabric/real-time-intelligence/event-streams/stream-sql-change-events-to-eventstream)
- [Parse JSON and Avro data in Azure Stream Analytics](/azure/stream-analytics/stream-analytics-parsing-json)
