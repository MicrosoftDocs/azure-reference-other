---
title: "RTRIM (Azure Stream Analytics)"
description: "Removes the space character from the end of a string."
applies_to:
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# RTRIM (Azure Stream Analytics)

Removes any white-space characters from the end of a string - from the right : RIGHT TRIM.

> [!NOTE]
>  This behavior differs from the [RTRIM](/sql/t-sql/functions/rtrim-transact-sql) function of T-SQL, that only removes the space character `(char(32))`

## Syntax

```SQL
RTRIM ( string_expression )
```

## Arguments

**string_expression**

Is the string expression to be evaluated. string_expression can be a constant or column of type nvarchar(max).

## Return Types

nvarchar(max)

## Remarks

White-space characters are the following Unicode characters:

- Members of the [UnicodeCategory.SpaceSeparator](/dotnet/api/system.globalization.unicodecategory#System_Globalization_UnicodeCategory_SpaceSeparator) category, which includes the characters SPACE (U+0020), NO-BREAK SPACE (U+00A0), OGHAM SPACE MARK (U+1680), EN QUAD (U+2000), EM QUAD (U+2001), EN SPACE (U+2002), EM SPACE (U+2003), THREE-PER-EM SPACE (U+2004), FOUR-PER-EM SPACE (U+2005), SIX-PER-EM SPACE (U+2006), FIGURE SPACE (U+2007), PUNCTUATION SPACE (U+2008), THIN SPACE (U+2009), HAIR SPACE (U+200A), NARROW NO-BREAK SPACE (U+202F), MEDIUM MATHEMATICAL SPACE (U+205F), and IDEOGRAPHIC SPACE (U+3000).
- Members of the [UnicodeCategory.LineSeparator](/dotnet/api/system.globalization.unicodecategory#System_Globalization_UnicodeCategory_LineSeparator) category, which consists solely of the LINE SEPARATOR character (U+2028).
- Members of the [UnicodeCategory.ParagraphSeparator](/dotnet/api/system.globalization.unicodecategory#System_Globalization_UnicodeCategory_ParagraphSeparator) category, which consists solely of the PARAGRAPH SEPARATOR character (U+2029).
- The characters CHARACTER TABULATION (U+0009), LINE FEED (U+000A), LINE TABULATION (U+000B), FORM FEED (U+000C), CARRIAGE RETURN (U+000D), and NEXT LINE (U+0085).

## Examples

```SQL

SELECT
  RTRIM( 'Right test    ' ) AS trimmedTest
FROM Input

```

Returns:

|trimmedTest|
|-|
|Right test|

## See Also

- [TRIM](trim-azure-stream-analytics.md)
- [LTRIM](ltrim-azure-stream-analytics.md)
- [REPLACE](replace-azure-stream-analytics.md)
