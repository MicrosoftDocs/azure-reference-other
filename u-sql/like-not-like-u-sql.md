---
title: "LIKE, NOT LIKE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bd05f3f4-5c23-4372-9414-aabd747b7952
caps.latest.revision: 7
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# LIKE, NOT LIKE (U-SQL)
U-SQL provides the `LIKE` and `NOT LIKE` comparison operators that are [familiar from T-SQL](https://msdn.microsoft.com/library/ms179859.aspx) that checks if a [string](textual-types-and-literals.md) value matches or does not match a simple pattern. The pattern can include regular characters and wildcard characters. During pattern matching, regular characters must exactly match the characters specified in the character [string](textual-types-and-literals.md). However, wildcard characters can be matched with arbitrary fragments of the character [string](textual-types-and-literals.md). Note that the comparison is done with culture invariant [string](textual-types-and-literals.md) comparison using UTF-8 byte-level comparison. 

<table><th align="left">Syntax</th><tr><td><pre>
LIKE_Expression :=                                                                                       
     <a href="#str_exp">string_expression</a> ['<a href="not-u-sql.md">NOT</a>'] 'LIKE' <a href="#patrn">Pattern</a>   
     [<a href="#esc_c_exp">'ESCAPE' char_expression</a>].<br />
Pattern := 
     <a href="#str_exp">string_expression</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
- <a name="str_exp"></a>**`string_expression`**  
  is the expression that creates the string value to be tested.
    
- <a name="patrn"></a>**`Pattern`**    
  is a string expression that provides the pattern to test against. The pattern in a LIKE can include the following valid wildcard characters.   
   
    | **Wildcard character** | **Description** | **Example** |  
    |---|---|---|  
    | % | Any string of zero or more characters. | `WHERE title LIKE '%computer%'` finds all rows with the word 'computer' anywhere in the title. |  
    | _ (underscore) | Any single character. | `WHERE fname LIKE '_ean'` finds all rows with four-letter first names that end with ean (Dean, Sean, and so on). |  
    | [ ] | Any single character within the specified range ([a-f]) or set ([abcdef]). | `WHERE lname LIKE '[C-P]arsen'` finds all rows with last names ending with arsen and starting with any single character between C and P, for example Carsen, Larsen, Karsen, and so on. In range searches, the characters included in the range are determined by the culture invariant sort order using UTF-8 byte ordering. |  
    | [^] | Any single character not within the specified range ([^a-f]) or set          | `WHERE lname LIKE 'de[^l]%'` finds all rows with last names starting with de and where the following letter is not l. |    
 
- <a name="esc_c_exp"></a>**`ESCAPE char_expression`**   
specifies optionally a non-null value of type char that can be used to escape any of the wildcard characters. It is put in front of a wildcard character to indicate that the wildcard should be interpreted as a regular character and not as a wildcard.   
  
### Return Type    
[bool](other-simple-built-in-types-and-literals.md) 
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

```sql
@data  = 
    SELECT * FROM 
        (VALUES  
        ("Carsen",      "Engineer"),
        ("Larsen",      "engineer"),
        ("Karsen",      "some%value"),
        ("Barbariol",   "somevalue"),
        ("Barber",      "some_value"),
        ("Olivia",      "someXvalue")
        ) AS T(col1, col2);

// Change "LIKE" to "NOT LIKE" for NOT LIKE examples

@result =
    SELECT * FROM @data
    WHERE col1 LIKE "_arsen";

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Like1.txt" USING Outputters.Tsv();


@result =
    SELECT * FROM @data
    WHERE col1 LIKE "[C-K]arsen";

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Like2.txt" USING Outputters.Tsv();


@result =
    SELECT * FROM @data
    WHERE col1 LIKE "Barb%";

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Like3.txt" USING Outputters.Tsv();


@result =
    SELECT * FROM @data
    WHERE col2 LIKE "Engineer";

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Like4.txt" USING Outputters.Tsv();


@result =
    SELECT * FROM @data
    WHERE col2 LIKE "[eE]ngineer";

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Like5.txt" USING Outputters.Tsv();


@result =
    SELECT * FROM @data
    WHERE col2 LIKE "some%value";

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Like6.txt" USING Outputters.Tsv();


@result =
    SELECT * FROM @data
    WHERE col2 LIKE "some|%value" ESCAPE '|';

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Like7.txt" USING Outputters.Tsv();


@result =
    SELECT * FROM @data
    WHERE col2 LIKE "some_value";

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Like8.txt" USING Outputters.Tsv();


@result =
    SELECT * FROM @data
    WHERE col2 LIKE "some$_value" ESCAPE '$';

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Like9.txt" USING Outputters.Tsv();
```

### See Also 
* [Comparison Operators (U-SQL)](comparison-operators-u-sql.md)  
* [BETWEEN (U-SQL)](between-u-sql.md)  
* [IN, NOT IN (U-SQL)](in-not-in-u-sql.md)  
* [C# Operators](https://msdn.microsoft.com/library/6a71f45d.aspx)  
