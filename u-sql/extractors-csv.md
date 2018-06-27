---
title: "Extractors.Csv() | Microsoft Docs"
ms.custom: ""
ms.date: "03/28/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d7318c71-e822-4852-b941-a86c6f533138
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Extractors.Csv()
The Csv() extractor disallows the `delimiter` parameter and defaults the field delimiter to ',' (comma). All other parameters are the same.  See [Extractor Parameters (U-SQL)](extractor-parameters-u-sql.md) for all supported parameters and their defaults values.
  
## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- `DriverShiftTrips.csv` is available @ https://github.com/Azure/usql/blob/master/Examples/Samples/Data/AmbulanceData/DriverShiftTrips.csv.


```sql
// Excel CSV (ANSI with ASCII only)
// You need to quote ASCII with [] to make sure it is not read as a reserved U-SQL keyword
@Trips =
    EXTRACT date    DateTime,
        driver_id   int,
        vehicle_id  int,
        trips       string // Array
        FROM "/Samples/Data/AmbulanceData/DriverShiftTrips.csv"
        USING Extractors.Csv(encoding: Encoding.[ASCII]);

OUTPUT @Trips 
TO "/ReferenceGuide/BuiltIn/UDOs/extractorCsv_DriverShiftTrips.csv" 
USING Outputters.Csv();
```
<br />

## See Also 
* [Extractor Parameters (U-SQL)](extractor-parameters-u-sql.md)
* [Extractors.Text()](extractors-text.md) 
* [Extractors.Tsv()](extractors-tsv.md)
* [Built-in U-SQL UDOs](built-in-u-sql-udos.md)  
* [EXTRACT Expression (U-SQL)](extract-expression-u-sql.md)
* [Input Files (U-SQL)](input-files-u-sql.md) 
