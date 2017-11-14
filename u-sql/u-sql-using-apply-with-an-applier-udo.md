---
title: "U-SQL Using APPLY with an Applier UDO | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3e647aa1-46bd-4fd3-a586-3ef06d1e5667
caps.latest.revision: 18
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Using APPLY with an Applier UDO
U-SQL’s [user-defined operators](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-objects--udo)
 (UDOs) provide the ability to write your own custom Applier in C#. The following provides the syntax of the applier expression as you call it in an APPLY.  
  
<table><th>Syntax</th><tr><td><pre>
Applier_Expression :=                                                                                    
     ['USING'] <a href="#ATE">applier_type_expression</a> <a href="#DTAT">Derived_Table_Alias_With_Types</a>
     [<a href="#ROC">Readonly_Clause</a>] [<a href="#RQC">Required_Clause</a>].
</pre></td></tr></table>
  
### Semantics of Syntax Elements  
-   <a name="ATE"></a>**`applier_type_expression`**  
    The applier typed expression creates an Applier UDO and in addition to the input row data, takes the derived table schema definition as its input as well as the provided clauses. Unlike [EXPLODE](explode-u-sql.md) (or in general rowset expressions) an Applier uses the UDO programming model to get access to the incoming row and to return zero to many rows as a result. If the expression is not resulting in an instance of an IApplier, an error is raised. The result will be typed as specified in the derived table schema. 
     
    For more information on the UDO programming model see [U-SQL Programmability Guide: User-Defined Applier](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-applier).  
  
- <a name="DTAT"></a>**`Derived_Table_Alias_With_Types`**   
Because the UDO model requires knowledge of the column data types, the derived table schema specification requires the column data types to be specified.  
  
   <table><th>Syntax</th><tr><td><pre>
Derived_Table_Alias_With_Types :=                                                                   
     'AS' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> '(' Column_Definition_List ')'.  
</pre></td></tr></table>
      
- <a name="ROC"></a>**`Readonly_Clause`**    
The optional READONLY clause can help the UDO programmer to write more efficient code.  The optional READONLY clause specifies that either all columns (if specified with *) or the specified columns are read only for the Applier and will be passed through to the output using either the same name or the specified column name in parenthesis.  
  
   <table><th>Syntax</th><tr><td><pre>
Readonly_Clause :=                                                                                  
    'READONLY' Star_Or_Readonly_Column_List.<br />
Star_Or_Readonly_Column_List :=  
    '*' | Readonly_Column_List.<br />
Readonly_Column_List :=  
    Readonly_Column { ',' Readonly_Column }.<br />
Readonly_Column :=  
    Column_Identifier [Output_Column_Dependency_Alias].<br />
Output_Column_Dependency_Alias :=  
    '(' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> ')'.  
</pre></td></tr></table>
  
- <a name="RQC"></a>**`Required_Clause`**    
The optional `REQUIRED` clause can help the UDO programmer to write more efficient code. The optional `REQUIRED` clause specifies that either all columns are required on input for the Applier (if specified with *) or the specified columns are required. If a specified column is followed by a list of columns in parenthesis, then the input column is only required if the columns in that list are referenced from the output.  
  
   <table><th>Syntax</th><tr><td><pre>
Required_Clause :=                                                                                  
    'REQUIRED' Star_Or_Required_Column_List.<br />
Star_Or_Required_Column_List :=  
    '*' | Required_Column_List.<br />
Required_Column_List :=  
    Required_Column { ',' Required_Column}.<br />
Required_Column :=  
    Column_Identifier [Required_Output_Column_Dependency_List].<br />
Required_Output_Column_Dependency_List :=  
    '(' Identifier_List ')'.  
</pre></td></tr></table>
  
### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](extending-u-sql-expressions-with-user-code.md#usingAssemblies).

<a name="ParserApplier">**ParserApplier**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.
```csharp
using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Types.Sql;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;

namespace ReferenceGuide_Examples
{
    [SqlUserDefinedApplier]
    public class ParserApplier : IApplier
    {
        private string parsingPart;

        public ParserApplier(string parsingPart)
        {
            if (parsingPart.ToUpper().Contains("ALL")
                || parsingPart.ToUpper().Contains("FORMALNAME")
                || parsingPart.ToUpper().Contains("ISOALPHA3CODE")
                || parsingPart.ToUpper().Contains("LATESTRECORDEDPOPULATION")
                || parsingPart.ToUpper().Contains("REGION")
                || parsingPart.ToUpper().Contains("SUBREGION")
                )
            {
                this.parsingPart = parsingPart;
            }
            else
            {
                throw new ArgumentException("Incorrect parameter. Please use: 'ALL[FORMALNAME|ISOALPHA3CODE|LATESTRECORDEDPOPULATION|REGION|SUBREGION]'");
            }
        }

        public override IEnumerable<IRow> Apply(IRow input, IUpdatableRow output)
        {
            string[] properties = input.Get<string>("Properties").Split(',');

            //  only process with correct number of properties
            if (properties.Count() == 5)
            {
                string FormalName = properties[0];
                string IsoAlpha3Code = properties[1];
                int LatestRecordedPopulation = -1;
                string Region = properties[3];
                string Subregion = properties[4];

                // Only return LatestRecordedPopulation if it is number, otherwise, -1
                if (!int.TryParse(properties[2], out LatestRecordedPopulation))
                {
                    LatestRecordedPopulation = -1;
                }

                if (parsingPart.ToUpper().Contains("FORMALNAME") || parsingPart.ToUpper().Contains("ALL")) output.Set<string>("FormalName", FormalName);
                if (parsingPart.ToUpper().Contains("ISOALPHA3CODE") || parsingPart.ToUpper().Contains("ALL")) output.Set<string>("IsoAlpha3Code", IsoAlpha3Code);
                if (parsingPart.ToUpper().Contains("LATESTRECORDEDPOPULATION") || parsingPart.ToUpper().Contains("ALL")) output.Set<int>("LatestRecordedPopulation", LatestRecordedPopulation);
                if (parsingPart.ToUpper().Equals("REGION") || parsingPart.ToUpper().Contains("ALL")) output.Set<string>("Region", Region);
                if (parsingPart.ToUpper().Contains("SUBREGION") || parsingPart.ToUpper().Contains("ALL")) output.Set<string>("Subregion", Subregion);
            }
            yield return output.AsReadOnly();
        }
    }
}
```
 
**Using ParserApplier**   
The user-defined Applier acts as a comma-delimited value parser for the country properties.  Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```U-SQL
@countries = 
    SELECT * FROM 
        ( VALUES
        (1, "Afghanistan", "Islamic State of Afghanistan,AFG,28400000,Asia,Southern Asia"),
        (3, "Albania", "Republic of Albania,ALB,3785031,Europe,Southern Europe"),
        (4, "Algeria", "People's Democratic Republic of Algeria,DZA,34178188,Africa,Northern Africa"),
        (6, "Andorra", "Principality of Andorra,AND,87243,Europe,Southern Europe"),
        (7, "Angola", "People's Republic of Angola,AGO,12799293,Africa,Middle Africa"),
        (10, "Antigua and Barb.", "Antigua and Barbuda,ATG,85632,Americas,Caribbean"),
        (11, "Argentina", "Argentine Republic,ARG,42550127,Americas,South America"),
        (12, "Armenia", "Republic of Armenia,ARM,2967004,Asia,Western Asia"),
        (15, "Australia", "Commonwealth of Australia,AUS,22997671,Oceania,Australia and New Zealand"),
        (16, "Austria", "Republic of Austria,AUT,2,Europe,Western Europe")
        ) AS T(CountryID, CountryName, Properties);

@result =
    SELECT
        c.CountryID,
        c.CountryName,
        Properties.FormalName,
        Properties.IsoAlpha3Code,
        Properties.LatestRecordedPopulation,
        Properties.Region,
        Properties.Subregion
    FROM @countries AS c
    CROSS APPLY
        new ReferenceGuide_Examples.ParserApplier ("all") AS Properties(
            FormalName string, 
            IsoAlpha3Code string, 
            LatestRecordedPopulation int, 
            Region string, 
            Subregion string);

OUTPUT @result
TO "/Output/ReferenceGuide/StatementsAndExpressions/Appplier/exampleA.txt"
USING Outputters.Text();
```

**U-SQL's CROSS/OUTER APPLY with VALUES**   
The VALUES clause allows to apply each row of the constructed rowset to be correlated to each row in the rowset source.
```
@bands = 
  SELECT * 
  FROM (VALUES ("Beatles", "George Harrison, John Lennon, Paul McCartney, Ringo Starr"), 
               ("Creedence Clearwater Revival", "Doug Clifford, John Fogerty, Stu Cook, Tom Fogerty"), 
               ("Eagles", "Don Henley, Glenn Frey, Joe Walsh, Timothy Schmit"), 
               ("Pink Floyd", "David Gilmour, Nick Mason, Richard Wright, Roger Watters, Syd Barrett"), 
               ("Rolling Stones", "Charlie Watts, Keith Richards, Mick Jagger, Ronnie Wood")) AS Bands(name, members);

@ca_val1 = SELECT * FROM @bands CROSS APPLY VALUES (1) AS T(x);
@ca_val2 = SELECT * FROM @bands CROSS APPLY VALUES (1),(name.Length) AS T(x);
@ca_val3 = SELECT * FROM @bands CROSS APPLY VALUES (1,name.Length,3) AS T(x,y,z);

OUTPUT @ca_val1 
TO "/output/ReferenceGuide/DML/Appplier/crossapply_value1.csv" 
USING Outputters.Csv();

OUTPUT @ca_val2 
TO "/output/ReferenceGuide/DML/Appplier/crossapply_value2.csv" 
USING Outputters.Csv();

OUTPUT @ca_val3 
TO "/output/ReferenceGuide/DML/Appplier/crossapply_value3.csv" 
USING Outputters.Csv();
```
 
### See Also 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md)
* [FROM Clause (U-SQL)](from-clause-u-sql.md) 
* [SELECT Expression (U-SQL)](select-expression-u-sql.md) 
* [U-SQL SELECT Selecting from CROSS APPLY and OUTER APPLY](u-sql-select-selecting-from-cross-apply-and-outer-apply.md)  
* [Output Statement (U-SQL)](output-statement-u-sql.md)  
* [U-SQL Programmability Guide: User-Defined Applier](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-applier)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)  
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)

