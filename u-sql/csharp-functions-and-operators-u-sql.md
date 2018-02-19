---
title: "C# Functions and Operators (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/31/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 14716fd9-fcdb-4294-b92e-cbc105924f4e
caps.latest.revision: 31
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# C# Functions and Operators (U-SQL)
U-SQL’s core reliance on C#-for its [U-SQL type](data-types-and-literals-u-sql.md) system and [U-SQL’s expression](expressions-u-sql.md) language provides the query writer access to the wealth of the C# and CLR libraries of classes, methods, functions, operators and types. It would go beyond the scope of this documentation to repeat all C# functions and operators, so it will limit itself to a few examples of frequently used operators and functions and shows which system assemblies are already included. The section [REFERENCE SYSTEM ASSEMBLY](reference-system-assembly-u-sql.md)   provides a list of all preloaded system assemblies and explains how to add additional system assemblies.  

All [C# operators](https://msdn.microsoft.com/library/6a71f45d.aspx) except for the assignment operators (=, += etc) are valid in U-SQL. In particular all comparison operators such as `==`, `!=`, `<`, `>` the ternary comparison `cond ? true-expression : false-expression`, the null coalesce operator `??` are supported. Even lambda expressions using `=>` can be used inside U-SQL expressions.  


<table><th align="left"><a href="#examples">Examples in this Topic</a></th>
<tr><td>
<a href="#sharpOps">C# Operators</a>  
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;     &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; <br />                                                                                                           
&emsp;&#9679;&emsp;<a href="#condl">?: (Conditional)</a><br />
&emsp;&#9679;&emsp;<a href="#nullCoal">?? (Null-Coalescing)</a><br />
&emsp;&#9679;&emsp;<a href="#lamda">=> (Lamda)</a>
</td></tr> 
<tr><td>
<a href="#stringMethods">String Methods</a><br />
&emsp;&#9679;&emsp;<a href="#Compare">Compare</a><br />
&emsp;&#9679;&emsp;<a href="#CompareOrdinal">CompareOrdinal</a><br />
&emsp;&#9679;&emsp;<a href="#CompareTo">CompareTo</a><br />
&emsp;&#9679;&emsp;<a href="#Concat">Concat</a><br />
&emsp;&#9679;&emsp;<a href="#Contains">Contains</a><br />
&emsp;&#9679;&emsp;<a href="#EndsWith">EndsWith</a><br />
&emsp;&#9679;&emsp;<a href="#Equals">Equals</a><br />
&emsp;&#9679;&emsp;<a href="#Format">Format</a><br />
&emsp;&#9679;&emsp;<a href="#GetHashCode">GetHashCode</a><br />
&emsp;&#9679;&emsp;<a href="#GetTypeCode">GetTypeCode</a><br />
&emsp;&#9679;&emsp;<a href="#IndexOf">IndexOf</a><br />
&emsp;&#9679;&emsp;<a href="#Insert">Insert</a><br />
&emsp;&#9679;&emsp;<a href="#IsNullOrEmpty">IsNullOrEmpty</a><br />
&emsp;&#9679;&emsp;<a href="#IsNullOrWhiteSpace">IsNullOrWhiteSpace</a><br />
&emsp;&#9679;&emsp;<a href="#Join">Join</a><br />
&emsp;&#9679;&emsp;<a href="#LastIndexOf">LastIndexOf</a><br />
&emsp;&#9679;&emsp;<a href="#PadLeft">PadLeft</a><br />
&emsp;&#9679;&emsp;<a href="#PadRight">PadRight</a><br />
&emsp;&#9679;&emsp;<a href="#Remove">Remove</a><br />
&emsp;&#9679;&emsp;<a href="#Replace">Replace</a><br />
&emsp;&#9679;&emsp;<a href="#Split">Split</a><br />
&emsp;&#9679;&emsp;<a href="#StartsWith">StartsWith</a><br />
&emsp;&#9679;&emsp;<a href="#Substring">Substring</a><br />
&emsp;&#9679;&emsp;<a href="#ToCharArray">ToCharArray</a><br />
&emsp;&#9679;&emsp;<a href="#ToLower">ToLower</a><br />
&emsp;&#9679;&emsp;<a href="#ToUpper">ToUpper</a><br />
&emsp;&#9679;&emsp;<a href="#Trim">Trim</a>
</td></tr> 
<tr><td>
<a href="#stringProperties">String Properties</a><br />
&emsp;&#9679;&emsp;<a href="#Length">Length</a>
</td></tr> 
<tr><td>
<a href="#ObjectMethods">Object Methods</a><br />
&emsp;&#9679;&emsp;<a href="#GetType">GetType</a><br />
</td></tr> 
<tr><td>
<a href="#DateTime">Date &amp; Time</a><br />
&emsp;&#9679;&emsp;<a href="#stringFormats">DateTime to String</a><br />
&emsp;&#9679;&emsp;<a href="#stringConversion">String to DateTime</a><br />
&emsp;&#9679;&emsp;<a href="#properties">Properties</a><br />
&emsp;&#9679;&emsp;<a href="#someMethods">Some Methods</a><br />
&emsp;&#9679;&emsp;<a href="#comparingDateTimes">Comparing DateTimes</a><br />
&emsp;&#9679;&emsp;<a href="#someOperators">Some Operators</a><br />
&emsp;&#9679;&emsp;<a href="#dateDiff">Date Diff</a><br />
&emsp;&#9679;&emsp;<a href="#addTimeSpan">Add TimeSpan</a><br />
&emsp;&#9679;&emsp;<a href="#TimeSpan">TimeSpan Plus TimeSpan</a>
</td></tr> 
<tr><td>
<a href="#Math">Math Methods</a><br />
&emsp;&#9679;&emsp;<a href="#abs">Abs</a><br />
&emsp;&#9679;&emsp;<a href="#bigMul">BigMul</a><br />
&emsp;&#9679;&emsp;<a href="#ceiling">Ceiling</a><br />
&emsp;&#9679;&emsp;<a href="#floor">Floor</a><br />
&emsp;&#9679;&emsp;<a href="#max">Max</a><br />
&emsp;&#9679;&emsp;<a href="#min">Min</a><br />
&emsp;&#9679;&emsp;<a href="#pow">Pow</a><br />
&emsp;&#9679;&emsp;<a href="extending-u-sql-expressions-with-user-code.md#usingRound">Round</a><br />
&emsp;&#9679;&emsp;<a href="#sign">Sign</a><br />
&emsp;&#9679;&emsp;<a href="#sqrt">Sqrt</a><br />
&emsp;&#9679;&emsp;<a href="#truncate">Truncate</a>
</td></tr> 
<tr><td>
<a href="#Random">Random Methods</a><br />
&emsp;&#9679;&emsp;<a href="#randomNext">Next</a>
</td></tr> 
</table>


### <a name="examples">Examples</a>
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.


### <a name="sharpOps">C# Operators</a>

<a name="condl"></a>**?: (Conditional)**  
The conditional operator (`?:`) returns one of two values depending on the value of a Boolean expression.  The condition must evaluate to true or false. If condition is true, first_expression is evaluated and becomes the result. If condition is false, second_expression is evaluated and becomes the result. Only one of the two expressions is evaluated.  Either the type of first_expression and second_expression must be the same, or an implicit conversion must exist from one type to the other.  The following example returns the string "Overpaid" if `Salary` exceeds 10000.
```sql
@employees = 
    SELECT * FROM 
        ( VALUES
        (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
        (11, "Ethan", 400, (int?)9000,  new DateTime(2015,08,22)),
        (12, "David", 800, (int?)100,   new DateTime(2016,11,01)),
        (13, "Andrew", 100, (int?)null, new DateTime(1995,07,16))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);

@result =
    SELECT EmpName,
           Salary > 10000? "Overpaid" : Salary.ToString() AS Salary
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/conditionalOperatorA.csv"
USING Outputters.Csv();
```

<a name="nullCoal"></a>**?? (Null-Coalescing)**  
The `??` operator is called the null-coalescing operator. It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.  The following example returns 0 where `Salary` is null.
```sql
@employees = 
    SELECT * FROM 
        ( VALUES
        (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
        (11, "Ethan", 400, (int?)9000,  new DateTime(2015,08,22)),
        (12, "David", 800, (int?)100,   new DateTime(2016,11,01)),
        (13, "Andrew", 100, (int?)null, new DateTime(1995,07,16))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);

@result =
    SELECT EmpName,
           Salary ?? 0 AS Salary
    FROM @employees;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/NullCoalescingOperator.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="lamda"></a>**=> (Lamda)**   
The `=>` token is called the lambda operator. It is used in lambda expressions to separate the input variables on the left side from the lambda body on the right side.  The following example shows two ways to find and display the length of the shortest string in an array of strings.
```sql
@someBooks =
    SELECT * FROM
        ( VALUES
        ("123; 1234; 12345; 123456"),
        ("1234; 12345; 123456")
        ) AS T(Books);

@array =
    SELECT new SQL.ARRAY<string>(Books.Split(';')) AS BooksArray
    FROM @someBooks;

@result =
    SELECT BooksArray.Min(w => w.Length) AS MinLength,
           BooksArray.Min((string w) => w.Length) AS MinLengthV2
    FROM @array;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/Lamda.csv"
USING Outputters.Csv(outputHeader: true);
```
--------------------------------------------------

### <a name="stringMethods">**String Methods**</a>   
<a name="Compare">**Compare**</a>   
Compares two specified String objects and returns an integer that indicates their relative position in the sort order.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("abc")
        ) AS T(string1);

@result =
    SELECT String.Compare(string1, string1) AS samePosition,
           String.Compare("ani\u00ADmal", "animal") AS ignorableCharacters,
           String.Compare("Noah", "N") AS Noah_follows_N,
           String.Compare("Noah", 0, "N", 0, 1) AS samePositionAtCount1,
           String.Compare("abc", 0, "ABC", 0, 3) AS abc_precedes_ABC,
           String.Compare("ABC", 0, "abc", 0, 3) AS ABC_follows_abc
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/Compare.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="CompareOrdinal">**CompareOrdinal**</a>   
Compares two String objects by evaluating the numeric values of the corresponding Char objects in each string.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("abc")
        ) AS T(string1);

@result =
    SELECT String.CompareOrdinal(string1, string1) AS samePosition,
           String.CompareOrdinal("ani\u00ADmal", "animal") AS ignorableCharacters,
           String.CompareOrdinal("Noah", "N") AS Noah_follows_N,
           String.CompareOrdinal("Noah", 0, "N", 0, 1) AS samePositionAtCount1,
           String.CompareOrdinal("abc", 0, "ABC", 0, 3) AS abc_follows_ABC,
           String.CompareOrdinal("ABC", 0, "abc", 0, 3) AS ABC_precedes_abc
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/CompareOrdinal.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="CompareTo">**CompareTo - Basic Syntax**</a>   
CompareTo compares this instance with a specified String object and indicates whether this instance precedes, follows, or appears in the same position in the sort order as the specified string. 
CompareTo was designed primarily for use in sorting or alphabetizing operations.

```sql
@someData = 
    SELECT * FROM 
    ( VALUES
    ("B")
    ) AS T(EmpID);

DECLARE @aString string = "C";

@result =
    SELECT EmpID.CompareTo(@aString) AS B_precedes_C,
           EmpID.CompareTo("A") AS B_follows_A,
           @aString.CompareTo(EmpID) AS C_follows_B,
           EmpID.CompareTo("B") AS samePosition,
           "ani\u00ADmal".CompareTo("animal") AS ignorableCharacters,
           "Noah".CompareTo("N") AS Noah_follows_N
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/CompareToA.csv"
USING Outputters.Csv(outputHeader: true);
```

**CompareTo - Additional Example**   
This query uses CompareTo inthe WHERE clause to identify all employees with names that start with "J" through "N."
```sql
@employees = 
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   100, (int?)10000, new DateTime(2012,05,31), "cell:030-0074321,office:030-0076545"),
        (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19), "cell:(5) 555-4729,office:(5) 555-3745"),
        (3, "Liam",   100, (int?)30000, new DateTime(2014,09,14), "cell:(5) 555-3932"),
        (4, "Amy",    100, (int?)35000, new DateTime(1999,02,27), "cell:(171) 555-7788,office:(171) 555-6750, home:(425) 555-6238"),
        (5, "Justin", 100, (int?)15000, new DateTime(2015,01,12), "cell:0921-12 34 65,office:0921-12 34 67"),
        (6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08), (string)null),
        (7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02), ""),
        (8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11), "cell:88.60.15.31,office:88.60.15.32"),
        (9, "Mason",  300, (int?)50000, new DateTime(2016,01,01), "cell:(91) 555 22 82,office:(91) 555 91 99, home:(425) 555-2819"),
        (10, "Ava",   400, (int?)15000, new DateTime(2014,09,14), "cell:91.24.45.40,office:91.24.45.41"),
        (11, "Ethan", 400, (int?)9000,  new DateTime(2015,08,22), "cell:(604) 555-4729,office:(604) 555-3745"),
        (12, "David", 800, (int?)100,   new DateTime(2016,11,01), "cell:(171) 555-1212"),
        (13, "Andrew", 100, (int?)null, new DateTime(1995,07,16), "cell:(1) 135-5555,office:(1) 135-4892"),
        (14, "Jennie", 100, (int?)34000, new DateTime(2000,02,12), "cell:(5) 555-3392,office:(5) 555-7293")
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate, PhoneNumbers);

@result =
    SELECT *
    FROM @employees
    WHERE EmpName.CompareTo("J") >= 0 AND EmpName.Substring(0, 1).CompareTo("N") <= 0;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/CompareToB.csv"
ORDER BY EmpName ASC
USING Outputters.Csv();
```

<a name="Concat">**Concat**</a>   
Concatenates one or more instances of String, or the String representations of the values of one or more instances of Object.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("abc", "def", "The Book Thief; Markus Zusak; 2005")
        ) AS T(string1, string2, Books);

@result =
    SELECT string1 AS originalString,
           String.Concat(string1, string2) AS Concatenated,
           "abc" + "def" AS concatenatedAltMethod,
           //Create and array from Books, then concatenate the elements
           String.Concat(new SQL.ARRAY<string>(Books.Split(';'))) AS concatenatedArray
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/Concat.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="Contains">**Contains**</a>   
Returns a value indicating whether a specified substring occurs within this string.  This query returns Films where Amy Adams is included as one of the MainActors.

```sql
@someFilms =
    SELECT * FROM
        ( VALUES
        ("Trouble with the Curve",  "Clint Eastwood, Amy Adams, Justin Timberlake, Matthew Lillard, John Goodman"),
        ("American Hustle",  "Christian Bale, Bradley Cooper, Amy Adams, Jeremy Renner, Jennifer Lawrence"),
        ("Silver Linings Playbook",  "Bradley Cooper, Jennifer Lawrence, Robert De Niro, Jacki Weaver, Anupam Kher, Chris Tucker"),
        ("La La Land", "Ryan Gosling, Emma Stone, John Legend, Rosemarie DeWitt, J.K. Simmons")
        ) AS T(Film, MainActors);

@result =
    SELECT Film,
           MainActors
    FROM @someFilms
    WHERE MainActors.Contains("Amy Adams");

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/Contains.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="EndsWith">**EndsWith**</a>    
Determines whether the end of this string instance matches the specified string. This example returns records where `PhoneNumber` ends with 2738.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        (2, "Sophia",  "2535551234"),
        (11, "Ethan",  "4255552738"),
        (12, "David",  "4255550937"),
        (13, "Andrew", "2068675309")
        ) AS T(EmpID, EmpName, PhoneNumber);

@result =
    SELECT EmpName,
           PhoneNumber
    FROM @someData
    WHERE PhoneNumber.EndsWith("2738");

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/EndsWith.csv"
USING Outputters.Csv();
```

<a name="Equals">**Equals**</a>    
Determines whether this instance and another specified String object have the same value. The following example demonstrates the Equals method. It compares the word `Sophia` with an equivalent word, its lowercase equivalent, and its uppercase equivalent.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        (2, "Sophia",  "2535551234")
        ) AS T(EmpID, EmpName, PhoneNumber);

@result =
    SELECT EmpName,
           EmpName.Equals("Sophia") AS [Sophia],
           EmpName.Equals("SOPHIA") AS [SOPHIA],
           EmpName.Equals("sophia") AS [sophia]
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/Equals.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="Format">**Format**</a>   
Converts the value of objects to strings based on the formats specified and inserts them into another string. 

```sql
@someData =
    SELECT * FROM
        ( VALUES
        (3.33m)
        ) AS T(price);

@result =
    SELECT String.Format("The current price is {0} per ounce.", price) AS Results FROM @someData
    UNION ALL
    SELECT String.Format("The current price is {0:C2} per ounce.", price) AS UnusedAlias1 FROM @someData
    UNION ALL
    SELECT String.Format("On {0}, the price was {1:C2} per ounce.", DateTime.Now, price) AS UnusedAlias2 FROM @someData
    UNION ALL
    SELECT String.Format("It is now {0:t} on {0:d}", DateTime.Now) AS UnusedAlias3 FROM @someData
    UNION ALL
    SELECT String.Format("Decimal: {0:G}, Hex: {0:X}", -27) AS UnusedAlias4 FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/Format.csv"
USING Outputters.Csv(outputHeader: false);


// additional example
@population = 
    SELECT * FROM 
        ( VALUES
        ("Los Angeles", new DateTime(1940, 1, 1), 1504277, new DateTime(1950, 1, 1), 1970358), 
        ("New York",    new DateTime(1940, 1, 1), 7454995, new DateTime(1950, 1, 1), 7891957), 
        ("Chicago",     new DateTime(1940, 1, 1), 3396808, new DateTime(1950, 1, 1), 3620962),  
        ("Detroit",     new DateTime(1940, 1, 1), 1623452, new DateTime(1950, 1, 1), 1849568)
        ) AS T(City, Year1, Population1, Year2, Population2);

@result =
    SELECT String.Format("{0,-12}{1,8:yyyy}{2,12:N0}{3,8:yyyy}{4,12:N0}{5,14:P1}",
           City, Year1, Population1, Year2, Population2,
           (Population2 - Population1) / (double) Population1) AS Results
    FROM @population;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/Format2.txt"
USING Outputters.Text();
```

<a name="GetHashCode">**GetHashCode**</a>  
Returns the hash code for this string.
The following example demonstrates the `GetHashCode` method using various input strings.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        (2, "Sophia",  "2535551234")
        ) AS T(EmpID, EmpName, PhoneNumber);

@result =
    SELECT EmpName.GetHashCode() AS [Sophia],
           "".GetHashCode() AS [doubleQuotes],
           "a".GetHashCode() AS [a],
           "A".GetHashCode() AS [A],
           "ab".GetHashCode() AS [ab]
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/GetHashCode.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="GetTypeCode">**GetTypeCode**</a>   
Returns the [TypeCode](https://msdn.microsoft.com/library/system.typecode(v=vs.110).aspx) for class String.  Call the GetTypeCode method on classes that implement the [IConvertible](https://msdn.microsoft.com/library/system.iconvertible(v=vs.110).aspx) interface to obtain the type code for an instance of that class.  Otherwise, call an object's GetType method to obtain its Type object, then call the Type object's GetTypeCode method to obtain the object's type code.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ((int)12, (long)10653, (byte)12, (sbyte)-5, (bool)true, (string)"hello", 16.3, 'l',  Guid.Parse("F9168C5E-CEB2-4faa-B6BF-329BF39FA1E4"))
        ) AS T(ID1, ID2, ID3, ID4, ID5, ID6, ID7, ID8, ID9);

@result =
    SELECT "abc".GetTypeCode().ToString("D") AS abc_TypeCode,
           "abc".GetTypeCode().ToString("F") AS abc_Type,
           Type.GetTypeCode("abc".GetType()).ToString("D") AS abc_TypeCode2,
           Type.GetTypeCode("abc".GetType()).ToString("F") AS abc_Type2,
           // ID9.GetTypeCode().ToString() AS willError,
           // 'System.Guid' does not contain a definition for 'GetTypeCode'
           Type.GetTypeCode(ID9.GetType()).ToString("D") AS guid_TypeCode,
           Type.GetTypeCode(ID9.GetType()).ToString("F") AS guid_Type
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/GetTypeCode.csv"
USING Outputters.Csv(outputHeader : true);
```

<a name="IndexOf">**IndexOf**</a>   
Reports the zero-based index of the first occurrence of the specified string in this instance.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("animal", "The only thing worse than a boy who hates you: a boy that loves you.") 
        // quote from The Book Thief by Markus Zusak
        ) AS T(string1, string2);

@result =
    SELECT string1.IndexOf("m") AS IndexOf_m,
           string1.IndexOf("z") AS IndexOf_z,
           string1.IndexOf("") AS IndexOf_emptyString,
           "ani\u00ADmal".IndexOf("\u00AD") AS softHyphen,
           "ani\u00ADmal".IndexOf("\u00ADn") AS softHyphenFollowedBy_n,
           "ani\u00ADmal".IndexOf("\u00ADm") AS softHyphenFollowedBy_m,
           string2.IndexOf("boy") AS IndexOf_boy,
           string2.IndexOf("boy", 29) AS IndexOf_boy_startingAt29,
           string2.IndexOf("boy", 29, 10) AS IndexOf_boy_startingAt29_count10
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/IndexOf.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="Insert">**Insert**</a>   
Returns a new string in which a specified string is inserted at a specified index position in this instance.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("abcghi")
        ) AS T(string1);

@result =
    SELECT string1 AS originalString,
           string1.Insert(3, "def") AS newString
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/Insert.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="IsNullOrEmpty">**IsNullOrEmpty**</a>   
Indicates whether the specified string is null or an Empty string.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("abcde", (string)null, "", " ", "  \t   ")
        ) AS T(string1, string2, string3, string4, string5);

@result =
    SELECT string.IsNullOrEmpty(string1) AS string1,
           string.IsNullOrEmpty(string2) AS nullString,
           string.IsNullOrEmpty(string3) AS emptyString,
           string.IsNullOrEmpty(string4) AS whitespaceString,
           string.IsNullOrEmpty(string5) AS tab
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/IsNullOrEmpty.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="IsNullOrWhiteSpace">**IsNullOrWhiteSpace**</a>   
Indicates whether a specified string is null, empty, or consists only of white-space characters.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("abcde", (string)null, "", " ", "  \t   ")
        ) AS T(string1, string2, string3, string4, string5);

@result =
    SELECT string.IsNullOrWhiteSpace(string1) AS string1,
           string.IsNullOrWhiteSpace(string2) AS nullString,
           string.IsNullOrWhiteSpace(string3) AS emptyString,
           string.IsNullOrWhiteSpace(string4) AS whitespaceString,
           string.IsNullOrWhiteSpace(string5) AS tab
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/IsNullOrWhiteSpace.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="Join">**Join**</a>   
Concatenates the elements of a specified array or the members of a collection, using the specified separator between each element or member.

```sql
@someFruit = 
    SELECT * FROM 
        ( VALUES
        ("apple; orange; grape; pear")
        ) AS T(Books);

// create an array
@array =
    SELECT new SQL.ARRAY<string>(Books.Split(';')) AS fruitArray
    FROM @someFruit;

// Concatenate the seperator ", " with each element of the array created above
@result =
    SELECT string.Join(", ", fruitArray) AS fruitString
    FROM @array;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/Join.txt"
USING Outputters.Text();
```

<a name="LastIndexOf">**LastIndexOf**</a>   
Reports the zero-based index position of the last occurrence of a specified Unicode character within this instance.  The zero-based starting index position of value if that string is found, or -1 if it is not. If value is String.Empty, the return value is the last index position in this instance.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("mammal") 
        ) AS T(string1);

@result =
    SELECT string1.LastIndexOf("m") AS LastIndexOf_m,
           string1.LastIndexOf("z") AS LastIndexOf_absentCharacter,
           string1.LastIndexOf("") AS LastIndexOf_emptyString,
           "ani\u00ADmal".LastIndexOf("\u00AD") AS softHyphen,
           "ani\u00ADmal".LastIndexOf("\u00ADn") AS softHyphenFollowedBy_n,
           "ani\u00ADmal".LastIndexOf("\u00ADm") AS softHyphenFollowedBy_m
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/LastIndexOf.csv"
USING Outputters.Csv(outputHeader: true, quoting: false);


// additional example
@someData =
    SELECT * FROM
        ( VALUES
        (1, "0----+----1----+----2----+----3----+----4----+----5----+----6----+--"),
        (2, "01234567890123456789012345678901234567890123456789012345678901234567"),
        (3, "The only thing worse than a boy who hates you: a boy that loves you.")
        // quote from The Book Thief by Markus Zusak
        ) AS T(Id, string1);

@result =
    // string1.LastIndexOf("boy")
    SELECT String.Format("The last index of 'boy' is at {0}.", string1.LastIndexOf("boy")) AS LastIndexOf_boy
    FROM @someData WHERE Id == 3
    UNION ALL

    // Search starts at end and then proceeds backwards until beginning.  Essentially same as above.
    // string1.LastIndexOf("boy", string1.Length-1, string1.Length)
    SELECT String.Format("The last index of 'boy' starting at {0} and then going backwards {1} positions is {2}.", string1.Length-1, string1.Length, string1.LastIndexOf("boy", string1.Length-1, string1.Length)) AS LastIndexOf_boy_startingAtEnd_thenProceedingBackward
    FROM @someData WHERE Id == 3
    UNION ALL

    // Search starts at position 31 and then proceeds backwards until begining
    // string1.LastIndexOf("boy", 31)
    SELECT String.Format("The last index of 'boy' starting at {0} and then going backwards to beginning is {1}.", 31, string1.LastIndexOf("boy", 31)) AS LastIndexOf_boy_startingAt31_thenProceedingBackward 
    FROM @someData WHERE Id == 3
    UNION ALL

    // Search starts at position 49 and the proceeds backwards 22 positions to position 29 (49 - 22 + 1)
    // string1.LastIndexOf("boy", 49, 22)
    SELECT String.Format("The last index of 'boy' starting at {0} and then going backwards {1} positions is {2}.", 49, 22, string1.LastIndexOf("boy", 49, 22)) AS LastIndexOf_boy_startingAt29_count22
    FROM @someData WHERE Id == 3
    UNION ALL
    SELECT "\n" AS blankLine FROM @someData WHERE Id == 3
    UNION ALL
    SELECT string1 FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/LastIndexOf2.txt"
USING Outputters.Text(outputHeader: false, quoting: false);
```

<a name="PadLeft">**PadLeft**</a>   
Returns a new string of a specified length in which the beginning of the current string is padded with spaces or with a specified Unicode character. 

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("a simple string") 
        ) AS T(string1);

@result =
    SELECT string1.Length AS string1Length,
    string1.PadLeft(5) AS Five, 
    string1.PadLeft(string1.Length + 5) AS lengthPlusFive,
    string1.PadLeft(string1.Length + 5, '.') AS paddingChar 
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/PadLeft.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="PadRight">**PadRight**</a>   
Returns a new string of a specified length in which the end of the current string is padded with spaces or with a specified Unicode character. 

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("a simple string") 
        ) AS T(string1);

@result =
    SELECT string1.Length AS string1Length,
    string1.PadRight(5) AS Five, 
    string1.PadRight(string1.Length + 5) AS lengthPlusFive,
    string1.PadRight(string1.Length + 5, '.') AS paddingChar 
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/PadRight.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="Remove">**Remove**</a>   
Returns a new string in which a specified number of characters from the current string are deleted.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("123456789")
        ) AS T(string1);

DECLARE @name string = "The Book Thief";
DECLARE @index1 int = @name.IndexOf(" ");
DECLARE @index2 int = @name.IndexOf(" ", @index1 + 1);

@result =
    SELECT string1.Length AS string1Length,
    string1.Remove(0) AS removeAll,
    string1.Remove(5) AS removeAllButFive, 
    string1.Remove(string1.Length - 5) AS removeOnlyFive,
    string1.Remove(string1.Length - 2, 2) AS removeLastTwo,
    string1.Remove(2, 3) AS remove345,
    @name.Remove(@index1, @index2 - @index1) AS removeBook
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/Remove.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="Replace">**Replace**</a>   
Returns a new string in which all occurrences of a specified Unicode character or String in the current string are replaced with another specified Unicode character or String.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("The Book Thief")
        ) AS T(string1);
@result =
    SELECT string1.Replace("Book", "Car") AS replaceBookForCar,
    string1.Replace(" ", ":") AS replaceSpaceForColon,
    string1.Replace(string1, "The Silver Linings Playbook") AS replaceEntireString
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/Replace.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="Split">**Split**</a>   
Returns a string array that contains the substrings in this instance that are delimited by elements of a specified string or Unicode character array.
  
```sql  
@someBooks = 
    SELECT * FROM 
        ( VALUES
        ("The Book Thief; Markus Zusak; 2005"),
        ("The Girl with the Dragon Tattoo; Stieg Larsson; 2005"),
        ("The Silver Linings Playbook; Matthew Quick; 2008"),
        ("Sarah's Key; Tatiana de Rosnay; 2006")
        ) AS T(Books);


@array =
    SELECT new SQL.ARRAY<string>(Books.Split(';')) AS BooksArray
    FROM @someBooks;
```  

<a name="StartsWith">**StartsWith**</a>    
StartsWith determines whether the beginning of this string instance matches a specified string. This example returns records where `PhoneNumber` starts with 425.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        (2, "Sophia",  "2535551234"),
        (11, "Ethan",  "4255552738"),
        (12, "David",  "4255550937"),
        (13, "Andrew", "2068675309")
        ) AS T(EmpID, EmpName, PhoneNumber);

@result =
    SELECT EmpName,
        PhoneNumber
    FROM @someData
    WHERE PhoneNumber.StartsWith("425");

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StartsWith.csv"
USING Outputters.Csv();
```

<a name="Substring">**Substring**</a>    
Substring retrieves a substring from an instance.  In this example, `withoutArea` starts at a specified character position and continues to the end of the string.  The remaining numbers start at a specified character position and has a specified length.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        (2, "Sophia",  "2535551234"),
        (11, "Ethan",  "4255552738"),
        (12, "David",  "4255550937"),
        (13, "Andrew", "2068675309")
        ) AS T(EmpID, EmpName, PhoneNumber);

@result =
    SELECT EmpName,
        PhoneNumber.Substring(3) AS withoutArea,
        PhoneNumber.Substring(0, 3) AS area,
        PhoneNumber.Substring(3, 3) AS exchange,
        PhoneNumber.Substring(6, 4) AS number
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/Substring.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="ToCharArray">**ToCharArray**</a>  
Copies the characters in this instance to a Unicode character array. 

```sql
@someData = 
    SELECT * FROM 
        ( VALUES
        ("AaBbCcDd")
        ) AS T(string1);


@array =
    SELECT new SQL.ARRAY<char>(string1.ToCharArray()) AS CharArray
    FROM @someData;

@result =
    SELECT CharArray[0] AS position0_UnicodeValue,
           CharArray[0].ToString() AS position0_StringValue,
           CharArray[3] AS position3_UnicodeValue,
           CharArray[3].ToString() AS position3_StringValue
    FROM @array;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/ToCharArray1.csv"
USING Outputters.Csv();


// Using a starting position and length.
@array =
    SELECT new SQL.ARRAY<char>(string1.ToCharArray(0, 2)) AS CharArray
    FROM @someData;

@result =
    SELECT CharArray[0] AS position0_UnicodeValue,
           CharArray[0].ToString() AS position0_StringValue
           // CharArray[3]AS position4_UnicodeValue, // Out of Range
    FROM @array;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/ToCharArray2.csv"
USING Outputters.Csv();
```

<a name="ToLower">**ToLower**</a>   
Returns a copy of this string converted to lowercase.

```sql
@someData = 
    SELECT * FROM 
        ( VALUES
        ("AaBbCcDd")
        ) AS T(string1);

@result =
    SELECT string1.ToLower() AS allLower
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/ToLower.txt"
USING Outputters.Text();
```

<a name="ToUpper">**ToUpper**</a>   
Returns a copy of this string converted to uppercase.

```sql
@someData = 
    SELECT * FROM 
        ( VALUES
        ("AaBbCcDd")
        ) AS T(string1);

@result =
    SELECT string1.ToUpper() AS allUpper
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/ToUpper.txt"
USING Outputters.Text();
```

<a name="Trim">**Trim**</a>   
Returns a new string in which all leading and trailing occurrences of a set of specified characters from the current String object are removed.

```sql
@someData = 
    SELECT * FROM 
        ( VALUES
        ("   AaBbCcDd   ")
        ) AS T(string1);

@result =
    SELECT string1.Trim() AS trimTrailingLeadingWhiteSpace,
           string1.TrimEnd() AS trimTrailingWhiteSpace,
           string1.TrimStart() AS trimLeadingWhiteSpace,
           "*Word*".Trim('*') AS trimSpecifiedCharacter,
           "*Word*Word! *".Trim('*', '!', ' ') AS trimSpecifiedCharacters
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringMethods/Trim.txt"
USING Outputters.Text();
```

--------------------------------------------------

### <a name="stringProperties">**String Properties**</a>
<a name="Length">**Length**</a>  
Gets the number of characters in the current String object.  The Length property returns the number of Char objects in this instance, not the number of Unicode characters. 

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ("abcdef", "abc\u0000def")
        ) AS T(string1, string2);

@result =
    SELECT string1.Length AS L1,
           string2.Length AS L2
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/StringProperties/Length.csv"
USING Outputters.Csv(outputHeader: true);
```
--------------------------------------------------

### <a name="ObjectMethods">**Object Methods**</a>
<a name="GetType">**GetType**</a>  
Gets the Type of the current instance.  For two objects x and y that have identical runtime types, Object.ReferenceEquals(x.GetType(),y.GetType()) returns true. The following example uses the GetType method with the [ReferenceEquals](https://msdn.microsoft.com/library/system.object.referenceequals(v=vs.110).aspx) method to determine whether one numeric value is the same type as two other numeric values.  The GetType method is also used determine the type of a particular object.

```sql
@someData =
    SELECT * FROM
        ( VALUES
        ((int)12, (long)10653, (byte)12, (sbyte)-5, (bool)true, (string)"hello", 16.3, 'l')
        ) AS T(ID1, ID2, ID3, ID4, ID5, ID6, ID7, ID8);

@result =
    SELECT Object.ReferenceEquals(ID1.GetType(), ID1.GetType()) AS intVSint,
           Object.ReferenceEquals(ID1.GetType(), ID2.GetType()) AS intVSlong,
           ID1.GetType().ToString() AS anInt,
           ID2.GetType().Name AS aLong,
           ID3.GetType().Name AS aByte,
           ID4.GetType().Name AS anSbyte,
           ID5.GetType().Name AS aBool,
           ID6.GetType().Name AS aString,
           ID7.GetType().Name AS aDouble,
           ID8.GetType().Name AS aChar
    FROM @someData;

OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/ObjectMethods/GetType.csv"
USING Outputters.Csv(outputHeader: true);
```
--------------------------------------------------
### <a name="DateTime">**Date & Time**</a>  

<a name="stringFormats">**DateTime to String**</a>   
Converting DateTime to string. See also, [Standard Date and Time Format Strings](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [Custom Date and Time Format Strings](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).  

```sql
DECLARE @now DateTime = DateTime.Now;

@stringFormats = 
    SELECT * FROM 
        ( VALUES
        // Standard
        ("ShortDatePattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.ShortDatePattern),
        ("ToShortDateString", @now.ToShortDateString()),
        ("d", @now.ToString("d")),
        ((string)null, (string)null),
        ("LongDatePattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.LongDatePattern),
        ("ToLongDateString", @now.ToLongDateString()),
        ("D", @now.ToString("D")),
        ((string)null, (string)null),
        ("LongDateShortTimePattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.LongDatePattern + " " + Thread.CurrentThread.CurrentCulture.DateTimeFormat.ShortTimePattern),
        ("f", @now.ToString("f")),
        ((string)null, (string)null),
        ("FullDateTimePattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.FullDateTimePattern),
        ("F", @now.ToString("F")),
        ((string)null, (string)null),
        ("ShortDateShortTimePattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.ShortDatePattern  + " " + Thread.CurrentThread.CurrentCulture.DateTimeFormat.ShortTimePattern),
        ("g", @now.ToString("g")),
        ((string)null, (string)null),
        ("ShortDateLongTimePattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.ShortDatePattern  + " " + Thread.CurrentThread.CurrentCulture.DateTimeFormat.LongTimePattern),
        ("G", @now.ToString("G")),
        ((string)null, (string)null),
        ("MonthDayPattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.MonthDayPattern),
        ("M", @now.ToString("M")),
        ((string)null, (string)null),
        ("RFC1123Pattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.RFC1123Pattern),
        ("R", @now.ToString("R")),
        ((string)null, (string)null),
        ("SortableDateTimePattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.SortableDateTimePattern),
        ("s", @now.ToString("s")),
        ((string)null, (string)null),
        ("ShortTimePattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.ShortTimePattern),
        ("ToShortTimeString ", @now.ToShortTimeString()),
        ("t", @now.ToString("t")),
        ((string)null, (string)null),
        ("LongTimePattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.LongTimePattern),
        ("ToLongTimeString ", @now.ToLongTimeString()),
        ("T", @now.ToString("T")),
        ((string)null, (string)null),
        ("UniversalSortableDateTimePattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.UniversalSortableDateTimePattern),
        ("u", @now.ToString("u")),
        ((string)null, (string)null),
        ("U", @now.ToString("U")),
        ((string)null, (string)null),
        ("YearMonthPattern", Thread.CurrentThread.CurrentCulture.DateTimeFormat.YearMonthPattern),
        ("y", @now.ToString("y")),
        ((string)null, (string)null),
        // Custom
        ("yyyy-MM-dd", @now.ToString("yyyy-MM-dd")),
        ("MMMM dd, yyyy", @now.ToString("MMMM dd, yyyy")),
        ("MM/dd/yy H:mm:ss", @now.ToString("MM/dd/yy H:mm:ss"))
        ) AS T(Property1, Value_DateTime);

OUTPUT @stringFormats
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/DateTime/stringFormats.txt"
USING Outputters.Tsv();
```

<a name="stringConversion">**String to DateTime**</a>  
Converting string to DateTime.  See also, [DateTime.Parse Method](https://msdn.microsoft.com/library/system.datetime.parse(v=vs.110).aspx) and [Convert.ToDateTime Method](https://msdn.microsoft.com/library/system.convert.todatetime(v=vs.110).aspx).

```sql
@convertString = 
    SELECT * FROM 
        ( VALUES
        ("DateTime.Parse", "2/16/2008", DateTime.Parse("2/16/2008")),
        ("DateTime.Parse", "2/16/2008 12:15:12 PM", DateTime.Parse("2/16/2008 12:15:12 PM")),
        ("DateTime.Parse", "16/02/2008 12:15:12", DateTime.Parse("16/02/2008 12:15:12", new CultureInfo("fr-FR", false))),
        ("DateTime.Parse", "2/16/2008", DateTime.Parse("2/16/2008", new CultureInfo("en-US"), DateTimeStyles.AssumeLocal)),

        ("Convert.ToDateTime", "2/16/2008", Convert.ToDateTime("2/16/2008")),
        ("Convert.ToDateTime", "2/16/2008 12:15:12 PM", Convert.ToDateTime("2/16/2008 12:15:12 PM")),
        ("Convert.ToDateTime", "16/02/2008 12:15:12", Convert.ToDateTime("16/02/2008 12:15:12", new CultureInfo("fr-FR", false))),
        ("Convert.ToDateTime", "2/16/2008", Convert.ToDateTime("2/16/2008", new CultureInfo("en-US")))
        ) AS T(Method, String, Result);

OUTPUT @convertString
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/DateTime/convertString.txt"
USING Outputters.Tsv();
```


<a name="properties">**Properties**</a>  
See also, [DateTime Properties](https://msdn.microsoft.com/library/system.datetime_properties(v=vs.110).aspx).  It is important to avoid misinterpreting a date returned by the Date property as a date and time. 

```sql
DECLARE @now DateTime = DateTime.Now;

@properties = 
    SELECT * FROM 
        ( VALUES
        ("Now",     (DateTime?)@now,            "Now.Day",          @now.Day,         "Now.DayOfWeek",@now.DayOfWeek.ToString("f")),
        ("Today",   (DateTime?)DateTime.Today,  "Now.DayOfYear",    @now.DayOfYear,   "Now.Kind",     @now.Kind.ToString()),
        ("UtcNow",  (DateTime?)DateTime.UtcNow, "Now.Year",         @now.Year,        "Now.TimeOfDay",@now.TimeOfDay.ToString()),
        ("Now.Date", (DateTime?)@now.Date,      "Now.Hour",         @now.Hour,        "Hour - 12-hour clock",   @now.ToString("%h")),
        ((string)null, (DateTime?)null,         "Now.Minute",       @now.Minute,      (string)null,   (string)null),
        ((string)null, (DateTime?)null,         "Now.Month",        @now.Month,       (string)null,   (string)null),
        ((string)null, (DateTime?)null,         "Now.Second",       @now.Second,      (string)null,   (string)null),
        ((string)null, (DateTime?)null,         "Now.Millisecond",  @now.Millisecond, (string)null,   (string)null)
        ) AS T(Property1, Value_DateTime, Property2, Value_Int, Property3, Value_String);

OUTPUT @properties
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/DateTime/properties.csv"
USING Outputters.Csv();
```

<a name="someMethods">**Some Methods**</a>   
See also, [DateTime Methods](https://msdn.microsoft.com/library/system.datetime_methods(v=vs.110).aspx).

```sql
DECLARE @now DateTime = DateTime.Now;

@someMethods = 
    SELECT * FROM 
        ( VALUES
        ("DaysInMonth_2017_2", DateTime.DaysInMonth(2017, 2),  "IsDaylightSavingTime_Now", @now.IsDaylightSavingTime()),
        ("DaysInMonth_2016_2", DateTime.DaysInMonth(2016, 2),  "IsLeapYear_2016", DateTime.IsLeapYear(2016))
        ) AS T(Method1, Value, Method2, Value2);

OUTPUT @someMethods
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/DateTime/someMethods.csv"
USING Outputters.Csv();
```
        
<a name="comparingDateTimes">**Comparing DateTimes**</a>   
See also, [DateTime.Compare Method (DateTime, DateTime)](https://msdn.microsoft.com/library/system.datetime.compare(v=vs.110).aspx) and [DateTime.CompareTo Method](https://msdn.microsoft.com/library/system.datetime.compareto(v=vs.110).aspx).

```sql
@someDates = 
    SELECT * FROM 
        ( VALUES
        (1, new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local), new DateTime(2017, 01, 02, 01, 01, 01, DateTimeKind.Local)),
        (2, new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local), new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local)),
        (3, new DateTime(2017, 01, 01, 01, 00, 00, DateTimeKind.Local), new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local))
        ) AS T(Id, Date1, Date2);
        
@compare =
    SELECT  // using Compare
            DateTime.Compare(Date1, Date2) AS compareValue,
            DateTime.Compare(Date1, Date2) < 0? Date1.ToString("G") + " is earlier than " + Date2.ToString("G") :
                (DateTime.Compare(Date1, Date2) == 0) ? Date1.ToString("G") + " is the same as " + Date2.ToString("G") :
                Date1.ToString("G") + " is later than " + Date2.ToString("G") AS usingCompare,

            // using CompareTo
            Date1.CompareTo(Date2) AS compareToValue,
            Date1.CompareTo(Date2) < 0 ? Date1.ToString("G") + " is earlier than " + Date2.ToString("G") :
                (Date1.CompareTo(Date2) == 0) ? Date1.ToString("G") + " is the same as " + Date2.ToString("G") :
                Date1.ToString("G") + " is later than " + Date2.ToString("G") AS usingcompareTo,

            // using an operator
            Date1 < Date2 ? Date1.ToString("G") + " is earlier than " + Date2.ToString("G") :
                Date1 == Date2 ? Date1.ToString("G") + " is the same as " + Date2.ToString("G") : 
                Date1.ToString("G") + " is later than " + Date2.ToString("G") AS usingOperator
    FROM @someDates;

OUTPUT @compare
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/DateTime/compare.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="someOperators">**Some Operators**</a>   
See also, [DateTime Operators](https://msdn.microsoft.com/library/system.datetime_operators(v=vs.110).aspx).

```sql
@someDates = 
    SELECT * FROM 
        ( VALUES
        (1, new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local), new DateTime(2017, 01, 02, 01, 01, 01, DateTimeKind.Local)),
        (2, new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local), new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local)),
        (3, new DateTime(2017, 01, 01, 01, 00, 00, DateTimeKind.Local), new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local))
        ) AS T(Id, Date1, Date2);
        
@operators =
    SELECT Date1.ToString("G") + " > " + Date2.ToString("G") AS aaa,
           Date1 > Date2 AS bbb,
           (Date1 > Date2) ? Date1.ToString("G") + " is later than " + Date2.ToString("G") : Date1.ToString("G") + " is not later than " + Date2.ToString("G") AS ccc
    FROM @someDates // WHERE Id == 3
    UNION ALL
    SELECT Date1.ToString("G") + " < " + Date2.ToString("G") AS aaa,
           (Date1 < Date2) AS bbb,
           (Date1 < Date2) ? Date1.ToString("G") + " is earlier than " + Date2.ToString("G") : Date1.ToString("G") + " is not earlier than " + Date2.ToString("G") AS ccc
    FROM @someDates; // WHERE Id == 3;

OUTPUT @operators
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/DateTime/operators.csv"
USING Outputters.Csv();
```

<a name="dateDiff">**Date Diff**</a>   
DateTime +- DateTime = TimeSpan.  See also, [TimeSpan Structure](https://msdn.microsoft.com/library/system.timespan(v=vs.110).aspx) and [TimeSpan Properties](https://msdn.microsoft.com/library/system.timespan_properties(v=vs.110).aspx).

```sql
@someDates = 
    SELECT * FROM 
        ( VALUES
        (1, new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local), new DateTime(2017, 01, 02, 01, 01, 01, DateTimeKind.Local)),
        (2, new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local), new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local)),
        (3, new DateTime(2017, 01, 01, 01, 00, 00, DateTimeKind.Local), new DateTime(2017, 01, 01, 00, 00, 00, DateTimeKind.Local))
        ) AS T(Id, Date1, Date2);
        
@dateDiff =
    SELECT 
        "TimeSpan difference between " + Date2.ToString("G") + " and " + Date1.ToString("G") AS DateDiff,
        (Date2 - Date1).Days AS Days,
        (Date2 - Date1).TotalDays AS TotalDays,
        (Date2 - Date1).Hours AS Hours,
        (Date2 - Date1).TotalHours AS TotalHours,
        (Date2 - Date1).Minutes AS Minutes,
        (Date2 - Date1).TotalMinutes AS TotalMinutes,
        (Date2 - Date1).Seconds AS Seconds,
        (Date2 - Date1).TotalSeconds AS TotalSeconds
    FROM @someDates WHERE Id == 1;
    
OUTPUT @dateDiff 
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/DateTime/dateDiff.csv"
USING Outputters.Csv(outputHeader: true);
```

<a name="addTimeSpan">**Add TimeSpan**</a>   
DateTime +- TimeSpan = DateTime.

```sql
DECLARE @now DateTime = DateTime.Now;

@add_subtract = 
    SELECT * FROM 
        ( VALUES
        (@now.ToString("G") + " PLUS 36 Days",    @now.Add(new System.TimeSpan(36, 0, 0, 0)).ToString("G"),      @now.AddDays(36).ToString("G"),     (@now + new System.TimeSpan(36, 0, 0, 0)).ToString("G")), 
        (@now.ToString("G") + " PLUS 12 Hours",   @now.Add(new System.TimeSpan(0, 12, 0, 0)).ToString("G"),      @now.AddHours(12).ToString("G"),    (@now + new System.TimeSpan(0, 12, 0, 0)).ToString("G")),
        (@now.ToString("G") + " LESS 20 Minutes", @now.Subtract(new System.TimeSpan(0, 0, 20, 0)).ToString("G"), @now.AddMinutes(-20).ToString("G"), (@now - new System.TimeSpan(0, 0, 20, 0)).ToString("G")),
        (@now.ToString("G") + " LESS 10 Seconds", @now.Subtract(new System.TimeSpan(0, 0, 0, 10)).ToString("G"), @now.AddSeconds(-10).ToString("G"), (@now - new System.TimeSpan(0, 0, 0, 10)).ToString("G"))
        ) AS T(Operation, Method1, Method2, Method3);

OUTPUT @add_subtract
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/DateTime/add_subtract.txt"
USING Outputters.Tsv();
```

<a name="TimeSpan">**TimeSpan Plus TimeSpan**</a>   
TimeSpan +- TimeSpan = TimeSpan.  See also, [TimeSpan Methods](https://msdn.microsoft.com/library/system.timespan_methods(v=vs.110).aspx).

```sql
@TimeSpan =
    SELECT 
        new TimeSpan(1, 0, 0, 0).ToString() AS baseTimeSpan,
        new TimeSpan(1, 0, 0, 0).Add(TimeSpan.FromDays(1)).ToString() AS addOneDay,
        new TimeSpan(1, 0, 0, 0).Add(TimeSpan.FromHours(1)).ToString() AS addOneHour,
        new TimeSpan(1, 0, 0, 0).Add(TimeSpan.FromMinutes(1)).ToString() AS addOneMinute,
        new TimeSpan(1, 0, 0, 0).Add(TimeSpan.FromSeconds(1)).ToString() AS addOneSecond
    FROM 
        (VALUES 
        (1)
        ) AS T(dummyTable);

OUTPUT @TimeSpan 
TO "/Output/ReferenceGuide/BuiltInFunctions/CSharpFunctions/DateTime/TimeSpan.csv"
USING Outputters.Csv(outputHeader: true);
```
--------------------------------------------------
### <a name="Math"></a>**Math Methods**
<a name="abs"></a>**Abs**   
Returns the absolute value of a specified number.
```sql
@data  = 
    SELECT * FROM   
        (VALUES  
        (-1, -1.23789),
        (1,   1.23789)
        ) AS  T (col1, col2);

@result =
    SELECT  Math.Abs(col1) AS Abs1,    
            Math.Abs(col2) AS Abs2     
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/CSharpFunctions/MathMethods/Abs.txt"
USING Outputters.Csv();
```

<a name="bigMul"></a>**BigMul**   
Returns the square root of a specified number.
```sql
@data  = 
    SELECT * FROM   
        (VALUES  
        (2),
        (2147483647)
        ) AS  T (col1);

@result =
    SELECT  Math.BigMul(col1, col1) AS BigMul 
    FROM    @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/CSharpFunctions/MathMethods/BigMul.txt"
USING Outputters.Tsv();
```

<a name="ceiling"></a>**Ceiling**   
Returns the smallest integer greater than or equal to the specified number.
```sql
@data  = 
    SELECT * FROM   
        (VALUES  
        (7.03m),
        (7.64m),
        (0.12m),
        (-0.12m),
        (-7.1m),
        (-7.6m)
        ) AS  T (col1);

@result =
    SELECT  col1 AS Value,
            Math.Ceiling(col1) AS Ceiling,    
            Math.Floor(col1) AS Floor     
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/CSharpFunctions/MathMethods/Ceiling.txt"
USING Outputters.Tsv(outputHeader: true);
```

<a name="floor"></a>**Floor**   
Returns the largest integer less than or equal to the specified number.
```sql
@data  = 
    SELECT * FROM   
        (VALUES  
        (7.03m),
        (7.64m),
        (0.12m),
        (-0.12m),
        (-7.1m),
        (-7.6m)
        ) AS  T (col1);

@result =
    SELECT  col1 AS Value,
            Math.Ceiling(col1) AS Ceiling,    
            Math.Floor(col1) AS Floor     
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/CSharpFunctions/MathMethods/Floor.txt"
USING Outputters.Tsv(outputHeader: true);
```

<a name="max"></a>**Max**   
Returns the larger of two specified numbers.
```sql
@data  = 
    SELECT * FROM   
        (VALUES  
        (2, 5),
        (10, 4)
        ) AS  T (col1, col2);

@result =
    SELECT  Math.Max(col1, col2) AS Max1,
            Math.Max(col1, -10) AS Max2
    FROM @data;

OUTPUT @result
TO "ReferenceGuide/Operators/CSharpFunctions/MathMethods/Max.txt"
USING Outputters.Csv();
```

<a name="min"></a>**Min**   
Returns the smaller of two numbers.
```sql
@data  = 
    SELECT * FROM   
        (VALUES  
        (2, 5),
        (10, 4)
        ) AS  T (col1, col2);

@result =
    SELECT  Math.Min(col1, col2) AS Min1,
            Math.Min(col1, -10) AS Min2
    FROM @data;

OUTPUT @result
TO "ReferenceGuide/Operators/CSharpFunctions/MathMethods/Min.txt"
USING Outputters.Csv();
```

<a name="pow"></a>**Pow**  
Returns a specified number raised to the specified power.
```sql
@data  = 
    SELECT * FROM   
        (VALUES  
        (2)
        ) AS  T (col1 );

@result =
    SELECT  Math.Pow(col1,2) AS twoSquared,
            Math.Pow(2,3) AS twoCubed
    FROM @data;

OUTPUT @result
TO "ReferenceGuide/Operators/CSharpFunctions/MathMethods/Pow.txt"
USING Outputters.Csv();
```

<a name="sign"></a>**Sign**   
Returns an integer that indicates the sign of a double-precision floating-point number.
```sql
@data  = 
    SELECT * FROM   
        (VALUES  
        (-5),
        (0),
        (5)
        ) AS  T (col1);

@result =
    SELECT  Math.Sign(col1) AS Sign 
    FROM    @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/CSharpFunctions/MathMethods/Sign1.txt"
USING Outputters.Tsv();


@result =
    SELECT      String.Format("{0} is {1}", col1,
                (Math.Sign(col1) == -1) ? "less than zero" :
                (Math.Sign(col1) == 0) ? "equal to zero" : "greater than zero") AS outcome
    FROM    @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/CSharpFunctions/MathMethods/Sign2.txt"
USING Outputters.Tsv();
```

<a name="sqrt"></a>**Sqrt**   
Returns the square root of a specified number.
```sql
@data  = 
    SELECT * FROM   
        (VALUES  
        (4.0),
        (2870.3)
        ) AS  T (col1);

@result =
    SELECT  col1,
            Math.Sqrt(col1) AS Sqrt 
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/CSharpFunctions/MathMethods/Sqrt.txt"
USING Outputters.Tsv();
```


<a name="truncate"></a>**Truncate**   
Calculates the integral part of a number. 
```sql
@data  = 
    SELECT * FROM   
        (VALUES  
        (32.7865, (decimal)32.7865m, (float)32.7865 )
        ) AS  T (col1, col2, col3);

@result =
    SELECT  col1,
            Math.Truncate(col2) AS Truncate2,
            Math.Truncate(col3)  AS Truncate3         
    FROM @data;

OUTPUT @result
TO "/ReferenceGuide/Operators/CSharpFunctions/MathMethods/Truncate.txt"
USING Outputters.Csv();
```

--------------------------------------------------
### <a name="Random"></a>**Random Methods**   
<a name="randomNext"></a>**Next**   
Returns random number.  Using the array for pet names in the example is a variant of the example taken from [Random.Next Method (Int32, Int32)](https://msdn.microsoft.com/library/2dx6wyd4(v=vs.110).aspx)
```sql
@data  = 
    SELECT * 
    FROM
        (VALUES  
        (new SQL.ARRAY<string>{ "Rufus", "Bear", "Dakota", "Fido", 
                                "Vanya", "Samuel", "Koani", "Volodya", 
                                "Prince", "Yiska" })
        ) AS  T (col1 );

DECLARE @malePetNames  = new SQL.ARRAY<string>{ "Rufus", "Bear", "Dakota", "Fido", 
                                "Vanya", "Samuel", "Koani", "Volodya", 
                                "Prince", "Yiska" };

// Generate random indexes for pet names.
DECLARE @mIndex int =  new Random().Next(0, @malePetNames.Count);

@result =
    SELECT  new Random().Next() AS RandomNumber1,       // Returns a non-negative random integer.
            new Random().Next(13) AS RandomNumber2,     // Returns a non-negative random integer that is less than the specified maximum.
            new Random().Next(1, 13) AS RandomNumber3,  // Returns a random integer that is within a specified range.
            new Random().NextDouble() AS RandomNumber4, // Returns a random floating-point number that is greater than or equal to 0.0, and less than 1.0.
            @malePetNames[@mIndex] AS petName1,                   // using the two variables
            col1[new Random().Next(0, col1.Count)] AS petName2    // using table
    FROM @data;

OUTPUT @result
TO "ReferenceGuide/Operators/CSharpFunctions/Random1.txt"
USING Outputters.Csv();
```

### See Also 
* [REFERENCE SYSTEM ASSEMBLY](reference-system-assembly-u-sql.md)
* [C# Operators](https://msdn.microsoft.com/library/6a71f45d.aspx)   
* [Built-in Functions (U-SQL)](built-in-functions-u-sql.md)  
* [Built-in U-SQL UDOs](built-in-u-sql-udos.md)  








