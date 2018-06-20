---
title: "Outputter Parameters (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/28/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: be2ae409-5534-4bc0-b428-c8a5f96cbc09
caps.latest.revision: 4
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Outputter Parameters (U-SQL)
|Parameters|
|---|
|&emsp;&#9679;&emsp;[delimiter](#delimiter)<br />&emsp;&#9679;&emsp;[dateTimeFormat](#dateTimeFormat)<br />&emsp;&#9679;&emsp;[encoding](#encoding)<br />&emsp;&#9679;&emsp;[escapeCharacter](#escapeCharacter)<br />&emsp;&#9679;&emsp;[nullEscape](#nullEscape)<br />&emsp;&#9679;&emsp;[quoting](#quoting)<br />&emsp;&#9679;&emsp;[rowDelimiter](#rowDelimiter)<br />&emsp;&#9679;&emsp;[charFormat](#charFormat)<br />&emsp;&#9679;&emsp;[outputHeader](#outputHeader)<br /><p>                                                                                                                                                                                                      </p>|


The supported parameters and their defaults are:  
  
| Parameter name | Parameter type | Default value |  
|----------------|----------------|---------------|  
| <a name="delimiter"></a>`delimiter`     | `char`           | `','`           |  
  
This parameter specifies the column separator character that separates columns in the file. The default column separator is ',' (comma).  The delimiter parameter is not available for [Outputters.Csv()](outputters-csv.md) and [Outputters.Tsv()](outputters-tsv.md).
  
Note that per default, the built-in outputters are quoting string values. Thus any delimiter inside a value will be protected. If quoting is turned off, then the escaping needs to be turned on to protect the delimiter character inside a value.  
  
--------------------------------------------------
<br />
  
| Parameter name | Parameter type | Default value |  
|----------------|----------------|---------------|  
| <a name="dateTimeFormat"></a>`dateTimeFormat` | `string`         | `"O"`           |  
  
The *dateTimeFormat* parameter sets the dateTime format used when writing a datetime typed column with the built-in outputters. The argument value corresponds to the valid C# formats and defaults to "O" to provide round tripping of values.  
  
If an invalid argument value has been specified, an error will be raised.  
  
For more details of the C# datetime formats see [Standard Date and Time Format Strings](http://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx). 
 
--------------------------------------------------
 <br />
  
| Parameter name | Parameter type       | Default Value |  
|----------------|----------------------|---------------|  
| <a name="encoding"></a>`encoding`       | `System.Text.Encoding` | `Encoding.UTF8` |  
  
Per default, files are assumed to be stored in UTF-8 encoding. However, some files may need to be stored using a different encoding. Since C#’s string types are always UTF-16 encoded, we need to have the ability to convert a string type’s UTF-16 encoding to the encoding used to store it. The `encoding` parameter gives us the ability to specify the output file’s actual encoding.  
  
> [!NOTE]
> Some encodings (e.g., UTF-16) often use a Byte-Order Mark (BOM) in the beginning of a file to indicate its encoding. Unfortunately, the outputter cannot generate a BOM for the encoding, since the parallel processing of the outputter does not know which split is going to be the beginning of the output file. Since the outputter should not generate BOMs for every split, the built-in outputters are **not** adding BOMs.
  
The supported Encoding Properties are:  
  
| Encoding Property         | Description                                                                                                                                                                         |  
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| `Encoding.[ASCII]`        | The file is being encoded using the ASCII (7-bit) character set. Since ASCII is an all uppercase keyword, it needs to be quoted to not conflict with U-SQL’s reserved keyword rule. |  
| `Encoding.BigEndianUnicode` | The file is being encoded using the UTF-16 format that uses the big endian byte order.                                                                                              |  
| `Encoding.Unicode`          | The file is being encoded using the UTF-16 format using the little endian byte order.                                                                                               |  
| `Encoding.UTF7`             | The file is being encoded using the UTF-7 format.                                                                                                                                   |  
| **`Encoding.UTF8`**         | The file is being encoded using the UTF-8 format. This is the default. SAME ISSUE about doing UTF-8 possibly getting corrupted through native code doing some interesting hacks.    |  
| `Encoding.UTF32`            | The file is being encoded using the UTF-32 format using the little endian byte order.                                                                                               |  
  
> [!IMPORTANT]
> `System.Text.Encoding.Default` is not supported, since it would use the operating system’s current ANSI code page which cannot be controlled by the user. For more details see [System.Text.Encoding](http://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).
  
The supported Code Page Identifiers are:  
  
| Identifier | .NET Name | Description |
|-----------------|---------------|-------------|
| 1250 | Windows-1250 | Central European (Windows) |
| 1251 | Windows-1251 | Cyrillic (Windows) |
| 1252 | Windows-1252 | Western European (Windows) |
| 1253 | Windows-1253 | Greek (Windows) |
| 1254 | Windows-1254 | Turkish (Windows) |
| 1255 | Windows-1255 | Hebrew (Windows) |
| 1256 | Windows-1256 | Arabic (Windows) |
| 1257 | Windows-1257 | Baltic (Windows) |
| 1258 | Windows-1258 | Vietnamese (Windows) |

In order to specify a code page identifier, an encoding object has to be created using the C# [System.Text.Encoding.GetEncoding](https://msdn.microsoft.com/en-us/library/system.text.encoding.getencoding(v=vs.110).aspx) expression. It takes either one of the above encoding [numbers](https://msdn.microsoft.com/en-us/library/wzsz3bk3(v=vs.110).aspx) or the encoding [name](https://msdn.microsoft.com/en-us/library/t9a3kf7c(v=vs.110).aspx) (with upper- or lower-case `W`) as argument. In the case of the outputters, if the rowset contains a value that is not able to be represented by the specified encoding, then the character will be replaced by `?` (hex 3F).

If the output contains a code point that is invalid for the specified encoding, a runtime error during output will occur that will indicate the offending data value.  
  
--------------------------------------------------
<br />

  
| Parameter name  | Parameter type | Default value |  
|-----------------|----------------|---------------|  
| <a name="escapeCharacter"></a>`escapeCharacter` | `char?`          | *`null`*        |  
  
The `escapeCharacter` parameter – if not set to *null* – specifies the character that is used to escape itself and all delimiter values in the file.  
  
If it set to *null*, there is no escape character specified and the delimiters will be written as is.  
  
The `escapeCharacter` parameter will be applied regarding of whether quoting is enabled or not. It however will not be used to escape the quoting character. The quoting character will get escaped with double-quotes in alignment with the Excel CSV behaviour.  
  
Note that if quoting is turned off, then the escape character needs to be turned on to protect the delimiter characters inside a value.    

--------------------------------------------------
<br />
  
| Parameter name | Parameter type | Default value |  
|----------------|----------------|---------------|  
| <a name="nullEscape"></a>`nullEscape`     | `string`         | *`null`*        |  
  
The nullEscape parameter specifies the string in a column that is used to represent the null value. It will be applied regardless of whether quoting is enabled or not.  
  
If nullEscape is set to *null* (the default), no special null value is being used and a null value will be written as an empty field. Note that this loses the distinction between a string value that is a zero-length string and the null value.  
  
--------------------------------------------------
<br />
  
| Parameter name | Parameter type | Default value |  
|----------------|----------------|---------------|  
| <a name="quoting"></a>`quoting`        | `bool`           | `true`          |  
  
The quoting parameter – if set to true (default) – indicates that the outputter will use " (double-quote) as a column field quotation in order to protect column delimiters inside a value that is output. A double-quote inside a quoted field will to be escaped by doubling it as "".  
  
> [!TIP]
> If the data does not requiring quoting, specifying false for the quoting parameter will be resulting in a faster processing. However, if there is a chance that one of the delimiter characters appears inside a value and quoting is turned off, then the escape character should be set.  
  
--------------------------------------------------
<br />

  
| Parameter name | Parameter type        | Default value                        |  
|----------------|-----------------------|--------------------------------------|  
| <a name="rowDelimiter"></a>`rowDelimiter`   | `string (max length=1)` | `"\r\n"` (carriage return, linefeed) |  
  
This parameter specifies the row separator character sequence that separates rows in the file. If the rowDelimiter is set to null, the default value is being used which is a carriage return followed by linefeed.  
  
If the length of the provided rowDelimiter is more than one UCS-4 character, an error is raised**.**  
  
Note that unless the escapeCharacter parameter is set, the rowDelimiter character inside a value is being written without escaping and may lead to incorrect or failing extractions.  

--------------------------------------------------
<br />

| Parameter name | Parameter type       | Default Value |  
|----------------|----------------------|---------------|  
| <a name="charFormat"></a>`charFormat`       | `string` | `"uint16"` |  

The supported values are:

| Value         | Description                                                                                                                                                                                |  
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| 
|uint16 or null|This is the default value.  Serializes the `char` value as an integral number (taking all other serialization options into account) and parses the input as the integral character code number to the corresponding character or errors if the input is not an integral character code (or mapable `null` if extracting it as `char?`).|
|string|Serializes the `char` value in its Unicode string representation (taking all other serialization options including encoding into account) and parses the input as the character codepoint using the specified encoding.|

--------------------------------------------------
<br />

| Parameter name | Parameter type       | Default Value |  
|----------------|----------------------|---------------|  
| <a name="outputHeader"></a>`outputHeader`      | `bool` | `false` |  

The parameter specifies whether to output the column names of the rowset as the first header row.

## See Also
* [U-SQL Built-in Outputters](u-sql-built-in-outputters.md)
* [Outputters.Text()](outputters-text.md)
* [Output Statement (U-SQL)](output-statement-u-sql.md)
* [Output to Files (U-SQL)](output-to-files-u-sql.md)
