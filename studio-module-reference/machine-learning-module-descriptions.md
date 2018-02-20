---
title: "Machine Learning Module Descriptions | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c72a3e1a-29cf-46c1-bf98-bd3d30d62c96
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Machine Learning Module Descriptions

This topic provides an overview of all the *modules* included in Azure Machine Learning Studio, which is an interactive, visual workspace to easily build and test predictive models. 

> [!TIP]
> Click here to learn about new features for the professional data scientist in Azure Machine Learning, such as Machine Learning Workbench: [Azure Machine Learning Concepts](https://docs.microsoft.com/azure/machine-learning/preview/overview-general-concepts). 

## What is a module?  

In Azure Machine Learning Studio, a *module* is a building block for creating experiments. Each module encapsulates a specific machine learning algorithm, function, or code library that can act on data in your workspace. The modules are designed to accept connections from other modules, to share and modify data. 

The code that runs in each module comes from many sources, including open source libraries and languages, algorithms developed by Microsoft Research, and tools for working with Azure and other cloud services. 
 
 > [!TIP]
> Looking for machine learning algorithms? See the [Machine Learning](machine-learning-initialize-model.md) category, which contains modules for decision trees, clustering, neural networks, and more. The [Train](machine-learning-train.md) and [Evaluate](machine-learning-evaluate.md) categories include modules to help train andd test your models. 

By connecting and configuring modules, you can create a workflow that reads data from external sources, prepares it for analysis, applies machine learning algorithms, and generates results. 

When an experiment is open in Studio, you can see the complete list of current modules in the navigation pane at left.  You drag these building blocks into your experiment, and then connect them to create a complete machine learning workflow, called an experiment. 

Sometimes modules are updated to add new functionality, or to remove older code. When this happens, any experiments that you created using the module continue to run, but the next time you open the experiment, you will be prompted to upgrade the module, or to use a different module.

### Examples

For an example of how to build a complete machine learning experiment, see these tutorials:  
  
-   [Develop a predictive solution by using Azure Machine Learning](http://azure.microsoft.com/documentation/articles/machine-learning-walkthrough-develop-predictive-solution/)  
  
-   [Create a simple experiment in Azure Machine Learning Studio](http://azure.microsoft.com/documentation/articles/machine-learning-create-experiment/)  
 
##  Module categories

To make it easier to find related modules, the machine learning tools in Azure Machine Learning Studio are grouped by these categories.

### [Data Format conversions](data-format-conversions.md)

Use these modules to convert data to one of the formats used by other machine learning tools or formats. 

+ [Data Input and Output](data-input-and-output.md)

  Use these modules to read data and models from cloud data sources, including Hadoop clusters, Azure table storage, and Web URLs, or to write results to storage or to a database.  

+ [Data Transformation](data-transformation.md)

  Use these modules to prepare data for analysis. You can change data types, flag columns as features or labels, generate features, and scale or normalize data, and much more.

+ [Filter](data-transformation-filter.md)

  Transform numeric data derived from digital signal processing.

+ [Learning With Counts](data-transformation-learning-with-counts.md)

  Use joint probability distributions to build features that compactly describe large datasets.

+ [Manipulation](data-transformation-manipulation.md)

  This group provides a variety of tools for data science: remove or replace missing values, choose a subset of columns, add column or concatenate two datasets, and so forth.  

+ [Sample and Split](data-transformation-sample-and-split.md)

  Divide a dataset by criteria or by size, to create training and test sets, or to isolate certain rows.

+ [Scale and Reduce](data-transformation-scale-and-reduce.md)

  Transform numerical data. 

### [Feature Selection](feature-selection-modules.md)

Use these modules to identify the best features in your data, using widely researched statistical methods.
  
### [Machine Learning](machine-learning-modules.md)

This group contains most of the machine learning algorithms supported by Azure Machine Learning.

It also contains modules intended to support the algorithms by training models, generating scores, and evaluating model performance.

+ [Evaluate](machine-learning-evaluate.md)

  After you have trained a model, use these tools to measure the model’s accuracy.

+ [Initialize](machine-learning-initialize-model.md)

  These modules provide the machine learning algorithms, which you can customize by setting parameters. The algorithms in this section are grouped by type:

  + [Anomaly detection algorithms](anomaly-detection.md)
  + [Classification algorithms](machine-learning-initialize-model-classification.md)
  + [Clustering algorithms](machine-learning-initialize-model-clustering.md)
  + [Regression algorithms](machine-learning-initialize-model-regression.md)

+ [Score](machine-learning-score.md)

  Use these modules to pass new data through the algorithm and generate a set of results for evaluation. You can also use the results of scoring as part of a predictive service.

+ [Train](machine-learning-train.md)

  These modules train an initialized machine learning model on data you provide.
 
### [OpenCV Library Modules](opencv-library-modules.md)

These modules give you easy access to a popular open source library for image processing and image classification.

### [R Language Modules](r-language-modules.md)

Use these modules to add custom R code to your experiment, or implement a machine learning model based on an R package.

### [Python Language Modules](python-language-modules.md)

Use these modules to add custom Python code to your experiment.|  

### [Statistical Functions](statistical-functions.md)

Use these modules to calculate probability distributions, create custom calculations, and perform a wide variety of other tasks related to numerical variables.

### [Text Analytics](text-analytics.md)

Use these modules to perform feature hashing and named entity recognition, or to preprocess text using NLP tools.

### [Time Series](time-series.md)

Use these modules to assess anomalies in trends, using algorithms specifically designed for time series data. 

### Related tasks

Studio modules don't attempt to duplicate data integration tools supported in other tools, such as Azure Data Factory. Instead, the modules in Azure Machine Learning provide functionality that is specific to machine learning:
 
 - Normalization, grouping, and scaling of data
 - Computing statistical distribution of data
 - Conversion to other machine learning formats
 - Import of data used for machine learning experiments and export of results
 - Text analytics, feature selection, dimensionality reduction, and more 

If you need more sophisticated facilities for data manipulation and storage, see these cloud services:

+ [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/): Enterprise-ready cloud data processing pipelines
+ [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/): Scalable storage with integrated access to machine learning
+ [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/): NoSQL data store; import data to Studio 
+ [Azure Data Lake Analytics](https://docs.microsoft.com/azure/data-lake-analytics/): Distributed analytics on big data
+ [Stream Analytics](https://docs.microsoft.com/azure/stream-analytics/): Event processing for the Internet of Things 
+ [Azure Text Analytics](https://docs.microsoft.com/azure/cognitive-services/text-analytics/): Multiple options for text processing, and related cognitive services for speech, image, and facial recognition
+ [Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/): Spark-based analytics platform


## See also

[A-Z Module List](a-z-module-list.md)