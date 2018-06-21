---
title: "@@JOBINFO (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2018-06-21"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# &#x40;&#x40;JOBINFO (U-SQL)
The system variable `@@JOBINFO` provides a variety of job related information.

## Syntax
<pre>
@@JOBINFIO
</pre>

The following parts are supported:

| Job Info Property | Return Type | Description |
|-------------------|-------------|------------------|
| `@@JobInfo.Id`      | `Guid?`       | The job's id typed as a nullable Guid. |
| `@@JobInfo.Name`    | `string`      | The job's name as set by the job submitter. |
| `@@JobInfo.Priority` | `int?`       | The job's priority as set by the job submitter. |
| `@@JobInfo.Allocation` | `int?`     | The job's analytic unit (AU) allocation as set by the job submitter. |
| `@@JobInfo.Account.Name` | `string`       | The name of the Azure Data Lake Analytics account against which the job got submitted. |
| `@@JobInfo.Submit.Alias` | `string`       | The alias of the job submitter. |
| `@@JobInfo.Submit.Date` | `DateTime?` | The timestamp when the job was submitted (in UTC-7 timezone). |

## Limitations and Notes
1. Currently, `@@JobInfo.Submit.Date` only returns `null`.
2. The property names are subject to change to align with the Azure SDK naming convention. The current properties will continue to be available.
3. The `@@JobInfo` properties are currently *not* available in the local run environment. The properties will be added in a future release.


## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.



**Basic Example**  
The following script collects job information as the script gets executed and outputs the result into a text file with header information. Note that since both `@@JobInfo.Name` and `@@JobInfo.Account.Name` result in the same column name `Name`, an explicit alias must be used to disambiguate the columns.
```sql
@data =
   SELECT @@JobInfo.Id, 
          @@JobInfo.Name AS JobName, 
          @@JobInfo.Priority, 
          @@JobInfo.Allocation, 
          @@JobInfo.Account.Name AS AccountName, 
          @@JobInfo.Submit.Alias, 
          @@JobInfo.Submit.Date 
   FROM(VALUES(1)) AS T(x);

OUTPUT @data
TO "/ReferenceGuide/BuiltInObjects/JobInfo/ExampleA.txt"
USING Outputters.Tsv(outputHeader : true);
```

**Using `Submit.Alias`**  
The following script mimics the use of a local user folder based on who submitted the script:
```sql
DECLARE CONST @output = 
    "/ReferenceGuide/BuiltInObjects/" + @@JobInfo.Submit.Alias.Substring(0, @@JobInfo.Submit.Alias.IndexOf('@')) + "/JobInfo/ExampleB.csv";

@data = 
   SELECT data 
   FROM (VALUES ("This data is inserted into a folder based on the alias who submitted the job")) AS T(data);

OUTPUT @data
TO @output
USING Outputters.Csv();
```

## See Also 
* [Built-in U-SQL System Objects and Extensions](built-in-u-sql-system-objects-and-extensions.md)
* [DECLARE Variables (U-SQL)](declare-variables-u-sql.md)
