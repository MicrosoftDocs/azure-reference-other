---
title: "Complex Built-In U-SQL Types | Microsoft Docs"
ms.custom: ""
ms.date: "09/12/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cbe2dd23-e1ba-410d-a2d7-d77a7b21b2c5
caps.latest.revision: 20
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Complex Built-In U-SQL Types
U-SQL supports the following two built-in complex types:  
```
SQL.MAP<K,V>
SQL.ARRAY<T>
```
The grammar rules use Complex_Type to refer to these types.

These two types are also available as `Microsoft.Analytics.Type.SqlMap<K,V>` and `Microsoft.Analytics.Types.SqlArray<T>` for use in .NET code and can be referred to as `SqlMap<K,V>` and `SqlArray<T>` in U-SQL.
    
The `SQL.MAP`'s value type V and the `SQL.ARRAY`'s item type T can be any built-in U-SQL type, including another `SQL.MAP` or `SQL.ARRAY`, while the `SQL.MAP`'s Key type K has to be a comparable scalar built-in type.  The `SQL.MAP`’s value type V has to be a nullable type, e.g. string or int?.

> [!NOTE]
> SQL.MAP is not comparable.  
> SQL.ARRAY is not comparable.
  
### Examples   
See [EXPLODE (U-SQL)](explode-u-sql.md) for examples involving the usage of `SQL.MAP` and `SQL.ARRAY` and `EXPLODE`.
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](extending-u-sql-expressions-with-user-code.md#usingAssemblies).


<a name="sqlMAP">**SQL.MAP**</a>  

```sql
// Data sets
@ProjectMembers1 = 
    SELECT * FROM 
        ( VALUES
        ("Website", "Chris;UX")
        ) AS T(Project, emp_role);

@ProjectMembers2 = 
    SELECT * FROM 
        ( VALUES
        ("Website", "Mallory", "PM"),
        ("Website", "Bob", "Dev"),
        ("Website", "Alice", "Dev"),
        ("Website", "Stan", "Dev"),
        ("DB", "Ted", "Test"),
        ("DB", "Joe", "Dev"),
        ("DB", "Chuck", "Dev")
        ) AS T(Project, Employee, Role);

@ProjectMembers3 = 
    SELECT * FROM 
        ( VALUES
        ("Operations", new SQL.MAP<string, string>{{"Claire", "DBA"}}),                             // alternative creation
        ("Operations", new SqlMap<string, string>{{"Danes", "Dev"}}),                               // alternative creation
        ("Operations", SqlMap.Create(new SqlMap<string, string>{{"Tina", "NetworkAdmin"}})),        // alternative creation
        ("Operations", new SqlMap<string, string>(new SqlMap<string, string>{{"Lewis", "DBA"}})),   // alternative creation
        ("Operations", new SqlMap<string, string>(new Dictionary<string, string>{{"Rudy", "Dev"}})) // alternative creation
        ) AS T(Project, emp_role);
/**************************************************************/         

// Building a MAP 1
@map1 =
    SELECT  Project,
            new SQL.MAP<string, string>(from p in emp_role select new KeyValuePair<string, string>(emp_role.Split(';')[0], emp_role.Split(';')[1])) AS emp_role
    FROM @ProjectMembers1; 

// Building a MAP 2
@map2 = 
    SELECT  Project, 
            MAP_AGG(Employee, Role) AS emp_role
    FROM @ProjectMembers2 
    WHERE Project == "Website"
    GROUP BY Project;

// Building a MAP 3; alternative method for MAP 2
@map3 = 
    SELECT  Project,
            new SQL.MAP<string, string>{{Employee, Role}} AS emp_role
    FROM @ProjectMembers2
    WHERE Project == "DB";

// UNION all rowsets
@mappedData =
    SELECT * FROM @map1
    UNION ALL
    SELECT * FROM @map2
    UNION ALL
    SELECT * FROM @map3
    UNION ALL
    SELECT * FROM @ProjectMembers3;

// review flattened results
@result1 =
    SELECT  Project,
            Emp.key AS Employee,
            Emp.value AS Role
    FROM @mappedData
    CROSS APPLY EXPLODE(emp_role) AS Emp(key, value);

// return emp_role as string of key/value pairs
@result2 =
    SELECT Project,
           string.Join(",", emp_role) AS emp_role
    FROM @mappedData;

// Filtering on key
// Projects that involve Employee Chuck
@result3 =
    SELECT Project
    FROM @mappedData
    WHERE emp_role.ContainsKey("Chuck");

// Filtering on key
// Projects that involve Employee Chuck; alternative 1
@result4 =
    SELECT Project
    FROM @mappedData
    WHERE emp_role.Keys.Contains("Chuck");

// Filtering on key
// Projects that involve Employee Chuck; alternative 2
@result5 =
    SELECT Project
    FROM @mappedData
    WHERE emp_role.Any(kv => kv.Key.Contains("Chuck"));

// Filtering on value
// Projects that involve Role UX
@result6 =
    SELECT Project
    FROM @mappedData
    WHERE emp_role.Values.Contains("UX");

// Projects that have more than 4 employees
@result7 = 
    SELECT  Project
    FROM @mappedData
    GROUP BY Project
    HAVING SUM(emp_role.Count) > 4;

// The number of employees per Project
@result8 =
    SELECT Project,
           SUM(emp_role.Count) AS NumEmployees,
           SUM(emp_role.Count()) AS NumEmployees2 // less efficient
    FROM @mappedData
    GROUP BY Project;

// The number of Employee Maps per Project
@result9 =
    SELECT Project,
           COUNT( emp_role ) AS numMaps
    FROM @mappedData
    GROUP BY Project;

// update a value 1; output a single record with a new value
@update1 =
    SELECT Project,
           SqlMap.Update(emp_role, new SqlMap<string, string>{{"Claire", "PM"}}) AS emp_role
    FROM @mappedData
    WHERE emp_role.ContainsKey("Claire");

@result10 = 
    SELECT  Project,
            Emp.key AS Employee,
            Emp.value AS Role
    FROM @update1
    CROSS APPLY EXPLODE(emp_role) AS Emp(key, value);

// update a value 2; output all records where one specific map has been updated
@mappedData =
    SELECT Project,
           emp_role.ContainsKey("Claire") ? new SQL.MAP<string, string>(emp_role) {{"Claire", "PM"}} : emp_role AS emp_role
    FROM @mappedData;

@result11 =
    SELECT Project,
           Emp.key AS Employee,
           Emp.value AS Role
    FROM @mappedData
    CROSS APPLY EXPLODE(emp_role) AS Emp(key, value);
    
OUTPUT @result1
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result1.txt"
USING Outputters.Text();

OUTPUT @result2
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result2.txt"
USING Outputters.Text();

OUTPUT @result3
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result3.txt"
USING Outputters.Text();

OUTPUT @result4
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result4.txt"
USING Outputters.Text();

OUTPUT @result5
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result5.txt"
ORDER BY Project
USING Outputters.Text();

OUTPUT @result6
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result6.txt"
USING Outputters.Text();

OUTPUT @result7
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result7.txt"
USING Outputters.Text();

OUTPUT @result8
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result8.txt"
USING Outputters.Text();

OUTPUT @result9
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result9.txt"
USING Outputters.Text();

OUTPUT @result10
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result10.txt"
USING Outputters.Text();

OUTPUT @result11
TO "ReferenceGuide/DataTpes/BuiltInComplex/MAP/result11.txt"
USING Outputters.Text();
```

**SQL.MAP - Additional Examples 1**  
```sql
// Data set where phone values initially appear as a string.
@employees = 
    SELECT * FROM 
        ( VALUES
        ("Noah",   "cell:030-0074321,office:030-0076545"),
        ("Sophia", "office:(5) 555-3745,cell:(5) 555-4729"),
        ("Liam",   "cell:(5) 555-3932"),
        ("Amy",    "office:(171) 555-6750")
        ) AS T(EmpName, PhoneNumbers);

// Parse through PhoneNumbers and create a new data set with a SQL.MAP column type.  All subsequent queries will be against the @map rowset.
@map =
    SELECT EmpName,
           new SQL.MAP<string, string>(from p in PhoneNumbers.Split(',') select new KeyValuePair<string, string>(p.Split(':') [0], p.Split(':') [1])) AS PhoneNumberMap
    FROM @employees;
/********************************/


// Basic query using CROSS APPLY EXPLODE
@result =
    SELECT EmpName,
           r.key.Trim() AS PhoneType, r.value AS PhoneNumber
    FROM @map
         CROSS APPLY
             EXPLODE(PhoneNumberMap) AS r(key, value);

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/ExampleA.csv"
USING Outputters.Csv(outputHeader: true);


// Modified format using OUTER UNION
@result =
    SELECT EmpName, c.value AS Cell
    FROM @map CROSS APPLY EXPLODE(PhoneNumberMap) AS c(key, value) WHERE c.key == "cell"
    OUTER UNION BY NAME ON (EmpName)
    SELECT EmpName, o.value AS Office 
    FROM @map CROSS APPLY EXPLODE(PhoneNumberMap) AS o(key, value) WHERE o.key == "office";

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/ExampleB.csv"
USING Outputters.Csv(outputHeader: true);


//  Cell numbers only
@result =
    SELECT EmpName, c.value AS Cell
    FROM @map
         CROSS APPLY
             EXPLODE(PhoneNumberMap) AS c(key, value)
    WHERE c.key == "cell";

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/ExampleC.csv"
USING Outputters.Csv();


// Using an OUTER JOIN to deliver Cell and Office numbers in a certain order regardless of order in SQL.MAP array.
@result =
    SELECT cc.EmpName ?? oo.EmpName AS Employee,
    cc.Cell, oo.Office
    FROM
    (SELECT EmpName, c.value AS Cell
    FROM @map AS aa CROSS APPLY EXPLODE(PhoneNumberMap) AS c(key, value) WHERE c.key == "cell") AS cc
    FULL OUTER JOIN 
    (SELECT EmpName, o.value AS Office 
    FROM @map CROSS APPLY EXPLODE(PhoneNumberMap) AS o(key, value) WHERE o.key == "office") AS oo
    ON cc.EmpName == oo.EmpName;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/ExampleD.csv"
USING Outputters.Csv(outputHeader: true);


// Same result as above using conditions and calling SQL.MAP values by index position.
@result =
    SELECT EmpName, 
        (PhoneNumberMap.Count == 2) ? 
            (PhoneNumberMap.Keys[0].Trim() == "cell") ? PhoneNumberMap.Values[0] : PhoneNumberMap.Values[1] : 
        (PhoneNumberMap.Keys[0].Trim() == "cell") ? PhoneNumberMap.Values[0] : "no cell number" AS Cell,
        (PhoneNumberMap.Count == 2) ? 
            (PhoneNumberMap.Keys[0].Trim() == "office") ? PhoneNumberMap.Values[0] : PhoneNumberMap.Values[1] : 
        (PhoneNumberMap.Keys[0].Trim() == "office") ? PhoneNumberMap.Values[0] : "no office number" AS Office            
    FROM @map;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/ExampleE.csv"
USING Outputters.Csv(outputHeader: true);
```

**SQL.MAP - Additional Examples 2**  
```sql
// Data set where phone values initially appear as SQL.MAP.
DECLARE @ma2p = new SQL.MAP<string, string>{{"office", "030-0076545"}, {"cell", "030-0074321"}, {"a key", "a value"}};

@map = 
    SELECT
        new SqlMap<string, string>{{"cell", "(5) 555-4729"}} AS PhoneNumberMap,
        new SQL.MAP<string, string>{{"office", "(5) 555-3745"}} AS PhoneNumberMap2,
        @ma2p AS PhoneNumberMap3
    FROM 
        (VALUES 
        (1)
        ) AS T(dummyTable);


// Querying by index position
@result =
    SELECT 
        PhoneNumberMap3.Keys[0] AS Key0,
        PhoneNumberMap3.Values[0]AS Value0
    FROM @map;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/Example1.csv"
USING Outputters.Csv();


// Keys only
@result =
    SELECT r.key AS PhoneType
    FROM @map
         CROSS APPLY
             EXPLODE(PhoneNumberMap3.Keys) AS r(key);

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/Example2.csv"
USING Outputters.Csv();


// Combining results
@result =
    SELECT a.key.Trim() AS PhoneType1,
           a.value AS PhoneNumber1,
           b.key.Trim() AS PhoneType2,
           b.value AS PhoneNumber2
    FROM @map
         CROSS APPLY
             EXPLODE(PhoneNumberMap) AS a(key, value)
         CROSS APPLY
             EXPLODE(PhoneNumberMap2) AS b(key, value);

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/Example3.csv"
USING Outputters.Csv();  


// Combining results using UNION 
@result =
    SELECT r.key.Trim() AS PhoneType,
           r.value AS PhoneNumber
    FROM @map
         CROSS APPLY
             EXPLODE(PhoneNumberMap) AS r(key, value)
    UNION
    SELECT r.key.Trim() AS PhoneType,
           r.value AS PhoneNumber
    FROM @map
         CROSS APPLY
             EXPLODE(PhoneNumberMap2) AS r(key, value);

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/Example4.csv"
USING Outputters.Csv();
```

<a name="ReadStringMap">**User-Defined Function - ReadStringMap/WriteQuotedStringMap**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.

```csharp
using System;
using System.Linq;
using System.Collections.Generic;
using Microsoft.Analytics.Types.Sql;

// slightly modied version from:
// https://github.com/Azure/usql/blob/master/Examples/AmbulanceDemos/AmbulanceDemoCode/Class1.cs

namespace ReferenceGuide_Examples
{
    public class MyClass
    {
        // transforms the input string val into a SQL.MAP instance using the provided delimiters to separate key-value pairs and the key and value in each pair.
        // Both the key and value types are string.
        public static SqlMap<string, string> ReadStringMap(string val, string map_item_delim, string map_kv_delim)
        {
            return new SqlMap<string, string>(
                from p in val.Split(new string[]
                {
                    map_item_delim
                }, StringSplitOptions.None)
                select new KeyValuePair<string, string>(p.Split(new string[]
                {
                    map_kv_delim
                }, StringSplitOptions.None)[0], p.Split(new string[]
                {
                    map_kv_delim
                }, StringSplitOptions.None)[1]));
        }
        
        // transforms a SQL.MAP<string, string> into a quoted string, using the provided delimiters to delimit keys and values and key-value pairs.
        public static string WriteQuotedStringMap(SqlMap<string, string> m, string map_item_delim = ",", string map_kv_delim = ":")
        {
            return "\"" + string.Join(map_item_delim,
                from p in m
                select string.Format("{0}{1}{2}", p.Key, map_kv_delim, p.Value)) + "\"";
        }
    }
}
```

**Using User-Defined Function - ReadStringMap/WriteQuotedStringMap**  
Function `ReadStringMap` transforms the input string val into a SQL.MAP instance using the provided delimiters to separate key-value pairs and the key and value in each pair. Function `WriteQuotedStringMap` transforms a SQL.MAP\<string, string> into a quoted string, using the provided delimiters to delimit keys and values and key-value pairs.
Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  

```sql
@employees = 
    SELECT * FROM 
        ( VALUES
        ("Noah",   "cell:030-0074321,office:030-0076545"),
        ("Sophia", "office:(5) 555-3745,cell:(5) 555-4729"),
        ("Liam",   "cell:(5) 555-3932"),
        ("Amy",    "office:(171) 555-6750")
        ) AS T(EmpName, PhoneNumbers);

@map = 
    SELECT  EmpName,
            ReferenceGuide_Examples.MyClass.ReadStringMap(PhoneNumbers, ",", ":") AS PhoneNumberMap
    FROM @employees;

// Exploded
@result =
    SELECT EmpName,
           r.key.Trim() AS PhoneType, r.value AS PhoneNumber
    FROM @map
         CROSS APPLY
             EXPLODE(PhoneNumberMap) AS r(key, value);

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/ExampleA_ReadStringMap.csv"
USING Outputters.Csv(outputHeader: true);

// Return the new SQL.MAP created above back to a string
@result =
    SELECT EmpName,
           ReferenceGuide_Examples.MyClass.WriteQuotedStringMap(PhoneNumberMap) AS BackToString
    FROM @map;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_MAP/ExampleA_WriteQuotedStringMap.csv"
USING Outputters.Csv(outputHeader: true);
```

**SQL.ARRAY**   
```sql
// Data sets
@popularCities1 = 
    SELECT * FROM 
        ( VALUES
        ("Washington", "Seattle;Spokane;Tacoma;Vancouver;Bellevue"),
        ("Arizona", "Phoenix;Tucson;Mesa;Chandler;Glendale")
        ) AS T(State, Cities);

@popularCities2 = 
    SELECT * FROM 
        ( VALUES
        ("Oregon", "Portland"),
        ("Oregon", "Eugene"),
        ("Oregon", "Salem"),
        ("Oregon", "Gresham"),
        ("Oregon", "Hillsboro")
        ) AS T(State, City);

@popularCities3 = 
    SELECT * FROM 
        ( VALUES
        ("Utah", "Salt Lake City", "West Valley City", "Provo")
        ) AS T(State, City1, City2, City3);

@popularCities4 = 
    SELECT * FROM 
        ( VALUES
        ("Idaho",   new SQL.ARRAY<string>{"Boise","Nampa","Meridian","Idaho Falls"}),
        ("Montana", new SqlArray<string>{"Billings","Missoula","Great Falls","Bozeman","Butte"}),              // alternative creation
        ("Alaska",  SqlArray.Create(new [] {"Birmingham","Montgomery","Mobile","Huntsville","Tuscaloosa"})),   // alternative creation
        ("Nevada",  new SQL.ARRAY<string>(new [] {"Las Vegas","Henderson","North Las Vegas","Reno;Sparks"}))   // alternative creation
        ) AS T(State, Cities);
/**************************************************************/

// Building an ARRAY 1
@array1 =
    SELECT  State,
            new SQL.ARRAY<string>(Cities.Split(';')) AS Cities
    FROM @popularCities1
    WHERE State == "Washington";

// Building an ARRAY 2
@array2 =
    SELECT  State,
            SqlArray.Create(Cities.Split(';')) AS Cities
    FROM @popularCities1
    WHERE State == "Arizona";

// Building an ARRAY 3
@array3 =
    SELECT  State,
            ARRAY_AGG(City) AS Cities
    FROM @popularCities2
    GROUP BY State;

// Building a ARRAY 4
@array4 = 
    SELECT  State,
            new SQL.ARRAY<string>{City1, City2, City3} AS Cities
    FROM @popularCities3;

// UNION all arrays
@combinedCities =
    SELECT * FROM @array1
    UNION ALL
    SELECT * FROM @array2
    UNION ALL
    SELECT * FROM @array3
    UNION ALL
    SELECT * FROM @array4
    UNION ALL
    SELECT * FROM @popularCities4;

// Flatten results
@result1 =
    SELECT  State,
            r.City AS City
    FROM @combinedCities
    CROSS APPLY EXPLODE(Cities) AS r(City);

// return Cities as one comma delimited string per State
@result2 =
    SELECT State,
           string.Join(";", Cities) AS Cities
    FROM @combinedCities;


// Use array index
@result3 =
    SELECT State,
           Cities[0]AS FirstCity
    FROM @combinedCities;

// Array length; The number of Cities per State
@result4 =
    SELECT State,
           Cities.Count AS CityCount1,
           Cities.Count() AS CityCount2 // less efficient
    FROM @combinedCities;

// The number of Cities Arrays per State
@result5 =
    SELECT State,
           COUNT(Cities) AS numArrays
    FROM @combinedCities
    GROUP BY State;

// Filtering
@result6a =
    SELECT  State, r.City
    FROM @combinedCities
    CROSS APPLY EXPLODE(Cities) AS r(City)
    WHERE r.City.StartsWith("B");

// Filtering
@result6b =
    SELECT State
    FROM @combinedCities
    WHERE Cities.Contains("Seattle");

// Creating an array from another array
/*
@data1 =
    SELECT State,
           new SQL.ARRAY<string>(Cities)  AS Cities
    FROM @combinedCities;
*/

// Adding an item to the array; adding a city
@array1 =
    SELECT State,
           new SQL.ARRAY<string>(Cities){"Redmond"}  AS Cities
    FROM @array1;

@result7a =
    SELECT State,
           r.City AS City
    FROM @array1
    CROSS APPLY EXPLODE(Cities) AS r(City);


// Adding an item to a specified array; adding a city to Washington and Idaho
@combinedCities =
    SELECT State,
           (State == "Washington") ? new SQL.ARRAY<string>(Cities){"Yakima"} :                    // method 1
           (State == "Idaho") ? SqlArray.Append(Cities, new []{"Pocatello"}) : Cities AS Cities   // method 2
    FROM @combinedCities;

@result7b =
    SELECT State,
           r.City AS City
    FROM @combinedCities
    CROSS APPLY EXPLODE(Cities) AS r(City);


OUTPUT @result1
TO "ReferenceGuide/DataTpes/BuiltInComplex/ARRAY/result1.txt"
ORDER BY State
USING Outputters.Text();

OUTPUT @result2
TO "ReferenceGuide/DataTpes/BuiltInComplex/ARRAY/result2.txt"
USING Outputters.Text();

OUTPUT @result3
TO "ReferenceGuide/DataTpes/BuiltInComplex/ARRAY/result3.txt"
USING Outputters.Text();

OUTPUT @result4
TO "ReferenceGuide/DataTpes/BuiltInComplex/ARRAY/result4.txt"
USING Outputters.Text();

OUTPUT @result5
TO "ReferenceGuide/DataTpes/BuiltInComplex/ARRAY/result5.txt"
USING Outputters.Text();

OUTPUT @result6a
TO "ReferenceGuide/DataTpes/BuiltInComplex/ARRAY/result6a.txt"
USING Outputters.Text();

OUTPUT @result6b
TO "ReferenceGuide/DataTpes/BuiltInComplex/ARRAY/result6b.txt"
USING Outputters.Text();

OUTPUT @result7a
TO "ReferenceGuide/DataTpes/BuiltInComplex/ARRAY/result7a.txt"
USING Outputters.Text();

OUTPUT @result7b
TO "ReferenceGuide/DataTpes/BuiltInComplex/ARRAY/result7b.txt"
USING Outputters.Text();
```

**SQL.ARRAY - Additional Examples**   
This example converts the `Books` values into the `SQL.ARRAY` type AS `BooksArray`.  Then each value in the array is returned separately by passing the index position.
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

@result =
    SELECT BooksArray[0] AS Book,
           BooksArray[1].TrimStart() AS Author,
           BooksArray[2].TrimStart() AS [Publication Year]
    FROM @array;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/exampleA.csv"
USING Outputters.Csv();
```

**SQL.ARRAY - Alternate example**   
Similiar as above; however, values are inputted directly as `SQL.ARRAY`.
```sql
@someBooks2 = 
    SELECT * FROM 
        ( VALUES
        (new SQL.ARRAY<string>{"The Book Thief", "Markus Zusak", "2005"}),
        (new SQL.ARRAY<string>{"The Girl with the Dragon Tattoo", "Stieg Larsson", "2005"}),
        (new SQL.ARRAY<string>{"The Silver Linings Playbook", "Matthew Quick", "2008"}),
        (new SQL.ARRAY<string>{"Sarah's Key", "Tatiana de Rosnay", "2006"})
        ) AS T(BooksArray);

@result2 =
    SELECT BooksArray[0] AS Book,
           BooksArray[1].TrimStart() AS Author,
           BooksArray[2].TrimStart() AS [Publication Year]
    FROM @someBooks2;

OUTPUT @result2
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/exampleB.csv"
USING Outputters.Csv();
```

<a name="ReadIntArray">**User-Defined Function - ReadIntArray/WriteQuotedIntArray**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.

```csharp
using System;
using System.Linq;
using Microsoft.Analytics.Types.Sql;

// slightly modied version from:
// https://github.com/Azure/usql/blob/master/Examples/AmbulanceDemos/AmbulanceDemoCode/Class1.cs

namespace ReferenceGuide_Examples
{
    public class MyClass
    {
        // returns a SQL.ARRAY<int> from the input string val using the provided array item delimiter.
        public static SqlArray<int> ReadIntArray(string val, string array_item_delim)
        {
            return new SqlArray<int>(
                from x in val.Split(new string[]
                {
                    array_item_delim
                }, StringSplitOptions.None)
                select Convert.ToInt32(x));
        }

        // transforms a SQL.ARRAY<int> into a quoted string using the provided array item delimiter.
        public static string WriteQuotedIntArray(SqlArray<int> a, string array_item_delim = ",")
        {
            return "\"" + string.Join<int>(array_item_delim, a) + "\"";
        }
    }
}
```

**Using User-Defined Function - ReadIntArray/WriteQuotedIntArray**  
Function `ReadIntArray` returns a SQL.ARRAY\<int> from the input string val using the provided array item delimiter.
Function `WriteQuotedIntArray` transforms a SQL.ARRAY\<int> into a quoted string using the provided array item delimiter.
Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**. 
 
```sql
@someStrings = 
    SELECT * FROM 
        ( VALUES
        ("0, 1, 2, 3, 4, 5, 6, 7, 8, 9")
        ) AS T(strings);

// transform to array
@newArray =
    SELECT ReferenceGuide_Examples.MyClass.ReadIntArray(strings, ",") AS newArray
    FROM @someStrings;

// view array by position
@result =
    SELECT newArray[0] AS position0,
           newArray[3] AS position3
    FROM @newArray;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_ARRAY/ReadIntArray_position.csv"
USING Outputters.Csv(outputHeader: true);


// view array exploded
@array_exploded =  
    SELECT array_exploded 
    FROM @newArray
    CROSS APPLY  
    EXPLODE(newArray) AS r(array_exploded);

OUTPUT @array_exploded
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_ARRAY/ReadIntArray_exploded.csv"
USING Outputters.Csv(outputHeader: true);


// return back to string
@result =
    SELECT ReferenceGuide_Examples.MyClass.WriteQuotedIntArray(newArray) AS BackToString
    FROM @newArray;

OUTPUT @result
TO "/Output/ReferenceGuide/Concepts/TypesAndLiterals/BuiltIn/Complex/SQL_ARRAY/WriteQuotedIntArray.csv"
USING Outputters.Csv(outputHeader: true);
```

  
### See Also
* [Data Types and Literals (U-SQL)](data-types-and-literals-u-sql.md)  
* [EXPLODE (U-SQL)](explode-u-sql.md) 
* [MAP_AGG (U-SQL)](map-agg-u-sql.md)   
* [ARRAY_AGG (U-SQL)](array-agg-u-sql.md)

