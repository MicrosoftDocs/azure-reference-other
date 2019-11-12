---
title: "Deprecated modules and features | Microsoft Docs"
description: "Review deprecated modules and functionality in Azure Machine Learning Studio (classic)."
titleSuffix: ML Studio (classic) - Azure
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Deprecated modules and functionality

This article lists Azure Machine Learning Studio (classic) modules and functionality that have been deprecated.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

To maintain backward compatibility with earlier versions of Machine Learning Studio (classic), some functionality, including machine learning algorithms and data processing modules, remain available to support existing experiments. Deprecated modules and functionality aren't available to use when you create new experiments.
 
We recommend that you modify your experiments to use the newer modules as soon as possible. The newer modules provide all the functionality of the deprecated module, in addition to some improvements.
 
The following table lists the deprecated modules and the new modules that replace them.
 
## Deprecated modules

- [Apply Quantization Function (deprecated)](apply-quantization-function-deprecated.md)

  **Use instead**: [Group Data into Bins](group-data-into-bins.md)
- [Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md)

  **Use instead**: [Assign Data to Clusters](assign-data-to-clusters.md)
- [Build Count Table (deprecated)](build-count-table-deprecated.md)

  **Use instead**: [Build Counting Transform](build-counting-transform.md)
- [Count Featurizer (deprecated)](count-featurizer-deprecated.md)

  **Use instead**: [Modify Count Table Parameters](modify-count-table-parameters.md)  
  
  Related modules: [Merge Count Transform](merge-count-transform.md), [Export Count Table](export-count-table.md), [Import Count Table](import-count-table.md)
- [Linear Discriminant Analysis (deprecated)](linear-discriminant-analysis-deprecated.md)

  **Use instead**: [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md)
- [Missing Values Scrubber (deprecated)](missing-values-scrubber-deprecated.md)

  **Use instead**: [Clean Missing Data](clean-missing-data.md)
- [Quantize (deprecated)](quantize-deprecated.md)

  **Use instead**: [Group Data into Bins](group-data-into-bins.md)
 
## See also

- [A-Z module list](a-z-module-list.md)
