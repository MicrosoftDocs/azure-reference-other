---
title: "IMPORT PACKAGE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "05/02/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d001cc2f-51ca-48cd-b8e9-e2ce437d54b6
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# IMPORT PACKAGE (U-SQL)
The `IMPORT PACKAGE` statement will import all the [assembly references](u-sql-assemblies.md), variable declarations and resource deployments exported by the specified package. The package identifier will be resolved in the static context of its invocation and can refer to a package in the current account or a different Azure Data Lake Analytics account. The optional arguments can be used inside the package.

If conflicting assemblies or references are being referenced, imported or deployed, errors are raised once a package gets imported in the main U-SQL script.

<table><th align="left">Syntax</th><tr><td><pre>
Import_Package_Statement :=                                                                              
    'IMPORT' 'PACKAGE' Global_Identifier ['(' [Argument_List] ')'] [Package_Alias].<br />
Package_Alias :=
    'AS' Package_Name_Alias.<br />
Package_Name_Alias := 
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>

The optional package alias must be used when referring to variables imported from the given package.

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples utilize the packages created from [CREATE PACKAGE (U-SQL)](create-package-u-sql.md).

The following script uses the now the previously defined package `XMLorJSON` from database `TestReferenceDB` with the parameter `xml` and parses the XML file that was provided in the package's `@xmlfile` variable. Please note that the file deployment will occur as well, but is not really required for this script to work.
```sql
IMPORT PACKAGE TestReferenceDB.dbo.XMLorJSON("xml") AS xmlpackage;

USING xml = Microsoft.Analytics.Samples.Formats.Xml;

// Currently the EXTRACT FROM and OUTPUT TO clauses do not support package variables.
// Therefore we need to rename them.
DECLARE @input = xmlpackage.@xmlfile;

@configdata =
EXTRACT option1 string,
        option2 string,
        option3 string
FROM @input
USING new xml.XmlDomExtractor("/config", 
                                new SqlMap<string,string>{
                                    {"option1", "option1"},
                                    {"option2", "option2"}, 
                                    {"option3", "option3"}});

@res =
SELECT xmlpackage.@format AS format,
        *
FROM @configdata;

OUTPUT @res
TO "/output/packexample.csv"
USING Outputters.Csv();
```

### See Also
* [CREATE PACKAGE (U-SQL)](create-package-u-sql.md)
* [DROP PACKAGE (U-SQL)](drop-package-u-sql.md)  
