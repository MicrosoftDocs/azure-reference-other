---
title: "ML Studio (classic): Data Transformation: Counts - Azure"
description: "Learn about the modules that support count-based featurization."
ms.custom: "formulas"
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Data Transformation - Learning with Counts

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes the modules in Machine Learning Studio (classic) that support count-based featurization.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

Learning with counts is an efficient way to create a compact set of dataset features that are based on counts of the values. You can use the modules in this category to build a set of counts and features. Later, you can update the counts and the features to take advantage of new data, or merge two sets of count data.

## About count-based featurization

The basic idea of *count-based featurization* is that by calculating counts, you can quickly and easily get a summary of what columns contain the most important information. The module counts the number of times a value appears, and then provides that information as a feature for input to a model.

Imagine that you’re validating a credit card transaction. A crucial piece of information is where this transaction came from. One of the most common encodings of the transaction origin is the postal code. However, there might be as many as 40,000 postal codes, zip codes, and geographical codes to account for. Does your model have the capacity to learn 40,000 more parameters? If you give it that capacity, do you have enough training data to prevent it from overfitting?

If you have good data, with lots of samples, such fine-grained local granularity can be powerful. However, if you have only one sample of a fraudulent transaction, from a small locality, does it mean that all of the transactions from that place are bad, or that you don’t have enough data?

One solution is to learn with counts. Instead of introducing 40,000 more features, you can observe the counts and proportions of fraud for each postal code. By using these counts as features, you get information about the strength of the evidence for each value. Moreover, by encoding the relevant statistics of the counts, the learner can use the statistics to decide when to change their approach and instead use other features to get the information.
 
Count-based learning is attractive for many reasons. With count-based learning, you have fewer features, which requires fewer parameters. Fewer parameters makes for faster learning, faster prediction, smaller predictors, and less potential to overfit.

### How count-based features are created

A basic example can help demonstrate how count-based features are created and applied. Suppose you have the following table like this, with labels and inputs. Each case (or row or sample) has a set of values in columns. In this example, the values are A and B.
 
|Label column|Input value|
|------------------|-----------------|
|0|A|
|0|A|
|1|A|
|0|B|
|1|B|
|1|B|
|1|B|

These are the steps you take to create count-based features:

1. For a specific set of values, find all the other cases in that dataset that have the same value. In this case, there are three instances of A and four instances of B.
2. Count the class membership of each value as a feature in itself. In this case, you get a small matrix: there are two cases where A = 0; one case where A = 1; one case where B = 0; and three cases where B = 1.
3. Based on this matrix, you get a variety of count-based features. These include a calculation of the log-odds ratio and the counts for each target class. The table in the next section displays the data.

### Sample table of count-based features

|Label|0_0_Class000_Count|0_0_Class001_Count|0_0_Class000_LogOdds|0_0_IsBackoff|
|-----------|---------------------------|---------------------------|-----------------------------|---------------------|
|0|2|1|0.510826|0|
|0|2|1|0.510826|0|
|1|2|1|0.510826|0|
|0|1|3|-0.8473|0|
|1|1|3|-0.8473|0|
|1|1|3|-0.8473|0|
|1|1|3|-0.8473|0|
 
## Examples

In [Use Machine Learning to build clickthrough prediction models](https://go.microsoft.com/fwlink/?LinkId=699305), the Microsoft Machine Learning team provides a detailed walkthrough of how to use counts in machine learning. The article compares the efficacy of count-based modeling with other methods.
 
## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### How the log-loss value is calculated
 
The log-loss value is not the plain log-odds. In this case, the prior distribution is used to smooth the log-odds computation.

Suppose you have a dataset that's used for binary classification. In this dataset, the prior frequency for class 0 is `p_0`, and the prior frequency for class 1 is `p_1 = 1 – p_0`. For a specific training example feature, the count for class 0 is `x_0`, and the count for class 1 is `x_1`.

Under these assumptions, the log-odds is computed as `LogOdds = Log(x0 + c * p0) – Log (x1 + c\p1)`, where `c` is the prior coefficient, which can be set by the user. The log function uses the natural base.

In other words, for each class `i`:
 
`Log_odds[i] = Log( (count[i] + prior_coefficient * prior_frequency[i]) / (sum_of_counts - count[i]) + prior_coefficient \* (1 - prior_frequency[i]))`
 
If the prior coefficient is positive, the log-odds can be different from `Log(count[i] / (sum_of_counts – count[i]))`.

### Why the log-odds aren't computed for some items

By default, all items with a count that's less than 10 are collected in a single bucket called the "garbage bin." You can change this value by using the **Garbage bin threshold** option in the [Modify Count Table Parameters](modify-count-table-parameters.md) module.

## List of modules

The **Learning with Counts** category includes the following modules:

- [Build Counting Transform](build-counting-transform.md): Creates a count table and count-based features from a dataset, and then saves the table and features as a transformation.
- [Export Count Table](export-count-table.md): Exports a count table from a counting transform. This module supports backward compatibility with experiments that create count-based features by using Build Count Table (deprecated) and Count Featurizer (deprecated).
- [Import Count Table](import-count-table.md): Imports an existing count table. This module supports backward compatibility with experiments that create count-based features by using Build Count Table (deprecated) and Count Featurizer (deprecated). The module supports conversion of count tables to count transformations.
- [Merge Count Transform](merge-count-transform.md): Merges two sets of count-based features.
- [Modify Count Table Parameters](modify-count-table-parameters.md): Modifies count-based features that are derived from an existing count table.
 
## See also

- [Data Transformation](data-transformation.md)
- [Feature Selection](feature-selection-modules.md)
