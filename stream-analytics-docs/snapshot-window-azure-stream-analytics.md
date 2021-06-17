---
title: Snapshot Window (Azure Stream Analytics)
description: "Describes the Snapshot Window function supported by the Stream Analytics Query Language."
applies_to:
  - "Azure"
ms.service: stream-analytics
ms.topic: reference
ms.date: 07/10/2020
---

# Snapshot window (Azure Stream Analytics)

Snapshot windows groups events that have the same timestamp. Unlike other windowing types, which require a specific window function (such as [SessionWindow()](session-window-azure-stream-analytics.md), you can apply a snapshot window by adding System.Timestamp() to the GROUP BY clause.

The following diagram illustrates a stream with a series of events and how they are mapped into snapshot windows.

![Snapshot window diagram](./media/snapshot-window-azure-stream-analytics/snapshot.png)

System.Timestamp() can be considered in the GROUP BY clause as a key column or a snapshot window definition because it groups events into a window based on the equality of timestamps. When combined with another window function, System.Timestamp() is treated as a key and not as a window definition. System.Timestamp() does not produce an error when used with other window functions unlike when multiple window functions are used in the GROUP BY clause. Using both System.Timestamp() and a window function in the GROUP BY can be useful to batch the results.

Any expression that contains System.Timestamp() is not considered a window. For example, `GROUP BY DATEPART(minute, System.Timestamp())` fails with the error "a window must be specified".

## Syntax

```sql
System.Timestamp()
```

## Examples

### Basic example

The following example returns the count of tweets with the same topic type that occur at exactly the same time:

```sql
SELECT Topic, COUNT(*)
FROM TwitterStream TIMESTAMP BY CreatedAt
GROUP BY Topic, System.Timestamp()
```

### Tumbling window snapshot example

It is usual to expect input events to occur at exactly the same time. It's more common to happen within an intermediate step of the query, especially after applying a different window function.

The following example returns the count of tweets with the same topic type by the same user within 30 minute intervals:

```sql
WITH PerInterval AS (
    SELECT Topic, User, COUNT(*)
    FROM TwitterStream TIMESTAMP BY CreatedAt
    GROUP BY Topic, User, TumblingWindow(minute, 30)
)
SELECT * INTO UserTopicsCount FROM PerInterval
```

To find the number of users and total tweets per topic within the same interval, you can use the result of the previous query. Because of the tumbling window results will all have timestamps aligned to the 30 minute boundary, you can use a snapshot window to return events at each boundary since they all have same timestamp value.

```sql
SELECT Topic, Users = COUNT(*), Total = SUM (count)
FROM PerInterval
GROUP BY Topic, System.Timestamp()
```

The previous query returned the number of users and total tweets per topic within the same 30 minute interval. To get same results once per 2 hours, add a tumbling window of 2 hours to the GROUP BY clause.

The following query returns results from all four 30 minute intervals at the end of each 2 hour window.

```sql
SELECT Topic, Users = COUNT(*), Total = SUM (count)
FROM PerInterval
GROUP BY Topic, System.Timestamp(), Tumbling (hour, 2)
```

### Aggregate windows example

You can use System.Timestamp() as one of the windows in the aggregate Windows() construct.

```sql
SELECT 
    TollId, 
    COUNT(*) 
FROM Input TIMESTAMP BY EntryTime 
GROUP BY 
    TollId, 
    Windows(
        TumblingWindow(minute, 10),
        TumblingWindow(minute, 20),
        System.Timestamp())
```
