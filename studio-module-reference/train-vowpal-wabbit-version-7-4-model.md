---
title: "Train Vowpal Wabbit Version 7-4 Model | Microsoft Docs"
ms.custom: ""
ms.date: 10/13/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8383eb49-c0a3-45db-95c8-eb56a1fef5bf
caps.latest.revision: 23
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Train Vowpal Wabbit Version 7-4 Model
*Trains a model using version 7-4 of the  Vowpal Wabbit machine learning system*  
  
 Category: [Text Analytics](text-analytics.md)  
  
## Module Overview  
 You can use the **Train Vowpal Wabbit Version 7-4** module to create a machine learning model by using an instance of Vowpal Wabbit 7-4, hosted in Azure Machine Learning.  
  
 To configure this module, you must have formatted your input according to Vowpal Wabbit requirements, and saved the data in an Azure blob. You use Vowpal Wabbit command-line arguments to specify how the data should be processed during training, and where the trained model should be saved. 
 
 When the experiment is run, the module calls an instance of Vowpal Wabbit version 7-4, and when training is complete, serializes the model back to the workspace so that you can use it to score data. By default, the trained model is also persisted in Azure storage so that you can use it later without having to reprocess the training data.   
  
  To incrementally train an existing model on new data, you connect a saved model to the **Pre-trained model** input port on the **Train Vowpal Wabbit Version 7-4** module, and add the new data to the other input. 
  
> [!NOTE]
>  This module uses the 7-4 version of the Vowpal Wabbit framework. If you create a model using this module, you must use the corresponding scoring module: [Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md).  
>   
>  For new models, we recommend that you use the latest version, [Train Vowpal Wabbit 8 Model](train-vowpal-wabbit-version-8-model.md).  
  
## What is Vowpal Wabbit?  
 Vowpal Wabbit (VW) is a fast, parallel machine learning framework that was developed for distributed computing by Yahoo! Research. Later it was ported to Windows and adapted by John Langford (Microsoft Research) for scientific computing in parallel architectures.  
  
 Features of Vowpal Wabbit that are important for machine learning include continuous learning (online learning), dimensionality reduction, and interactive learning. Vowpal Wabbit is also a solution for problems when you cannot fit the model data into memory.  
  
 The primary users of Vowpal Wabbit in Azure Machine Learning  are data scientists who have previously used the framework for machine learning tasks such as classification, regression, topic modeling or matrix factorization. The Azure wrapper for Vowpal Wabbit has very similar performance characteristics to the on-premise version, which means that users can continue to build models, retrain, and score using the powerful features and native performance of Vowpal Wabbit, while gaining the ability to easily publish the trained model as an operationalized service.  
  
 The [Feature Hashing](feature-hashing.md) module also includes functionality provided by Vowpal Wabbit, that lets you transform text datasets into binary features using a hashing algorithm.  
  
## How to Use Train Vowpal Wabbit Version 7-4  
  
#### To create a new Vowpal Wabbit model  
  
1.  Add the **Train Vowpal Wabbit Version 7-4** module to your experiment.  
  
    > [!NOTE]
    >  For this module, you do not use datasets in Azure Machine Learning Studio; instead, your training data should be already prepared in the correct format and saved in Azure blob storage.  
  
2.  Specify the account where the training data is stored and where the model and hashing file will be stored.  
  
    -   **Azure storage account name**  
  
    -   **Azure storage key**  
  
    -   **Azure container name**  
  
3.  Specify command-line arguments that will be passed to the Vowpal Wabbit executable, by using the **VW arguments** property of the module.  
  
     For example, you might add *`–l`* to specify the learning rate, or *`-b`* to indicate the number of hashing bits.  
  
     For more information, see the [Options](#bkmk_Options) section.  
  
4.  Specify the file name and format of the input dataset.  
  
     The input dataset must consist of a single string column in one of the two supported formats: **LibSVM** or **VW**. Note that this doesn't mean that Vowpal Wabbit analyzes only text data, only that the features and values must be prepared in the required text file format.  
  
     It is not possible to use [Export Data](export-data.md) to directly save the input file to Azure for use with Vowpal Wabbit, because the format requires some additional modification. You must ensure the data is in the correct format and then upload the data to Azure blob storage.  
  
     However, as a shortcut, you can use the [Convert to SVMLight](convert-to-svmlight.md) module to generate an SVMLight format file. Then, you can either upload the SVMLight format file to Azure blob storage and use it as the input, or you can modify the file slightly to conform to the Vowpal Wabbit input file requirements.  
  
5.  Provide a name for saving the trained model, and a name for saving the hash file associated with the model.  
  
     The trained model and hash file must be stored in the same storage account and container as the data used to train the model.  
  
6.  Use the option, **Use cached results**, to indicate whether the Vowpal Wabbit model should be retrained each time you run the experiment.  
  
     When you select this option, the experiment will use a cached version of the data so that you don't need ot reload it each time, assuming no other parameters have changed and a valid cache can be found.  
  
     If this option is deselected, the module will always read the data and retrain the model.  
  
7.  Run the experiment.  
  
8.  After the model has been generated, right-click the output of **Train Vowpal Wabbit Version 7-4** and select **Save as trained model**, so that you can re-use and re-train the model later.  
  
#### To retrain an existing version 7-4 Vowpal Wabbit model  
  
1.  Add the **Train Vowpal Wabbit Version 7-4** module to your experiment.  
  
2.  Connect a previously trained model to the input port of **Train Vowpal Wabbit Version 7-4**:  
  
    -   Use the output of another **Train Vowpal Wabbit Version 7-4** module in the same experiment.  
  
    -   Locate a saved model in the **Trained Models** group of Studio’s left navigation pane.  
  
3.  In the **Properties** pane of **Train Vowpal Wabbit Version 7-4**, specify the location and format of the training data.  
  
4.  Provide the location for saving the updated model, and a name for saving the human-readable model output file and the hash file associated with the updated model.  
  
    > [!NOTE]
    >  If there is an Vowpal Wabbit model or hash file in the specified location , the files will be silently overwritten by the new trained model. To preserve intermediate models when retraining, you must change the storage location or make a local copy of the model files.  
  
5.  Use the option, **Use cached results**, to indicate whether the Vowpal Wabbit model should be retrained each time you run the experiment.  
  
     When you select this option, the experiment will use a cached version of the data so that you don't need to reload it each time, assuming no other parameters have changed and a valid cache can be found.  
  
     If this option is deselected, the module will always read the data and retrain the model.  
  
6.  Run the experiment.  
  
7.  Right-click the module and select **Save model** to preserve the trained model in your Azure Machine Learning workspace.  
  
###  <a name="bkmk_Options"></a> Options  
 **Azure storage account name**  
 Type the name of the account where you want to store the input data and the trained model. The model and input files cannot be saved in different containers or different accounts.  
  
 **Azure storage key**  
 Copy and paste the key that is provided for accessing the storage account  
  
 If you don’t have a key, see [How to regenerate storage access keys](http://azure.microsoft.com/documentation/articles/storage-manage-storage-account/)  
  
 **Azure container name**  
 Type the container name without the account name or protocol prefix. For example, if the full container path and name is **https://myaccount.blob.core.windows.net/vwmodel**, you should type just **vwmodel**.  
  
 For more information about container names, see [Naming and Referencing Containers, Blobs, and Metadata](https://msdn.microsoft.com/library/azure/dd135715.aspx).  
  
 **VW arguments**  
 Type a set of valid command-line arguments to the Vowpal Wabbit executable.  
  
 **Not supported**: You cannot use the following command-line arguments in Azure Machine Learning Studio.  
  
-   The input/output options specified in [https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments](https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments)  
  
     These properties are already configured automatically by the module.  
  
-   Additionally, any option that generates multiple outputs or takes multiple inputs is disallowed. These include *`--cbt`*, *`--lda`*, and *`--wap`*.  
  
-   Only supervised learning algorithms are supported. Therefore, these options are not supported: *`–active`*, `--rank`, *`--search`* etc.  
  
 **Supported**: All arguments other than those described above are allowed.  
  
 For a complete list of arguments, use the [Vowpal Wabbit wiki page](https://github.com/JohnLangford/vowpal_wabbit/wiki/Command-line-arguments).  
  
 **Name of the input VW file**  
 Type the name of the file that contains the input data.  
  
 The file must be an existing blob file, located in the previously specified storage account and container, and must have been prepared in one of the supported formats.  
  
 **Name of the output readable model (--readable_model) file**  
 Type the name of the file in which the trained model will be saved.  
  
 The file is saved within the same storage account and container as the input file.  
  
 This argument corresponds to the `--readable_model` parameter in the VW command line.  
  
 **Name of the output inverted hash (--invert_hash) file**  
 Type the name of the file in which the inverted hashing function will be saved.  
  
 The file is saved within the same storage account and container as the input file.  
  
 This argument corresponds to the `--invert_hash` parameter in the VW command line.  
  
 **Please specify file type**  
 Choose one of the two input file formats supported by Vowpal Wabbit:  
  
-   **VW**  
  
     The internal format used by  Vowpal Wabbit . See the [Vowpal Wabbit wiki page](https://github.com/JohnLangford/vowpal_wabbit/wiki/Input-format) for details.  
  
     The Vowpal Wabbit data format has the advantage that it does not require a columnar format, which saves space when dealing with sparse data.  
  
-   **SVMLight**  
  
     You can use the [Convert to SVMLight](convert-to-svmlight.md) module to convert your data to this format.  
  
 **Use cached results**  
 If you select this option, the data will not be re-loaded when the experiment runs, and previously cached results will be used as the output, assuming all the following conditions are met:  
  
-   A valid cache exists from a previous  run.  
  
-   The input data and parameters settings of the module have not changed since the previous run.  
  
 Otherwise, this module will be executed each time the experiment runs.  
  
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
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Azure storage account name|any|String|none|Type the Azure storage account name|  
|Azure storage key|any|SecureString|none|Provide the Azure storage key|  
|Azure container name|any|String|none|Type the Azure container name|  
|VW arguments|any|String|none|Specify any Vowpal Wabbit arguments.<br /><br /> The argument *–f* is not supported.|  
|Name of the input VW file|any|String|none|Specify the name of an input file in the Vowpal Wabbit format|  
|Name of the output readable model (--readable_model) file|any|String||If specified, outputs a readable model back to the Azure container.<br /><br /> This argument is optional.|  
|Name of the output inverted hash (--invert_hash) file|any|String||If specified, outputs a file containing the inverted hash function back to the Azure container.<br /><br /> This argument is optional.|  
|Please specify file type|VW<br /><br /> SVMLight|DataType|VW|Indicate whether the file type uses the SVMLight format or the Vowpal Wabbit format.|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained learner|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all module errors, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
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
 [Vowpal Wabbit Train](train-vowpal-wabbit-version-7-4-model.md)   
 [A-Z Module List](a-z-module-list.md)