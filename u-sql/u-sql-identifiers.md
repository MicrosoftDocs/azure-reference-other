---
title: "U-SQL Identifiers | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c89a833d-1bdd-46d2-becf-bdbc618382c9
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# U-SQL Identifiers
U-SQL identifiers are used to identify the objects in the [U-SQL metadata context](securing-meta-data-objects.md). They can be composed of up to three parts parts: 

<table><th align="left">Syntax</th><tr><td><pre>
Identifier :=                                                                                            
     DB_Name '.' [Schema_Name] '.' Object_Name
|    Schema_Name '.' Object_Name
|    Object_Name.
</pre></td></tr></table>

The first part in a three part name identifies the database name, the second part refers to the schema name, or defaults to the database’s default schema named dbo if omitted and the third part identifies the object name such as a table or view. If the database name is left out, the current database context is implied, if the database name and the schema name is left out, then the current database and schema context is implied.  
  
Objects that are scoped to the database, such as a schema, assembly or data source may be referred to by a two-part name:  

<table><th align="left">Syntax</th><tr><td><pre>
DB_Object_Identifier :=                                                                                  
     [DB_Name '.'] Object_Name.
</pre></td></table>

Each name is either a quoted or unquoted U-SQL simple identifier:  
<table><th align="left">Syntax</th><tr><td><pre>
DB_Name :=                                                                                               
     Quoted_or_Unquoted_Identifier.<br />
Schema_Name := 
     Quoted_or_Unquoted_Identifier.<br />
Object_Name := 
     Quoted_or_Unquoted_Identifier.<br />
Quoted_or_Unquoted_Identifier := 
     Quoted_Identifier | Unquoted_Identifier.
</pre></td></table>
  
The unquoted identifiers in U-SQL are any valid names in accordance to the Unicode Standard Annex 31, except that underscore is allowed as an initial character (as is traditional in the C programming language), as long as they are not in conflict with reserved keywords. The grammar for an unquoted identifier is:  

<table><th align="left">Syntax</th><tr><td><pre>
Unquoted_Identifier :=                                                                                   
     Identifier_Start_Character {Identifier_Part_Character}.<br /> 
Identifier_Start_Character :=  
     <a href="#let_char">letter_character</a>  
|    '_'. // the underscore character U+005F<br />  
Identifier_Part_Character :=  
     <a href="#let_char">letter_character</a>   
|    <a href="#dec_char">decimal_digit_character</a>   
|    <a href="#con_char">connecting_character</a>  
|    <a href="#com_char">combining_character</a>  
|    <a href="#form_char">formatting_character</a>.
</pre></td></table>

* <a name="let_char"></a>**`letter_character`**  
Any Unicode 5.0 character of the classes Lu, Ll, Lt, Lm, Lo, or Nl.  
  
* <a name="com_char"></a>**`combining_character`**   
Any Unicode 5.0 character of classes Mn or Mc.  
  
* <a name="dec_char"></a>**`decimal_digit_character`**  
Any Unicode 5.0 character of the class Nd.  
  
* <a name="con_char"></a>**`connecting_character`**  
Any Unicode 5.0 character of the class Pc.  
  
* <a name="form_char"></a>**`formatting_character`**  
Any Unicode 5.0 character of the class Cf.  
  
The list of reserved keywords is comprised of:    
1.  Any all-uppercase keyword of length greater than 2. Note that if the keyword contains a non-letter character such as an _, it is no longer considered a reserved a keyword.    
2.  Any C# version 5.0 reserved keyword.    
3.  Any of the following keywords: AS, BY, DO, IF, IN, IS, ON, OR, TO.  
  
In order to allow arbitrary identifiers that are either keywords or contain any Unicode code point, U-SQL allows to quote identifiers using '[' and ']', e.g., [MYTABLE]. Note that the quoting characters are not part of the name and if the closing quote appear inside the name it needs to be escaped by being doubled:  

<table><th align="left">Syntax</th><tr><td><pre>
Quoted_Identifier :=                                                                                     
     '[' (any_unicode_cp_less_quotes | Escaped_Quote)   
        {any_unicode_cp_less_quotes | Escaped_Quote} ']'.<br />
Escaped_Quote := 
     ']]'.
</pre></td></table>
  
Furthermore, any U-SQL identifier, whether quoted or unquoted has to following the following rules:
1.  A U-SQL identifier is **case-sensitive**.    
2.  Maximal length of a quoted or unquoted identifier is 128 characters (although some named objects may have further restrictions).    
3.  Unicode escape sequences are NOT supported in identifiers.  
  
### Examples    
A.  The following script uses quoted identifiers to create some objects with uncommon names:
```sql  
DROP DATABASE IF EXISTS [^];  
CREATE DATABASE [^];  
USE DATABASE [^];  
CREATE SCHEMA []]];  
USE SCHEMA []]];  
CREATE TABLE [*] (  
    []]] int, INDEX idx CLUSTERED ([]]]) PARTITIONED BY ROUND ROBIN INTO 5  
);
```

B.  The following script reads from the generated table and outputs the result:
```  
@r = 
    SELECT * FROM [^].[]]].[*];  
    OUTPUT @r TO "/output/test.csv" USING Outputters.Csv();
```

### See Also
* [U-SQL Concepts](u-sql-concepts.md)
* [U-SQL Language Reference](u-sql-language-reference.md)
* [C# Identifiers](csharp-identifiers.md)



