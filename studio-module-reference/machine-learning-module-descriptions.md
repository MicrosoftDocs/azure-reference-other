---
title: "ML Studio (classic): Module descriptions - Azure"
description: An overview of all the modules included in Azure Machine Learning Studio (classic), an interactive, visual workspace to easily build and test predictive models.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Machine Learning module descriptions

This topic provides an overview of all the *modules* included in Azure Machine Learning Studio (classic), which is an interactive, visual workspace to easily build and test predictive models.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## What is a module?

In Machine Learning Studio (classic), a module is a building block for creating experiments. Each module encapsulates a specific machine learning algorithm, function, or code library that can act on data in your workspace. The modules are designed to accept connections from other modules, to share and modify data. 

The code that runs in each module comes from many sources. These include open source libraries and languages, algorithms developed by Microsoft Research, and tools for working with Azure and other cloud services.
 
 > [!TIP]
> Looking for machine learning algorithms? See the [Machine Learning](machine-learning-initialize-model.md) category, which contains modules for decision trees, clustering, neural networks, among others. The [Train](machine-learning-train.md) and [Evaluate](machine-learning-evaluate.md) categories include modules to help train and test your models. 

By connecting and configuring modules, you can create a workflow that reads data from external sources, prepares it for analysis, applies machine learning algorithms, and generates results.

When an *experiment* is open in Machine Learning Studio (classic), you can see the complete list of current modules in the navigation pane at left. You drag these building blocks into your experiment, and then connect them to create a complete machine learning workflow, called an experiment. 

Sometimes modules are updated to add new functionality, or to remove older code. When this happens, any experiments that you created that use the module continue to run. But the next time you open the experiment, you are prompted to upgrade the module, or to use a different module.

### Examples

For an example of how to build a complete machine learning experiment, see these tutorials:  
  
-   [Develop a predictive solution by using Azure Machine Learning](/azure/machine-learning/classic/tutorial-part1-credit-risk)  
  
-   [Create a simple experiment in Azure Machine Learning Studio (classic)](/azure/machine-learning/classic/create-experiment)  
 
##  Module categories

To make it easier to find related modules, the machine learning tools in Machine Learning Studio (classic) are grouped by these categories.

### [Data Format conversions](data-format-conversions.md)

Use these modules to convert data to one of the formats used by other machine learning tools or formats. 

+ [Data Input and Output](data-input-and-output.md)

  Use these modules to read data and models from cloud data sources, including Hadoop clusters, Azure Table storage, and web URLs. You can also use these modules to write results to storage or to a database.  

+ [Data Transformation](data-transformation.md)

  Use these modules to prepare data for analysis. You can change data types, flag columns as features or labels, generate features, and scale or normalize data.

+ [Filter](data-transformation-filter.md)

  Transform numeric data derived from digital signal processing.

+ [Learning With Counts](data-transformation-learning-with-counts.md)

  Use joint probability distributions to build features that compactly describe large datasets.

+ [Manipulation](data-transformation-manipulation.md)

  This group provides a variety of tools for data science. For example, you can remove or replace missing values, choose a subset of columns, add a column, or concatenate two datasets.  

+ [Sample and Split](data-transformation-sample-and-split.md)

  Divide a dataset by criteria or by size, to create training and test sets, or to isolate certain rows.

+ [Scale and Reduce](data-transformation-scale-and-reduce.md)

  Transform numerical data. 

### [Feature Selection](feature-selection-modules.md)

Use these modules to identify the best features in your data, using widely researched statistical methods.
  
### [Machine Learning](machine-learning-modules.md)

This group contains most of the machine learning algorithms supported by Machine Learning.

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

  Use these modules to pass new data through the algorithm, and generate a set of results for evaluation. You can also use the results of scoring as part of a predictive service.

+ [Train](machine-learning-train.md)

  These modules train an initialized machine learning model on data you provide.
 
### [OpenCV Library Modules](opencv-library-modules.md)

These modules give you easy access to a popular open source library for image processing and image classification.

### [R Language Modules](r-language-modules.md)

Use these modules to add custom R code to your experiment, or implement a machine learning model based on an R package.

### [Python Language Modules](python-language-modules.md)

Use these modules to add custom Python code to your experiment.  

### [Statistical Functions](statistical-functions.md)

Use these modules to calculate probability distributions, create custom calculations, and perform a wide variety of other tasks related to numerical variables.

### [Text Analytics](text-analytics.md)

Use these modules to perform feature hashing and named entity recognition, or to preprocess text using natural language processing tools.

### [Time Series](time-series.md)

Use these modules to assess anomalies in trends, by using algorithms specifically designed for time series data. 

### Related tasks

Machine Learning Studio (classic) modules don't attempt to duplicate data integration tools supported in other tools, such as Azure Data Factory. Instead, the modules provide functionality that is specific to machine learning:
 
 - Normalization, grouping, and scaling of data
 - Computing statistical distribution of data
 - Conversion to other machine learning formats
 - Import of data used for machine learning experiments and export of results
 - Text analytics, feature selection, and dimensionality reduction 

If you need more sophisticated facilities for data manipulation and storage, see the following:

- [Azure Data Factory](/azure/data-factory/): Enterprise-ready, cloud data processing pipelines.
- [Azure SQL Database](/azure/sql-database/): Scalable storage, with integrated access to machine learning.
- [CosmosDB](/azure/cosmos-db/): NoSQL data store; import data to Machine Learning Studio (classic). 
- [Azure Data Lake Analytics](/azure/data-lake-analytics/): Distributed analytics on big data.
- [Stream Analytics](/azure/stream-analytics/): Event processing for the Internet of Things. 
- [Azure Text Analytics](/azure/cognitive-services/text-analytics/): Multiple options for text processing, and related Cognitive Services for speech, image, and facial recognition.
- [Azure Databricks](/azure/azure-databricks/): Spark-based analytics platform.

## See also

- [A-Z module list](a-z-module-list.md)
