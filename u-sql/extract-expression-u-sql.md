---
title: "EXTRACT Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/17/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 578cc7d8-4d7e-4c8e-acfc-d155df94a512
caps.latest.revision: 32
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# EXTRACT Expression (U-SQL)
One of U-SQL’s core capabilities is to be able to schematize unstructured data on the fly without having to create a metadata object for it. This capability is provided by the EXTRACT expression that will invoke either a [user-defined extractor](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-extractor) or [built-in extractor](built-in-u-sql-udos.md) to process the input file or set of files specified in the FROM clause and produces a rowset whose schema is specified in the EXTRACT clause.  
  
The processing of the extraction is done in parallel unless otherwise specified by the extractor. Even a single file will be split into parts which then are processed in parallel. The degree of parallelism depends on how big the files are, how many files there are, what the job’s specified degree of parallelism is etc. For more information about the processing model of extractors, please refer to the the [U-SQL Programmability Guide](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide).  


## Syntax
<pre>
Extract_Expression :=
    'EXTRACT' <a href="#cdl">Column_Definition_List</a>
    <a href="#efc">Extract_From_Clause</a>
    [<a href="#sbc">SortedBy_Clause</a>]   
    [<a href="#req_cla">Required_Clause</a>] 
    <a href="#us_cl">USING_Clause</a>.
</pre>
  
## Semantics of Syntax Elements    
- <a name="cdl"></a>**`Column_Definition_List`**   
This list defines the schema of the extraction. The extracted columns are defined in the EXTRACT clause as a pair of column names and column types:  

  ### Syntax
  <pre>
  Column_Definition_List :=            
      Column_Definitions { ',' Column_Definitions}.
  </pre>

  - <a name="cdefs"></a>**`Column_Definitions`**   
    ### Syntax
    <pre>
    Column_Definitions :=            
        Identifier '.*' | Column_Definition}.
    </pre>

    A fully or partially specified identifier that resolves into a table type followed by a `.*` to indicate that the columns of the type are being used to define the columns of the extract schema, or a `Column_Definition`.  If the identifier is not referring to a table type, does not exist or the query has no permission to access it, an appropriate compile time error is raised.

    > [!NOTE]   
    > [Script-bound table types]() are not currently supported. 

    - **`Column_Definition`**  
      A column definition is of the form    
      ### Syntax
      <pre>
      Column_Definition :=  
          <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> 
            ( <a href="built-in-u-sql-types.md">Built_in_Type</a> | '=' <a href="#fpf">File_Property_Function</a> ).
      </pre>
    
      Each column has an identifier that can be either an unquoted or quoted identifier which is typed with one of the [built-in U-SQL types](built-in-u-sql-types.md) and has to be supported by the extractor.  
  
      If the files are being specified with a file set, then the column definition list also needs to include the so-called virtual columns that are being used in the file set pattern in the EXTRACT’s FROM clause and the specification of their types.  

        - <a name="fpf"></a>**`File_Property_Function`**  
          ### Syntax
          <pre>
          File_Property_Function :=
              ['<a href="#file_uri">FILE.URI()</a>']
              ['<a href="#file_mod">FILE.MODIFIED()</a>'] 
              ['<a href="#file_cre">FILE.CREATED()</a>'] 
              ['<a href="#file_len">FILE.LENGTH()</a>'] 
          </pre>

          File property functions provide the following capabilities:  
          1. Expose specific file properties.
          2. A way to assign the properties to "virtual" columns in the `EXTRACT`'s schema. This is done using a "calculated column" syntax.
          3. Allow constant-foldable comparisons on these "virtual" columns in subsequent query predicates to limit the files being processed by the `EXTRACT` expression.  <br /><br />

          | File Property Function | Return type | Description |
          |------------------------|-------------|-------------|
          | <a name="file_uri"></a>`FILE.URI()`     | `string` | Returns the file's absolute URI or the full local path if used in a local run. |
          | <a name="file_mod"></a>`FILE.MODIFIED()` | `DateTime?` | Returns the file's last modification time stamp in UTC-0 timezone. |
          | <a name="file_cre"></a>`FILE.CREATED()`    | `DateTime?` | Returns the file's creation time stamp in UTC-0 timezone. |
          | <a name="file_len"></a>`FILE.LENGTH()` | `long?` | Returns the file's size in bytes. | 

          The `EXTRACT` expression's schema definition needs to contain at least one non-virtual, non-computed column.  The file property functions are modeled after the file intrinsic functions, and are taking implicit context from the `EXTRACT` expression's file set.  Only `FILE.URI()` is currently supported in local run, the other intrinsics will be added soon.

- <a name="efc"></a>**`Extract_From_Clause`**   
  The EXTRACT’s FROM clause designates the source of the data that needs to be extracted in form of an [Input_File_Path](input-files-u-sql.md) that is either a file path, a comma-separated list of file paths, or a pattern over a set of files (follow the link for more details on the different supported file paths and patterns):

  ### Syntax
  <pre>
  Extract_From_Clause :=   
      'FROM' <a href="input-files-u-sql.md">Input_File_Path</a>.
  </pre>
  
  The [Input_File_Path](input-files-u-sql.md) is specified as a string literal, a reference to a string typed variable or a constant foldable expression.  

- <a name="sbc"></a>**`SortedBy_Clause`**  
  ### Syntax
  <pre>
  SortedBy_Clause := 
      'SORTED' 'BY' Identifier_List.
  </pre>

  The optional `SORTED BY` clause asserts that the rows are ordered by the specified columns. This information allows the optimizer to potentially improve the performance of your script since it knows that the data is ordered. However, if the expression returns data that is not ordered according to the assertion, a runtime error is raised. If it is specified on a built-in Extractor, it will raise a compile-time error.
  
- <a name="req_cla"></a>**`Required_Clause`**      
  The optional `REQUIRED` clause can help the UDO programmer to write more efficient code. For more information on how the UDO programmer can take advantage of this hint, see the U-SQL C# Developer’s Guide.  
  
  The `REQUIRED` clause specifies which columns are required and cannot be pruned by the optimizer. It specifies that either all columns are required on input for the UDO (if specified with `*`), no columns are required (if specified with `NONE`) or the specified columns are required. If a specified column is followed by a list of columns in parenthesis, then the input column is only required if the columns in that list are referenced from the output. The default is that all columns are required. 

  If you want to allow the optimizer to pass column pruning up through the UDO invocation, we recommend specifying the minimal set of columns that are required. Passing the column pruning up higher in the script will provide faster script execution since less data needs to be passed, or - if the column pruning reaches the extractor - read. 
  
  ### Syntax
  <pre>
  Required_Clause := 
      'REQUIRED' None_Star_Or_Required_Column_List.<br />
  None_Star_Or_Required_Column_List :=  
      '*' | 'NONE' | Required_Column_List.<br />
  Required_Column_List :=  
      Required_Column { ',' Required_Column}.<br />
  Required_Column :=  
      Column_Identifier [Required_Output_Column_Dependency_List].<br />
  Required_Output_Column_Dependency_List :=  
      '(' Identifier_List ')'.
  </pre>

- <a name="us_cl"></a>**`USING_Clause`**  
  The USING clause specifies which extractor should be used to turn the file(s) into a rowset.

  ### Syntax
  <pre>
  USING_Clause :=  
      'USING' udo_expression.
  </pre>

  It takes a C# expression that returns an instance of `IExtractor`. U-SQL provides a small set of predefined extractors for common text formats and users can write their own by implementing an `IExtractor`, see [U-SQL Programmability Guide: User-Defined Extractor](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-extractor) for more detail on how to write your own extractor. The built-in extractors are part of the built-in `Extractors` namespace. See [U-SQL Built-in Extractors](u-sql-built-in-extractors.md) for more information on the built-in extractors and their arguments.  
  
## Extraction from compressed data    
In general, the files are passed as is to the UDO. One exception is that `EXTRACT` will recognize GZip compressed files with the file extension `.gz` and automatically decompress them as part of the extraction process. The actual UDO will see the uncompressed data. For any other compression scheme, users will have to write their own custom extractor.  Note that U-SQL has an upper limit of 4GB on a GZip compressed file. If you apply your `EXTRACT` expression to a file larger than this limit, the error `E_RUNTIME_USER_MAXCOMPRESSEDFILESIZE` is being raised during the **compilation** of the job.
  
## Examples    
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.  
- SearchLog.tsv is available @ https://github.com/Azure/usql/blob/master/Examples/Samples/Data/SearchLog.tsv
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](extending-u-sql-expressions-with-user-code.md#usingAssemblies).


**Using Built-In Extractor**     
The following EXTRACT expression schematizes the file SearchLog.txt in the /Samples/Data directory of the default Azure Data Lake Storage by using the built-in TSV format extractor:  
```sql
@searchlog =  
    EXTRACT UserId          int  
          , Start           DateTime  
          , Region          string  
          , Query           string  
          , Duration        int  
          , Urls            string  
          , ClickedUrls     string  
    FROM "/Samples/Data/SearchLog.tsv"  
    USING Extractors.Tsv();
```

**Extractor with ORDER BY, FETCH, and file properties**   
The [ORDER BY clause with FETCH](order-by-and-offset-fetch-clause-u-sql.md) allows the selection of a limited number of rows based on the specified order.
```sql
// Only extracts top 10 records by Start date
@searchlog =  
    EXTRACT UserId          int,
            Start           DateTime,
            Region          string,
            Query           string,
            Duration        int,
            Urls            string,
            ClickedUrls     string,
            uri = FILE.URI(),
            modified_date = FILE.MODIFIED(),
            created_date = FILE.CREATED(),
            file_sz = FILE.LENGTH()
    FROM "/Samples/Data/SearchLog.tsv"  
    USING Extractors.Tsv()
    ORDER BY Start DESC FETCH 10 ROWS;

OUTPUT @searchlog
TO "/ReferenceGuide/QSE/Extract/SearchLog_extracted.txt"
USING Outputters.Tsv();
```

**One directory with multiple files**     
The following EXTRACT expression schematizes the files specified by the file set in the FROM clause. The schema contains the additional virtual columns date and filename that are part of the file set pattern and will be used in later query expressions to identify the actual selected files.  
```sql
// Sample file naming convention: vehicle1_09142014.csv, vehicle2_09142014.csv
DECLARE @dir string = "/Samples/Data/AmbulanceData/";
DECLARE @file_set_path string = @dir + "vehicle{vid}_{date:MM}{date:dd}{date:yyyy}.csv";

@data = 
    EXTRACT vehicle_id int, 
            entry_id long, 
            event_date DateTime, 
            latitude float, 
            longitude float, 
            speed int, 
            direction string, 
            trip_id int?, 
            vid int,  // virtual file set column
            date DateTime // virtual file set column
    FROM @file_set_path
    USING Extractors.Csv();

@result = 
    SELECT  vehicle_id, entry_id, event_date, latitude,longitude,
            speed, direction, trip_id, vid,
            date.ToString("yyyy-MM-dd") AS fileDate
    FROM @data
    WHERE date >= DateTime.Parse("2014-08-31") AND date < DateTime.Parse("2014-10-31")
    AND vid == 1;

OUTPUT @result
TO "/ReferenceGuide/QSE/Extract/Example1.txt"
USING Outputters.Csv();
```

**Multiple directories with multiple files**   
```sql
// Sample file naming convention: vehicle1_09142014.csv, vehicle2_09142014.csv
// Sample directory naming convention: /Samples/Data/AmbulanceData/2014/09/15/, /Samples/Data/AmbulanceData/2014/09/14/
DECLARE @dir string = "/Samples/Data/AmbulanceData/";
DECLARE @file_set_path2 string = @dir + "{date:yyyy}/{date:MM}/{date:dd}/vehicle{vid}_{date:MM}{date:dd}{date:yyyy}.csv";

@data = 
    EXTRACT vehicle_id int, 
            entry_id long, 
            event_date DateTime, 
            latitude float, 
            longitude float, 
            speed int, 
            direction string, 
            trip_id int?, 
            vid int,  // virtual file set column
            date DateTime // virtual file set column
    FROM @file_set_path2
    USING Extractors.Csv();

@result = 
    SELECT *
    FROM @data
    WHERE date == DateTime.Parse("2014-09-15")
    AND vid == 2;

OUTPUT @result
TO "/ReferenceGuide/QSE/Extract/Example2.txt"
USING Outputters.Csv();
```
---

<a name="SampleExtractor">**User-Defined Extractor - SampleExtractor**</a>   
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
    public class SampleExtractor : IExtractor
    {
        private Encoding _encoding;
        private byte[] _row_delim;
        private char _col_delim;

        public SampleExtractor(Encoding encoding, string row_delim = "\r\n", char col_delim = '\t')
        {
            this._encoding = ((encoding == null) ? Encoding.UTF8 : encoding);
            this._row_delim = this._encoding.GetBytes(row_delim);
            this._col_delim = col_delim;
        }

        public override IEnumerable<IRow> Extract(IUnstructuredReader input, IUpdatableRow output)
        {
            string line;
            //Read the input line by line
            foreach (Stream current in input.Split(_encoding.GetBytes("\r\n")))
            {
                using (StreamReader streamReader = new StreamReader(current, this._encoding))
                {
                    line = streamReader.ReadToEnd().Trim();
                    //Split the input by the column delimiter
                    string[] parts = line.Split(this._col_delim);
                    int count = 0;
                    foreach (string part in parts)
                    {
                        //If its the second column, treat it in a special way, split the column into first name and last name columns
                        if (count == 1)
                        {
                            // identify number of parts in name
                            int nameCount = part.Trim().Count(f => f == ' ');

                            // two part name
                            if (nameCount == 1)
                            {
                                string[] name = part.Trim().Split(' ');
                                output.Set<string>(count, name[0]);
                                count += 1;
                                output.Set<string>(count, name[1]);
                            }

                            // three part name
                            else if (nameCount == 2)
                            {
                                string[] name = part.Trim().Split(' ');

                                // combine first & middle name
                                output.Set<string>(count, name[0] + " " + name[1]);

                                // alternatively skip the middle name
                                // output.Set<string>(count, name[0]);
                                count += 1;
                                output.Set<string>(count, name[2]);
                            }

                            // one part name
                            else
                            {
                                output.Set<string>(count, part);
                                count += 1;
                            }
                        }
                        else
                        {
                            output.Set<string>(count, part);
                        }
                        count += 1;
                    }
                }
                yield return output.AsReadOnly();
            }
            yield break;
        }
    }
}
```

**Using User-Defined Extractor - SampleExtractor**  
Extracts first and last names as separate columns using the custom extractor defined **above**.

```sql
@drivers =
    EXTRACT id string,
            first_name string,
            last_name string,
            address string,
            city string,
            region string,
            zipcode string,
            country string,
            phone_numbers string
    FROM "/Samples/Data/AmbulanceData/Drivers.txt"
    USING new ReferenceGuide_Examples.SampleExtractor(Encoding.Unicode);

OUTPUT @drivers
TO "/ReferenceGuide/QSE/Extract/Drivers.txt"
USING Outputters.Tsv(encoding:Encoding.UTF8, quoting:false);
```

<a name="DriverExtractor">**User-Defined Extractor - DriverExtractor**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;

using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Types.Sql;

/*
 slightly modied version from:
 https://github.com/Azure/usql/blob/master/Examples/AmbulanceDemos/AmbulanceDemoCode/Class1.cs

The outputter utilizes  three functions which are defined below:
    RemoveOptionalQuotes, ReadStringMap, and ReadIntArray
*/

namespace ReferenceGuide_Examples
{
    public class DriverFunctions
    {
        // string RemoveOptionalQuotes(string s)
        //
        // Removes Quotes from string s (and de-duplicate contained "") if the string is embedded in "
        public static string RemoveOptionalQuotes(string s)
        {
            return (s.Length > 1 && s[0] == '"' && s[s.Length - 1] == '"') ? s.Substring(1, s.Length - 2).Replace("\"\"", "\"") : s;
        }

        // SqlMap<string, string> ReadStringMap(string val, string map_item_delim = ",", string map_kv_delim = ":")
        //
        // transforms the input string val into a SQL.MAP instance using the provided delimiters to separate key-value pairs and the key and value in each pair.
        // Both the key and value types are string.
        public static SqlMap<string, string> ReadStringMap(string val, string map_item_delim = ",", string map_kv_delim = ":")
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

        // SqlArray<int> ReadIntArray(string val, string array_item_delim = ",")
        //
        // returns a SQL.ARRAY<int> from the input string val using the provided array item delimiter.
        public static SqlArray<int> ReadIntArray(string val, string array_item_delim = ",")
        {
            return new SqlArray<int>(
                from x in val.Split(new string[]
                {
                    array_item_delim
                }, StringSplitOptions.None)
                select Convert.ToInt32(x));
        }
    }

    // DriverExtractor
    //
    // Defines a user-defined extractor that can supports reading CSV-like data into SQL.MAP<string,string> columns and SQL.ARRAY<int> columns.
    // Extractor assume homogeneous row formats and can be parallelized
    //
    // Usage (after registration of assembly and referencing assembly in script, default values shown):
    //   EXTRACT ... FROM ... 
    //   USING new AmbulanceDemoCode.DriverExtractor(row_delim:"\r\n", col_delim: ",",map_item_delim: ",", map_kv_delim:":", array_item_delim:",", encoding:Encoding.UTF8);
    //
    [SqlUserDefinedExtractor(AtomicFileProcessing = false)]
    public class DriverExtractor : IExtractor
    {

        // Class variables that are set with the class initializer
        private byte[] _row_delim;
        private string _col_delim;
        private string _map_item_delim;
        private string _map_kv_delim;
        private string _array_item_delim;
        private Encoding _encoding;

        // DriverExtractor(string row_delim = "\r\n", string col_delim = ",", string map_item_delim = ",", string map_kv_delim = ":", string array_item_delim = ",", Encoding encoding = null)
        //
        // Class initializer that provides optional extractor parameters.
        public DriverExtractor(string row_delim = "\r\n", string col_delim = ",", string map_item_delim = ",", string map_kv_delim = ":", string array_item_delim = ",", Encoding encoding = null)
        {
            this._encoding = ((encoding == null) ? Encoding.UTF8 : encoding);
            this._row_delim = this._encoding.GetBytes(row_delim);
            this._col_delim = col_delim;
            this._map_item_delim = map_item_delim;
            this._map_kv_delim = map_kv_delim;
            this._array_item_delim = array_item_delim;
        }

        // void OutputValueAtCol_I(string c, int i, IUpdatableRow outputrow)
        // 
        // Helper function that takes the string value c and puts it into the column at position i in the output row.
        // The value will be cast to the expected type of the column.
        private void OutputValueAtCol_I(string c, int i, IUpdatableRow outputrow)
        {
            ISchema schema = outputrow.Schema;
            if (schema[i].Type == typeof(SqlMap<string, string>))
            {
                c = DriverFunctions.RemoveOptionalQuotes(c);
                SqlMap<string, string> scopeMap = String.IsNullOrEmpty(c) ? null : DriverFunctions.ReadStringMap(c, this._map_item_delim, this._map_kv_delim);
                outputrow.Set<SqlMap<string, string>>(i, scopeMap);
            }
            else if (schema[i].Type == typeof(SqlArray<int>))
            {
                c = DriverFunctions.RemoveOptionalQuotes(c);
                SqlArray<int> scopeArray = String.IsNullOrEmpty(c) ? null : DriverFunctions.ReadIntArray(c, this._array_item_delim);
                outputrow.Set<SqlArray<int>>(i, scopeArray);
            }
            else if (schema[i].Type == typeof(int))
            {
                int num = Convert.ToInt32(c);
                outputrow.Set<int>(i, num);
            }
            else if (schema[i].Type == typeof(int?))
            {
                int? num2 = (c == "") ? null : new int?(Convert.ToInt32(c));
                outputrow.Set<int?>(i, num2);
            }
            else if (schema[i].Type == typeof(long))
            {
                long num3 = Convert.ToInt64(c);
                outputrow.Set<long>(i, num3);
            }
            else if (schema[i].Type == typeof(long?))
            {
                long? num4 = (c == "") ? null : new long?(Convert.ToInt64(c));
                outputrow.Set<long?>(i, num4);
            }
            else if (schema[i].Type == typeof(DateTime))
            {
                DateTime dateTime = Convert.ToDateTime(c);
                outputrow.Set<DateTime>(i, dateTime);
            }
            else if (schema[i].Type == typeof(DateTime?))
            {
                DateTime? dateTime2 = (c == "") ? null : new DateTime?(Convert.ToDateTime(c));
                outputrow.Set<DateTime?>(i, dateTime2);
            }
            else if (schema[i].Type == typeof(string))
            {
                string text = DriverFunctions.RemoveOptionalQuotes(c);
                outputrow.Set<string>(i, text);
            }
            else
            {
                outputrow.Set<string>(i, c);
            }
        }

        // IEnumerable<IRow> Extract(IUnstructuredReader input, IUpdatableRow outputrow)
        //
        // Actual implementation of DriverExtractor that overwrites the Extract method of IExtractor.
        public override IEnumerable<IRow> Extract(IUnstructuredReader input, IUpdatableRow outputrow)
        {
            foreach (Stream current in input.Split(this._row_delim))
            {
                using (StreamReader streamReader = new StreamReader(current, this._encoding))
                {
                    int num = 0;
                    string[] array = streamReader.ReadToEnd().Split(new string[] { this._col_delim }, StringSplitOptions.None);
                    for (int i = 0; i < array.Length; i++)
                    {
                        string c = array[i];
                        this.OutputValueAtCol_I(c, num++, outputrow);
                    }
                }
                yield return outputrow.AsReadOnly();
            }
            yield break;
        }
    }
}
```

**Using User-Defined Extractor - DriverExtractor**  
Defines a user-defined extractor that supports reading CSV-like data into `SQL.MAP<string,string>` columns and `SQL.ARRAY<int>` columns.  Extractor assume homogeneous row formats and can be parallelized.  Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**. 
 
```sql
@Drivers =
 EXTRACT driver_id int
       , name string
       , street   string
	   , city string
       , region string
       , zipcode  string
       , country  string
       , phone_numbers  SQL.MAP<string, string>
 FROM "/Samples/Data/AmbulanceData/Drivers.txt"
 USING new ReferenceGuide_Examples.DriverExtractor(col_delim: "\t", encoding: Encoding.Unicode);

 // Optional if you want to view results
@result =
    SELECT name,
           r.key.Trim() AS PhoneType, r.value AS PhoneNumber
    FROM @Drivers
         CROSS APPLY
             EXPLODE(phone_numbers) AS r(key, value);

OUTPUT @result
TO "/ReferenceGuide/QSE/Extract/DriverExtractor.txt"
USING Outputters.Tsv(encoding:Encoding.UTF8, quoting:false);
```

<a name="FlexExtractor">**User-Defined Extractor - FlexExtractor**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.

```csharp
using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Types.Sql;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;

namespace FlexibleSchemaExtractor
{
    public class FlexExtractor : IExtractor
    {
        private Encoding _encoding;
        private byte[] _row_delim;
        private string _col_delim;

        public FlexExtractor(Encoding encoding = null, string row_delim = "\r\n", string col_delim = ",")
        {
            this._encoding = ((encoding == null) ? Encoding.UTF8 : encoding);
            this._row_delim = this._encoding.GetBytes(row_delim);
            this._col_delim = col_delim;
        }

        public override IEnumerable<IRow> Extract(IUnstructuredReader input, IUpdatableRow output)
        {
            var colsInSchema = output.Schema.Count;

            // let's check global assumptions
            // - first 4 provided columns are int, string, int, decimal.

            if (output.Schema[0].Type != typeof(System.Int32)
                || output.Schema[1].Type != typeof(System.String)
                || output.Schema[2].Type != typeof(System.Int32)
                || output.Schema[3].Type != typeof(System.Decimal)
               )
            {
                throw new Exception("First 4 columns are not of expected types int32, string, int32, decimal.");
            }

            foreach (Stream currentline in input.Split(this._row_delim))
            {
                using (StreamReader lineReader = new StreamReader(currentline, this._encoding))
                {
                    string[] columns = lineReader.ReadToEnd().Split(new string[] { this._col_delim }
                                                                   , StringSplitOptions.None);
                    var colsInData = columns.Length;

                    // let's check row level assumptions
                    // - if less columns are specified, then last column needs to be of type SqlMap<Int32, string>

                    if (colsInData > colsInSchema
                        && output.Schema[colsInSchema - 1].Type != typeof(SqlMap<Int32, string>))
                    {
                        throw new Exception(
                              "Too many columns detected and last column is not of type SqlMap<Int32,string>. "
                            + "Add a final column of type SqlMap<Int32,string&ht; into your extract schema.");
                    }
                    // Set first 4 fixed columns
                    output.Set<Int32>(0, Int32.Parse(columns[0]));
                    output.Set<String>(1, columns[1]);
                    output.Set<Int32>(2, Int32.Parse(columns[2]));
                    output.Set<Decimal>(3, Decimal.Parse(columns[3]));

                    // Fill all remaining columns except the last which may be a map
                    for (int i = 4; i < Math.Min(colsInData, colsInSchema) - 1; i++)
                    {
                        output.Set<String>(i, columns[i]);
                    }

                    // Now handle last column: if it is a map
                    if (colsInData >= colsInSchema
                        && output.Schema[colsInSchema - 1].Type == typeof(SqlMap<Int32, string>))
                    {
                        var sqlmap = new Dictionary<Int32, string>();
                        for (int j = colsInSchema - 1; j < colsInData; j++)
                        {
                            sqlmap.Add(j - colsInSchema + 1, columns[j]);
                        }
                        output.Set<SqlMap<Int32, string>>(colsInSchema - 1, new SqlMap<Int32, string>(sqlmap));
                    }
                    // Now handle last column: if it is not a map
                    else if (colsInData == Math.Min(colsInData, colsInSchema))
                    {
                        output.Set<string>(colsInData - 1, columns[colsInData - 1]);
                    }

                    yield return output.AsReadOnly();
                }
            }
        }
    }
}
```

**Using User-Defined Extractor - FlexExtractor**  
A flexible schema extractor that is able to read a row-oriented file that has different column counts.  The first 4 columns are fixed as order ID, product type, ordered amount and per item price. Remaining columns, both in their number and semantics, depend upon the product type.  This example is taken from [How to deal with files containing rows with different column counts in U-SQL: Introducing a Flexible Schema Extractor](https://blogs.msdn.microsoft.com/mrys/2016/08/15/how-to-deal-with-files-containing-rows-with-different-column-counts-in-u-sql-introducing-a-flexible-schema-extractor/).  Please refer to the referenced article for full details.  Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```sql
/*
Copy the data below into a file called OrderData.csv.

1,Shoes,2,99.99,10
1,Pants,3,59,34,32
2,Camera,1,999.00,Canon,70D
2,Lens,1,999.99,Canon,100mm,Macro,1.4
2,Lens,1,459.99,Sigma,28-85mm,Macro/Zoom,2.8
3,Camera,1,745,Sony,RX-100-II
3,Shoes,1,69.99,13
*/

// Update with your actual file path.
DECLARE @input string = "/ReferenceGuide/QSE/Extract/OrderData.csv";

// Usage with all columns known
@data = EXTRACT orderid int, producttype string, orderamount int, itemprice decimal,
                c1 string, c2 string, c3 string, c4 string
        FROM @input 
        USING new FlexibleSchemaExtractor.FlexExtractor();

// product type Camera
@cameras =
    SELECT orderid,
           orderamount,
           itemprice,
           c1 AS make,
           c2 AS model
    FROM @data
    WHERE producttype == "Camera";

OUTPUT @cameras
TO "/ReferenceGuide/QSE/Extract/cameras.csv"
USING Outputters.Csv();


// product type Lens
@lenses =
    SELECT orderid,
           orderamount,
           itemprice,
           c1 AS make,
           c2 AS focallength,
           c3 AS lenstype,
           c4 == null ? (decimal?) null : Decimal.Parse(c4) AS aperture
    FROM @data
    WHERE producttype == "Lens";

OUTPUT @lenses
TO "/ReferenceGuide/QSE/Extract/lenses.csv"
USING Outputters.Csv();

/*******************************************************************/
/***             Variant Using SqlMap<Int32,string>             ***/
/*******************************************************************/

// Usage with only a few known columns and a map for the rest
@data = EXTRACT orderid int, producttype string, orderamount int, itemprice decimal,
                c1 string, map SqlMap<Int32,string>
        FROM @input
        USING new FlexibleSchemaExtractor.FlexExtractor();

// product type Camera
@cameras =
    SELECT orderid,
           orderamount,
           itemprice,
           c1 AS make,
           map[0] AS model
    FROM @data
    WHERE producttype == "Camera";

OUTPUT @cameras
TO "/ReferenceGuide/QSE/Extract/cameras2.csv"
USING Outputters.Csv();

// product type Lens
@lenses =
    SELECT orderid,
           orderamount,
           itemprice,
           c1 AS make,
           map[0] AS focallength,
           map[1] AS lenstype,
           map[2] == null ? (decimal?) null : Decimal.Parse(map[2]) AS aperture
    FROM @data
    WHERE producttype == "Lens";

OUTPUT @lenses
TO "/ReferenceGuide/QSE/Extract/lenses2.csv"
USING Outputters.Csv();

// remaining product types (serialize map generically)
@others =
    SELECT orderid,
           producttype,
           orderamount,
           itemprice,
           c1,
           map == null ? (string) null 
                       : string.Join(" ; ", 
                                     from p in map 
                                     select string.Format("{0}{1}{2}", p.Key, " : ", p.Value)) AS map 
    FROM @data
    WHERE producttype NOT IN ("Camera", "Lens");

OUTPUT @others
TO "/ReferenceGuide/QSE/Extract/others.csv"
USING Outputters.Csv();
```  

**EXTRACT & ORDER BY**  
The following statement extracts from the search log sample data and takes the 10 rows with the longest `Duration`.  
```sql
 @searchlog =
    EXTRACT UserId          int,
            Start           DateTime,
            Region          string,
            Query           string,
            Duration        int?,
            Urls            string,
            ClickedUrls     string
    FROM "/Samples/Data/SearchLog.tsv"
    USING Extractors.Tsv()
    ORDER BY Duration DESC FETCH 10;

 OUTPUT @searchlog
 TO "/ReferenceGuide/QSE/OrderBY/wExtract.csv"
 USING Outputters.Csv(outputHeader:true);
```

**EXTRACT with FUNCTION (Script Bound Object) & ORDER BY**  
The following statement uses a locally declared TVF to wrap the EXTRACT expression in a prior example and only returns the 5 rows with the longest `Duration`.
```sql
 DECLARE FUNCTION @sl() RETURNS @searchlog2 AS
 BEGIN
   @searchlog2 =
     EXTRACT UserId int,
             Start DateTime,
             Region string,
             Query string,
             Duration int?,
             Urls string,
             ClickedUrls string
     FROM "/Samples/Data/SearchLog.tsv"
     USING Extractors.Tsv();
 END;

 @searchlog2 = @sl() ORDER BY Duration DESC FETCH 5;

 OUTPUT @searchlog2
 TO "/ReferenceGuide/QSE/OrderBY/wFunction.csv"
 USING Outputters.Csv(outputHeader:true);
```


<a name="SLExtractor">**User-Defined Extractor - SLExtractor**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.
```csharp
using Microsoft.Analytics.Interfaces;
using System;
using System.Collections.Generic;
using System.IO;
using System.Text;

namespace ReferenceGuide
{
    public static class UpdatableRowExtensions
    {
        public static void SetColumnIfRequested<T>(this IUpdatableRow source, string colName, Func<T> expr)
        {
            var colIdx = source.Schema.IndexOf(colName);
            if (colIdx != -1)
            { source.Set<T>(colIdx, expr()); }
        }
    }

    public class SLExtractor : IExtractor
    {
        public override IEnumerable<IRow> Extract(IUnstructuredReader input, IUpdatableRow output)
        {
            foreach (Stream current in input.Split())
            {
                using (StreamReader streamReader = new StreamReader(current, Encoding.UTF8))
                {
                    string[] array = streamReader.ReadToEnd().Split(new string[] { "\t" }, StringSplitOptions.None);

                    output.SetColumnIfRequested("UserId", () => Int32.Parse(array[0]));
                    output.SetColumnIfRequested("Start", () => DateTime.Parse(array[1]));
                    output.SetColumnIfRequested("Region", () => (array[2]));
                    output.SetColumnIfRequested("Query", () => (array[3]));
                    output.SetColumnIfRequested("Duration", () => Int32.Parse(array[4]));
                    output.SetColumnIfRequested("Urls", () => (array[5]));
                    output.SetColumnIfRequested("ClickedUrls", () => (array[6]));
                }
                yield return output.AsReadOnly();
            }
        }
    }
}
```

**Using User-Defined Extractor - SLExtractor with SORTED BY**  
Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```SQL
@searchlog =
   EXTRACT UserId          int,
           Start           DateTime,
           Region          string,
           Query           string,
           Duration        int?,
           Urls            string,
           ClickedUrls     string
   FROM "/Samples/Data/SearchLog.tsv"
   SORTED BY Start
   USING new ReferenceGuide.SLExtractor();

 OUTPUT @searchlog
 TO "/ReferenceGuide/QSE/Extract/extract-sorted-by.csv" 
 USING Outputters.Csv(outputHeader:true);
```


<a name="SLExtractor_diag">**User-Defined Extractor - SLExtractor_diag**</a>   
The following extractor will only process the columns Start,Region, Query, Duration, Urls, ClickedUrls of the search log file if they are specified in the EXTRACT schema and are not pruned by the query optimizer. The column UserId is always processed and raises an error if it is missing. It writes information about whether the column is used into the diagnostic stream info for better observing the behavior.   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.
```csharp
using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Diagnostics;
using System;
using System.Collections.Generic;
using System.IO;
using System.Text;

namespace ReferenceGuide
{
    public static class UpdatableRowExtensions_diag
    {
        public static void SetColumnIfRequested<T>(this IUpdatableRow source, string colName, Func<T> expr)
        {
            var colIdx = source.Schema.IndexOf(colName);
            if (colIdx != -1)
            {
                DiagnosticStream.WriteLine(String.Format("Column <{0}> is requested.", colName));
                source.Set<T>(colIdx, expr());
            }
        }
    }

    public class SLExtractor_diag : IExtractor
    {
        public override IEnumerable<IRow> Extract(IUnstructuredReader input, IUpdatableRow output)
        {
            foreach (Stream current in input.Split())
            {
                using (StreamReader streamReader = new StreamReader(current, Encoding.UTF8))
                {
                    string[] array = streamReader.ReadToEnd().Split(new string[] { "\t" }, StringSplitOptions.None);

                    output.Set<int>("UserId", Int32.Parse(array[0]));
                    output.SetColumnIfRequested("Start", () => DateTime.Parse(array[1]));
                    output.SetColumnIfRequested("Region", () => (array[2]));
                    output.SetColumnIfRequested("Query", () => (array[3]));
                    output.SetColumnIfRequested("Duration", () => Int32.Parse(array[4]));
                    output.SetColumnIfRequested("Urls", () => (array[5]));
                    output.SetColumnIfRequested("ClickedUrls", () => (array[6]));
                }
                yield return output.AsReadOnly();
            }
        }
    }
}
```

**Using User-Defined Extractor - SLExtractor_diag with REQUIRED**  
If the above extractor is invoked with the following script, then only the columns will actually be executed and the pruned columns will not be requested from the extractor, even though they have been requested.  
Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```SQL
SET @@Diagnostics = true;

@searchlog =
  EXTRACT UserId          int,
          Start           DateTime,
          Region          string,
          Query           string
  FROM "/Samples/Data/SearchLog.tsv"
  REQUIRED UserId
  USING new ReferenceGuide.SLExtractor_diag();

@res =
  SELECT UserId,
         Start
  FROM @searchlog;

OUTPUT @res
TO "//ReferenceGuide/QSE/Extract/extract-required.csv"
USING Outputters.Csv(outputHeader:true);
```


**EXTRACT with Table Type**
Create the Table Types and then reference them in the EXTRACT expression.
```sql
/* Create Types
USE TestReferenceDB;

DROP TYPE IF EXISTS dbo.type1;
DROP TYPE IF EXISTS dbo.type2;

CREATE TYPE dbo.type1 AS TABLE(UserId int, Start DateTime, Region string, Query string);
CREATE TYPE dbo.type2 AS TABLE(Urls string, ClickedUrls string);
 */

USE TestReferenceDB;

@searchlog =
    EXTRACT dbo.type1.*, 
            Duration int?, 
            TestReferenceDB.dbo.type2.*
    FROM "/Samples/Data/SearchLog.tsv"
    USING Extractors.Tsv();

OUTPUT @searchlog
TO "/ReferenceGuide/QSE/Extract/extract_wType.csv"
USING Outputters.Csv();
```
  
## See Also 
* [U-SQL Built-in Extractors](u-sql-built-in-extractors.md) 
* [Input Files (U-SQL)](input-files-u-sql.md) 
* [Create U-SQL EXTRACT Script Automatically](https://blogs.msdn.microsoft.com/azuredatalake/2017/08/08/create-u-sql-extract-script-automatically/)
* [Data Modification Language (DML) Statements (U-SQL)](data-modification-language-dml-statements-u-sql.md)    
* [Output Statement (U-SQL)](output-statement-u-sql.md)  
* [U-SQL Programmability Guide](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide)  
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)  
* [How to register U-SQL Assemblies in your U-SQL Catalog](https://blogs.msdn.microsoft.com/azuredatalake/2016/08/26/how-to-register-u-sql-assemblies-in-your-u-sql-catalog/)

