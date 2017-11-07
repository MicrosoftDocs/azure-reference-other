---
title: "Extractor Parameters (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-28"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 630ca300-e422-4b5e-99bd-d23197234535
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Extractor Parameters (U-SQL)
|Parameters|
|---|
|&emsp;&#9679;&emsp;[delimiter](#delimiter)<br />&emsp;&#9679;&emsp;[encoding](#encoding)<br />&emsp;&#9679;&emsp;[escapeCharacter](#escapeCharacter)<br />&emsp;&#9679;&emsp;[nullEscape](#nullEscape)<br />&emsp;&#9679;&emsp;[quoting](#quoting)<br />&emsp;&#9679;&emsp;[rowDelimiter](#rowDelimiter)<br />&emsp;&#9679;&emsp;[silent](#silent)<br />&emsp;&#9679;&emsp;[skipFirstNRows](#skipFirstNRows)<br />&emsp;&#9679;&emsp;[charFormat](#charFormat)<br /><p>                                                                                                                                                                                                      </p>|  
  
The supported parameters and their defaults are:  
  
| Parameter name | Parameter type | Default value |  
|----------------|----------------|---------------|  
| <a name="delimiter"></a>`delimiter`      | `char`           | `','` (comma)   |  
  
This parameter specifies the column separator character that separates columns in the file. The default column separator for is a comma (','). It can be any valid Unicode character including those that are represented with multi-byte encodings in any of the Unicode-Transfer-Formats (i.e. UTF-*).  The delimiter parameter is not available for [Extractors.Csv()](../USQL/extractors-csv.md) and [Extractors.Tsv()](../USQL/extractors-tsv.md).
  
> [!IMPORTANT]
> If the `quoting` parameter is set to `false`, the delimiter character inside a quoted string is being used as a column separator and may lead to incorrect or failing extractions.

--------------------------------------------------
  
  
| Parameter name | Parameter type       | Default Value |  
|----------------|----------------------|---------------|  
| <a name="encoding"></a>`encoding`       | `System.Text.Encoding` | `Encoding.UTF8` |  
  
Per default, files are assumed to be stored in UTF-8 encoding. However, some files may be stored using a different encoding. The `encoding` parameter provides the option to specify the file’s actual encoding and also translate non-UTF-8 encoded files.  
  
The supported encodings are:  
  
| Encoding Property         | Description                                                                                                                                                                                |  
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| `Encoding.[ASCII]`        | Assumes that the file is encoded using the ASCII (7-bit) character set. Since ASCII is an all uppercase keyword, it needs to be quoted to not conflict with U-SQL’s reserved keyword rule. |  
| `Encoding.BigEndianUnicode` | Assumes that the file is encoded using the UTF-16 format that uses the big endian byte order.                                                                                              |  
| `Encoding.Unicode`          | Assumes that the file is encoded using the UTF-16 format using the little endian byte order.                                                                                               |  
| `Encoding.UTF7`             | Assumes that the file is encoded using the UTF-7 format.                                                                                                                                   |  
| **`Encoding.UTF8`**         | Assumes that the file is encoded using the UTF-8 format. This is the default.                                                                                                              |  
| `Encoding.UTF32`            | Assumes that the file is encoded using the UTF-32 format using the little endian byte order.                                                                                               |  
  
> [!IMPORTANT]
> System.Text.Encoding.Default is not supported, since it would use the processing node’s operating system’s current ANSI code page that cannot be controlled by the user and is not the same as the default of the extractor. For more details see [System.Text.Encoding](http://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).
  
If the file contains a code point that is invalid for the specified encoding, a runtime error during extraction will occur regardless of the `silent` parameter setting that will indicate the offending data value.  
  
--------------------------------------------------

  
| Parameter name  | Parameter type | Default value |  
|-----------------|----------------|---------------|  
| <a name="escapeCharacter"></a>`escapeCharacter` | `char?`          | *`null`*        |  
  
The `escapeCharacter` parameter – if not set to *null* – specifies the character in the file that is used to escape itself and all delimiter values in the file.  
  
If the escape character is followed by a value other than itself or any of the delimiter values, the escape character is dropped when reading the value.   
  
[//]: # '**TODO: Check if this is the implemented behavior.**'  
  
If it set to *null*, there is no escape character specified.  
  
The `escapeCharacter` parameter will be applied regarding of whether quoting is enabled or not. It however will not be used to escape the quoting character. The quoting character will get escaped with double-quotes in alignment with the Excel CSV behaviour.  

--------------------------------------------------
  
  
| Parameter name | Parameter type | Default value |  
|----------------|----------------|---------------|  
| <a name="nullEscape"></a>`nullEscape`     | `string`         | *`null`*        |  
  
The `nullEscape` parameter specifies the string in a column that is used to represent the null value. It will be applied regardless of whether quoting is enabled or not.  
  
If the textual input of the field is not exactly equal the `nullEscape` string sequence, then the string sequence will not be interpreted as a `null` value and it will be treated like any other input string.  
  
If the textual input is the zero-length string and the target type is a nullable non-string type, then it will also be interpreted as NULL.   
  
[//]: # '**TODO: Check**'  
  
If `nullEscape` is set to *null* (the default), no special null value is being interpreted. A zero-length textual representation (before removing quotes) will be interpreted as a zero-length string for target type string, and null for all non-string nullable types. A zero-length string with quotes will be a zero-length string for both type categories.   
  
[//]: # '**\[TODO: Check what is implemented now\]**'  
  
If the target type of the extraction is not a nullable type and the value is interpreted as null, an `E_RUNTIME_USER_EXTRACT_COLUMN_CONVERSION_NULL_ERROR` error will be raised.  
  
  
The following table gives some examples on how different inputs are being interpreted based on the target types for the fields (using int? as the representative type for nullable non-string types) and the value for null_escape (ERR indicates a runtime conversion error) using the row value  
  
1,,"",\N,#NULL#,"Some \N fun"  
  
| nullEscape | String                                      | int?                     |  
|------------|---------------------------------------------|--------------------------|  
| "\N"      | "1","","",null,"#NULL#","Some \N fun"    | 1,null,ERR,null,ERR, ERR |  
| ""         | "1","",null,"\N","#NULL#","Some \N fun" | 1,null,null,ERR,ERR,ERR  |  
| null       | "1",null,"","\N","#NULL#","Some \N fun" | 1,null,ERR,ERR,ERR,ERR   |  
| "#NULL#"   | "1","","","\N","#NULL#","Some \N fun"   | 1,null,ERR,ERR,null,ERR  |  
  
---  
  
| Parameter name | Parameter type | Default value |  
|----------------|----------------|---------------|  
| <a name="quoting"></a>`quoting`        | `bool`           | `true`          |  
  
The `quoting` parameter if set to `true` indicates that the extractor should consider " (double-quote) as a column field quotation which inhibits the interpretation of the column delimiters inside the quoted field. A double-quote inside a quoted field needs to be escaped by doubling it as "" in the file.  
  
> [!IMPORTANT]
> Due to the parallel processing and splitting of input files, quoting cannot inhibit the interpretation of the row delimiters. Thus for example an input Excel CSV file that contains an unescaped carriage return or linefeed will cause the extraction to fail even if these delimiters are quoted. They will have to be escaped. Currently no other quoting characters are supported.  
  
> [!TIP]
> If the input data does not use quoting, specifying false for the quoting parameter will be resulting in a faster extraction.  

--------------------------------------------------
  
  
| Parameter name | Parameter type        | Default values                       |  
|----------------|-----------------------|--------------------------------------|  
| <a name="rowDelimiter"></a>`rowDelimiter`   | `string (max length=1)` | `"\r\n" (carriage return, linefeed)`<br />`"\r" (carriage return)`<br />`"\n" (linefeed)` |  

  
This parameter specifies the row separator character sequence that separates rows in the file. If the `rowDelimiter` is set to null, the default values are being used which are carriage return followed by linefeed, or carriage return or linefeed.  
  
If the length of the `rowDelimiter` is more than one UCS-4 characters, an error is raised**.**  
  
The comparison of the `rowDelimiter` will be done using a byte-wise comparison after applying the encoding got applied.  
  
Note that the `rowDelimiter` character inside a quoted string will not be escaped and will be used as a row separator which will lead to incorrect or failing extractions.  
 
--------------------------------------------------
 
  
| Parameter name | Parameter type | Default Value |  
|----------------|----------------|---------------|  
| <a name="silent"></a>`silent`        | `bool`           | `false`         |  
  
This parameter tells the extractor to ignore and skip rows that have a different number of columns than the requested number of columns. It also replaces corrupt column data with null when the datatype is nullable (for example, it replaces "int?" with null when there is a non-digit character in the column). If the column type is not nullable, an error is raised.  
  
Rows are checked for the correct number of columns first. For example, if there is corrupt data in a column with the wrong number of rows, the extractor skips the row. There is no conversion. If the row has the correct number of columns, however, the extractor doesn't skip it. The conversion occurs (assuming that the column's type is nullable).  
  
> [!IMPORTANT] 
> `silent` does **not** ignore encoding errors since such errors often indicate that the file encoding and the specified encoding are not compatible and thus could lead to more severe data corruption.  

--------------------------------------------------

| Parameter name | Parameter type       | Default Value |  
|----------------|----------------------|---------------|  
| <a name="skipFirstNRows"></a>`skipFirstNRows`       | `Int` | `0` |  

The parameter specifies the number of rows to skip.  The rows being skipped do not need to conform to the column schema in either type or count of columns.  Note, you can only skip rows that are in the first segment of a file; otherwise, an error will be raised.

--------------------------------------------------

| Parameter name | Parameter type       | Default Value |  
|----------------|----------------------|---------------|  
| <a name="charFormat"></a>`charFormat`       | `string` | `"uint16"` |  

The supported values are:

| Value         | Description                                                                                                                                                                                |  
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| 
|uint16 or null|This is the default value.  Serializes the `char` value as an integral number (taking all other serialization options into account) and parses the input as the integral character code number to the corresponding character or errors if the input is not an integral character code (or mapable `null` if extracting it as `char?`).|
|string|Serializes the `char` value in its Unicode string representation (taking all other serialization options including encoding into account) and parses the input as the character codepoint using the specified encoding.|

### See Also 
* [Built-in U-SQL UDOs](../USQL/built-in-u-sql-udos.md)
* [EXTRACT Expression (U-SQL)](../USQL/extract-expression-u-sql.md)
* [Input Files (U-SQL)](../USQL/input-files-u-sql.md)
