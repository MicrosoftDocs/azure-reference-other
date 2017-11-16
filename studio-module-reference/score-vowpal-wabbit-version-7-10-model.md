---
title: "Score Vowpal Wabbit Version 7-10 Model | Microsoft Docs"
ms.custom: ""
ms.date: 06/21/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e3a0906a-a5ba-4721-b0de-885c31abd676
caps.latest.revision: 9
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Score Vowpal Wabbit Version 7-10 Model
*Scores data using the Vowpal Wabbit machine learning system from the command line interface*  
  
 Category: [Text Analytics](text-analytics.md)  
  
## Module Overview  
 You can use the **Score Vowpal Wabbit Version 7-10 Model** module to generate scores for a set of input data, using an existing trained Vowpal Wabbit model.  
  
> [!NOTE]
>  This module provides version 7-10 of the Vowpal Wabbit framework, . Use this module to score data using a trained model that was saved in the 7-10 format.  
>   
>  If you have existing models created using an earlier version, use these modules: [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md), [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md).  
>   
>  For the latest version of Vowpal Wabbit, use [Train Vowpal Wabbit 8 Model](train-vowpal-wabbit-version-8-model.md) and [Score Vowpal Wabbit 8 Model](score-vowpal-wabbit-version-8-model.md).  
  
## How to Use Score Vowpal Wabbit Version 7-10 Model  
  
1.  Add the **Score Vowpal Wabbit Version 7-10 Model** module to your experiment.  
  
2.  Add a trained Vowpal Wabbit model and connect it to the left-hand input port. You can use a trained model created in the same experiment, or locate a saved model in the **Trained Models** group of Studio’s left navigation pane. However, the model must be available in Azure Machine Learning Studio; you cannot directly load a model from Azure storage.  
  
    > [!NOTE]
    >  Only Vowpal Wabbit 7-10 models are supported; you cannot connect saved models that were trained by using other algorithms, and you cannot use models that were trained using earlier or later versions.  
  
3.  In the **VW arguments** text box, type a set of valid command-line arguments to the Vowpal Wabbit executable.  
  
     For information about which Vowpal Wabbit arguments are supported and unsupported in Azure Machine Learning, see the [Technical Notes](#bkmk_TechnicalNotes) section.  
  
4.  Click **Specify data type**, and select one of the supported data types from the list.  
  
     Scoring requires a single column of VW-compatible data.  
  
     If you have an existing file that was created in the SVMLight or VW formats, you can load it into the Azure ML workspace  as a new dataset in one of these formats: Generic CSV without header, TSV without header.  
  
     The **VW** option requires that a label be present, but it is not used in scoring except for comparison.  
  
5.  Add a [Import Data](import-data.md) module and connect it to the right-hand input port of **Score Vowpal Wabbit Version 7-10**.  Configure the [Import Data](import-data.md) to access the input data.  
  
     The input data for scoring must have been prepared ahead of time in one of the supported formats and stored in Azure blob storage.  
  
6.  Select the option, **Include an extra column containing labels**, if you want to output labels together with the scores.  
  
     Typically, when handling text data, Vowpal Wabbit does not require labels, and will return only the scores for each row of data.  
  
7.  Select the option, **Use cached results**, if you want to re-use results from a previous run, assuming the following conditions are met:  
  
    -   A valid cache exists from a previous  run.  
  
    -   The input data and parameters settings of the module have not changed since the previous run.  
  
     Otherwise, this module will be executed each time the experiment runs.  
  
8.  Run the experiment, and right-click the output of the [Score Vowpal Wabbit Version 7-10 Model](score-vowpal-wabbit-version-7-10-model.md) module to visualize the results.  
  
     The output indicates a prediction score normalized from 0 to 1.  
  
## Examples  
 The following video provides a walkthrough of the training and scoring process for Vowpal Wabbit:  
  
 [https://azure.microsoft.com/en-us/documentation/videos/text-analytics-and-vowpal-wabbit-in-azure-ml-studio/](https://azure.microsoft.com/en-us/documentation/videos/text-analytics-and-vowpal-wabbit-in-azure-ml-studio/)  
  
##  <a name="bkmk_TechnicalNotes"></a> Technical Notes  
 Vowpal Wabbit has many command-line options for choosing and tuning algorithms. A full discussion of these options is not possible here; we recommend that you view the [Vowpal Wabbit wiki page](https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments).  
  
 Note that some options are not supported in Azure Machine Learning Studio.  
  
 **Not supported**  
  
-   The input/output options specified in [https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments](https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments)  
  
     These properties are already configured automatically by the module.  
  
-   Additionally, any option that generates multiple outputs or takes multiple inputs is disallowed. These include *`--cbt`*, *`--lda`*, and *`--wap`*.  
  
-   Only supervised learning algorithms are supported. This disallows these options: *`–active`*, `--rank`, *`--search`* etc.  
  
 **Supported**  
  
 All arguments other than those described above are allowed.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained learner|  
|Dataset|[Data Table](data-table.md)|Dataset to be scored|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|VW arguments|Any|String|none|Type Vowpal Wabbit arguments.<br /><br /> The following arguments are not supported:<br /><br /> -   *-i*<br />-   *-p* or<br />-   *-t*|  
|Include an extra column containing labels|True/False|Boolean|false|Specify whether the zipped file should include labels with the predictions|  
|Specify data type|VW<br /><br /> SVMLight|DataType|VW|Indicate whether the file format is SVMLight or Vowpal Wabbit|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with the prediction results|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](errors/error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  
  
## See Also  
 [Text Analytics](text-analytics.md)   
 [Feature Hashing](feature-hashing.md)   
 [Named Entity Recognition](named-entity-recognition.md)   
 [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md)   
 [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md)   
 [Train Vowpal Wabbit 7-10 Model](train-vowpal-wabbit-version-7-10-model.md)   
 [A-Z Module List](a-z-module-list.md)