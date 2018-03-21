---
title: "Machine Learning Module Data Types | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/31/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9cfd19ab-5ddd-4810-82a5-0a299fca1372
caps.latest.revision: 7
author: rastala
ms.author: roastala
manager: cgronlun
---
# Machine Learning Module Data Types

This article describes the .NET data types that are supported in Microsoft Azure Machine Learning Studio for external data. It also describes the custom data type classes that are used for passing data between modules within an experiment.

##  <a name="types"></a> Table of .NET data types

The following .NET types are supported by Machine Learning Studio modules.

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

In addition, Machine Learning Studio supports the following custom data classes.  

|Data Type|Description|  
|---------------|-----------------|  
|[Data Table](data-table.md)|The DataTable interface defines the structure of all datasets used in Azure Machine Learning.|  
|[ICluster interface](icluster-interface.md)|The ICluster interface defines the structure of clustering models.|  
|[IFilter interface](ifilter-interface.md)|The IFilter interface defines the structure of digital signal processing filters applied to an entire series of numerical values. Filters can be created and then saved and applied to a new series.|  
|[ILearner interface](ilearner-interface.md)|The ILearner interface provides a generic structure for defining and saving analytical models, excluding some special types such as clustering models.|  
|[ITransform interface](itransform-interface.md)|The ITransform interface provides a generic structure for defining and saving transformations. You can create an iTransform using Machine Learning Studio and then apply the transformation to new datasets.|  

## See also

 [Machine Learning Studio](machine-learning-studio-algorithm-and-module-help.md)