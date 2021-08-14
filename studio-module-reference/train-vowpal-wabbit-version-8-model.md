---
title: "ML Studio (classic): Train Vowpal Wabbit Version 8 Model - Azure"
description: Learn how to use the Train Vowpal Wabbit Version 8 module to create a machine learning model by using an instance of Vowpal Wabbit (version 8).
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"


author: xiaoharper
ms.author: amlstudiodocs

---
# Train Vowpal Wabbit Version 8 Model

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Trains a model using version 8 of the Vowpal Wabbit machine learning system*  
  
 Category: [Text Analytics](text-analytics.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the **Train Vowpal Wabbit Version 8** module in Machine Learning Studio (classic), to create a machine learning model by using Vowpal Wabbit (version 8).  

To use Vowpal Wabbit for machine learning, format your input according to Vowpal Wabbit requirements, and save the data in an Azure blob. Use this module to specify Vowpal Wabbit command-line arguments. 

When the experiment is run, an instance of Vowpal Wabbit is loaded into the experiment run-time, together with the specified data. When training is complete, the model is serialized back to the workspace. You can use the model immediately to score data. The trained model is also persisted in Azure storage so that you can use it later without having to reprocess the training data.

To incrementally train an existing model on new data, connect a saved model to the **Pre-trained model** input, and add the new data to the other input.  
  
> [!NOTE]
> Machine Learning Studio (classic) hosts multiple versions of the Vowpal Wabbit framework.  This module uses the latest version of the Vowpal Wabbit framework, which is version 8.  To score new input data, you must use [Score Vowpal Wabbit Version 8 Model](score-vowpal-wabbit-version-8-model.md).
>   
>  Vowpal Wabbit versions 7-4 or 7-6: [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md) and [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md).  
>   
>  Vowpal Wabbit version 7-10:  [Train Vowpal Wabbit 7-10 Model](train-vowpal-wabbit-version-7-10-model.md) and [Score Vowpal Wabbit 7-10 Model](score-vowpal-wabbit-version-7-10-model.md).  
  
## What is Vowpal Wabbit?  

Vowpal Wabbit (VW) is a fast, parallel machine learning framework that was developed for distributed computing by Yahoo! Research. Later it was ported to Windows and adapted by John Langford (Microsoft Research) for scientific computing in parallel architectures.  

Features of Vowpal Wabbit that are important for machine learning include continuous learning (online learning), dimensionality reduction, and interactive learning. Vowpal Wabbit is also a solution for problems when you cannot fit the model data into memory.  

The primary users of Vowpal Wabbit are data scientists who have previously used the framework for machine learning tasks such as classification, regression, topic modeling or matrix factorization. The Azure wrapper for Vowpal Wabbit has very similar performance characteristics to the on-premises version, so you can use the powerful features and native performance of Vowpal Wabbit, and easily publish the trained model as an operationalized service.  

The [Feature Hashing](feature-hashing.md) module also includes functionality provided by Vowpal Wabbit, that lets you transform text datasets into binary features using a hashing algorithm.  

## How to configure Vowpal Wabbit Version 8 Model  

This section describes how to train a new model, and how to add new data to an existing model.

Unlike other modules in Studio (classic), this module both specifies the module parameters, and trains the model. If you have an existing model, you can add it as an optional input, to incrementally train the model.

+ [Prepare input data in one of the required formats](#bkmk_prepData)
+ [Train a new model](#bkmk_NewModel)
+ [Incrementally train an existing model](#bkmk_Retrain)

Use of this module requires authentication to an Azure storage account.  

### <a name="bkmk_prepData"></a> Prepare the input data

To train a model using this module, the input dataset must consist of a single text column in one of the two supported formats: **LibSVM** or **VW**. This doesn't mean that Vowpal Wabbit analyzes only text data, only that the features and values must be prepared in the required text file format.  

The data must be read from Azure storage. It is not possible to use [Export Data](export-data.md) to directly save the input file to Azure for use with Vowpal Wabbit, because the format requires some additional modification. You must ensure the data is in the correct format and then upload the data to Azure blob storage.  

However, as a shortcut, you can use the [Convert to SVMLight](convert-to-svmlight.md) module to generate an SVMLight format file. Then, you can either upload the SVMLight format file to Azure blob storage and use it as the input, or you can modify the file slightly to conform to the Vowpal Wabbit input file requirements.  

The Vowpal Wabbit data format has the advantage that it does not require a columnar format, which saves space when dealing with sparse data. For more information about this format, see the [Vowpal Wabbit wiki page](https://github.com/JohnLangford/vowpal_wabbit/wiki/Input-format).  

### <a name="bkmk_NewModel"></a> Create and train a Vowpal Wabbit model

1. Add the **Train Vowpal Wabbit Version 8** module to your experiment. 
  
2.  Specify the account where the training data is stored. The trained model and hashing file are stored in the same location.

    - For  **Azure storage account name**, type the name of the Azure storage account.  
  
    - For  **Azure storage key**, copy and paste the key that is provided for accessing the storage account,  
  
    If you don’t have a key, see [How to regenerate storage access keys](/azure/storage/common/storage-create-storage-account)  

4.  For **Azure container name**, type the name of a single container in the specified Azure storage account where the model training data is stored. Do not type the account name or any protocol prefix.   
   
    For example, if the full container path and name is `https://myaccount.blob.core.windows.net/vwmodels`, you should type just `vwmodels`.  For more information about container names, see [Naming and Referencing Containers, Blobs, and Metadata](/rest/api/storageservices/Naming-and-Referencing-Containers--Blobs--and-Metadata?redirectedfrom=MSDN).  

5. In the **VW arguments** text box, type the command-line arguments for the Vowpal Wabbit executable.
  
     For example, you might add *`–l`* to specify the learning rate, or *`-b`* to indicate the number of hashing bits.  
  
     For more information, see the [Vowpal Wabbit parameters](#bkmk_Options) section.  
  
6.   **Name of the input VW file**: Type the name of the file that contains the input data. The file must be an existing file in Azure blob storage, located in the previously specified storage account and container. The file must have been prepared using one of the supported formats.  
  
7. **Name of the output readable model (--readable_model) file**: Type the name of a file where the trained model should be saved. The file must be saved within the same storage account and container as the input file.  
  
    This argument corresponds to the `--readable_model` parameter in the VW command line.  
  
8. **Name of the output inverted hash (--invert_hash) file**: Type the name of the file in which the inverted hashing function should be saved.  The file must be saved within the same storage account and container as the input file.  
  
    This argument corresponds to the `--invert_hash` parameter in the VW command line.  
  
9. **Please specify file type**: Indicate which format your training data uses. Vowpal Wabbit supports these two input file formats:  
  
    - **VW** represents the internal format used by  Vowpal Wabbit . See the [Vowpal Wabbit wiki page](https://github.com/JohnLangford/vowpal_wabbit/wiki/Input-format) for details. 
  
    - **SVMLight** is a format used by some other machine learning tools. 

6.  Select the option, **Use cached results**, if you don't want to load the data from storage each time the experiment is re-reun. Assuming no other parameters have changed and a valid cache can be found, Studio (classic) uses a cached version of the data.
  
     If this option is deselected, the module always reads the data from storage.
  
7.  Run the experiment.

8. When training is complete, right-click the output and select **Save as Trained Model** to save the model to your Studio (classic) workspace.

### <a name="bkmk_Retrain"></a> Retrain an existing Vowpal Wabbit model

Vowpal Wabbit supports incremental training by adding new data to an existing model. There are two ways to get an existing model for retraining:

+ Use the output of another **Train Vowpal Wabbit Version 8** module in the same experiment.  
  
+ Locate a saved model in the **Trained Models** group of Studio (classic)’s left navigation pane, and drag it in to your experiment.  

1. Add the **Train Vowpal Wabbit Version 8** module to your experiment.  
  
2. Connect the previously trained model to the input port of **Train Vowpal Wabbit Version 8**.

3. In the **Properties** pane of **Train Vowpal Wabbit Version 8**, specify the location and format of the new training data. 
  
4. Specify a name for the human-readable model output file, and another name for the hash file associated with the updated model.
  
    > [!NOTE]
    >  If there is an existing Vowpal Wabbit model or hash file in the specified location, the files are silently overwritten by the new trained model. To preserve intermediate models when retraining, you must change the storage location or make a local copy of the model files.  
  
6.  Run the experiment.  
  
7.  Right-click the module and select **Save as Trained Model** to preserve the updated model in your Machine Learning workspace.  If you don't specify a new name, the updated model overwrites the existing saved model.

## Examples

For examples of how Vowpal Wabbit can be used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/):

+ [Vowpal Wabbit sample](https://gallery.azure.ai/Collection/Vowpal-Wabbit-Samples-2)

    This experiment demonstrates data prepration, training, and operationalization of a VW model.  

Also, see these resources:  
  
-   Blog describing Vowpal Wabbit implementation and roadmap  
  
     [https://blogs.technet.com/b/machinelearning/archive/2014/10/02/vowpal-wabbit-modules-in-azureml.aspx](https://blogs.technet.com/b/machinelearning/archive/2014/10/02/vowpal-wabbit-modules-in-azureml.aspx)  
  
-   Video that demonstrates building and scoring a model using Vowpal Wabbit in Machine Learning  
  
     [https://channel9.msdn.com/Blogs/Windows-Azure/Text-Analytics-and-Vowpal-Wabbit-in-Azure-ML-Studio](https://channel9.msdn.com/Blogs/Windows-Azure/Text-Analytics-and-Vowpal-Wabbit-in-Azure-ML-Studio)  
  
## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Advantages of Vowpal Wabbit

Vowpal Wabbit provides extremely fast learning over non-linear features like n-grams.  
  
Vowpal Wabbit uses *online learning* techniques such as stochastic gradient descent (SGD) to fit a model one record at a time. Thus it iterates very quickly over raw data and can develop a good predictor faster than most other models. This approach also avoids having to read all training data into memory.  
  
Vowpal Wabbit converts all data to hashes, not just text data but other categorical variables. Using hashes makes lookup of regression weights more efficient, which is critical for effective stochastic gradient descent.  
  
During training, the module makes calls into a Vowpal Wabbit wrapper developed for Azure. The training data is downloaded in blocks from Azure, utilizing the high bandwidth between the worker roles executing the computations and the store, and is streamed to the VW learners. The resulting model is generally very compact due to the internal compression done by VW. The model is copied back to the experiment workspace where it can be utilized like other models in Machine Learning.  

###  <a name="bkmk_Options"></a> Supported and unsupported parameters 

This section describes support for Vowpal Wabbit command line parameters in Machine Learning Studio (classic). 

Generally, all but a limited set of arguments are supported. For a complete list of arguments, use the [Vowpal Wabbit wiki page](https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments).    

The following parameters are not suppported:

-   The input/output options specified in [https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments](https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments)  
  
     These properties are already configured automatically by the module.  
  
-   Additionally, any option that generates multiple outputs or takes multiple inputs is disallowed. These include *`--cbt`*, *`--lda`*, and *`--wap`*.  
  
-   Only supervised learning algorithms are supported. Therefore, these options are not supported: *`–active`*, `--rank`, *`--search`* etc.  ### Restrictions

### Restrictions

Because the goal of the service is to support experienced users of Vowpal Wabbit, input data must be prepared ahead of time using the Vowpal Wabbit native text format, rather than the dataset format used by other modules.

Rather than using data in the Azure ML workspace, the training data is directly streamed from Azure, for maximal performance and minimal parsing overhead. For this reason, there is only limited interoperability between the VW modules and other modules in Azure ML.  

##  Module parameters  

|Name|Range|Type|Optional|Default|Description|  
|----------|-----------|----------|--------------|-------------|-----------------|  
|Please specify file type|VW<br /><br /> SVMLight|DataType|Required|VW|Indicate whether the file type is SVMLight or Vowpal Wabbit.|  
|Azure storage account name|any|String|Required||Type the Azure storage account name|  
|Azure storage key|any|SecureString|Required||Provide the Azure storage key|  
|Azure container name|any|String|Required||Type the Azure container name|  
|VW arguments|any|String|Optional||Specify any Vowpal Wabbit arguments. Do not include -f.|  
|Name of the input VW file|any|String|Required||Specify the name of an input file in the Vowpal Wabbit format|  
|Name of the output readable model (--readable_model) file|any|String|Optional||If specified, outputs a readable model back to the Azure container.|  
|Name of the output inverted hash (--invert_hash) file|String|String|Optional||If specified, outputs a file containing the inverted hash function back to the Azure container.|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained learner|  
  
##  Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](errors/error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also  
 [Text Analytics](text-analytics.md)   
 [Feature Hashing](feature-hashing.md)   
 [Named Entity Recognition](named-entity-recognition.md)   
 [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md)  
 [Score Vowpal Wabbit Version 8 Model](score-vowpal-wabbit-version-8-model.md).  
 [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md)   
 [A-Z Module List](a-z-module-list.md)
