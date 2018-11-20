---
title: "Score Vowpal Wabbit Version 8 Model | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/17/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43d255dc-c03d-4dce-acc4-884e660210d9
caps.latest.revision: 10
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Score Vowpal Wabbit Version 8 Model
*Scores data using the Vowpal Wabbit machine learning system from the command line interface*  
  
 Category: [Text Analytics](text-analytics.md)  
  
## Module overview  

This article describes how to use the **Score Vowpal Wabbit Version 8 Model** module in Azure Machine Learning Studio, to generate scores for a set of input data, using an existing trained Vowpal Wabbit model.  

This module provides the latest version of the Vowpal Wabbit framework, version 8. Use this module to score data using a trained model saved in the VW version 8 format.  

If you have existing models created using an earlier version, use these modules: 
+ [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md)
+ [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md)

## How to configure Score Vowpal Wabbit Model 8  

1.  Add the **Score Vowpal Wabbit Version 8 Model** module to your experiment.  
  
2.  Add a trained Vowpal Wabbit model and connect it to the left-hand input port. You can use a trained model created in the same experiment, or locate a saved model in the **Trained Models** group of Studio’s left navigation pane. However, the model must be available in Azure Machine Learning Studio; you cannot directly load a model from Azure storage.  
  
    > [!NOTE]
    >  Only Vowpal Wabbit 8 models are supported; you cannot connect saved models that were trained by using other algorithms, and you cannot use models that were trained using earlier versions.  
  
3.  In the **VW arguments** text box, type a set of valid command-line arguments to the Vowpal Wabbit executable.  
  
     For information about which Vowpal Wabbit arguments are supported and unsupported in Azure Machine Learning, see the [Technical Notes](#bkmk_TechnicalNotes) section.  
  
4.  Click **Specify data type**, and select one of the supported data types from the list.  
  
     Scoring requires a single column of VW-compatible data.  
  
     If you have an existing file that was created in the SVMLight or VW formats, you can load it into the Azure ML workspace  as a new dataset in one of these formats: Generic CSV without header, TSV without header.  
  
     The **VW** option requires that a label be present, but it is not used in scoring except for comparison.  
  
5.  Add an [Import Data](import-data.md) module and connect it to the right-hand input port of **Score Vowpal Wabbit Version 8**.  Configure the [Import Data](import-data.md) to access the input data.  
  
     The input data for scoring must have been prepared ahead of time in one of the supported formats and stored in Azure blob storage.  
  
6.  Select the option, **Include an extra column containing labels**, if you want to output labels together with the scores.  
  
     Typically, when handling text data, Vowpal Wabbit does not require labels, and will return only the scores for each row of data.  
  
7.  Select the option, **Include an extra column containing raw scores**, if you want to output raw scores  together with the results.  
  
    > [!TIP]
    >  This option is new for Vowpal Wabbit Version 8.  
  
8.  Select the option, **Use cached results**, if you want to re-use results from a previous run, assuming the following conditions are met:  
  
    - A valid cache exists from a previous run.
  
    - The input data and parameters settings of the module have not changed since the previous run.  
  
    Otherwise, the import process is repeated each time the experiment runs.  
  
9. Run the experiment.

### Results

After training is complete:

+ To visualize the results, right-click the output of the [Score Vowpal Wabbit Version 8 Model](score-vowpal-wabbit-version-8-model.md) module. 

The output indicates a prediction score normalized from 0 to 1.

## Examples

For examples of how Vowpal Wabbit can be used in machine learning, see the [Azure AI Gallery](https://gallery.cortanaintelligence.com/):

+ [Vowpal Wabbit sample](https://gallery.cortanaintelligence.com/Collection/Vowpal-Wabbit-Samples-2)

    This experiment demonstrates data preparation, training, and operationalization of a VW model.  

The following video provides a walkthrough of the training and scoring process for Vowpal Wabbit:  
  
 [https://azure.microsoft.com/documentation/videos/text-analytics-and-vowpal-wabbit-in-azure-ml-studio/](https://azure.microsoft.com/documentation/videos/text-analytics-and-vowpal-wabbit-in-azure-ml-studio/)  
  
##  <a name="bkmk_TechnicalNotes"></a> Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Parameters

Vowpal Wabbit has many command-line options for choosing and tuning algorithms. A full discussion of these options is not possible here; we recommend that you view the [Vowpal Wabbit wiki page](https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments).  
  
The following parameters are not supported in Azure Machine Learning Studio.  

-   The input/output options specified in [https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments](https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments)  
  
     These properties are already configured automatically by the module.  
  
-   Additionally, any option that generates multiple outputs or takes multiple inputs is disallowed. These include *`--cbt`*, *`--lda`*, and *`--wap`*.  
  
-   Only supervised learning algorithms are supported. This disallows these options: *`–active`*, `--rank`, *`--search`* etc.  

All arguments other than those described above are allowed.
  
##  Expected inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained learner|  
|Dataset|[Data Table](data-table.md)|Dataset to be scored|  
  
##  Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Specify data type|VW<br /><br /> SVMLight|DataType|VW|Indicate whether the file type is SVMLight or Vowpal Wabbit|  
|*VW arguments*|any|String|none|Type Vowpal Wabbit arguments. Do not include -i or -p, or -t|  
|Include an extra column containing labels|True/False|Boolean|false|Specify whether the zipped file should include labels with the predictions|  
|Include an extra column containing raw scores|True/False|Boolean|false|Specify whether the result should include an additional columns containing the raw scores (corresponding to --raw_predictions)|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with the prediction results|  
  
##  Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](errors/error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  

For a list of errors specific to Studio modules, see [Machine Learning Error codes](\errors\machine-learning-module-error-codes.md)

For a list of API exceptions, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes).  

## See also  
 [Text Analytics](text-analytics.md)   
 [Feature Hashing](feature-hashing.md)   
 [Named Entity Recognition](named-entity-recognition.md)   
 [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md)   
 [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md)   
 [Train Vowpal Wabbit 8 Model](train-vowpal-wabbit-version-8-model.md)   
 [A-Z Module List](a-z-module-list.md)
