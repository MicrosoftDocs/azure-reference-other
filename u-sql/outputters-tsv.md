---
title: "Outputters.Tsv() | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-28"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6e7cc044-5bd2-4145-9b85-652162febc53
caps.latest.revision: 7
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Outputters.Tsv()
### Outputting TSV Files    
The Tsv() outputter disallows the `delimiter` parameter and defaults the field delimiter to '\t' (tab).  All other parameters are the same.  See [Outputter Parameters (U-SQL)](outputter-parameters-u-sql.md) for supported parameters and their defaults values.
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Syntax**   
The examples below show the basic syntax for each parameter using the Tsv() outputter.  Compare the output against the dataset as well as against the other created data files.
```
@sampleData = 
    SELECT * FROM 
        ( VALUES
        ((char?)'☺',      1,  "Noah☺",  100, (int?)10000, new DateTime(2012,05,31),  "cell:030-0074321,office:030-0076545"),
        ((char?)'数',     3,  "Liam数",  100, (int?)30000, new DateTime(2014,09,14),  "cell:(5) 555-3932"),
        ((char?)'\xFFFD', 4,  "\xFFFD", 100, (int?)35000, new DateTime(1999,02,27),  "cell:(171) 555-7788,office:(171) 555-6750, home:(425) 555-6238"),
        ((char?)'\n',     6,  "Emma",   200, (int?)8000,  new DateTime(2014,03,08),  (string)null),
        ((char?)',',      7,  "Jacob",  200, (int?)8000,  new DateTime(2014,09,02),  ""),
        ((char?)null,     14, "Jennie", 100, (int?)null,  new DateTime(2000,02,12),  "cell:(5) 555-3392,office:(5) 555-7293")
        ) AS T(character, EmpID, EmpName, DeptID, Salary, StartDate, PhoneNumbers);
        
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv.txt" USING Outputters.Tsv();
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv_outputHeader.txt" USING Outputters.Tsv(outputHeader: true);
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv_charFormat.txt" USING Outputters.Tsv(charFormat: "string");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv_dateTimeFormat.txt" USING Outputters.Tsv(dateTimeFormat: "D");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv_encoding.txt" USING Outputters.Tsv(encoding: Encoding.UTF32);
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv_escapeCharacter.txt" USING Outputters.Tsv(escapeCharacter: ':');
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv_nullEscape.txt" USING Outputters.Tsv(nullEscape: "null");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv_quoting.txt" USING Outputters.Tsv(quoting: false);
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv_rowDelimiter.txt" USING Outputters.Tsv(rowDelimiter: "\u0003");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv_charFormat_nullEscape_escapeCharacter.txt" USING Outputters.Tsv(charFormat: "string", nullEscape:"NULL", escapeCharacter:'#');
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Tsv_charFormat_encoding.txt" USING Outputters.Tsv(charFormat: "string", encoding:Encoding.Unicode);
```


### See Also  
* [Outputter Parameters (U-SQL)](outputter-parameters-u-sql.md)
* [Outputters.Text()](outputters-text.md)  
* [Outputters.Csv()](outputters-csv.md)  
* [U-SQL Built-in Outputters](u-sql-built-in-outputters.md)
* [Output Statement (U-SQL)](output-statement-u-sql.md)
* [Output to Files (U-SQL)](output-to-files-u-sql.md)



