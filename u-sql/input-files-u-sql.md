---
title: "Input Files (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "07/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 08873783-e3e1-4236-a7f0-0bbff16a40f0
caps.latest.revision: 21
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Input Files (U-SQL)
U-SQL provides access to files that are stored either in Azure Data Lake Storage accounts or in Windows Azure Blob Storage accounts. Azure Data Lake Storage accounts have to be in the same Azure region as the Azure Data Lake Analytics account where you run your U-SQL script. Windows Azure Blob Storage accounts need to be registered with the Azure Data Lake Analytics account where you will run your U-SQL script but can be in any region. See [Registering Your Windows Azure Blob Storage account](#registerWABS) below for more information.  Note that if the data is in a different region than the Azure Data Lake Analytics account, you will get billed for data egress and data transfer rates will be based on the internet connection between the two regions and considerably lower than accessing data inside the same region.  Any input files referenced in a script have to exist at the time the script is compiled.
  
  
In order to process files with U-SQL, they have to be schematized with an [`EXTRACT`](extract-expression-u-sql.md) expression that will read from either a single file, a list of files, or a set of files, a so-called *unstructured file set*.  

## Registering Your Windows Azure Blob Storage account<a name="registerWABS"></a>  
Windows Azure Blob Storage (WABS) accounts need to be registered with the Azure Data Lake Analytics account where you will run your U-SQL script but can be in any region.  Follow the steps below to verify whether your WABS account is registered with your Azure Data Lake Analytics account and add if necessary.
1. Navigate to the [Azure Portal](http://portal.azure.com/) and log in.
2. Navigate to your Azure Data Lake Analytics Account.
3. Select **Data Sources** under **Settings**.
4. Verify whether your WABS account is listed.  If yes, stop here.  If no, continue to next step.
5. Click **Add Data Source**.
6. Select **Azure Storage** from the **Storage Type** drop-down list.
7. Select **Select Account** from the **Selection Method** drop-down list.
8. Select your WABS account from the **Azure Storage** drop-down list.
9. Click **Add**.

Alternatively, you can use the AzureRM PowerShell cmdlets [Get-AzureRmDataLakeAnalyticsDataSource](https://docs.microsoft.com/powershell/module/azurerm.datalakeanalytics/get-azurermdatalakeanalyticsdatasource?) and [Add-AzureRmDataLakeAnalyticsDataSource](https://docs.microsoft.com/powershell/module/azurerm.datalakeanalytics/add-azurermdatalakeanalyticsdatasource?). 

  
## Input File Path URIs  
The input file path URIs (Universal Resource Identifier) can be specified as a single file path URI, a list of file path URIs, or a path pattern expression that identifies an unstructured file set.   
  
* Since file paths are URIs, characters such as spaces need to be _URI-encoded_. For example the file name `a has 3 spaces` has to be written as `a%20has%203%20spaces`.  
  
* A file path URI or a path pattern expression has to be provided as a [static string expression](expressions-u-sql.md) (an expression that can be constant folded) in the [`FROM`](from-clause-u-sql.md) clause of an [`EXTRACT`](extract-expression-u-sql.md) expression.  
 
* A file path can also be specified as a local file path.

### Syntax
<pre>
Input_File_Path :=                
    <a href="#singlefilepath">Single_File_Path</a> 
|   <a href="#listfilepath">List_File_Path</a> 
|   <a href="#inputfilesetpath">File_Set_Path</a>.
</pre>
 
## <a name="singlefilepath"></a>`Single_File_Path`  
A single file path URI can be a relative or absolute Azure Data Lake Storage URI, or a Windows Azure Blob Storage URI:

### Syntax
<pre>
Single_File_Path :=                              
    <a href="#defaultaccountpath">Default_Account_Path_URI</a> 
|   <a href="#adlpath">ADL_Path_URI</a> 
|   <a href="#wasbpath">WASB_Path_URI</a>.
</pre>
 
The following sections show the syntax and semantics for each of the supported paths.  
  
* <a name="defaultaccountpath"></a>**`Default_Account_Path_URI`**    
  The  Default Account Path URI is a relative Azure Data Lake Storage URI (a path without the URI header). It refers to a path in the Data Lake Analytics account’s associated default Data Lake Storage account.  
  
  ### Syntax
  <pre>
  Default_Account_Path_URI :=            
      ['/']+Relative_Path.<br />
  Relative_Path :=
      {pathstep+'/'}+file_name.
  </pre>
 
  > [!NOTE]  
  > The `+` in the grammar indicates that spaces are not allowed between the parts.
  
  ### Example  
  The URI `"/Samples/Data/searchlog.tsv"` refers to the `searchlog.tsv` file in the directory path `/Samples/Data` inside the default Azure Data Lake Storage account.   
  
* <a name="adlpath"></a>**`ADL_Path_URI`**  (Azure Data Lake Path URI)  
  You can specify a full URI using either the `webhdfs` or `adl` URI schemes. They both look the same, except for the scheme name. `webhdfs` is supported for compatibility reasons with WebHDFS. It is recommended to use the `adl` URI scheme with U-SQL, since it provides some performance benefits.   
  
  Both URI schemes use encryption during data retrieval.  
  
  ### Syntax
  <pre>
  ADL_Path_URI :=                    
      ADL_URI | WebHDFS_URI.<br />  
  ADL_URI :=        
      ADL_Header +'/'+Relative_Path.<br />   
  ADL_Header := 
      'adl://'+ADL_Domain.<br />   
  ADL_Domain := 
      adl_accountname+'.azuredatalakestore.net'.<br />   
  WebHDFS_URI := 
      WebHDFS_Header+'/'+Local_Path.<br />   
  WebHDFS_Header := 
      'swebhdfs://'+ADL_Domain.
  </pre>
  
  > [!NOTE]  
  > The `+` in the grammar indicates that spaces are not allowed between the parts.
  
  ### Example  
  Both URIs `"webhdfs://myadl.azuredatalakestore.net/Samples/Data/searchlog.tsv"` and `"adl://myadl.azuredatalakestore.net/Samples/Data/searchlog.tsv"` refer to the `searchlog.tsv` file in the directory path `/Samples/Data` inside the Azure Data Lake Storage account `myadl`.   
  
  
* <a name="wasbpath"></a>**`WASB_Path_URI`**  (Windows Azure Blob Storage Path URI)  
  U-SQL can refer to block blobs and append blobs stored in Windows Azure Blob Storage with the `wasb` URI scheme.If a short-form account name is provided, it will default to the `blob.core.windows.net` domain.  
  
  The `wasb` URI scheme uses encryption during data retrieval.  
  
  ### Syntax
  <pre>
  WASB_Path :=                          
      WASB_Header+Relative_Path.<br />  
  WASB_Header := 
      'wasb://'+wasb_container+'@'+wasb_accountname+  
           ['.blob.core.windows.net']+'/'.
  </pre>
 
  > [!NOTE]  
  > The `+` in the grammar indicates that spaces are not allowed between the parts.
  
  ### Example  
  The URI `"wasb://samples@mywasb/Samples/Data/searchlog.tsv"` refers to the `searchlog.tsv` file in the directory path `/Samples/Data` inside the Windows Azure Blob Store account `mywasb`'s `samples` container.   
  
### <a name="listfilepath"></a>`List_File_Path`  
Files can be specified in a list that enumerates all the files that are being processed.  

<table><th align="left">Syntax</th><tr><td><pre>
List_File_Path :=                                                                                        
     Single_File_Path {',' Single_File_Path}.
</pre></td></table>
  
## <a name="inputfilesetpath"></a>`File_Set_Path`  
If the list of files cannot be enumerated or it would be too cumbersome to enumerate them, a file set path can be specified. A file set path is a relative or absolute URI where parts of the folder or file names (but **not** the domain or container names) can be replaced with a file set pattern that is embedded inside curly braces `{}`.  
  
### Syntax
<pre>
File_Set_Path :=                     
    [ADL_Header | WebHDFS_Header | WASB_Header]+  
         FileSet_Pattern.<br />  
FileSet_Pattern := 
    '/'+{directory_name | Directory_Name_Pattern +'/'}+  
         file_name | File_Name_Pattern.<br />  
Directory_Name_Pattern := 
    (character | Pattern) {character | Pattern}.<br />  
Pattern := 
    '{'+((Virtual_Col_Name+[':'+ Date_Pattern ]) | '*')+'}'.<br />  
Date_Pattern := 
    'yyyy' | 'MM' | 'M' | 'dd' | 'd' | 'HH' | 'H' | 'mm' | 'm' | 'ss' | 's'.<br />  
Virtual_Col_Name := 
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.<br />   
File_Name_Pattern := 
    (character | Pattern) {character | Pattern}.
</pre>

> [!NOTE]   
> The + in the grammar indicates that spaces are not allowed between the parts.

  
The semantics of file sets is the following:    
-   File set patterns can appear either in part of a directory path or in a filename.    
-   Several patterns can appear in the same directory step or file name.    
-   Each pattern is either associated with a virtual column name that has an optional date pattern, or is just a \* wild card.    
-   If the pattern is just a wild card, then file paths that are matching the pattern will be included in the file set, but you cannot refer to the identified pattern in the query.    
-   If the pattern is associated with a virtual column name then file paths matching the pattern will be included, and in addition, the matched values for the pattern will be available through the virtual column name. 
- The virtual column names can be used in subsequent [SELECT](select-clause-u-sql.md) expressions to eliminate files from the matched files. If the expression can be evaluated at compile time, the files will not be included in the query at all.   
-   The data type of the column is determined by the [EXTRACT](extract-expression-u-sql.md) schema.    
-   If a date pattern is provided, then the virtual column has to be of type DateTime and the column can be compared against constant DateTime values in a predicate in the script to eliminate files from the processing.

Not all of the date patterns have to be specified for a given virtual column. If a pattern is conflicting with another pattern then no path will be found. Currently the year (`yyyy`), month (`MM` or `M`), day (`dd` or `d`), hours (`HH` or `H`), minutes (`mm` or `m`) and second (`ss` or `s`) patterns are supported.  

  
For more details and examples on extracting from file sets, please see [EXTRACT Expression (U-SQL)](extract-expression-u-sql.md).  
   
## Examples    
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- SearchLog.tsv is available @ https://github.com/Azure/usql/blob/master/Examples/Samples/Data/SearchLog.tsv.

**Single_File_Path: Default_Account_Path_URI**   
```sql
@searchLog =  
    EXTRACT UserId          int  
          , Start           DateTime  
          , Region          string  
          , Query           string  
          , Duration        int  
          , Urls            string  
          , ClickedUrls     string
    FROM "/Samples/Data/SearchLog.tsv"
    USING Extractors.Tsv();

// The file created below will be used in later examples; otherwise, the OUTPUT statement is not necessarily needed.
OUTPUT @searchLog
TO "/Samples/Outputs/ExampleA.csv" 
USING Outputters.Csv();
```

**Single_File_Path: ADL_Path_URI**    
```sql
@searchLog =  
    EXTRACT UserId          int  
          , Start           DateTime  
          , Region          string  
          , Query           string  
          , Duration        int  
          , Urls            string  
          , ClickedUrls     string  
    FROM "adl://<adl_accountname>.azuredatalakestore.net/Samples/Data/SearchLog.tsv"
    USING Extractors.Tsv();

// The file created below will be used in later examples; otherwise, the OUTPUT statement is not necessarily needed.
OUTPUT @searchLog
TO "/Samples/Outputs/ExampleB.csv" 
USING Outputters.Csv();
```

**Single_File_Path: WASB_Path_URI**   
```sql
@searchLog =  
    EXTRACT UserId          int  
          , Start           DateTime  
          , Region          string  
          , Query           string  
          , Duration        int  
          , Urls            string  
          , ClickedUrls     string  
    FROM "wasb://<wasb_container>@<wasb_accountname>/SearchLog.tsv"
    USING Extractors.Tsv();

// The OUTPUT statement is not necessarily needed.
OUTPUT @searchLog
TO "/Samples/Outputs/wasb.csv" 
USING Outputters.Csv();
```

**List_File_Path**   
This example extracts data from the two files created in earlier examples by enumerating each file.
```sql
@searchLog =  
    EXTRACT UserId          int  
          , Start           DateTime  
          , Region          string  
          , Query           string  
          , Duration        int  
          , Urls            string  
          , ClickedUrls     string
    FROM "/Samples/Outputs/ExampleA.csv",
         "/Samples/Outputs/ExampleB.csv"
    USING Extractors.Csv();

// The file created below will be used in a later example; otherwise, the OUTPUT statement is not necessarily needed.
OUTPUT @searchLog
TO "/Samples/Outputs/ExampleC.csv" 
USING Outputters.Csv();
```

**File_Set_Path**   
This example extracts data from the three files created in earlier examples by using a file set pattern.
```sql
@searchLog =  
    EXTRACT UserId          int  
          , Start           DateTime  
          , Region          string  
          , Query           string  
          , Duration        int  
          , Urls            string  
          , ClickedUrls     string
    FROM "/Samples/Outputs/Example{*}.csv"
    USING Extractors.Csv();

// The OUTPUT statement is not necessarily needed.
OUTPUT @searchLog
TO "/Samples/Outputs/FileSetPattern.csv" 
USING Outputters.Csv();
```

**Virtual Columns**  
This example schematizes the files specified by the file set in the FROM clause. The schema contains the additional virtual columns date and filename that are part of the file set pattern and will be used in later query expressions to identify the actual selected files. 
See additional virtual columns usgae examples @ [EXTRACT Expression (U-SQL)](https://msdn.microsoft.com/azure/data-lake-analytics/u-sql/extract-expression-u-sql).
```sql
// Sample file naming convention: vehicle1_09142014.csv, vehicle2_09142014.csv
// Sample directory naming convention: /Samples/Data/AmbulanceData/2014/09/15/, /Samples/Data/AmbulanceData/2014/09/14/

DECLARE @dir string = "/Samples/Data/AmbulanceData/";
DECLARE @file_set_path2 string = @dir + "{date:yyyy}/{date:MM}/{date:dd}/vehicle{vid}_{*}.csv";

@data = 
    EXTRACT vehicle_id int, 
            entry_id long, 
            event_date DateTime, 
            latitude float, 
            longitude float, 
            speed int, 
            direction string, 
            trip_id int?, 
            vid int,      // virtual file set column
            date DateTime // virtual file set column
    FROM @file_set_path2
    USING Extractors.Csv();

// sample usage 1
@result1 =
    SELECT *
    FROM @data
    WHERE date == DateTime.Parse("2014-09-15")
    AND vid == 2;

// sample usage 2
@result2 =
    SELECT *
    FROM @data
    WHERE date >= DateTime.Now.AddDays(-30) AND date <= DateTime.Now.AddDays(-1)
    AND vid == 2;

OUTPUT @result1
TO "/ReferenceGuide/Concepts/FileSets/InputFiles/Example1.txt"
USING Outputters.Csv();

OUTPUT @result2
TO "/ReferenceGuide/Concepts/FileSets/InputFiles/Example2.txt"
USING Outputters.Csv();
```


## See Also
- [Files and File Sets as Inputs and Outputs (U-SQL)](files-and-file-sets-as-inputs-and-outputs-u-sql.md) 
- [Output to Files (U-SQL)](output-to-files-u-sql.md)  
- [EXTRACT Expression (U-SQL)](extract-expression-u-sql.md) 
- [U-SQL Built-in Extractors](u-sql-built-in-extractors.md)
