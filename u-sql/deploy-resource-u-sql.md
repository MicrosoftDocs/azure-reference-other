---
title: "DEPLOY RESOURCE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-11-02"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e1139af5-7d2e-49bb-a97d-3c6a9ba2f1f6
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---

# DEPLOY RESOURCE (U-SQL)
The `RESOURCE` statement identifies the data to be used as a resource. 

## Syntax
<pre>
Deploy_Resource_Statement :=
    'DEPLOY' 'RESOURCE' <a href="input-files-u-sql.md#input-file-path-uris">file_path_URI</a> { ',' <a href="input-files-u-sql.md#input-file-path-uris">file_path_URI</a>}.  
</pre>

## Using a Resource   
Files have to be in Azure Data Lake Storage or Windows Azure Storage Blob. Files are deployed to vertex and are accessible from any custom code.  The file paths of deployed resources have to be unique among all deployed resources in a script and the additional files included when [referencing assemblies](reference-assembly-u-sql.md) as they are put into a single directory during compilation and execution. Ensure that all resources have unique file names or in case of identical files use only one copy.  Otherwise, you will receive the error message `E_CSC_USER_SAMERESOURCEWITHDIFFERENTPATH: Script contains <N> different resources with identical file name.`


## Size Limits
- Single resource file limit is 400MB.  
- Overall limit for deployes resource files is 3GB.  

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](extending-u-sql-expressions-with-user-code.md#usingAssemblies).

**Basic Example**
```sql
// a small file containing text
DEPLOY RESOURCE "/Samples/Data/helloworld.txt";

@departments =
  SELECT * 
  FROM (VALUES
      (31, "Sales"),
      (33, "Engineering"),
      (34, "Clerical"),
      (35, "Marketing")
    ) AS D( DepID, DepName );

@departments =
    SELECT DepID, DepName, System.[IO].File.ReadAllText("helloworld.txt") AS Message
    FROM @departments;

OUTPUT @departments 
TO "/ReferenceGuide/Concepts/Resource/Test.txt"
USING Outputters.Tsv();
```


--------------------------------------------------

**RESOURCE with a Processor**  
<a name="HelloWorldProcessor">**HelloWorldProcessor**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file.  See usage in next section, **below**.
```csharp
using Microsoft.Analytics.Interfaces;

namespace ReferenceGuide
{
    [SqlUserDefinedProcessor]
    public class HelloWorldProcessor : IProcessor
    {
        private string hw;

        public HelloWorldProcessor()
        {
            this.hw = System.IO.File.ReadAllText("helloworld.txt");
        }

        public override IRow Process(IRow input, IUpdatableRow output)
        {
            output.Set<int>("DepID", input.Get<int>("DepID"));
            output.Set<string>("DepName", input.Get<string>("DepName"));
            output.Set<string>("HelloWorld", hw);
            return output.AsReadOnly();
        }
    }
}
```

**Using RESOURCE with a Processor**  
Using [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) from previous section, **above**.  
```sql
// a small file containing text
DEPLOY RESOURCE "/Samples/Data/helloworld.txt";

@departments =
  SELECT * 
  FROM (VALUES
      (31, "Sales"),
      (33, "Engineering"),
      (34, "Clerical"),
      (35, "Marketing")
    ) AS D( DepID, DepName );


@departments =
     PROCESS @departments
     PRODUCE DepID int,
             DepName string,
             HelloWorld string
     USING new ReferenceGuide.HelloWorldProcessor();

OUTPUT @departments 
TO "/ReferenceGuide/Concepts/Resource/Test2.txt"
USING Outputters.Tsv();
```

--------------------------------------------------
**Other Examples utilizing `DEPLOY RESOURCE`:**
* [Tutorial: Get started with extending U-SQL with R](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-r-extensions)
* [Using Custom Python Libraries with U-SQL](https://blogs.msdn.microsoft.com/azuredatalake/2017/03/10/using-custom-python-libraries-with-u-sql/)
* [PredictLinearModel](https://github.com/Azure/usql/tree/master/Examples/R_Extensions/PredictLinearModel)

## See Also
* [U-SQL Assemblies](u-sql-assemblies.md)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
* [Input Files (U-SQL)](input-files-u-sql.md) 
