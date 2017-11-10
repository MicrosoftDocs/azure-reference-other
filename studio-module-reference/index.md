---
title: "Azure Machine Learning Studio Algorithm and Module Reference | Microsoft Docs"
ms.custom: ""
ms.date: 09/21/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: f5c746fd-dcea-4929-ba50-2a79c4c067d7
caps.latest.revision: 18
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Azure Machine Learning Studio Algorithm and Module Reference
Azure Machine Learning is a cloud predictive analytics service that makes it possible to quickly create and deploy predictive models as analytics solutions. The Machine Learning service is cloud-based, and eliminates setup and installation concerns because you can work through your web browser on any Internet-connected PC.

+ Log into your [Studio workspace](https://studio.azureml.net/Home) and get started
  
## What is Azure Machine Learning Studio?

Microsoft Azure Machine Learning Studio is a collaborative visual development environment that helps you build, test, and deploy predictive analytics solutions in the cloud.  You upload data or connect to data already in the cloud, choose an algorithm from a ready-to-use library of algorithms, and build an end-to-end predictive workflow. You can then quickly deploy the model and integrate the workflow in applications by calling a web service.

If you have not used machine learning before, see these resources:
+ [Webinars and on-demand videos](https://gallery.cortanaintelligence.com/learnings)
+ [Tutorial: Create your first machine learning experiment](https://docs.microsoft.com/azure/machine-learning/machine-learning-create-experiment)
+ The [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/) provides examples of how machine machine learning has been applied in various industries.
  
## Help for Machine Learning Modules  

This documentation contains detailed technical and how-to information for the **modules** that are available in Azure Machine Learning Studio. 

### What Is a Module?

Each module represents a set of code that can run independently and perform a machine learning task, given the required inputs. A module might contain a particular algorithm, or perform a task that is important in machine learning, such as missing value replacement, or statistical analysis. 
 
In Studio, you'll find modules organized by functionality:
 
 + [Machine learning algorithms](machine-learning-modules.md), such as clustering, SVM, or neural networks, are contained within modules that let you customize the machine learning task with appropriate parameters. For classification tasks, you can choose from binary or multiclass algorithms. After you've configured a particular type of model, you use another module to perform [training](machine-learning-train.md), [scoring](machine-learning-score.md), or [evaluation](machine-learning-evaluate.md). 
 + Use the [Data Input and Output](data-input-and-output.md) modules to get data from cloud sources. You can write your results or intermediate data to Azure storage, SQL database, or Hive, while running an experiment, or use cloud storage to exchange data between experiments.  
 + [Data transformation modules](data-transformation.md) support operations on data that are unique to machine learning, such as normalizing or binning data, feature selection, and dimensionality reduction.
 + [Text analytics modules](text-analytics.md) include support for [Vowpal Wabbit](train-vowpal-wabbit-version-8-model.md) and various natural language proessing (NLP) tasks.
 + Support for external languages is provided by [Python](python-language-modules.md) and [R language](r-language-modules.md) modules. 
 + Categories for specific machine learning tasks, such as using the [OpenCV library](opencv-library-modules.md) for image recognition, [time series analysis](time-series.md), and [anomaly detection](anomaly-detection.md).
+ Other modules support a wide range of [statistical functions](statistical-functions.md) and statistical methods that are core to data science, or create data summaries. 
  
In this reference section, you'll find technical background on the machine learning algorithms,  implementation details if available, and links to sample experiments that demonstrate how the module is used. All examples are available for public use, in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com).  

 > [!TIP]
 > If you are logged into Studio and have created an experiment, you can get information about a specific module by selecting the module and then clicking the **more help** link in the **Quick Help** pane.  
 

## Other Technical Reference

|Section|Description|  
|-------------|-----------------|  
|[Data Types List](machine-learning-module-data-types.md#types)|This section contains reference topics describing the learner interfaces, and  the `DataTable` format used for datasets.|  
|[Module Parameter Types](machine-learning-module-parameter-types.md)|This section contains reference topics describing the parameter API.|  
|[Exceptions List](machine-learning-module-error-codes.md#errors)|This section lists the errors that can be generated by modules, with causes and possible workarounds.<br /><br /> For the list of error codes related to the Web service API, see [Machine Learning REST API Error Codes](http://msdn.microsoft.com/library/0eccb2eb-27a1-407e-88a9-2092dba847e0)|  

    
## See Also  
 [Azure Machine Learning Documentation Center](http://azure.microsoft.com/documentation/services/machine-learning/)