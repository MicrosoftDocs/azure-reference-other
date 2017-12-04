---
title: "Outputters.Csv() | Microsoft Docs"
ms.custom: ""
ms.date: "03/28/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e439d202-1b1d-4cd9-b2b9-71c275cc2ae3
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Outputters.Csv()
### Outputting CSV Files    
The Csv() outputter disallows the `delimiter` parameter and defaults the field delimiter to ',' (comma). All other parameters are the same.  See [Outputter Parameters (U-SQL)](outputter-parameters-u-sql.md) for supported parameters and their defaults values.  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Syntax**   
The examples below show the basic syntax for each parameter using the Csv() outputter.  Compare the output against the dataset as well as against the other created data files.
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
        
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv.csv" USING Outputters.Csv();
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv_outputHeader.csv" USING Outputters.Csv(outputHeader: true);
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv_charFormat.csv" USING Outputters.Csv(charFormat: "string");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv_dateTimeFormat.csv" USING Outputters.Csv(dateTimeFormat: "D");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv_encoding.csv" USING Outputters.Csv(encoding: Encoding.UTF32);
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv_escapeCharacter.csv" USING Outputters.Csv(escapeCharacter: ':');
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv_nullEscape.csv" USING Outputters.Csv(nullEscape: "null");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv_quoting.csv" USING Outputters.Csv(quoting: false);
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv_rowDelimiter.csv" USING Outputters.Csv(rowDelimiter: "\u0003");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv_charFormat_nullEscape_escapeCharacter.csv" USING Outputters.Csv(charFormat: "string", nullEscape:"NULL", escapeCharacter:'#');
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Csv_charFormat_encoding.csv" USING Outputters.Csv(charFormat: "string", encoding:Encoding.Unicode);

```

### See Also
* [Outputter Parameters (U-SQL)](outputter-parameters-u-sql.md)
* [Outputters.Text()](outputters-text.md)  
* [Outputters.Tsv()](outputters-tsv.md)  
* [U-SQL Built-in Outputters](u-sql-built-in-outputters.md)
* [Output Statement (U-SQL)](output-statement-u-sql.md)
* [Output to Files (U-SQL)](output-to-files-u-sql.md)