---
title: "Method Syntax in U-SQL | Microsoft Docs"
ms.custom: ""
ms.date: "07/01/2018"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
caps.latest.revision: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Method Syntax in U-SQL
The methods in the [Enumberable Class](https://docs.microsoft.com/dotnet/api/system.linq.enumerable) provide an implementation of the standard query operators for querying data sources that implement [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1). The standard query operators are general purpose methods that follow the LINQ pattern and enable you to express traversal, filter, and projection operations over data in any .NET-based programming language. 


## In This Section    
|Method|Description|  
|------------|-----------------|  
|[Aggregate](aggregate-method-syntax-in-u-sql.md)|Applies an accumulator function over a sequence.|  
|[All](all-method-syntax-in-u-sql.md)|Determines whether all elements of a sequence satisfy a condition.|
|[Any](any-method-syntax-in-u-sql.md)|Determines whether any element of a sequence exists or satisfies a condition.|
|[Append](append-method-syntax-in-u-sql.md)|Appends a value to the end of the sequence.|
|[AsEnumerable](asenumerable-method-syntax-in-u-sql.md)|Returns the input typed as [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1).|
|[Average](averge-method-syntax-in-u-sql.md)|Computes the average of a sequence of numeric values.|
|[Cast](cast-method-syntax-in-u-sql.md)|Casts the elements of an [IEnumerable](https://docs.microsoft.com/dotnet/api/system.collections.ienumerable) to the specified type.|
|[Concat](concat-method-syntax-in-u-sql.md)|Concatenates two sequences.|
|[Contains](contains-method-syntax-in-u-sql.md)|Determines whether a sequence contains a specified element.|
|[Count](count-method-syntax-in-u-sql.md)|Returns the number of elements in a sequence.|
|[DefaultIfEmpty](defaultifempty-method-syntax-in-u-sql.md)|Returns the elements of an [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1), or a default valued singleton collection if the sequence is empty.|
|[Distinct](distinct-method-syntax-in-u-sql.md)|Returns distinct elements from a sequence.|
|[ElementAt](elementat-method-syntax-in-u-sql.md)|Returns the element at a specified index in a sequence.|
|[ElementAtOrDefault](elementatordefault-method-syntax-in-u-sql.md)|Returns the element at a specified index in a sequence or a default value if the index is out of range.|
|[Empty](empty-method-syntax-in-u-sql.md)|Returns an empty [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1) that has the specified type argument.|
|[Except](except-method-syntax-in-u-sql.md)|Produces the set difference of two sequences.|
|[First](first-method-syntax-in-u-sql.md)|Returns the first element of a sequence.|
|[FirstOrDefault](firstordefault-method-syntax-in-u-sql.md)|Returns the first element of a sequence, or a default value if no element is found.|
|[GroupBy](groupby-method-syntax-in-u-sql.md)|Groups the elements of a sequence.|
|[Intersect](intersect-method-syntax-in-u-sql.md)|Produces the set intersection of two sequences.|
|[Join](join-method-syntax-in-u-sql.md)|Correlates the elements of two sequences based on matching keys.|
|[Last](last-method-syntax-in-u-sql.md)|Returns the last element of a sequence.|
|[LastOrDefault](lastordefault-method-syntax-in-u-sql.md)|Returns the last element of a sequence, or a default value if no element is found.|
|[LongCount](longcount-method-syntax-in-u-sql.md)|Returns an Int64 that represents the number of elements in a sequence.|
|[Max](max-method-syntax-in-u-sql.md)|Returns the maximum value in a sequence of values.|
|[Min](min-method-syntax-in-u-sql.md)|Returns the minimum value in a sequence of values.|
|[OfType](oftype-method-syntax-in-u-sql.md)|Filters the elements of an [IEnumerable](https://docs.microsoft.com/dotnet/api/system.collections.ienumerable) based on a specified type.|
|[OrderBy](orderby-method-syntax-in-u-sql.md)|Sorts the elements of a sequence in ascending order.|
|[OrderByDescending](orderbydescending-method-syntax-in-u-sql.md)|Sorts the elements of a sequence in descending order.|
|[Prepend](prepend-method-syntax-in-u-sql.md)|Adds a value to the beginning of the sequence.|
|[Range](range-method-syntax-in-u-sql.md)|Generates a sequence of integral numbers within a specified range.|
|[Repeat](repeat-method-syntax-in-u-sql.md)|Generates a sequence that contains one repeated value.|
|[Reverse](reverse-method-syntax-in-u-sql.md)|Inverts the order of the elements in a sequence.|
|[Select](select-method-syntax-in-u-sql.md)|Projects each element of a sequence into a new form.|
|[SelectMany](selectmany-method-syntax-in-u-sql.md)|Projects each element of a sequence to an [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1) and flattens the resulting sequences into one sequence.|
|[SequenceEqual](sequenceequal-method-syntax-in-u-sql.md)|Determines whether two sequences are equal according to an equality comparer.|
|[Single](single-method-syntax-in-u-sql.md)|Returns a single, specific element of a sequence.|
|[SingleOrDefault](singleordefault-method-syntax-in-u-sql.md)|Returns a single, specific element of a sequence, or a default value if that element is not found.|
|[Skip](skip-method-syntax-in-u-sql.md)|Bypasses a specified number of elements in a sequence and then returns the remaining elements.|
|[SkipWhile](skipwhile-method-syntax-in-u-sql.md)|Bypasses elements in a sequence as long as a specified condition is true and then returns the remaining elements.|
|[Sum](sum-method-syntax-in-u-sql.md)|Computes the sum of a sequence of numeric values.|
|[Take](take-method-syntax-in-u-sql.md)|Returns a specified number of contiguous elements from the start of a sequence.|
|[TakeWhile](takewhile-method-syntax-in-u-sql.md)|Returns elements from a sequence as long as a specified condition is true, and then skips the remaining elements.|
|[ThenBy](thenby-method-syntax-in-u-sql.md)|Performs a subsequent ordering of the elements in a sequence in ascending order.|
|[ThenByDescending](thenbydescending-method-syntax-in-u-sql.md)|Performs a subsequent ordering of the elements in a sequence in descending order.|
|[ToArray](toarray-method-syntax-in-u-sql.md)|Creates an array from an [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1).|
|[ToDictionary](todictionary-method-syntax-in-u-sql.md)|Creates a [Dictionary<TKey,TValue>](https://docs.microsoft.com/dotnet/api/system.collections.generic.dictionary-2)  from an [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1).|
|[ToList](tolist-method-syntax-in-u-sql.md)|Creates a [List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1) from an [IEnumerable\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.ienumerable-1).|
|[Union](union-method-syntax-in-u-sql.md)|Produces the set union of two sequences.|
|[where](where-method-syntax-in-u-sql.md)|Filters a sequence of values based on a predicate.|
|[Zip](zip-method-syntax-in-u-sql.md)|Applies a specified function to the corresponding elements of two sequences, producing a sequence of the results.|



## See Also
* [Query Syntax in U-SQL](query-syntax-in-u-sql.md)
* [Standard Query Operators Overview (C#)](https://docs.microsoft.com/dotnet/csharp/programming-guide/concepts/linq/standard-query-operators-overview)
* [Enumerable Class](https://docs.microsoft.com/dotnet/api/system.linq.enumerable)
* [Query Keywords (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/query-keywords)

