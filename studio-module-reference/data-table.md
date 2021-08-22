---
title: "ML Studio (classic): Data Table - Azure"
description: Learn about the DataTable, which consists of a collection of columns with associated metadata. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Data Table

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

**Data Table Class**  

A dataset is data that has been uploaded to Machine Learning Studio (classic) so that it can be used in the modeling process.  Even if you upload data in another format, or specify a storage format such as CSV, ARFF, or TSV, the data is implicitly converted to a `DataTable` object whenever used by a module in an experiment.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

The dataset is based on the .NET [Data Table](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.110\).aspx)  
  
## Column types

A `DataTable` consists of a collection of columns with associated metadata.  These columns implement the `IArray` interface. Columns of data in Machine Learning Studio (classic) are understood to be one-dimensional arrays – that is, *vectors*.  

The .NET [Array](https://msdn.microsoft.com/library/system.array.aspx) class implements these generic interfaces:  `System.Collections.Generic.IList<T>`, `System.Collections.Generic.ICollection<T>`, and `System.Collections.Generic.IEnumerable<T>`.  
  

Columns of types `int`, `double`, and `Boolean` are typically represented as numeric dense arrays.  If a dense column contains missing values, it will handled either as a missing values array or as a nullable object dense array.  

Columns containing strings are handled as object dense arrays. If there are missing values, the missing values are represented either as nulls or as the type `MissingValuesObjectArray<string>`.  
  
For more information, see [Array Class (MSDN Library)](https://msdn.microsoft.com/library/system.array.aspx).  
  
## Getting columns in a DataTable  

You can get a column by calling the `GetColumn` method on the DataTable.  The `GetColumn` method has two overloads:  
  
-   `GetColumn(<Int64>)` gets a column by its index.  
  
-   `GetColumn(<string>)` gets a column by its name.  
  
## Other interfaces in Studio (classic)  

This section also describes the following interfaces for Machine Learning Studio (classic):  
  
|Type|Description|  
|----------|-----------------|  
|[ICluster interface](icluster-interface.md)|The ICluster interface defines the structure of clustering models.|  
|[IFilter interface](ifilter-interface.md)|The IFilter interface defines the structure of digital signal processing filters applied to an entire series of numerical values. Filters can be created and then saved and applied to a new series.|  
|[ILearner interface](ilearner-interface.md)|The ILearner interface provides a generic structure for defining and saving analytical models, excluding some special types such as clustering models.|  
|[ITransform interface](itransform-interface.md)|The ITransform interface provides a generic structure for defining and saving transformations. You can create an iTransform using Machine Learning Studio (classic) and then apply the transformation to new datasets.|  
  
## See also  
 [Module Data Types](machine-learning-module-data-types.md)
