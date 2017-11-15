---
title: "Output Statement (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 7d6d620e-80c8-450d-b31e-3caae8ca9f1b
caps.latest.revision: 28
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Output Statement (U-SQL)
U-SQL does not only support processing unstructured data with the [EXTRACT](../u-sql/extract-expression-u-sql.md) expression but also provides the OUTPUT Statement that writes a rowset back into an unstructured file.    

The output processing is done in parallel unless otherwise specified. The rowset will be split into parts which then are written into several file parts in parallel which at the end will be stitched together. The degree of parallelism depends on how much data the rowset contains, what the job’s specified degree of parallelism is etc.. Note that the stitching performance depends on the efficiency of the underlying storage system. For example, the stitching of files in the Azure Data Lake is just a meta-data operation and thus very efficient. For more information about the processing model of outputters, please refer to [U-SQL Programmability Guide: User-Defined Outputter](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-outputter).  
  
OUTPUT will provide atomic (all or nothing) semantics. A file is only committed when the script succeeds. If an OUTPUT statement fails for any reason during execution, for example due to a system failure or a user code error in a custom outputter, then the original file (if present) will be preserved and the new file will not be written. Note that this failure will cause the script to fail and any other written file in that script will also be reverted to the before-script status.  
  
OUTPUT will provide snapshot isolation of its writes if the underlying file system provides some form of [multi-version concurrency control](https://en.wikipedia.org/wiki/Multiversion_concurrency_control) (MVCC). This means concurrently executing scripts continue to see the last committed version until the script succeeds. Only jobs started after the script succeeds will see the new file content.  
  
> [!IMPORTANT]
> Of the currently supported file systems, writing to Windows Azure Blob Storage does not provide (MVCC) while writing to Azure Data Lake Storage should (but is currently not working, a fix is under investigation).
  
<table><th align="left">Syntax</th><tr><td><pre>
Output_Statement :=                                                                                      
     'OUTPUT' <a href="#out_row">Output_Rowset</a>   
     TO_Clause   
     [ <a href="#OBOFC">Order_By_Opt_Fetch_Clause</a> ]  
     <a href="#us_cla">USING_Clause</a>.<br />                   
TO_Clause :=
     'TO' <a href="#out_fp">Output_File_Path</a>.
</pre></td></tr></table>
   
### Semantics of Syntax Elements    
- <a name="out_row"></a>**`Output_Rowset`**  
  Specifies the expression that is being written into the target file or files. The supported rowset expressions are any of the following:
  <table><th>Syntax</th><tr><td><pre>
  Output_Rowset :=                                                                                    
       Rowset  
  |    Rowset_Expression.<br />
  Rowset :=                                                                       
       Rowset_Variable
  |    Identifier.<br />
  Rowset_Expression :=
       '(' <a href="query-statements-and-expressions-u-sql.md">Query_Expression</a> ')'
  |    <a href="table-valued-function-expression-u-sql.md">Function_Call</a>
  |    <a href="u-sql-select-selecting-from-an-external-rowset.md">External_Rowset_Expression</a>.
  </pre></td></tr></table>
  
   The simplest rowset sources are a rowset variable that has been defined in a previous statement of the script or a table that has been created in the account’s catalog. A table can be referenced either with its fully 3-part qualified name, within the current database context with a 2-part name or within the current database and schema context with a single-part name.  
  
  Other rowsets that can be output are any query expression inside parenthesis, a table-valued function call or an external rowset expression. Please follow the links to the detailed description of each of the rowset expressions.  
  
- <a name="out_fp"></a>**`Output_File_Path`**     
Specifies the target file or files. The rowset will be written at the specified [output file path](../u-sql/output-to-files-u-sql.md) location atomically. If the file at the output file path already exists, it will be overwritten.  
  
- <a name="OBOFC"></a>**`Order_By_Opt_Fetch_Clause`**     
  The output can be sorted with the optional ORDER BY/FETCH clause.  
  <table><th>Syntax</th><tr><td><pre>
  Order_By_Opt_Fetch_Clause :=                                                                        
       Order_By_Clause [ <a href="order-by-and-offset-fetch-clauses-u-sql.md#off_F">Offset_Fetch</a> ].
  </pre></td></tr></table>
  
  Because the order by list expressions can only refer to columns of the rowset that needs to be outputted, one can only order on data contained in the result or use an order expression that does not refer to a column at all.  
  
  Unlike the [ORDER BY](../u-sql/order-by-and-offset-fetch-clause-u-sql.md) clause on the [SELECT](../u-sql/select-expression-u-sql.md) expression, the `OUTPUT ORDER BY` clause does not require the `OFFSET/FETCH` clause. However, if it is specified it can be used to output only a subset of the data. For further details on the [ORDER BY](../u-sql/order-by-and-offset-fetch-clause-u-sql.md) and `OFFSET/FETCH` syntax and semantics see [ORDER BY and OFFSET/FETCH Clauses (U-SQL)](../u-sql/order-by-and-offset-fetch-clause-u-sql.md).
  
- <a name="us_cla"></a>**`USING_Clause`**   
  The USING clause specifies which outputter should be used to turn the rowset into a file.
  <table><th>Syntax</th><tr><td><pre>
  USING_Clause :=                                                                                     
       'USING' udo_expression.
  </pre></td></tr></table>
  
  It takes a C# expression that returns an instance of IOutputter. U-SQL provides a small set of predefined outputters for common text formats and users can write their own by implementing an IOutputter (see [U-SQL Programmability Guide: User-Defined Outputter](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-outputter) for more detail on how to write your own outputter). The built-in outputters are part of the built-in Outputters namespace. For more information on the built-in `outputters` and their arguments please follow the link.  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](../u-sql/extending-u-sql-expressions-with-user-code.md#usingAssemblies).


**Using Built-In Outputter**    
```
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
    SELECT EmpName,
           Salary ?? 0 AS Salary
    FROM @employees;

DECLARE @out_path string = "/Output/ReferenceGuide/Output/";
DECLARE @out_file string = @out_path + "exampleA.csv";

OUTPUT @result
TO @out_file    // Using a variable
ORDER BY Salary
USING Outputters.Csv();


OUTPUT @result
TO "/Output/ReferenceGuide/Output/exampleB.csv"
ORDER BY Salary DESC
OFFSET 2 ROW    // Can be used without FETCH
FETCH 5 ROWS    // Can be used without OFFSET
USING Outputters.Csv();
```  
---

<a name="HTMLOutputter">**User-Defined Outputter - HTMLOutputter**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.
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
    [SqlUserDefinedOutputter(AtomicFileProcessing = true)]
    public class HTMLOutputter : IOutputter
    {
        // Local variables initialization
        private string row_delimiter;
        private char col_delimiter;
        private bool isHeaderRow;
        private Encoding encoding;
        private bool IsTableHeader = true;
        private Stream g_writer;

        // Parameters definition            
        public HTMLOutputter(bool isHeader = false, Encoding encoding = null)
        {
            this.isHeaderRow = isHeader;
            this.encoding = ((encoding == null) ? Encoding.UTF8 : encoding);
        }

        // Close method is used to write footer to file - executed only once after all rows
        public override void Close()
        {
            //Reference to IO.Stream object - g_writer
            StreamWriter streamWriter = new StreamWriter(g_writer, this.encoding);
            streamWriter.Write("</table>");
            streamWriter.Flush();
            streamWriter.Close();
        }

        public override void Output(IRow row, IUnstructuredWriter output)
        {
            System.IO.StreamWriter streamWriter = new StreamWriter(output.BaseStream, this.encoding);

            // Metadata schema initialization to enumerate column names
            ISchema schema = row.Schema;

            // This is data independent header - HTML table definition
            if (IsTableHeader)
            {
                streamWriter.Write("<table border=1>");
                IsTableHeader = false;
            }

            // HTML table attributes
            string header_wrapper_on = "<th>";
            string header_wrapper_off = "</th>";
            string data_wrapper_on = "<td>";
            string data_wrapper_off = "</td>";

            // Header row output - runs only once
            if (isHeaderRow)
            {
                streamWriter.Write("<tr>");
                for (int i = 0; i < schema.Count(); i++)
                {
                    var col = schema[i];
                    streamWriter.Write(header_wrapper_on + col.Name + header_wrapper_off);
                }
                streamWriter.Write("</tr>");
            }

            // Data row output
            streamWriter.Write("<tr>");
            for (int i = 0; i < schema.Count(); i++)
            {
                var col = schema[i];
                string val = "";
                try
                {
                    // Data type enumeration - require to match the distinct list of types form OUTPUT statement
                    switch (col.Type.Name.ToString().ToLower())
                    {
                        case "string": val = row.Get<string>(col.Name).ToString(); break;
                        case "guid": val = row.Get<Guid>(col.Name).ToString(); break;
                        default: break;
                    }
                }
                // Hnadling NULL values - keeping them empty
                catch (System.NullReferenceException)
                {
                }
                streamWriter.Write(data_wrapper_on + val + data_wrapper_off);
            }
            streamWriter.Write("</tr>");

            if (isHeaderRow)
            {
                isHeaderRow = false;
            }
            // Reference to the instance of the IO.Stream object for footer generation
            g_writer = output.BaseStream;
            streamWriter.Flush();
        }
    }

    // Define the factory classes
    public static class Factory
    {
        public static HTMLOutputter HTMLOutputter(bool isHeader = false, Encoding encoding = null)
        {
            return new HTMLOutputter(isHeader, encoding);
        }
    }

}
```

**Using User-Defined Outputter - HTMLOutputter**  
Output creates an HTML file with table data.  Example is a slightly modified version from [U-SQL Programmability Guide: User-Defined Outputter](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-outputter).  Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```U-SQL
@employees = 
    SELECT * FROM 
        ( VALUES
        (new Guid("c8fc966a-6144-4054-9170-6f05ff240812"), "01/01/2017", "Maria Anders", "Obere Str. 57, Berlin, 12209 Germany"),
        (new Guid("9499718f-1c21-4b78-84e7-3868a7fab280"), "01/02/2017", "Thomas Hardy", "120 Hanover Sq., London, WA1 1DP UK"),
        (new Guid("e1f04df2-b391-4a6c-a66a-9360626f3cdb"), "02/01/2017", "Elizabeth Lincoln", "23 Tsawassen Blvd., Tsawassen BC, T2F 8M4 Canada"),
        (new Guid("5609618a-a77a-4230-bae1-aee126b0f0ac"), "02/02/2017", "Patricio Simpson", "Cerrito 333, Buenos Aires, 1010 Argentina"),
        (new Guid("7ee97a9d-b00b-4b47-8846-020c53ec6f24"), "03/04/2017", "Yang Wang", "Hauptstr. 29, Bern, 3012 Switzerland")
        ) AS T(guid, dt, user, address);

OUTPUT @employees 
TO "/Output/ReferenceGuide/Outut/output_file.html"
USING new ReferenceGuide_Examples.HTMLOutputter(isHeader: true);
```

<a name="DriverOutputter">**User-Defined Outputter - DriverOutputter**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.
```csharp
using System.IO;
using System.Linq;
using System.Text;

using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Types.Sql;

/*
 slightly modied version from:
 https://github.com/Azure/usql/blob/master/Examples/AmbulanceDemos/AmbulanceDemoCode/Class1.cs

The outputter utilizes  three functions which are defined below:
    AddQuotes, WriteQuotedStringMap, and WriteQuotedIntArray
*/


namespace ReferenceGuide_Examples
{
    // DriverFunctions
    //
    // defines a class of utility functions that will be used by the Extractor and can be used as UDFs
    public class DriverFunctions
    {
        // string AddQuotes(string s)
        //
        // returns s with embedded in " and containing " are doubled.
        public static string AddQuotes(string s)
        {
            return "\"" + s.Replace("\"", "\"\"") + "\"";
        }

        // string WriteQuotedStringMap(SqlMap<string, string> m, string map_item_delim = ",", string map_kv_delim = ":")
        //
        // transforms a SQL.MAP<string, string> into a quoted string, using the provided delimiters to delimit keys and values and key-value pairs.
        public static string WriteQuotedStringMap(SqlMap<string, string> m, string map_item_delim = ",", string map_kv_delim = ":")
        {
            return "\"" + string.Join(map_item_delim,
                from p in m
                select string.Format("{0}{1}{2}", p.Key, map_kv_delim, p.Value)) + "\"";
        }

        // string WriteQuotedIntArray(SqlArray<int> a, string array_item_delim = ",")
        //
        // transforms a SQL.ARRAY<int> into a quoted string using the provided array item delimiter.
        public static string WriteQuotedIntArray(SqlArray<int> a, string array_item_delim = ",")
        {
            return "\"" + string.Join<int>(array_item_delim, a) + "\"";
        }
    }

    // DriverOutputter
    //
    // Defines a user-defined outputter that can supports writing CSV-like data from SQL.MAP<string,string> columns and SQL.ARRAY<int> columns.
    // Outputter will write homogeneous row formats and can be parallelized
    //
    // Usage (after registration of assembly and referencing assembly in script, default values shown):
    //   EXTRACT ... FROM ... 
    //   USING new AmbulanceDemoCode.DriverOutputter(row_delim:"\r\n", col_delim: ",",map_item_delim: ",", map_kv_delim:":", array_item_delim:",", encoding:Encoding.UTF8);
    //
    [SqlUserDefinedOutputter]
    public class DriverOutputter : IOutputter
    {
        // Class variables that get set by class initializer
        private string _row_delim;
        private string _col_delim;
        private string _map_item_delim;
        private string _map_kv_delim;
        private string _array_item_delim;
        private Encoding _encoding;

        // DriverOutputter(string row_delim = "\r\n", string col_delim = ",", string map_item_delim = ",", string map_kv_delim = ":", string array_item_delim = ",", Encoding encoding = null)
        //
        // Class initializer that provides optional outputter parameters.
        public DriverOutputter(string row_delim = "\r\n", string col_delim = ",", string map_item_delim = ",", string map_kv_delim = ":", string array_item_delim = ",", Encoding encoding = null)
        {
            this._encoding = ((encoding == null) ? Encoding.UTF8 : encoding);
            this._row_delim = row_delim;
            this._col_delim = col_delim;
            this._map_item_delim = map_item_delim;
            this._map_kv_delim = map_kv_delim;
            this._array_item_delim = array_item_delim;
        }

        // void WriteValue(object val, StreamWriter writer)
        //
        // Helper function that takes a value val and writes it into the output stream. It will convert the value to a string serialization.
        private void WriteValue(object val, StreamWriter writer)
        {
            if (val is SqlMap<string, string>)
            {
                writer.Write(DriverFunctions.WriteQuotedStringMap(val as SqlMap<string, string>, this._map_item_delim, this._map_kv_delim));
            }
            else if (val is SqlArray<int>)
            {
                writer.Write(DriverFunctions.WriteQuotedIntArray(val as SqlArray<int>, this._array_item_delim));
            }
            else if (val is string)
            {
                writer.Write(DriverFunctions.AddQuotes(val as string));
            }
            else
            {
                writer.Write(val);
            }
        }

        // void Output(IRow row, IUnstructuredWriter output)
        //
        // Actual implementation of DriverOutputter that overwrites the Output method of IOutputter.
        public override void Output(IRow row, IUnstructuredWriter output)
        {
            using (StreamWriter streamWriter = new StreamWriter(output.BaseStream, this._encoding))
            {
                streamWriter.NewLine = this._row_delim;
                ISchema schema = row.Schema;
                for (int i = 0; i < schema.Count; i++)
                {
                    object val = row.Get<object>(i);
                    if (i > 0)
                    {
                        streamWriter.Write(this._col_delim);
                    }
                    this.WriteValue(val, streamWriter);
                }
                streamWriter.WriteLine();
            }
        }
    }
}
```

**Using User-Defined Outputter - DriverOutputter**  
Defines a user-defined outputter that can supports writing CSV-like data from SQL.MAP\<string,string> columns and SQL.ARRAY\<int> columns.  Outputter will write homogeneous row formats and can be parallelized.
Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```U-SQL
@drivers = 
    SELECT * FROM 
        ( VALUES
        ("Maria Anders",        "Berlin",       "cell:030-0074321,office:030-0076545"),
        ("Ana Trujillo",        "México D.F.",  "cell:(5) 555-4729,office:(5) 555-3745"),
        ("Antonio Moreno",      "México D.F.",  "cell:(5) 555-3932"),
        ("Thomas Hardy",        "London",       "cell:(171) 555-7788,office:(171) 555-6750"),
        ("Christina Berglund",  "Luleå",        "cell:0921-12 34 65,office:0921-12 34 67")
        ) AS T(Driver, City, PhoneNumbers);

// Parse through PhoneNumbers and create a new data set with a SQL.MAP column type.  All subsequent queries will be against the @map rowset.
@map =
    SELECT  Driver,
            City,
            new SQL.MAP<string, string>(from p in PhoneNumbers.Split(',') select new KeyValuePair<string, string>(p.Split(':') [0], p.Split(':') [1])) AS PhoneNumberMap
    FROM @drivers;

// Using custom outputter - DriverOutputter
OUTPUT @map
TO "/Output/ReferenceGuide/Outut/DriverOutputter.txt"
USING new ReferenceGuide_Examples.DriverOutputter();

/*
// Will fail w/o custum outputter
OUTPUT @map
TO "/Output/ReferenceGuide/Outut/DriverOutputter_willFail.txt"
USING Outputters.Csv();
*/


// Workaround if custom outputter is not used.
@result =
    SELECT  Driver,
            City,
            String.Join(",", MAP_AGG(r.key, r.value).Select(p => String.Format("{0}:{1}", p.Key, p.Value))).Trim() AS PhoneNumbers
    FROM @map
    CROSS APPLY
    EXPLODE(PhoneNumberMap) AS r(key, value)
    GROUP BY Driver, City;

OUTPUT @result
TO "/Output/ReferenceGuide/Outut/drivers_withoutCustomOutputter.txt"
USING Outputters.Csv();
```

### See Also
* [ORDER BY and OFFSET/FETCH Clause (U-SQL)](../u-sql/order-by-and-offset-fetch-clause-u-sql.md)   
* [U-SQL Built-in Outputters](../u-sql/u-sql-built-in-outputters.md)   
* [Output to Files (U-SQL)](../u-sql/output-to-files-u-sql.md)   
* [U-SQL Programmability Guide: User-Defined Outputter](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-outputter)
* [Extending U-SQL Expressions with User-Code](../u-sql/extending-u-sql-expressions-with-user-code.md)  
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)

