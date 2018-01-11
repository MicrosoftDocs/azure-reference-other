---
title: "Machine Learning Studio: Algorithm and Module Help | Microsoft Docs"
ms.custom: ""
ms.date: 01/10/2018
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
manager: "cgronlund"
---
# Machine Learning Studio: Algorithm and Module Help
Azure Machine Learning is a cloud predictive analytics service that makes it possible to quickly create and deploy predictive models as analytics solutions. The machine learning tools are services are mostly cloud-based, which eliminates setup and installation concerns because you can work through your web browser on any internet-connected PC.

+ Log into your [Studio workspace](https://studio.azureml.net/Home) and get started
  
## What is Azure Machine Learning Studio?

Microsoft Azure Machine Learning Studio is a collaborative visual development environment that helps you build, test, and deploy predictive analytics solutions in the cloud.  You upload data or connect to data already in the cloud, choose an algorithm from a ready-to-use library of algorithms, and build an end-to-end predictive workflow. You can then quickly deploy the model and integrate the workflow in applications by calling a web service.

If you have not used machine learning before, see these resources:
+ [Webinars and on-demand videos](https://gallery.cortanaintelligence.com/learnings)
+ [Tutorial: Create your first machine learning experiment](https://docs.microsoft.com/azure/machine-learning/machine-learning-create-experiment)
+ The [Azure AI Gallery](https://gallery.cortanaintelligence.com/) provides examples of how machine machine learning has been applied in various industries.
  
## Help for Machine Learning Modules  

This documentation contains detailed technical and how-to information for the **modules** that are available in Azure Machine Learning Studio. 

> [!NOTE]
There are other ways to build machine learning solutions in Azure Machine Learning, including the new [Workbench](https://docs.microsoft.com/azure/machine-learning/preview/quickstart-installation), currently in preview. This documentation focuses only on Studio.

### What Is a Module?

Each module represents a set of code that can run independently and perform a machine learning task, given the required inputs. A module might contain a particular algorithm, or perform a task that is important in machine learning, such as missing value replacement, or statistical analysis. 
 
In Studio, modules are organized by functionality:

+ [Data input and output modules](data-input-and-output.md) do the work of moving from cloud sources into your experiment. You can write your results or intermediate data to Azure storage, SQL database, or Hive, while running an experiment, or use cloud storage to exchange data between experiments.  
 + [Data transformation modules](data-transformation.md) support operations on data that are unique to machine learning, such as normalizing or binning data, feature selection, and dimensionality reduction.
 + [Machine learning algorithms](machine-learning-modules.md), such as clustering, SVM, or neural networks, are available within individual modules that let you customize the machine learning task with appropriate parameters. For classification tasks, you can choose from binary or multiclass algorithms. 
 
     After you've configured the model, you use a [training module](machine-learning-train.md) to run data through the algorithm, and measure the accuracy of the trained model using one of the [evaluation modules](machine-learning-evaluate.md). To get predictions from the model youve just trained, use one of the [scoring modules](machine-learning-score.md).  
 + For [anomaly detection](anomaly-detection.md), Studio includes multiple algorithms specialized for these tasks.
 + [Text analytics modules](text-analytics.md) support various natural language proessing (NLP) tasks. You can also run [Vowpal Wabbit](train-vowpal-wabbit-version-8-model.md)!
 + Support for external languages is provided by [Python](python-language-modules.md) and [R language](r-language-modules.md) modules. You write the code, and embed it in a module, to integrate Python and R with an experiment service.
 + The [OpenCV library](opencv-library-modules.md) provides modules to use in specific image recognition tasks.
 + [Time series analysis](time-series.md) supports anomaly detection in time series.
+ [Statistical modules](statistical-functions.md) provide a wide variety of numerical methods related to data science. Look in this group for correlation methods, data summaries, statistical and math operations. 
  
In this reference section, you'll find technical background on the machine learning algorithms,  implementation details if available, and links to sample experiments that demonstrate how the module is used. All examples are available for public use, in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com).  

 > [!TIP]
 > If you are logged into Studio and have created an experiment, you can get information about a specific module by selecting the module and then clicking the **more help** link in the **Quick Help** pane.  
 

## Other Technical Reference

|Section|Description|  
|-------------|-----------------|  
|[Data Types List](machine-learning-module-data-types.md#types)|This section contains reference topics describing the learner interfaces, and  the `DataTable` format used for datasets.|  
|[Module Parameter Types](machine-learning-module-parameter-types.md)|This section contains reference topics describing the parameter API.|  
|[Exceptions List](machine-learning-module-error-codes.md#errors)|This section lists the errors that can be generated by modules, with causes and possible workarounds.<br /><br /> For the list of error codes related to the Web service API, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes)|  


## See Also  
 [Azure Machine Learning Documentation (Preview)](https://docs.microsoft.com/azure/machine-learning/preview/)