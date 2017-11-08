---
title: "Load Trained Model | Microsoft Docs"
ms.custom: ""
ms.date: 06/09/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 204f6baa-c5f3-4748-844b-1d122a76792e
caps.latest.revision: 20
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Load Trained Model
*Load a web-hosted trained model*  
  
 Category: [Data Input and Output](data-input-and-output.md)  
  
## Overview  
 You can use the **Load Trained Model** module to load a trained model, and use the model to make predictions for new data. The model must have previouly been trained and then saved in the iLearner format. You can access the model either by URL or in Azure blob storage.  
  
## How to Use **Load Trained Model**  
 This module requires an existing trained model. Typically, you will create and then train the model in a different experiment, and then save the model either to your  workspace, or to one of the supported cloud storage options.  
  
 Then, you use the **Load Trained model** module to point to the trained model and run it in a new experiment.  
  
### Save a trained model  
 You  can save models by using an experiment that runs as a web service, or by using the Studio interface.  
  
-   **Using a web service**  
  
     First,  create an experiment that does the training or retraining of the model as a  web service, and then publish that experiment as a Web service. When you call the BES endpoint of the training web service, the Web service saves a trained model using the iLearner interface and saves the file in the Azure blob storage account that you specify.  
  
     For step-by step information about how to create a training web service, see these articles: [Retrain Machine Learning Models Programmatically](https://docs.microsoft.com/azure/machine-learning/machine-learning-retrain-models-programmatically) or [Saving an experiment as a Web service](https://docs.microsoft.com/azure/machine-learning/machine-learning-model-progression-experiment-to-web-service).  
  
-   **Using the Studio interface.**  
  
     After you have run the experiment that builds and trains the model, right-click the module that was used for  training, select **Trained model**, and then click **Save as trained model.** By default , models are saved to your Studio workspace.  
  
     The following modules can create a saved model using the iLearner interface:  
  
    -   [Train Model](train-model.md)  
  
    -   [Train Clustering Model](train-clustering-model.md)  
  
    -   [Train Anomaly Detection Model](train-anomaly-detection-model.md)  
  
    -   [Tune Model Hyperparameters](tune-model-hyperparameters.md)  
  
    -   [Sweep Clustering](sweep-clustering.md)  
  
### Load the model into a new experiment  
  
1.  Add the **Load Trained Model** module to your experiment.  
  
2.  For **Data source**, indicate the location of the trained model, using one of the following options:  
  
    -   Select **Web URL via HTTP** and then type the URL.  
  
         The URL should point to the experiment and the file representing the trained model. In Azure Machine Learning, trained models are by default saved in the iLearner format.  
  
    -   Select **Azure Blob Storage** if you exported the trained model to Azure storage.  
  
         You must then provide the account name and account key, and the path to the container, directory, or blob.  
  
    > [!NOTE]
    >  Arbitrary models are not supported; the model must have been saved in the [ILearner interface](ilearner-interface.md), which is the default binary format used for persisting Azure Machine Learning models.  
  
3.  If you intend to create a Request-Response web-service that is based on the current experiment, select the option, **Allow to use in RRS**. Otherwise, scoring is performed using the Batch Execution Service (BES) option, which is recommended. See [Technical Notes](#bkmk_Notes) for details.  
  
4.  Select the **Use cached results** option if you want to load the trained model from cache, when the cache is available and populated.  
  
     This option will be ignored when the experiment is deployed as a Web service API.  
  
## Examples  
 See the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/) for examples of how to use this module.  
  
-   [Load a Trained Deep Learning Model](https://gallery.cortanaintelligence.com/Collection/Load-a-Trained-Deep-Learning-Model-3): This collection includes a training experiment, to create the model, and a predictive experiment, in which the model is loaded as a web service and used for predictions.  
  
     The example creates a custom neural network for image detection. By using the **Load Trained Model** module, you can easily re-use this model without having to train it, which can be time-consuming. I  
  
<a name="bkmk_Notes"></a>   
## Technical Notes  
 This section contains advanced configuration options and answers to commonly asked questions.  
  
-   **Why is RRS use not enabled by default?**  
  
     It is generally expected that RRS calls return results within a short period of time. However, because the module must load the trained model in the form of a blob from an Azure storage account or a file hosted on a public HTTP endpoint, file operations might introduce unpredictable delays.  
  
     Therefore, we generally advise that the Web service be run in batch execution mode (BES). If you select the option for .execution using RRS, be aware of the potential for delay. For general information about execution times, see the [Azure Machine Learning SLA](https://azure.microsoft.com/support/legal/sla/machine-learning-studio/v1_0/).  
  
-   **Will the trained model load faster if I use the option, Use cached results?**  
  
     Yes, but only when the experiment is run in Azure Machine Learning Studio, and only after the cache has been filled by the first run. After the experiment is deployed as web service, this flag is ignored by  web service execution.  
  
-   **Is there a way to automate the process?**  
  
     You can use PowerShell to simplify or automate many tasks in Azure Machine Learning. For example, you can download the contents of an entire experiment or a particular module, export the definition of web service, or invoke the web service execution API. For more information, see [PowerShell Module for Microsoft Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/machine-learning-powershell-module).  
  
<a name="parameters"></a>   
## Module Parameters  
  
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
  
<a name="Outputs"></a>   
## Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained Model|[ILearner interface](ilearner-interface.md)|Trained model|  
  
<a name="exceptions"></a>   
## Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
  
## See Also  
 [A-Z Module List](a-z-module-list.md)  
  
 [Data Input and Output](data-input-and-output.md)