---
title: "Textual Types and Literals | Microsoft Docs"
ms.custom: ""
ms.date: "07/28/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 15eecf2d-2801-4857-bc9f-936b9df7c8eb
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Textual Types and Literals
U-SQL’s built-in textual types are:
```
char       char?  
string   
```
The grammar rules use `Textual_Type` to refer to one of these types.  
  
String and character literals follow the C# string and character literals. In particular, this means that character literals are demarked by single quotes such as `'c'`, while string literals are enclosed with double quotes, e.g., `"string"`. Note the difference here from ANSI SQL where strings and characters both are using single quotes and the double quotes are being used to define quoted identifiers!  
  
U-SQL textual types currently do not support culturally aware sort orders and are always ordered according to their Unicode UTF-8 encoding byte order.  
  
U-SQL supports both the regular C# string literals and the verbatim C# string literals.  
  
The regular C# string literals require characters such as the double quote, backslash or carriage return and linefeed to be escape as in the examples below:  
```
"\"Hello\" I said"  
"a\\b\\c"  
"a\r\nb\r\nc"  
```
Verbatim C# string literals simplify the handling of such characters by prepending the `@` character in front of the starting double quote of the string. In this case, double quotes are being doubled for escaping but all other values do not have to be escaped. The above regular strings can be written as verbatim strings as follows:  
```
@"""Hello"" I said"  
@"a\b\c"  
@"a  
b  
c"  
```

## Limits
The maximal size of a column of type string is 128kB in U-SQL (based on the byte count of the string value represented in UTF-8 encoding). 

### See Also
* [Simple Built-In U-SQL Types](simple-built-in-u-sql-types.md)
* [Data Types and Literals (U-SQL)](data-types-and-literals-u-sql.md)  
