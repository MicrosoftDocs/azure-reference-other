---
title: "Extractors.Text() | Microsoft Docs"
ms.custom: ""
ms.date: "03/28/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8eb9cc92-0533-4039-b769-ef90dc9b63f9
caps.latest.revision: 8
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Extractors.Text()
The Text() extractor supports a variety of text file formats that all follow a row/column format. It provides a set of delimiters to identify the row and column boundaries and several other parameters to parse the text file and produces a rowset based on the [EXTRACT](extract-expression-u-sql.md) expression’s schema.  
  
See [Extractor Parameters (U-SQL)](extractor-parameters-u-sql.md) for supported parameters and their defaults values.
  
## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- `SearchLog.tsv` is available @ https://github.com/Azure/usql/blob/master/Examples/Samples/Data/SearchLog.tsv.
- `Drivers.txt` is available @ https://github.com/Azure/usql/blob/master/Examples/Samples/Data/AmbulanceData/Drivers.txt.
- `DriverShiftTrips.csv` is available @ https://github.com/Azure/usql/blob/master/Examples/Samples/Data/AmbulanceData/DriverShiftTrips.csv.


**Basic Syntax**  
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
    USING Extractors.Text(delimiter: '\t', skipFirstNRows: 1);

OUTPUT @searchlog 
TO "/ReferenceGuide/BuiltIn/UDOs/ExtractorText/SearchLog.csv" 
USING Outputters.Csv();
```

**Additionl Example**  
```sql
@Drivers =
    EXTRACT driver_id   int,
        name            string,
        street          string,
        city            string,
        region          string,
        zipcode         string,
        country         string,
        phone_numbers   string // Map
    FROM "/Samples/Data/AmbulanceData/Drivers.txt"
    USING Extractors.Text(delimiter: '\t', encoding:Encoding.Unicode);

OUTPUT @Drivers 
TO "/ReferenceGuide/BuiltIn/UDOs/ExtractorText/Drivers.csv" 
USING Outputters.Csv();
```

**Using a Code Page Identifier**  
Using file created from `OUTPUT` example [Using a Code Page Identifier](outputters-tsv.md#cpi).
```sql
@data = 
   EXTRACT text string 
   FROM "/ReferenceGuide/BuiltIn/UDOs/Outputters/text_1258.txt"
   USING Extractors.Tsv(encoding: System.Text.Encoding.GetEncoding("Windows-1258")); // Calling by name

OUTPUT @data
TO "/ReferenceGuide/BuiltIn/UDOs/ExtractorText/text_1258.txt" 
USING Outputters.Tsv(encoding: System.Text.Encoding.GetEncoding(1258)); // Calling by number
```

**ASCI Encoding**  
You need to quote ASCII with [] to make sure it is not read as a reserved U-SQL keyword
```sql
@Trips =
    EXTRACT date    DateTime,
        driver_id   int,
        vehicle_id  int,
        trips       string // Array
        FROM "/Samples/Data/AmbulanceData/DriverShiftTrips.csv"
        USING Extractors.Text(encoding: Encoding.[ASCII]);

OUTPUT @Trips 
TO "ReferenceGuide/BuiltIn/UDOs/ExtractorText/DriverShiftTrips.csv" 
USING Outputters.Csv();
```
 
## See Also 
* [Extractor Parameters (U-SQL)](extractor-parameters-u-sql.md)
* [Extractors.Csv()](extractors-csv.md)
* [Extractors.Tsv()](extractors-tsv.md)
* [Built-in U-SQL UDOs](built-in-u-sql-udos.md)
* [EXTRACT Expression (U-SQL)](extract-expression-u-sql.md)
* [Input Files (U-SQL)](input-files-u-sql.md)

