---
title: "Slash Star Comment (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e804b965-3b44-4517-85b9-ee5c9de855d1
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Slash Star Comment (U-SQL)
Indicates user-provided text. The text between `/*` and `*/` is not evaluated by the query processor.

<table><th align="left">Syntax</th><tr><td><pre>
Slash_Star_Comment :=                                                                                    
     '/*' <a href="#comment1">text_of_comment</a> '*/'.
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
-   <a name="comment1"></a>**`text_of_comment`**  
Is the text of the comment. This is one or more character strings.

A "comment" is a sequence of characters beginning with a forward slash/asterisk combination (`/*`) that is treated as a single white-space character by the compiler and is otherwise ignored. A comment can include any combination of characters from the representable character set, including newline characters, but excluding the "end comment" delimiter (`*/`). Comments can occupy more than one line but cannot be nested.

### Example    
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following example uses the `/* */` commenting characters.
```sql
/*
This is a comment.
Another comment on a separate line.
*/
@someBooks = 
    SELECT * FROM 
        ( VALUES
        ("The Book Thief", "Markus Zusak", "2005"),
        ("The Girl with the Dragon Tattoo", "Stieg Larsson", "2005"),
        ("The Silver Linings Playbook", "Matthew Quick", "2008"),
        ("Sarah's Key", "Tatiana de Rosnay", "2006")
        ) AS T(Books, Author, [Publication Year]);

@result =
    SELECT *
    FROM @someBooks /* Comments can appear on the same line as a code */
    WHERE [Publication Year] == "2006";
   
OUTPUT @result
TO "/Output/ReferenceGuide/LanguageElements/Comments/exampleB.txt"
USING Outputters.Csv();
```

### See Also
* [Double Slash Comment (U-SQL)](double-slash-comment-u-sql.md)
