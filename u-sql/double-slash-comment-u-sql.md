---
title: "Double Slash Comment (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 7f3babf4-4ef1-4b6a-aead-40d99fb7b2de
caps.latest.revision: 2
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Double Slash Comment (U-SQL)
Indicates user-provided text. Comments can be inserted on a separate line, nested at the end of a U-SQL command line, or within a U-SQL statement. The query processor does not evaluate the comment.

<table><th align="left">Syntax</th><tr><td><pre>
Double_Slash_Comment :=                                                                             
    '//' <a href="#comment1">text_of_comment</a>.
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
-   <a name="comment1"></a>**`text_of_comment`**  
Is the character string that contains the text of the comment.

Use two slashes (`//`) for single-line or nested comments. Comments inserted with `//` are terminated by the newline character. There is no maximum length for comments. 

### Example    
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following example uses the `//` commenting characters.
```
// simple rowset variable
@someBooks = 
    SELECT * FROM 
        ( VALUES
        ("The Book Thief", "Markus Zusak", "2005"),
        ("The Girl with the Dragon Tattoo", "Stieg Larsson", "2005"),
        ("The Silver Linings Playbook", "Matthew Quick", "2008"),
        ("Sarah's Key", "Tatiana de Rosnay", "2006")
        ) AS T(Books, Author, [Publication Year]);

// return books from 2006
@result =
    SELECT *
    FROM @someBooks // this is a nested comment
    WHERE [Publication Year] == "2006";
   
OUTPUT @result
TO "/Output/ReferenceGuide/LanguageElements/Comments/exampleA.txt"
USING Outputters.Csv();
```

### See Also
* [Slash Star Comment (U-SQL)](slash-star-comment-u-sql.md)
