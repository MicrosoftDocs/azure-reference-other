---
title: "join clause (Query Syntax in U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "07/01/2018"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
caps.latest.revision: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# join clause (Query Syntax in U-SQL)
The `join` clause is useful for associating elements from different source sequences that have no direct relationship in the object model.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
 
### A.    Basic Examples
The examples in this section utilize the dataset below:  
**Dataset**  
```sql
DECLARE @categories = new SQL.MAP<int, string>{
                            {001, "Beverages"},
                            {002, "Condiments"},
                            {003, "Vegetables"},
                            {004, "Grains"},
                            {005, "Fruit"}            
                            };

DECLARE @products = new SQL.MAP<string, int?>{
                          {"Cola", 001},
                          {"Tea", 001},
                          {"Mustard", 002},
                          {"Pickles", 002},
                          {"Carrots", 003},
                          {"Bok Choy", 003},
                          {"Peaches", 005},
                          {"Melons", 005}
                          };
```

**Inner Join**  
```sql
DECLARE @innerJoinQuery =
    from category in @categories
    join prod in @products on category.Key equals prod.Value
    select new SQL.ARRAY<string>{ prod.Key, category.Value };

@result1 = 
        SELECT  T.value[0] AS productName,
                T.value[1] AS categoryName              
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@innerJoinQuery) AS T(value);

OUTPUT @result1
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/example1.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Group Join**   
```sql
DECLARE @groupJoinQuery =
            (from category in @categories
            join product in @products on category.Key equals product.Value into prodGroup
            from prod in prodGroup
            orderby prod.Value
            select new { Category = prod.Value, ProductName = prod.Key })
           .ToDictionary(k => k.ProductName, v => v.Category);

@result2 = 
        SELECT  T.key AS productName,
                T.value AS categoryID              
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@groupJoinQuery) AS T(key, value);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/example2.txt"
USING Outputters.Tsv(outputHeader: true);
```

**Left Outer Join**   
```sql
DECLARE @leftOuterQuery =
        (from category in @categories
        join prod in @products on category.Key equals prod.Value into prodGroup
        from item in prodGroup.DefaultIfEmpty()
        select new { Name = item.Key == null ? "Nothing!" : item.Key, CategoryID = category.Key })
       .ToDictionary(k => k.Name, v => v.CategoryID);

@result3 = 
        SELECT  T.key AS productName,
                T.value AS categoryID              
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@leftOuterQuery) AS T(key, value);

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/example3.txt"
USING Outputters.Tsv(outputHeader: true);
```

### B.    Inner Join - Complex Examples
The examples in this section utilize the dataset below:  
**Dataset**  
```sql
// One level of nesting
DECLARE @people = new List<SQL.MAP<string, string>>{ @magnus, @terry, @charlotte, @arlene, @rui };

// No nesting; variant of @people
DECLARE @people2 = new SQL.MAP<string, string>{
                        {"Magnus", "Hedlund"}, {"Terry", "Adams"}, {"Charlotte", "Weiss"},
                        {"Arlene", "Huff"}, {"Rui", "Raposo"} 
                        };

// Two levels of nesting
DECLARE @cats = new List<SQL.MAP<string, SQL.MAP<string, string>>> { @barley, @boots, @whiskers, @bluemoon, @daisy };
DECLARE @dogs = new List<SQL.MAP<string, SQL.MAP<string, string>>> { @fourwheeldrive, @duke, @denim, @wiley, @snoopy, @snickers };

// One level of nesting; variant of @cats
DECLARE @cats2 = new SQL.MAP<string, SQL.MAP<string, string>>{
                 {"Barley", @terry},
                 {"Boots", @terry},
                 {"Whiskers", @charlotte},
                 {"Blue Moon", @rui},
                 {"Daisy", @magnus}
                 };

// No nesting; variant of @cats2
DECLARE @cats3 = new SQL.MAP<string, string>{
                        {"Barley", "Terry"},
                        {"Boots", "Terry"},
                        {"Whiskers", "Charlotte"},
                        {"Blue Moon", "Rui"},
                        {"Daisy", "Magnus"}
                        };
```

**Joining on Nested Values** 
```sql
// Simple key join example (Two levels of nested values)
DECLARE @query1a = ( from x in @people from person in x
                    join cat in (from y in @cats from cat in y select cat)
                    on 
                    new {FirstName = person.Key, LastName = person.Value} // this works; don't modify
                    equals  
                    new {FirstName = cat.Value.Keys[0], LastName = cat.Value.Values[0]} // this works; don't modify
                    select new {catName = cat.Key, OwnerName = person.Key}
                  ).ToDictionary(k => k.catName, v => v.OwnerName);

// slightly less complicated (One level of nested values)
DECLARE @query1b = ( from person in @people2
                    join cat in @cats2
                    on 
                    new {FirstName = person.Key, LastName = person.Value} // this works; don't modify
                    equals  
                    new {FirstName = cat.Value.Keys[0], LastName = cat.Value.Values[0]} // this works; don't modify
                    select new {catName = cat.Key, OwnerName = person.Key}
                  ).ToDictionary(k => k.catName, v => v.OwnerName);

// Least complicated; no nested values
DECLARE @query1c = ( from person in @people2
                    join cat in @cats3
                    on person.Key
                    equals  
                    cat.Value 
                    select new {catName = cat.Key, OwnerName = person.Key}
                  ).ToDictionary(k => k.catName, v => v.OwnerName);

@result1a = 
        SELECT  T.key + " is owned by " + T.value AS catsAndOwners
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query1a) AS T(key, value);

@result1b = 
        SELECT  T.key + " is owned by " + T.value AS catsAndOwners
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query1b) AS T(key, value);

@result1c = 
        SELECT  T.key + " is owned by " + T.value AS catsAndOwners
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query1c) AS T(key, value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/inner/example1a.txt"
USING Outputters.Tsv();

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/inner/example1b.txt"
USING Outputters.Tsv();

OUTPUT @result1c
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/inner/example1c.txt"
USING Outputters.Tsv();
```

**Inner join by using grouped join**    
Variant of @query1a, above.
```sql
DECLARE @query2 = from x in @people from person in x
                  join cat in (from y in @cats from cat in y select cat)
                  on
                  new {FirstName = person.Key, LastName = person.Value} // this works; don't modify
                  equals
                  new {FirstName = cat.Value.Keys[0], LastName = cat.Value.Values[0]}
                  into gj
                  from subpet in gj
                  select new SQL.ARRAY<string>{subpet.Key, person.Key};

@result2 = 
        SELECT  T.value[0] + " is owned by " + T.value[1] AS catsAndOwners
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query2) AS T(value);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/inner/example2.txt"
USING Outputters.Tsv();
```

**Multiple joins**  
```sql
DECLARE @query3 =   from x in @people from person in x
                    join cat in (from y in @cats from cat in y select cat)
                    on 
                    new {FirstName = person.Key, LastName = person.Value} 
                    equals  
                    new {FirstName = cat.Value.Keys[0], LastName = cat.Value.Values[0]} 
                    join dog in (from z in @dogs from dog in z select dog)
                    on   
                    new {FirstName = person.Key, LastName = person.Value, Letter = cat.Key.Substring(0,1)}
                    equals  
                    new {FirstName = dog.Value.Keys[0], LastName = dog.Value.Values[0], Letter = dog.Key.Substring(0,1)} 
                    select new SQL.ARRAY<string> {cat.Key, dog.Key};

@result3 = 
        SELECT  "The cat, " +
                T.value[0] + 
                ", shares a house, and the first letter of its name with the dog " + 
                T.value[1] AS catsAndOwners
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query3) AS T(value);

OUTPUT @result3
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/inner/example3.txt"
USING Outputters.Tsv();
```

### C.    Left Outer Join - Complex Example
```sql
DECLARE @magnus = new SQL.MAP<string, string>{ {"Magnus", "Hedlund"} };
DECLARE @terry = new SQL.MAP<string, string>{ {"Terry", "Adams"} };
DECLARE @charlotte = new SQL.MAP<string, string>{ {"Charlotte", "Weiss"} };
DECLARE @arlene = new SQL.MAP<string, string>{ {"Arlene", "Huff"} };
DECLARE @rui = new SQL.MAP<string, string>{ {"Rui", "Raposo"} };

DECLARE @barley = new SQL.MAP<string, SQL.MAP<string, string>>{ {"Barley", @terry} };
DECLARE @boots = new SQL.MAP<string, SQL.MAP<string, string>>{ {"Boots", @terry} };
DECLARE @whiskers = new SQL.MAP<string, SQL.MAP<string, string>>{ {"Whiskers", @charlotte} };
DECLARE @bluemoon = new SQL.MAP<string, SQL.MAP<string, string>>{ {"Blue Moon", @rui} };
DECLARE @daisy = new SQL.MAP<string, SQL.MAP<string, string>>{ {"Daisy", @magnus} };

DECLARE @people = new List<SQL.MAP<string, string>>{ @magnus, @terry, @charlotte, @arlene, @rui };
DECLARE @cats = new List<SQL.MAP<string, SQL.MAP<string, string>>> { @barley, @boots, @whiskers, @bluemoon, @daisy };

DECLARE @query1a = ( from x in @people from person in x
                    join cat in (from y in @cats from cat in y select cat)
                    on 
                    new {FirstName = person.Key, LastName = person.Value} 
                    equals  
                    new {FirstName = cat.Value.Keys[0], LastName = cat.Value.Values[0]} 
                    into gj
                    from subpet in gj.DefaultIfEmpty()
                    select new {catName = subpet.Key ?? String.Empty, FirstName = person.Key}
                  ).ToDictionary(k => k.catName, v => v.FirstName);

@result1a = 
        SELECT  T.value + ":\t" + T.key AS catsAndOwners
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@query1a) AS T(key, value);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/leftOuter/example1.txt"
USING Outputters.Tsv(quoting: false);
```

### D.    Group Joins & XML
**Example One**  
```sql
// References
REFERENCE SYSTEM ASSEMBLY [System.Xml];
REFERENCE SYSTEM ASSEMBLY [System.Xml.Linq];

USING XElement = System.Xml.Linq.XElement;

// Dataset
DECLARE @employees = new SQL.MAP<string, string>{ {"Bob", "Sales"}, {"Susan", "Sales"}, {"Willis", "Management"},
                                                  {"Sean", "Sales"}, {"Jennifer", "Management"}, {"Michael", "IT"}
                                                };
 
 // Queries                                               
DECLARE @query1a = new System.Xml.Linq.XElement("EmployeesByDept",
                   from x in @employees
                   group x by x.Value into gb 
                    select new System.Xml.Linq.XElement("Department",
                        new System.Xml.Linq.XAttribute("DeptName", gb.Key),
                        from sub in gb
                        select new System.Xml.Linq.XElement("Employee", sub.Key)));

DECLARE @query1b = new XElement("EmployeesByDept",
                   from x in @employees
                   group x by x.Value into gb 
                    select new XElement("Department", gb.Key,
                        from sub in gb
                        select new XElement("Employee", sub.Key)));


@result1a = 
        SELECT @query1a.ToString() AS xmlWithAttribute
        FROM (VALUES(1)) AS A(x);

@result1b = 
        SELECT @query1b.ToString() AS xml
        FROM (VALUES(1)) AS A(x);

OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/group/example1a.txt"
USING Outputters.Tsv(quoting: false);

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/group/example1b.txt"
USING Outputters.Tsv(quoting: false);
```

**Example Two**  
```sql
// References
REFERENCE SYSTEM ASSEMBLY [System.Xml];
REFERENCE SYSTEM ASSEMBLY [System.Xml.Linq];
USING xx = System.Xml.Linq;

// Datasets
DECLARE @magnus = new SQL.MAP<string, string>{ {"Magnus", "Hedlund"} };
DECLARE @terry = new SQL.MAP<string, string>{ {"Terry", "Adams"} };
DECLARE @charlotte = new SQL.MAP<string, string>{ {"Charlotte", "Weiss"} };
DECLARE @arlene = new SQL.MAP<string, string>{ {"Arlene", "Huff"} };
DECLARE @rui = new SQL.MAP<string, string>{ {"Rui", "Raposo"} };

DECLARE @barley = new SQL.MAP<string, SQL.MAP<string, string>>{ {"Barley", @terry} };
DECLARE @boots = new SQL.MAP<string, SQL.MAP<string, string>>{ {"Boots", @terry} };
DECLARE @whiskers = new SQL.MAP<string, SQL.MAP<string, string>>{ {"Whiskers", @charlotte} };
DECLARE @bluemoon = new SQL.MAP<string, SQL.MAP<string, string>>{ {"Blue Moon", @rui} };
DECLARE @daisy = new SQL.MAP<string, SQL.MAP<string, string>>{ {"Daisy", @magnus} };

DECLARE @people = new List<SQL.MAP<string, string>>{ @magnus, @terry, @charlotte, @arlene, @rui };
DECLARE @cats = new List<SQL.MAP<string, SQL.MAP<string, string>>> { @barley, @boots, @whiskers, @bluemoon, @daisy };


// Query
DECLARE @query2 =   new xx.XElement("PetOwners",
                    from x in @people from person in x
                    join cat in (from y in @cats from cat in y select cat)
                    on 
                    new {FirstName = person.Key, LastName = person.Value} 
                    equals  
                    new {FirstName = cat.Value.Keys[0], LastName = cat.Value.Values[0]} 
                    into gj
                    select new xx.XElement("Person",
                        new xx.XAttribute("FirstName", person.Key),
                        new xx.XAttribute("LastName", person.Value),
                        from subpet in gj
                        select new xx.XElement("Pet", subpet.Key)));

@result2 = 
        SELECT @query2.ToString() AS xml
        FROM (VALUES(1)) AS A(x);

OUTPUT @result2
TO "/ReferenceGuide/cSharp/LINQ/Keywords/join/group/example2.txt"
USING Outputters.Tsv(quoting: false);
```

## See Also
* [join clause (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/join-clause)
* [Join (Method Syntax in U-SQL)](join-method-syntax-in-u-sql.md)
* [U-SQL SELECT Selecting from Joins](u-sql-select-selecting-from-joins.md)
* [Enumerable.Join (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.join)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
* [Perform inner joins](https://docs.microsoft.com/dotnet/csharp/linq/perform-inner-joins)
* [Perform left outer joins](https://docs.microsoft.com/dotnet/csharp/linq/perform-left-outer-joins)
* [Perform grouped joins](https://docs.microsoft.com/dotnet/csharp/linq/perform-grouped-joins)