---
title: "U-SQL Built-in Outputters | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-28"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: eb0ea384-2068-4b56-985e-3bbc1b1f8b23
caps.latest.revision: 13
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Built-in Outputters
U-SQL provides a built-in outputter class called `Outputters` that provides the following three built-in outputters to transform a rowset into a [file or set of files](../USQL/output-to-files-u-sql.md):    
-   [`Outputters.Text()`](../USQL/outputters-text.md): Provides outputting a rowset into a variety of delimited text formats.    
-   [`Outputters.Csv()`](../USQL/outputters-csv.md): Provides outputting a rowset into a comma-separated value (CSV) file of different encodings.   
-   [`Outputters.Tsv()`](../USQL/outputters-tsv.md): Provides outputting a rowset into a tab-separated value (TSV) file of different encodings.  
  
The `Csv()` and `Tsv()` outputters are special versions of the generic `Text()` outputter where the delimiter has been fixed to comma and tab respectively.  
  
The built-in outputters serialize a rowset by serializing the individual data types, using a set of delimiters to identify the row and column boundaries and encode certain values according to the set parameters.  
  
Technically speaking these are factory methods that generate an instance of the `IOutputter` class and they can be used in the [USING](../USQL/output-statement-u-sql.md#us_cla) clause of the [OUTPUT](../USQL/output-statement-u-sql.md) statement. Since they create the outputter object, one does not need to call them with `new`.  
 
If the [OUTPUT](../USQL/output-statement-u-sql.md) statement specifies a file set pattern, then the outputter [parameters](../USQL/outputter-parameters-u-sql.md) will be applied to all the selected files equally. If different files require different parameter values, then different [OUTPUT](../USQL/output-statement-u-sql.md)  statements need to be used.   
  
### See Also 
* [Outputter Parameters (U-SQL)](../USQL/outputter-parameters-u-sql.md)
* [Outputters.Text()](../USQL/outputters-text.md) 
* [Outputters.Csv()](../USQL/outputters-csv.md) 
* [Outputters.Tsv()](../USQL/outputters-tsv.md)  
* [Output Statement (U-SQL)](../USQL/output-statement-u-sql.md)
* [Output to Files (U-SQL)](../USQL/output-to-files-u-sql.md)
* [U-SQL Programmability Guide: User-Defined Outputter](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-outputter)
* [Extending U-SQL Expressions with User-Code](../USQL/extending-u-sql-expressions-with-user-code.md)  

