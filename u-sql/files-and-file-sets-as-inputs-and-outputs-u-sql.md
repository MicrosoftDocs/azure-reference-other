---
title: "Files and File Sets as Inputs and Outputs (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b7bc8893-7083-47af-9bb5-1de91e3fa6c2
caps.latest.revision: 18
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Files and File Sets as Inputs and Outputs (U-SQL)
U-SQL as a Big Data processing language can operate over unstructured data such as files and set of files as well as over structured data that has been stored in form of [tables](u-sql-tables.md). The processed results of U-SQL queries can then be written back into “unstructured” files or stored in structured tables.  
  
A quick note on the term “unstructured data”: This data often has internal structure such as a CSV format, a JSON or XML structure. However, from the point of view of the language it is unstructured, because it is stored in a file as byte stream and has no metadata stored in a place that is accessible or understood by the language processor. While this makes it impossible for the query processor to know what the structure is and to optimize the data processing accordingly, it provides more flexibility and agility to the data processing and gives the user the ability to provide a late-bound schema that is appropriate to the processing at-hand, instead of having a pre-determined schema and interpretation of the data.  
  
In this section we focus on the unstructured data as input and output. Please refer to the section on [U-SQL tables](u-sql-tables.md), [SELECT](select-expression-u-sql.md) expressions and [INSERT](insert-u-sql.md) for more information about tables as input and output.  
  
## See Also  
* [Input Files (U-SQL)](input-files-u-sql.md)
* [Output to Files (U-SQL)](output-to-files-u-sql.md)
* [Built-in U-SQL UDOs](built-in-u-sql-udos.md)
* [EXTRACT Expression (U-SQL)](extract-expression-u-sql.md) 
* [Output Statement (U-SQL)](output-statement-u-sql.md)
