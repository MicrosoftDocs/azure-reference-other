---
title: "Train Vowpal Wabbit Version 8 Model | Microsoft Docs"
ms.custom: ""
ms.date: 02/21/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 86f666bb-d459-4117-bbb0-4edfd566c3a9
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Train Vowpal Wabbit Version 8 Model
*Trains a model using version 8 of the Vowpal Wabbit machine learning system*  
  
 Category: [Text Analytics](text-analytics.md)  
  
## Module Overview  
 You can use the **Train Vowpal Wabbit Version 8** module to create a machine learning model by using the latest version of Vowpal Wabbit, hosted in Azure Machine Learning.  
  
 To use this module, you must first format your input according to Vowpal Wabbit requirements, and save the data in an Azure blob. You use Vowpal Wabbit command-line arguments to specify how the data should be processed during training, and where the trained model should be saved. 
 
 When the experiment is run, the **Train Vowpal Wabbit Version 8** module calls an instance of Vowpal Wabbit version 8, and when training is complete, serializes the model back to the workspace so that you can use it to score data. By default, the trained model is also persisted in Azure storage so that you can use it later without having to reprocess the training data.   
  
  To incrementally train an existing model on new data, you connect a saved model to the **Pre-trained model** input port on the **Train Vowpal Wabbit Version 8** module, and add the new data to the other input.  
  
> [!NOTE]
>  This module uses the latest version of the Vowpal Wabbit framework, which is version 8.  To score new input data, you must use [Score Vowpal Wabbit Version 8 Model](score-vowpal-wabbit-version-8-model.md).
>   
>  Vowpal Wabbit versions 7-4 or 7-6: [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md) and [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md).  
>   
>  Vowpal Wabbit version 7-10:  [Train Vowpal Wabbit 7-10 Model](train-vowpal-wabbit-version-7-10-model.md) and [Score Vowpal Wabbit 7-10 Model](score-vowpal-wabbit-version-7-10-model.md).  
  
## What is Vowpal Wabbit?  
 Vowpal Wabbit (VW) is a fast, parallel machine learning framework that was developed for distributed computing by Yahoo! Research. Later it was ported to Windows and adapted by John Langford (Microsoft Research) for scientific computing in parallel architectures.  
  
 Features of Vowpal Wabbit that are important for machine learning include continuous learning (online learning), dimensionality reduction, and interactive learning. Vowpal Wabbit is also a solution for problems when you cannot fit the model data into memory.  
  
 The primary users of Vowpal Wabbit in Azure Machine Learning  are data scientists who have previously used the framework for machine learning tasks such as classification, regression, topic modeling or matrix factorization. The Azure wrapper for Vowpal Wabbit has very similar performance characteristics to the on-premise version, which means that users can continue to build models, retrain, and score using the powerful features and native performance of Vowpal Wabbit, while gaining the ability to easily publish the trained model as an operationalized service.  
  
 The [Feature Hashing](feature-hashing.md) module also includes functionality provided by Vowpal Wabbit, that lets you transform text datasets into binary features using a hashing algorithm.  
  
## How to create a new Vowpal Wabbit model  
      
1.  Prepare the input data. To train a model using this module, the input dataset must consist of a single text column in one of the two supported formats: **LibSVM** or **VW**. Note that this doesn't mean that Vowpal Wabbit analyzes only text data, only that the features and values must be prepared in the required text file format.  
  
     > [!TIP] 
     > It is not possible to use [Export Data](export-data.md) to directly save the input file to Azure for use with Vowpal Wabbit, because the format requires some additional modification. You must ensure the data is in the correct format and then upload the data to Azure blob storage.  
     >   
     > However, as a shortcut, you can use the [Convert to SVMLight](convert-to-svmlight.md) module to generate an SVMLight format file. Then, you can either upload the SVMLight format file to Azure blob storage and use it as the input, or you can modify the file slightly to conform to the Vowpal Wabbit input file requirements.  

2. Add the **Train Vowpal Wabbit Version 8** module to your experiment.  
  
3.  Specify the account where the training data is stored. The trained model and hashing file will be stored in the same location.  
    - For  **Azure storage account name**, type the name of the Azure storage account.  
  
    - For  **Azure storage key**, copy and paste the key that is provided for accessing the storage account,  
  
    If you don’t have a key, see [How to regenerate storage access keys](http://azure.microsoft.com/documentation/articles/storage-manage-storage-account/)  
  

  
4.  For **Azure container name**, type the name of a single container in the specified Azure storage account where the model training data is stored. Do not type the account name or any protocol prefix.   
   
    For example, if the full container path and name is **https://myaccount.blob.core.windows.net/vwmodels**, you should type just **vwmodels**.  For more information about container names, see [Naming and Referencing Containers, Blobs, and Metadata](https://msdn.microsoft.com/library/azure/dd135715.aspx).  

5. Specify command-line arguments that will be passed to the Vowpal Wabbit executable, by using the **VW arguments** property of the module.  
  
     For example, you might add *`–l`* to specify the learning rate, or *`-b`* to indicate the number of hashing bits.  
  
     For more information, see the [Vowpal Wabbit Options](#bkmk_Options) section.  
  
6.   **Name of the input VW file**: Type the name of the file that contains the input data. The file must be an existing file in Azure blob storage, located in the previously specified storage account and container. The file must have been prepared using one of the supported formats.  
  
7. **Name of the output readable model (--readable_model) file**: Type the name of the file in which the trained model will be saved. The file must be saved within the same storage account and container as the input file.  
  
    This argument corresponds to the `--readable_model` parameter in the VW command line.  
  
8. **Name of the output inverted hash (--invert_hash) file**: Type the name of the file in which the inverted hashing function will be saved.  The file must be saved within the same storage account and container as the input file.  
  
    This argument corresponds to the `--invert_hash` parameter in the VW command line.  
  
9. **Please specify file type**: Indicate which format your training data uses. Vowpal Wabbit supports these two input file formats:  
  
    - **VW** represents the internal format used by  Vowpal Wabbit . See the [Vowpal Wabbit wiki page](https://github.com/JohnLangford/vowpal_wabbit/wiki/Input-format) for details.  The Vowpal Wabbit data format has the advantage that it does not require a columnar format, which saves space when dealing with sparse data.  
  
    - **SVMLight** is a format used by some other machine learning tools. You can use the [Convert to SVMLight](convert-to-svmlight.md) module to convert your data to this format.  
  
 

10.  Use the option, **Use cached results**, to indicate whether the Vowpal Wabbit model should be retrained each time you run the experiment.  
  
     When you select this option, the experiment will use a cached version of the data so that you don't need to reload it each time, assuming no other parameters have changed and a valid cache can be found. If the data in the file has changed, the experiment cannot detect this, and will continue to use the data in the cache.  
  
     If this option is deselected, the module will always read the data and retrain the model.  
  
7.  Run the experiment.  
  
8.  After the model has been generated, right-click the output and select **Save as trained model**, so that you can re-use and re-train the model later.  
  
### How to retrain an existing Vowpal Wabbit model  
  
1.  Add the **Train Vowpal Wabbit Version 8** module to your experiment.  
  
2.  Connect a previously trained model to the input port of **Train Vowpal Wabbit Version 8**:  
  
    -   Use the output of another **Train Vowpal Wabbit Version 8** module in the same experiment.  
  
    -   Locate a saved model in the **Trained Models** group of Studio’s left navigation pane.  
  
3.  In the **Properties** pane of **Train Vowpal Wabbit Version 8**, specify the location and format of the training data. The  same location will be used to save the updated model and hash files.  
  
4.  Specify a name for the human-readable model output file, and another  name for the hash file associated with the updated model.  
  
    > [!NOTE]
    >  If there is an Vowpal Wabbit model or hash file in the specified location , the files will be silently overwritten by the new trained model. To preserve intermediate models when retraining, you must change the storage location or make a local copy of the model files.  
  
5.  Use the option, **Use cached results**, to indicate whether the Vowpal Wabbit model should be retrained each time you run the experiment.  
  
     When you select this option, the experiment will use a cached version of the data so that you don't need to reload it each time, assuming no other parameters have changed and a valid cache can be found.  
  
     If this option is deselected, the module will always read the data and retrain the model.  
  
6.  Run the experiment.  
  
7.  Right-click the module and select **Save model** to preserve the trained model in your Azure Machine Learning workspace.  
  
##  <a name="bkmk_Options"></a> Supported Vowpal Wabbit Options  

This section lists the Vowpal Wabbit command line arguments that are supported within Azure Machine Learning. Generally, all but a limited set of arguments are supported.  
  
 For a complete list of arguments, use the [Vowpal Wabbit wiki page](https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments).    

 **Not supported**
  
-   The input/output options specified in [https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments](https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments)  
  
     These properties are already configured automatically by the module.  
  
-   Additionally, any option that generates multiple outputs or takes multiple inputs is disallowed. These include *`--cbt`*, *`--lda`*, and *`--wap`*.  
  
-   Only supervised learning algorithms are supported. Therefore, these options are not supported: *`–active`*, `--rank`, *`--search`* etc.  
  

  

  
## Examples  
 There are no examples of this machine learning algorithm in the [Model Gallery](https://gallery.cortanaintelligence.com/) because this module requires authentication to an Azure storage account. We encourage you to review published community samples to see applications for the Vowpal Wabbit libraries. Also, see these resources:  
  
-   Blog describing Vowpal Wabbit implementation and roadmap  
  
     [http://blogs.technet.com/b/machinelearning/archive/2014/10/02/vowpal-wabbit-modules-in-azureml.aspx](http://blogs.technet.com/b/machinelearning/archive/2014/10/02/vowpal-wabbit-modules-in-azureml.aspx)  
  
-   Video that demonstrates building and scoring a model using Vowpal Wabbit in Azure Machine Learning  
  
     [https://channel9.msdn.com/Blogs/Windows-Azure/Text-Analytics-and-Vowpal-Wabbit-in-Azure-ML-Studio](https://channel9.msdn.com/Blogs/Windows-Azure/Text-Analytics-and-Vowpal-Wabbit-in-Azure-ML-Studio)  
  
## Technical Notes  
 Vowpal Wabbit provides extremely fast learning over non-linear features like n-grams.  
  
 Vowpal Wabbit uses *online learning* techniques such as stochastic gradient descent (SGD) to fit a model one record at a time. Thus it iterates very quickly over raw data and can develop a good predictor faster than most other models. This approach also avoids having to read all training data into memory.  
  
 Vowpal Wabbit converts all data to hashes, not just text data but other categorical variables. Using hashes makes lookup of regression weights more efficient, which is critical for effective stochastic gradient descent.  
  
 During training, the module makes calls into a Vowpal Wabbit wrapper developed for Azure. The training data is downloaded in blocks from Azure, utilizing the high bandwidth between the worker roles executing the computations and the store, and is streamed to the VW learners. The resulting model is generally very compact due to the internal compression done by VW. The model is copied back to the experiment workspace where it can be utilized like other models in Azure Machine Learning.  
  
 Because the goal of the service is to support experienced users of Vowpal Wabbit, input data must be prepared ahead of time using the Vowpal Wabbit native text format, rather than the dataset format used by other modules. Further, rather than using data in the Azure ML workspace, the training data is directly streamed from Azure, for maximal performance and minimal parsing overhead. For this reason, there is only limited interoperability between the VW modules and other modules in Azure ML.  
  
##  <a name="parameters-old"></a> Module Parameters  
  
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
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained learner|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all module errors, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
|[Error 0017](error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  
  
## See Also  
 [Text Analytics](text-analytics.md)   
 [Feature Hashing](feature-hashing.md)   
 [Named Entity Recognition](named-entity-recognition.md)   
 [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md)  
 [Score Vowpal Wabbit Version 8 Model](score-vowpal-wabbit-version-8-model.md).  
 [Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md)   
 [A-Z Module List](a-z-module-list.md)