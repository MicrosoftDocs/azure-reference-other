---
title: "Outputters.Text() | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-28"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a4efb3a8-b3ac-4334-a01b-f63461f3fa67
caps.latest.revision: 7
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Outputters.Text()
### Outputting textual row-oriented files    
The Text() outputter supports a variety of text file formats that all follow a row/column format. It provides a set of delimiters to identify the row and column boundaries and several other parameters to transform the rowset values into the text file.  See [Outputter Parameters (U-SQL)](../USQL/outputter-parameters-u-sql.md) for supported parameters and their defaults values.
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**Basic Syntax**   
The examples below show the basic syntax for each parameter using the Text() outputter.  Compare the output against the dataset as well as against the other created data files.
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
        
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text.txt" USING Outputters.Text();
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_outputHeader.txt" USING Outputters.Text(outputHeader: true);
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_charFormat.txt" USING Outputters.Text(charFormat: "string");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_delimiter.txt" USING Outputters.Text(delimiter: '|');
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_dateTimeFormat.txt" USING Outputters.Text(dateTimeFormat: "D");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_encoding.txt" USING Outputters.Text(encoding: Encoding.UTF32);
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_escapeCharacter.txt" USING Outputters.Text(escapeCharacter: ':');
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_nullEscape.txt" USING Outputters.Text(nullEscape: "null");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_quoting.txt" USING Outputters.Text(quoting: false);
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_rowDelimiter.txt" USING Outputters.Text(rowDelimiter: "\u0003");
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_charFormat_nullEscape_escapeCharacter.txt" USING Outputters.Text(charFormat: "string", nullEscape:"NULL", escapeCharacter:'#');
OUTPUT @sampleData TO "/Output/ReferenceGuide/BuiltIn/UDOs/Text_charFormat_encoding.txt" USING Outputters.Text(charFormat: "string", encoding:Encoding.Unicode);

```

### See Also
* [Outputter Parameters (U-SQL)](../USQL/outputter-parameters-u-sql.md)
* [Outputters.Csv()](../USQL/outputters-csv.md)
* [Outputters.Tsv()](../USQL/outputters-tsv.md)
* [U-SQL Built-in Outputters](../USQL/u-sql-built-in-outputters.md)
* [Output Statement (U-SQL)](../USQL/output-statement-u-sql.md)
* [Output to Files (U-SQL)](../USQL/output-to-files-u-sql.md)