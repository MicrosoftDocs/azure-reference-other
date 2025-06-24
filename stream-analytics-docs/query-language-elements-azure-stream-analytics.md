---
title: "Query Language Elements"
description: "Azure Stream Analytics provides a variety of  elements for building queries. They are summarized below."
applies_to:
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# Query Language Elements

Azure Stream Analytics provides a variety of  elements for building queries. They are summarized below.

|Element|Summary|
|-------------|-------------|
|[APPLY](apply-azure-stream-analytics.md)|The APPLY operator allows you to invoke a table-valued function for each row returned by an outer table expression of a query. There are two forms of APPLY:<br /><br /> CROSS APPLY returns only rows from the outer table that produce a result set from the table-valued function.<br /><br /> OUTER APPLY returns both rows that produce a result set, and rows that do not, with NULL values in the columns produced by the table-valued function.|
|[CASE](case-azure-stream-analytics.md)|CASE evaluates a list of conditions and returns one of multiple possible result expressions|
|[COALESCE](coalesce-azure-stream-analytics.md)|COALESCE evaluates the arguments in order and returns the value of the first expression that initially does not evaluate to NULL.|
|[CREATE TABLE](create-table-stream-analytics.md)|CREATE TABLE is used to define the schema of the payload of the events coming into Azure Stream Analytics.|
|[FROM](from-azure-stream-analytics.md)|FROM specifies the input stream or a step name associated in a WITH clause. The FROM clause is **always** required for any SELECT statement.|
|[GROUP BY](group-by-azure-stream-analytics.md)|GROUP BY groups a selected set of rows into a set of summary rows grouped by the values of one or more columns or expressions.|
|[HAVING](having-azure-stream-analytics.md)|HAVING specifies a search condition for a group or an aggregate. HAVING can be used **only** with the SELECT expression.|
|[INTO](into-azure-stream-analytics.md)|INTO explicitly specifies an output stream, and is **always** associated with an SELECT expression.  If not specified, the default output stream is "output".|
|[JOIN](join-azure-stream-analytics.md) and<br /><br /> [Reference Data JOIN](reference-data-join-azure-stream-analytics.md)|JOIN is used to combine records from two or more input sources.  JOIN is temporal in nature, meaning that each JOIN must define how far the matching rows can be separated in time.<br /><br /> JOIN is also used to   correlate persisted historical data or a slow changing dataset (aka. reference data) with the real-time event stream to make smarter decisions about the system. For example, join an event stream to a static dataset which maps IP Addresses to locations. This is the **only** JOIN supported in Stream Analytics where a temporal bound is not necessary.|
|[MATCH_RECOGNIZE](match-recognize-stream-analytics.md)|MATCH_RECOGNIZE is used to search for a set of events over a data stream.|
|[NULLIF](nullif-azure-stream-analytics.md)|NULLIF evaluates two arguments and returns null if they are equal.|
|[OVER](over-azure-stream-analytics.md)|OVER defines the grouping of rows before an associated aggregate or analytic function is applied. |
|[SELECT](select-azure-stream-analytics.md)|SELECT is used to retrieve rows from input streams and enables the selection of one or many columns from one or many input streams in Azure Stream Analytics.|
|[UNION](union-azure-stream-analytics.md)|UNION combines two or more queries into a single result set that includes all the rows that belong to all queries in the union.|
|[WHERE](where-azure-stream-analytics.md)|WHERE specifies the search condition for the rows returned by the query.|
|[WITH](with-azure-stream-analytics.md)|WITH specifies a temporary named result set which can be referenced by a FROM clause in the query. This is defined within the execution scope of a single SELECT statement.|

## See Also
 [Built-In Functions](built-in-functions-azure-stream-analytics.md)
 [Data Types](data-types-azure-stream-analytics.md)
 [Time Management](time-management-azure-stream-analytics.md)


