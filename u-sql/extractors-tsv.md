---
title: "Extractors.Tsv() | Microsoft Docs"
ms.custom: ""
ms.date: "03/28/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 50842423-ab2c-4300-9509-5a087be36578
caps.latest.revision: 6
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Extractors.Tsv()
The Tsv() extractor disallows the `delimiter` parameter and defaults the field delimiter to '\t' (tab). All other parameters are the same.   See [Extractor Parameters (U-SQL)](extractor-parameters-u-sql.md) for supported parameters and their defaults values.   
  
## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- `SearchLog.tsv` is available @ https://github.com/Azure/usql/blob/master/Examples/Samples/Data/SearchLog.tsv.
- `Drivers.txt` is available @ https://github.com/Azure/usql/blob/master/Examples/Samples/Data/AmbulanceData/Drivers.txt.


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
        USING Extractors.Tsv(skipFirstNRows: 1);

OUTPUT @searchlog 
TO "/Output/ReferenceGuide/BuiltIn/UDOs/extractorTsv_SearchLog.csv" 
USING Outputters.Csv();
    
    
// TAB Separated Unicode file
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
    USING Extractors.Tsv(encoding:Encoding.Unicode);

OUTPUT @Drivers 
TO "/Output/ReferenceGuide/BuiltIn/UDOs/extractorTsv_Drivers.csv" 
USING Outputters.Csv();
```
<br />

## See Also 
* [Extractor Parameters (U-SQL)](extractor-parameters-u-sql.md)
* [Extractors.Text()](extractors-text.md) 
* [Extractors.Csv()](extractors-csv.md)  
* [Built-in U-SQL UDOs](built-in-u-sql-udos.md)
* [EXTRACT Expression (U-SQL)](extract-expression-u-sql.md) 
* [Input Files (U-SQL)](input-files-u-sql.md)

