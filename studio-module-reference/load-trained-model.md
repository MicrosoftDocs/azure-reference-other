---
title: "ML Studio (classic): Load Trained Model - Azure"
description: Learn how to use the Load Trained Model module to load an already trained model for use in an experiment.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Load Trained Model

*Load a web-hosted trained model*

Category: [Data Input and Output](data-input-and-output.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Load Trained Model** module in Azure Machine Learning Studio (classic), to load an already trained model for use in an experiment. 

This module requires an existing trained model. Typically, you create and then train the model in a different experiment, and then save the model either to your workspace, or to one of the supported cloud storage options.  

Then, you use the **Load Trained model** module to get the trained model and run it in a new experiment.

## How to use Load Trained Model

To use an existing model to make predictions for new data:

+ The model must have previously been trained and then saved in the iLearner format.
+ The model must be accessible either by URL or in Azure blob storage.

This section describes how to save a model, get a saved model, and apply a saved model.

### Save a trained model 

You can save models by using the Studio (classic) interface, or using an experiment that runs as a web service.  

#### Save a model using a web service

1. Create an experiment that does the training or retraining of the model as a web service
2. Publish that experiment as a Web service. 
3. When you call the BES endpoint of the training web service, the Web service saves a trained model using the iLearner interface and saves the file in the Azure blob storage account that you specify.  

For step-by step information about how to create a training web service, see these articles: 

+ [Retrain Machine Learning Models Programmatically](/azure/machine-learning/classic/retrain-machine-learning-model)
+ [Saving an experiment as a Web service](/azure/machine-learning/classic/deploy-a-machine-learning-web-service)

#### Save a model in Studio (classic)

1. Run the experiment that builds and trains the model.
2. When training is complete, right-click the module that was used for training, select **Trained model**, and then click **Save as trained model.**
3. By default, models are saved to your Studio (classic) workspace. You can view them using the Studio (classic) UI.

The following modules can create a saved model that uses the required [iLearner](ilearner-interface.md) interface:

+ [Train Model](train-model.md)  
+ [Train Clustering Model](train-clustering-model.md)  
+ [Train Anomaly Detection Model](train-anomaly-detection-model.md)  
+ [Tune Model Hyperparameters](tune-model-hyperparameters.md)  
+ [Sweep Clustering](sweep-clustering.md)  

> [!NOTE]
> Arbitrary models are not supported; the model must have been saved in the default binary format used for persisting Azure Machine Learning models.

### Load the model into a new experiment

1. Add the **Load Trained Model** module to your experiment in Studio (classic).

2. For **Data source**, indicate the location of the trained model, using one of the following options:

    + **Web URL via HTTP**: Provide a URL that points to the experiment and the file representing the trained model. In Azure Machine Learning, trained models are by default saved in the [ILearner](ilearner-interface.md) format.

    + **Azure Blob Storage**: Select this option only if you exported the trained model to Azure storage. You must then provide the account name and account key, and the path to the container, directory, or blob.

3. If you intend to create a Request-Response web-service that is based on the current experiment, select the option, **Allow to use in RRS**. Otherwise, scoring is performed using the Batch Execution Service (BES) option, which is recommended. See the [Technical notes](#bkmk_Notes) section for details.

4. Select the **Use cached results** option if you want to load the trained model from cache, when the cache is available and populated. This option is ignored after the experiment is deployed as a Web service API.

## Examples

For examples of how to use this module, see the [Cortana Intelligence Gallery](https://gallery.azure.ai/).

+ [Load a Trained Deep Learning Model](https://gallery.azure.ai/Collection/Load-a-Trained-Deep-Learning-Model-3): The example creates a custom neural network for image detection. By using the **Load Trained Model** module, you can easily re-use this model without having to train it, which can be time-consuming.

    This collection includes a training experiment, to create the model, and a predictive experiment, in which the model is loaded as a web service and used for predictions.

## <a name="bkmk_Notes"></a> Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Common questions

#### Why is RRS use not enabled by default

It is generally expected that RRS calls return results within a short period of time. However, because the module must load the trained model in the form of a blob from an Azure storage account or a file hosted on a public HTTP endpoint, file operations might introduce unpredictable delays.

Therefore, we generally advise that the Web service be run in batch execution mode (BES). If you select the option for .execution using RRS, be aware of the potential for delay. For general information about execution times, see the [Azure Machine Learning SLA](https://azure.microsoft.com/support/legal/sla/machine-learning-studio/v1_0/).

### Does the trained model load faster if I use the cached results option

Yes, but only when the experiment is run in Azure Machine Learning Studio (classic), and only after the cache has been filled by the first run. After the experiment is deployed as web service, this flag is ignored by  web service execution.

#### Is there a way to automate the process

You can use PowerShell to simplify or automate many tasks in Azure Machine Learning. For example, you can download the contents of an entire experiment or a particular module, export the definition of web service, or invoke the web service execution API. For more information, see [PowerShell Module for Microsoft Azure Machine Learning](/azure/machine-learning/classic/powershell-module).

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Allow to use in RRS|True/False|Boolean|false|Allow this module to run in request-response web service, which may incur unpredictable delays|  
|Data source|Web URL via HTTP, or Azure Blob Storage|T_DataSourceOrSink|Azure Blob Storage|Data source can be HTTP or a file in Azure blob storage (required)|  
|For **Web URL via HTTP**:|||||  
|Data source URL|any|String||URL for HTTP|  
|For **Azure Blob Storage**:|||||  
|Account Name|any|String||Account name|  
|Account key|any|SecureString||Key associated with the Windows Azure Storage account|  
|Path to container or directory or blob|any|String||Path to blob or name of table|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained Model|[ILearner interface](ilearner-interface.md)|Trained model|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [Data Input and Output](data-input-and-output.md)
