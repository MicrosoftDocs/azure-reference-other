---
title: "Files and File Sets as Inputs and Outputs (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b7bc8893-7083-47af-9bb5-1de91e3fa6c2
caps.latest.revision: 18
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Files and File Sets as Inputs and Outputs (U-SQL)
[//]: * "Input and Output of Data"  
U-SQL as a Big Data processing language can operate over unstructured data such as files and set of files as well as over structured data that has been stored in form of [tables](../USQL/u-sql-tables.md). The processed results of U-SQL queries can then be written back into “unstructured” files or stored in structured tables.  
  
A quick note on the term “unstructured data”: This data often has internal structure such as a CSV format, a JSON or XML structure. However, from the point of view of the language it is unstructured, because it is stored in a file as byte stream and has no metadata stored in a place that is accessible or understood by the language processor. While this makes it impossible for the query processor to know what the structure is and to optimize the data processing accordingly, it provides more flexibility and agility to the data processing and gives the user the ability to provide a late-bound schema that is appropriate to the processing at-hand, instead of having a pre-determined schema and interpretation of the data.  
  
In this section we focus on the unstructured data as input and output. Please refer to the section on [U-SQL tables](../USQL/u-sql-tables.md), [SELECT](../USQL/select-expression-u-sql.md) expressions and [INSERT](../USQL/insert-u-sql.md) for more information about tables as input and output.  
  
### See Also  
* [Input Files (U-SQL)](../USQL/input-files-u-sql.md)
* [Output to Files (U-SQL)](../USQL/output-to-files-u-sql.md)
* [Built-in U-SQL UDOs](../USQL/built-in-u-sql-udos.md)
* [EXTRACT Expression (U-SQL)](../USQL/extract-expression-u-sql.md) 
* [Output Statement (U-SQL)](../USQL/output-statement-u-sql.md)



