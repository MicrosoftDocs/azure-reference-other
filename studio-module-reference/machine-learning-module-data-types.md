---
title: "ML Studio (classic): Module Data Types - Azure"
description: Learn about the .NET data types for external data and the custom data type classes that are used for passing data between modules within an experiment.
ms.date: 01/31/2018
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
---
# ML Studio (classic) Module Data Types

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes the .NET data types that are supported in Machine Learning Studio (classic) for external data. It also describes the custom data type classes that are used for passing data between modules within an experiment.

##  <a name="types"></a> Table of .NET data types

The following .NET types are supported by Machine Learning Studio (classic) modules.

|.NET Data Type|Comments|  
|--------------------|--------------|  
|Boolean|[https://msdn.microsoft.com/library/wts33hb3.aspx](https://msdn.microsoft.com/library/wts33hb3.aspx)|  
|Int16|[https://msdn.microsoft.com/library/system.int16(v=vs.110).aspx](https://msdn.microsoft.com/library/system.int16\(v=vs.110\).aspx)|  
|Int32|[https://msdn.microsoft.com/library/06bkb8w2.aspx](https://msdn.microsoft.com/library/06bkb8w2.aspx)|  
|Int64|[https://msdn.microsoft.com/library/system.int64.aspx](https://msdn.microsoft.com/library/system.int64.aspx)|  
|Single|[https://msdn.microsoft.com/library/system.single(v=vs.110).aspx](https://msdn.microsoft.com/library/system.single\(v=vs.110\).aspx)|  
|Double|[https://msdn.microsoft.com/library/system.double(v=vs.110).aspx](https://msdn.microsoft.com/library/system.double\(v=vs.110\).aspx)|  
|String|[https://msdn.microsoft.com/library/system.string(v=vs.110).aspx](https://msdn.microsoft.com/library/system.string\(v=vs.110\).aspx)|  
|datetime|[https://msdn.microsoft.com/library/system.datetime(v=vs.110).aspx](https://msdn.microsoft.com/library/system.datetime\(v=vs.110\).aspx)|  
|DateTimeOffset|[https://msdn.microsoft.com/library/system.datetimeoffset(v=vs.110).aspx](https://msdn.microsoft.com/library/system.datetimeoffset\(v=vs.110\).aspx)|  
|TimeSpan|[https://msdn.microsoft.com/library/system.timespan(v=vs.110).aspx](https://msdn.microsoft.com/library/system.timespan\(v=vs.110\).aspx)|  
|Byte|[https://msdn.microsoft.com/library/system.byte(v=vs.110).aspx](https://msdn.microsoft.com/library/system.byte\(v=vs.110\).aspx)|  
|Byte[]|[https://msdn.microsoft.com/library/system.byte.aspx](https://msdn.microsoft.com/library/system.byte.aspx)|  
|Guid|GUIDs are converted to strings on input|  

## Table of custom data types

In addition, Machine Learning Studio (classic) supports the following custom data classes.  

|Data Type|Description|  
|---------------|-----------------|  
|[Data Table](data-table.md)|The DataTable interface defines the structure of all datasets used in Machine Learning.|  
|[ICluster interface](icluster-interface.md)|The ICluster interface defines the structure of clustering models.|  
|[IFilter interface](ifilter-interface.md)|The IFilter interface defines the structure of digital signal processing filters applied to an entire series of numerical values. Filters can be created and then saved and applied to a new series.|  
|[ILearner interface](ilearner-interface.md)|The ILearner interface provides a generic structure for defining and saving analytical models, excluding some special types such as clustering models.|  
|[ITransform interface](itransform-interface.md)|The ITransform interface provides a generic structure for defining and saving transformations. You can create an iTransform using Machine Learning Studio (classic) and then apply the transformation to new datasets.|  

## See also

 [Machine Learning Studio (classic)](/azure/machine-learning/studio-module-reference/index)
