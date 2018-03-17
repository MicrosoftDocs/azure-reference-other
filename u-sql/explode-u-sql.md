---
title: "EXPLODE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "07/18/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: fbf34283-3a54-43de-b040-602801bed463
caps.latest.revision: 27
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# EXPLODE (U-SQL)
The EXPLODE rowset expression accepts an expression or value of either type [SQL.ARRAY](complex-built-in-u-sql-types.md), [SQL.MAP](complex-built-in-u-sql-types.md)  or IEnumerable and unpacks (explodes) the values into a rowset.  
  
If EXPLODE is applied on an instance of [SQL.ARRAY](complex-built-in-u-sql-types.md) \<T>, the resulting rowset contains a single column of type T where each item in the array is placed into its own row. If the array value was empty or null, then the resulting rowset is empty.  
  
If EXPLODE is applied on an instance of [SQL.MAP](complex-built-in-u-sql-types.md) \<K,V>, the resulting rowset contains two columns of type K and V respectively where each key-value pair in the map is placed into its own row. If the map value was empty or null, then the resulting rowset is empty.
  
<table><th align="left">Syntax</th><tr><td><pre>
Explode_Expression :=                                                                                    
    'EXPLODE' '(' (<a href="#SE">sqlmap_expression | sqlarray_expression</a> | <a href="#expression">ienumerable_expression</a> ) ')'  
    <a href="#DTAWOT">Derived_Table_Alias_With_Opt_Types</a>.  
</pre></td></tr></table>
  
### Semantics of Syntax Elements    
-   <a name="SE"></a>**`sqlmap_expression | sqlarray_expression`**  
    Any U-SQL/C# expression that results in a value of either type `SQL.MAP` or `SQL.ARRAY` respectively. If the provided expression does not resolve in either type, an error is raised.  
    
-   <a name="expression"></a>**`ienumerable_expression`**  
A C# expression returning a value of either type `IEnumerable<T>`, `IEnumerable<KeyValuePair<K,V>>`, or `IEnumerable<Tuple>`. The expression normally refers to at least one of the columns from the `Rowset_Source`.
  
- <a name="DTAWOT"></a>**`Derived_Table_Alias_With_Opt_Types`**  
  Defines the rowset schema for the result of the EXPLODE.

  <table><th>Syntax</th><tr><td><pre>
  Derived_Table_Alias_With_Opt_Types :=                                                               
      'AS' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> ['(' Column_Alias_Opt_Type_List ')'].<br />
  Column_Alias_Opt_Type_List :=  
      Column_Alias_Opt_Type {',' Column_Alias_Opt_Type }.<br />
  Column_Alias_Opt_Type := 
      <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> [<a href="built-in-u-sql-types.md">Built_in_Type</a>].
  </pre></td></tr></table>

  The derived table alias requires the correct number of columns to be specified (one in the case of an `EXPLODE` on `SQL.ARRAY` and two in the case of `SQL.MAP`). Optionally a type can be specified, but if it is specified it has to be the exact type of the item type in the case of an array (`T` for `SQL.ARRAY<T>`) or the key and value types in the case of a map (`K` and `V` for `SQL.MAP<K,V>`).  
  
> [!NOTE]
> EXPLODE is syntactically only supported in the context of an APPLY and is not a general rowset expression.
  
### Example   
```sql
@dep_employees = SELECT *  
                   FROM (VALUES  
                            ("Sales", "Rafferty")  
                          , ("Engineering", "Jones,Heisenberg")  
                          , ("Clerical", "Robinson,Smith,Johnson")  
                          , ("Marketing", "")  
                          , ("", "Williams")  
                         ) AS DE(DepName, DepEmp);  
  
@dep_employees_as_array =  
    SELECT DepName, new SQL.ARRAY<string>(DepEmp.Split(',')) AS Employees  
      FROM @dep_employees;  
  
@deps_exploded =  
    SELECT de.DepName, emp   
      FROM @dep_employees_as_array AS de  
     CROSS APPLY  
     EXPLODE(de.Employees) AS dp(emp);  
                   
  
OUTPUT @deps_exploded   
TO "/output/rsExplode.csv"  
USING Outputters.Csv();
```  
The resulting rowset looks like:  
  
| **DepName** |   **EmpName**        |  
|------------|-----------|  
| "Sales"   | "Rafferty"       |  
| "Engineering"      | "Jones"        |  
| "Engineering"| "Heisenbert"        |  
| "Clerical"| "Robinson"        |  
| "Clerical"   | "Smith"     |  
| "Clerical"   | "Johnson"    |  
| "Marketing" | ""|  
|"" | "Williams" |  

### Additional Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](extending-u-sql-expressions-with-user-code.md#usingAssemblies).
- Some of the examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

**Dataset**  
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
```

**SQL.ARRAY**   
This example first converts the `PhoneNumbers` values into the `SQL.ARRAY` type `AS PhoneNumbersArray`.  `PhoneNumbersArray` is then unpacked resulting in a single column where each item in the array is placed into its own row.
```sql
@array =
    SELECT EmpName,
           PhoneNumbers == "" ? null : new SQL.ARRAY<string>(PhoneNumbers.Split(',')) AS PhoneNumbersArray
    FROM @employees
    WHERE PhoneNumbers != null;

@exploded =
    SELECT EmpName,
           PhoneNumber.Trim() AS PhoneNumber
    FROM @array
    CROSS APPLY 
    EXPLODE(PhoneNumbersArray) AS r(PhoneNumber);

OUTPUT @exploded
TO "/Output/ReferenceGuide/StatementsAndExpressions/Explode/exampleA.csv"
USING Outputters.Csv();
```

**ARRAY_AGG - Bonus Example**   
This example does not use `CROSS APPLY` or `EXPLODE`; however, it illustrates how to reverse the outcome from the above example using [ARRAY_AGG](array-agg-u-sql.md).
```sql
@result =
    SELECT EmpName,
           string.Join(", ", ARRAY_AGG(PhoneNumber)) AS PhoneNumbers
    FROM @exploded
    GROUP BY EmpName;

OUTPUT @result
TO "/Output/ReferenceGuide/StatementsAndExpressions/Explode/exampleB.csv"
USING Outputters.Csv();
```

**SQL.MAP**    
This example first converts the `PhoneNumbers` values into the `SQL.MAP` type `AS PhoneNumberMap`.  `PhoneNumberMap` is then unpacked resulting in two columns where each key-value pair in the map is placed into its own row.
```sql
@map =
    SELECT EmpName,
           PhoneNumbers == ""? null : new SQL.MAP<string, string>(from p in PhoneNumbers.Split(',') select new KeyValuePair<string, string>(p.Split(':') [0], p.Split(':') [1])) AS PhoneNumberMap
    FROM @employees
    WHERE PhoneNumbers != null;

@exploded =
    SELECT EmpName,
           r.key.Trim() AS PhoneType, r.value AS PhoneNumber
    FROM @map
    CROSS APPLY
    EXPLODE(PhoneNumberMap) AS r(key, value);

OUTPUT @exploded
TO "/Output/ReferenceGuide/StatementsAndExpressions/Explode/exampleC.csv"
USING Outputters.Csv();
```

**MAP_AGG - Bonus Example**   
This example does not use `CROSS APPLY` or `EXPLODE`; however, it illustrates how to reverse the outcome from the above example using [MAP_AGG](map-agg-u-sql.md).
```sql
@result =
    SELECT EmpName,
           String.Join(",", MAP_AGG(PhoneType, PhoneNumber).Select(p => String.Format("{0}:{1}", p.Key, p.Value))).Trim() AS PhoneNumbers
    FROM @exploded
    GROUP BY EmpName;
    
OUTPUT @result
TO "/Output/ReferenceGuide/StatementsAndExpressions/Explode/exampleD.csv"
USING Outputters.Csv();
```


**MAP\<string, MAP\<int, string>>**
```sql
// MAP<string, MAP<int, string>>
DECLARE @aMap SQL.MAP<int, string> = new SQL.MAP<int, string>{{1, "Seattle"}};

// Illustrating two methods to pass Value
@popularCitiesM = 
    SELECT * FROM 
        ( VALUES
        (new SQL.MAP<string, SQL.MAP<int, string>>{{"Washington", @aMap}}),
        (new SQL.MAP<string, SQL.MAP<int, string>>{{"Oregon", new SQL.MAP<int, string>{{2, "Portland"}}}})
        ) AS T(cityMaps);

@result2 =
    SELECT c.key AS State,
           n.key AS id,
           n.value AS City
    FROM @popularCitiesM
         CROSS APPLY
             EXPLODE(cityMaps) AS c(key, value)
         CROSS APPLY
             EXPLODE(c.value) AS n(key, value);

OUTPUT @result2
TO "ReferenceGuide/DML/From/Explode/nestedMAP.txt"
USING Outputters.Text();
``` 

**MAP\<string, ARRAY\<string>>**
```sql
DECLARE @anArray SQL.ARRAY<string> = new SQL.ARRAY<string>{"Seattle", "Spokane", "Tacoma"};

// Illustrating two methods to pass Value
@popularCitiesA = 
    SELECT * FROM 
        ( VALUES
        (new SQL.MAP<string, SQL.ARRAY<string>>{{"Washington", @anArray}}),
        (new SQL.MAP<string, SQL.ARRAY<string>>{{"Oregon", new SQL.ARRAY<string>{"Portland", "Eugene", "Salem"}}})
        ) AS T(cityMaps);

@result =
    SELECT c.key AS State,
           n.value AS City
    FROM @popularCitiesA
         CROSS APPLY
             EXPLODE(cityMaps) AS c(key, value)
         CROSS APPLY
             EXPLODE(c.value) AS n(value);

OUTPUT @result
TO "ReferenceGuide/DML/From/Explode/nestedArray.txt"
USING Outputters.Text();
```

**ARRAY\<MAP\<int, string>>**
```sql
DECLARE @aMap1 SQL.MAP<int, string> = new SQL.MAP<int, string>{{503, "Portland"}};
DECLARE @aMap2 SQL.MAP<int, string> = new SQL.MAP<int, string>{{541, "Eugene"}};
DECLARE @aMap3 SQL.MAP<int, string> = new SQL.MAP<int, string>{{602, "Phoenix"}, {520, "Tucson"}, {480, "Mesa"}};

// Illustrating various methods to pass Value
@data = 
    SELECT * FROM 
        ( VALUES
        ("AK", new SQL.ARRAY<SQL.MAP<int, string>>{new SQL.MAP<int, string>{ {907, "Anchorage"}} , new SQL.MAP<int, string>{ {250, "Hyder"}}  }),
        ("AZ", new SQL.ARRAY<SQL.MAP<int, string>>{@aMap3}),
        ("OR", new SQL.ARRAY<SQL.MAP<int, string>>{@aMap1, @aMap2}),
        ("WA", new SQL.ARRAY<SQL.MAP<int, string>>{new SQL.MAP<int, string>{ {253, "Tacoma"}, {360, "Olympia"}, {425, "Redmond"} } })
        ) AS T(State, ac_cities);

// Flatten results
@result1 =
    SELECT  State,
            n.key AS areaCode,
            n.value AS City
    FROM @data
    CROSS APPLY EXPLODE(ac_cities) AS c(value)
    CROSS APPLY EXPLODE(c.value) AS n(key, value);

// return data as one comma delimited string per State
@result2 =
    SELECT  State,
            string.Join(",", MAP_AGG(n.key, n.value)) AS data1
    FROM @data
    CROSS APPLY EXPLODE(ac_cities) AS c(value)
    CROSS APPLY EXPLODE(c.value) AS n(key, value)
    GROUP BY State; 

// compare count results
@result3a =
    SELECT State,
           ac_cities.Count AS Count
    FROM @data; 

@result3b =
    SELECT State,
           c.value.Count AS Count
    FROM @data
    CROSS APPLY EXPLODE(ac_cities) AS c(value);

@result3c =
    SELECT State,
          SUM(c.value.Count) AS Count
    FROM @data
    CROSS APPLY EXPLODE(ac_cities) AS c(value)
    GROUP BY State; 


OUTPUT @result1
TO "ReferenceGuide/DML/From/Explode/mapInArray/result1.txt"
ORDER BY State
USING Outputters.Text();

OUTPUT @result2
TO "ReferenceGuide/DML/From/Explode/mapInArray/result2.txt"
USING Outputters.Text();

OUTPUT @result3a
TO "ReferenceGuide/DML/From/Explode/mapInArray/result3a.txt"
ORDER BY State
USING Outputters.Text();

OUTPUT @result3b
TO "ReferenceGuide/DML/From/Explode/mapInArray/result3b.txt"
ORDER BY State
USING Outputters.Text();

OUTPUT @result3c
TO "ReferenceGuide/DML/From/Explode/mapInArray/result3c.txt"
ORDER BY State
USING Outputters.Text();
```

**ARRAY\<ARRAY\<string>>**
```sql
DECLARE @anArrayB1 SqlArray<string> = SqlArray.Create(new [] {"The Girl with the Dragon Tattoo", "Stieg Larsson", "2005"});
DECLARE @anArrayB2 SQL.ARRAY<string> = new SQL.ARRAY<string>{"The Book Thief", "Markus Zusak", "2005"};
DECLARE @anArrayB3 SQL.ARRAY<string> = new SQL.ARRAY<string>{"The Silver Linings Playbook", "Matthew Quick", "2008"};
DECLARE @anArrayB4 SQL.ARRAY<string> = new SQL.ARRAY<string>{"Sarah's Key", "Tatiana de Rosnay"};
DECLARE @anArrayF1 SQL.ARRAY<string> = new SQL.ARRAY<string>{"The Counselor", "Ridley Scott", "2013"};
DECLARE @anArrayF2 SQL.ARRAY<string> = new SQL.ARRAY<string>{"Goodfellas", "Martin Scorsese", "1990"};
DECLARE @anArrayF3 SQL.ARRAY<string> = new SQL.ARRAY<string>{"The Book Thief", "Brian Percival", "2013"};

@publications = 
    SELECT * FROM 
        ( VALUES
        ("Book", new SQL.ARRAY<SQL.ARRAY<string>>{@anArrayB1, @anArrayB2, @anArrayB3, @anArrayB4}),
        ("Film", new SQL.ARRAY<SQL.ARRAY<string>>{@anArrayF1, @anArrayF2, @anArrayF3})
        ) AS T(medium, data);

// Flatten results
@result1 =
    SELECT medium,
           n.value AS BookInfo
    FROM @publications
    CROSS APPLY EXPLODE(data) AS c(value)
    CROSS APPLY EXPLODE(c.value) AS n(value);

// Filtering results by index position
@result2 =
    SELECT medium,
           c.value[0] AS Title
    FROM @publications
    CROSS APPLY EXPLODE(data) AS c(value);

// return data as one comma delimited string per medium
@result3 =
    SELECT  medium,
            string.Join(",", c.value) AS data1
    FROM @publications
    CROSS APPLY EXPLODE(data) AS c(value);

// number of items in top array
@result4a =
    SELECT medium,
           data.Count AS CityCount1
    FROM @publications;

// number of items in each nested array
@result4b =
    SELECT medium,
           c.value.Count AS Title
    FROM @publications
    CROSS APPLY EXPLODE(data) AS c(value);

OUTPUT @result1
TO "ReferenceGuide/DML/From/Explode/arrayInArray/result1.txt"
USING Outputters.Text();

OUTPUT @result2
TO "ReferenceGuide/DML/From/Explode/arrayInArray/result2.txt"
USING Outputters.Text();

OUTPUT @result3
TO "ReferenceGuide/DML/From/Explode/arrayInArray/result3.txt"
USING Outputters.Text();

OUTPUT @result4a
TO "ReferenceGuide/DML/From/Explode/arrayInArray/result4a.txt"
USING Outputters.Text();

OUTPUT @result4b
TO "ReferenceGuide/DML/From/Explode/arrayInArray/result4b.txt"
USING Outputters.Text();
```

**IEnumerable\<T>**  
```sql
@bands = 
  SELECT * 
  FROM (VALUES ("Beatles", "George Harrison, John Lennon, Paul McCartney, Ringo Starr"), 
               ("Creedence Clearwater Revival", "Doug Clifford, John Fogerty, Stu Cook, Tom Fogerty"), 
               ("Eagles", "Don Henley, Glenn Frey, Joe Walsh, Timothy Schmit"), 
               ("Pink Floyd", "David Gilmour, Nick Mason, Richard Wright, Roger Watters, Syd Barrett"), 
               ("Rolling Stones", "Charlie Watts, Keith Richards, Mick Jagger, Ronnie Wood")) AS Bands(name, members);

@ca_ie_T1 = 
  SELECT name, member 
  FROM @bands CROSS APPLY EXPLODE (members.Split(',')) AS T(member);
@ca_ie_T2 = 
  SELECT name, member 
  FROM @bands CROSS APPLY EXPLODE (from m in members.Split(',') select m) AS T(member);

OUTPUT @ca_ie_T1 
TO "/output/ReferenceGuide/DML/Explode/crossapply_IE_T1.csv" 
USING Outputters.Csv();

OUTPUT @ca_ie_T2 
TO "/output/ReferenceGuide/DML/Explode/crossapply_IE_T2.csv" 
USING Outputters.Csv();
```


**IEnumerable\<T> - Additional Example, Part 1**  
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.
```csharp
using System.Collections.Generic;
using System.IO;
using System.Linq;

namespace FileOps
{
    public class myDirectories
    {
        public static IEnumerable<string> ProcessDirectory1(string targetDirectory)
        {
            return Directory.EnumerateFiles(targetDirectory);
        }

        public static IEnumerable<string> ProcessDirectory2(string targetDirectory, string excludedFile)
        {
            var files = from file in
                Directory.EnumerateFiles(targetDirectory)
                        where !file.Contains(excludedFile)
                        select file;
            return files;
        }
    }
};
```

**IEnumerable\<T> - Additional Example, Part 2**  
Example is meant to be executed *locally*.  Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```sql
// The Directory.EnumerateFiles method returns an enumerable collection of file names.

@directories = 
    SELECT * FROM 
        ( VALUES
        (@"C:\Temp"),
        (@"C:\Temp\Temp2")
        ) AS T(directory);

// aliasing namespace and class
USING xx = FileOps.myDirectories;

DECLARE @excludedFile string = "Test2.txt";

// Calling EnumerateFiles inline
@result1 =
    SELECT file
    FROM @directories CROSS APPLY EXPLODE (Directory.EnumerateFiles(directory)) AS T(file);

OUTPUT @result1
TO "/ReferenceGuide/DML/FROM/Explode/Test1.txt"
USING Outputters.Tsv();


// Calling EnumerateFiles through a function
@result2 = 
  SELECT file
  FROM @directories CROSS APPLY EXPLODE (ProcessDirectory1(directory)) AS T(file);

OUTPUT @result2
TO "/ReferenceGuide/DML/FROM/Explode/Test2.txt"
USING Outputters.Tsv();


//excluding a file in the WHERE clause
@result3 = 
  SELECT file
  FROM @directories CROSS APPLY EXPLODE (xx.ProcessDirectory1(directory)) AS T(file)
 // WHERE !file.Contains(@excludedFile);
  WHERE file != @"C:\Temp\Test2.txt";

OUTPUT @result3
TO "/ReferenceGuide/DML/FROM/Explode/Test3.txt"
USING Outputters.Tsv();


//excluding a file through the function
@result4 = 
  SELECT file
  FROM @directories CROSS APPLY EXPLODE (xx.ProcessDirectory2(directory, @excludedFile)) AS T(file);

OUTPUT @result4
TO "/ReferenceGuide/DML/FROM/Explode/Test4.txt"
USING Outputters.Tsv();
```

**IEnumerable<KeyValuePair\<K,V>>**   
```sql
@bands = 
  SELECT * 
  FROM (VALUES ("Beatles", "George Harrison, John Lennon, Paul McCartney, Ringo Starr"), 
               ("Creedence Clearwater Revival", "Doug Clifford, John Fogerty, Stu Cook, Tom Fogerty"), 
               ("Eagles", "Don Henley, Glenn Frey, Joe Walsh, Timothy Schmit"), 
               ("Pink Floyd", "David Gilmour, Nick Mason, Richard Wright, Roger Watters, Syd Barrett"), 
               ("Rolling Stones", "Charlie Watts, Keith Richards, Mick Jagger, Ronnie Wood")) AS Bands(name, members);

@ca_ie_kvp = 
  SELECT T.* 
  FROM @bands CROSS APPLY EXPLODE (from m in members.Split(',') select new KeyValuePair<string,string>(name,m)) AS T(k,v);

OUTPUT @ca_ie_kvp 
TO "/output/ReferenceGuide/DML/Explode/crossapply_ie_kvp.csv" 
USING Outputters.Csv();
```

**IEnumerable<KeyValuePair\<K,V>> - Additional Example, Part 1**   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.
```csharp
using System.Collections.Generic;
using Microsoft.Win32;

// Returns names and values for a given registry key

namespace RegOps
{
    public class myReg
    {
        public static IEnumerable<KeyValuePair<string, string>> regReader(string registryKey)
        {
            RegistryKey rk = Registry.LocalMachine.OpenSubKey(registryKey);
            var list = new List<KeyValuePair<string, string>>();

            foreach (string valueName in rk.GetValueNames())
            {
               list.Add(new KeyValuePair<string, string>(valueName, rk.GetValue(valueName).ToString()));
            }
            return list;
        }
    }
};
```

**IEnumerable<KeyValuePair\<K,V>> - Additional Example, Part 2**  
Example is meant to be executed *locally*.  Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```sql
// Returns names and values for a given registry key

@registry = 
    SELECT * FROM 
        ( VALUES
        (@"SYSTEM\CurrentControlSet\Control\CrashControl")
        ) AS T(registryKey);

// aliasing namespace and class
USING xx = RegOps.myReg;


@result =
    SELECT T.key AS Name,
           T.value AS Value
    FROM @registry
         CROSS APPLY
             EXPLODE(xx.regReader(registryKey)) AS T(key, value);

OUTPUT @result
TO "/ReferenceGuide/DML/FROM/Explode/keyValuePair1.txt"
USING Outputters.Tsv(outputHeader: true);
```

**IEnumerable\<Tuple>**   
```sql
@bands = 
  SELECT * 
  FROM (VALUES ("Beatles", "George Harrison, John Lennon, Paul McCartney, Ringo Starr"), 
               ("Creedence Clearwater Revival", "Doug Clifford, John Fogerty, Stu Cook, Tom Fogerty"), 
               ("Eagles", "Don Henley, Glenn Frey, Joe Walsh, Timothy Schmit"), 
               ("Pink Floyd", "David Gilmour, Nick Mason, Richard Wright, Roger Watters, Syd Barrett"), 
               ("Rolling Stones", "Charlie Watts, Keith Richards, Mick Jagger, Ronnie Wood")) AS Bands(name, members);

@ca_tuple = 
  SELECT name, m1, m2, m3, m4 
  FROM @bands CROSS APPLY EXPLODE (new [] {Tuple.Create(members.Split(',')[0],
                                                        members.Split(',')[1],
                                                        members.Split(',')[2],
                                                        members.Split(',')[3] )}) AS T(m1,m2,m3,m4);

OUTPUT @ca_tuple 
TO "/output/ReferenceGuide/DML/Explode/crossapply_tuple.csv" 
USING Outputters.Csv();
```
  
### See Also 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md)
* [FROM Clause (U-SQL)](from-clause-u-sql.md)
* [SELECT Expression (U-SQL)](select-expression-u-sql.md) 
* [U-SQL SELECT Selecting from CROSS APPLY and OUTER APPLY](u-sql-select-selecting-from-cross-apply-and-outer-apply.md)  
* [Output Statement (U-SQL)](output-statement-u-sql.md)  
* [ARRAY_AGG (U-SQL)](array-agg-u-sql.md)
* [MAP_AGG (U-SQL)](map-agg-u-sql.md)  
* [Complex Built-In U-SQL Types](complex-built-in-u-sql-types.md)
