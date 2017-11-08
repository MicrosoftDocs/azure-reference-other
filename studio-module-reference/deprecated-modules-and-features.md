---
title: "Deprecated Modules and Features | Microsoft Docs"
ms.custom: ""
ms.date: 09/22/2015
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d88e45c9-9c3c-4e5c-8bc9-7a80af8113c2
caps.latest.revision: 9
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Deprecated Modules and Features
To maintain backward compatibility with earlier versions of Azure Machine Learning, some features, including machine learning algorithms and data processing modules, remain available to support existing experiments, but are not available when you create new experiments.  
  
 We recommend that you modify your experiments to use the newer modules as soon as possible. The newer modules provide all the functionality of the deprecated module, as well as some improvements.  
  
 The following table lists the deprecated modules and the new modules that replace them.  
  
## Deprecated Modules  
  
|Deprecated module|Replaced with|  
|-----------------------|-------------------|  
|[Apply Quantization Function (deprecated)](apply-quantization-function-deprecated.md)|[Group Data into Bins](group-data-into-bins.md)|  
|[Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md)|[Assign Data to Clusters](assign-data-to-clusters.md)|  
|[Build Count Table (deprecated)](build-count-table-deprecated.md)|[Build Counting Transform](build-counting-transform.md)|  
|[Count Featurizer (deprecated)](count-featurizer-deprecated.md)|[Modify Count Table Parameters](modify-count-table-parameters.md)<br /><br /> Also see:<br /><br /> [Merge Count Transform](merge-count-transform.md)<br /><br /> [Export Count Table](export-count-table.md)<br /><br /> [Import Count Table](import-count-table.md)|  
|[Linear Discriminant Analysis (deprecated)](linear-discriminant-analysis-deprecated.md)|[Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md)|  
|[Missing Values Scrubber (deprecated)](missing-values-scrubber-deprecated.md)|[Clean Missing Data](clean-missing-data.md)|  
|[Quantize (deprecated)](quantize-deprecated.md)|[Group Data into Bins](group-data-into-bins.md)|  
  
## See Also  
 [A-Z Module List](a-z-module-list.md)