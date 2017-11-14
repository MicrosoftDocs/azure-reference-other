---
title: "USING Keyword | Microsoft Docs"
ms.custom: ""
ms.date: "2017-04-19"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 7e40faaa-c1b9-4903-b153-fe42f78d27a2
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# USING Keyword
The `USING` directive is similar to the [C# using Directive](https://msdn.microsoft.com/library/sf0df423.aspx) in that it allows to shorten function, type, extention methods, and UDO path names.

<table><th>Syntax</th><tr><td><pre>
Using_Directive :=                                                                                
      'USING' 
      ( csharp_namespace | Alias '=' csharp_namespace_or_type ['.' class]).
</pre></td></tr></table>

The scope of a using directive is limited to the file in which it appears.

Create a using alias to make it easier to qualify an identifier to a namespace or type. The right side of a using alias directive must always be a fully-qualified type regardless of the using directives that come before it.

Create a using directive to use the types in a namespace without having to specify the namespace. A using directive does not give you access to any namespaces that are nested in the namespace you specify.

### Examples

**Specify namespace**    
In this example we default C# namespace resolution to the specified namespace:
```
DECLARE @ input string = "somejsonfile.json";

REFERENCE ASSEMBLY [Newtonsoft.Json];
REFERENCE ASSEMBLY [Microsoft.Analytics.Samples.Formats];

USING Microsoft.Analytics.Samples.Formats.Json;

@data0 = 
    EXTRACT IPAddresses string
    FROM @input
    USING new JsonExtractor("Devices[*]");

...
```

**Alias namespace**   
In this example we use an alias to shorten the namespace path with an alias:
```
DECLARE @ input string = "somejsonfile.json";

REFERENCE ASSEMBLY [Newtonsoft.Json];
REFERENCE ASSEMBLY [Microsoft.Analytics.Samples.Formats];

USING json = Microsoft.Analytics.Samples.Formats.Json;

@data0 = 
    EXTRACT IPAddresses string
    FROM @input
    USING new json.JsonExtractor("Devices[*]");

...
```

**Alias Type**    
In the following example, we alias the full type name. Note that we support quoting the name to allow all uppercase namespaces.
```
DECLARE @ input string = "somejsonfile.json";

REFERENCE ASSEMBLY [Newtonsoft.Json];
REFERENCE ASSEMBLY [Microsoft.Analytics.Samples.Formats];

USING json = [Microsoft.Analytics.Samples.Formats.Json.JsonExtractor];

@data0 = 
    EXTRACT IPAddresses string
    FROM @input
    USING new json("Devices[*]");

...
```

**Additional Examples**   
See the examples under:
* [Code-Behind vs. Assembly Registration Walkthrough](extending-u-sql-expressions-with-user-code.md#usingAssemblies)
* [REFERENCE ASSEMBLY (U-SQL)](reference-assembly-u-sql.md)


### See Also
* [U-SQL Assemblies](u-sql-assemblies.md)  
* [Built-in Functions (U-SQL)](built-in-functions-u-sql.md)  
* [U-SQL Programmability Guide](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
