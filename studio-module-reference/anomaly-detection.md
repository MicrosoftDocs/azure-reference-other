---
title: "Anomaly Detection | Microsoft Docs"
ms.custom: ""
ms.date: 06/13/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ae17795c-6437-47b5-9853-646d77d461b0
caps.latest.revision: 18
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Anomaly Detection

 This topic describes the modules provided in Azure Machine Learning for *anomaly detection*.
  
 Anomaly detection encompasses many important tasks in machine learning:  
  
-   Identifying transactions that are potentially fraudulent    
-   Learning patterns that indicate a network intrusion has occurred    
-   Finding abnormal clusters of patients    
-   Checking values input to a system  
  
 Because anomalies are by definition rare events, it can be difficult to collect a representative sample of data that can be used for modeling. The algorithms included in this section have been especially designed to address the core challenges of building and training models using imbalanced datasets.  
  
## Using the Anomaly Detection Modules

Azure Machine Learning provides the following modules to use for creating an anomaly detection model. Just drag the module into your experiment to begin working with the model.

+ [One-Class Support Vector Machine](one-class-support-vector-machine.md)
+ [PCA-Based Anomaly Detection](pca-based-anomaly-detection.md) 

After setting model parameters, you must train the model using a labeled dataset and a special training module, [Train Anomaly Detection Model](train-anomaly-detection-model.md). The result is a trained model that you can use to test new data. To do this, use the all-purpose [Score Model](score-model.md) module.

For an example of how these modules work together, see this experiment in the Cortana Intelligence Gallery: [Anomaly Detection: Credit Risk](https://gallery.cortanaintelligence.com/Experiment/Anomaly-Detection-Credit-Risk-5)


### Related tasks
 
The [Time Series Anomaly Detection](time-series-anomaly-detection.md) is a new module that is a bit different from the other anomaly detection models. It is specifically designed for time series data, and is intended to analyze trends in the data. The algorithm identifies potentially anomalous trends in the time series data and flags deviations from the trend's direction or magnitude.  

Azure also provides an anomaly detection service API that you can call as a web service: [Machine Learning Anomaly Detection API](https://docs.microsoft.com/azure/machine-learning/machine-learning-apps-anomaly-detection-api)

> [!TIP]
> If you are not sure whether anomaly detection is the right algorithm to use with your data, see these guides:  
>   
> -   [Machine learning algorithm cheat sheet for Azure ML](https://azure.microsoft.com/en-us/documentation/articles/machine-learning-algorithm-cheat-sheet/)  provides a graphical decision chart to guide you through the selection process   
> 
> + [How to choose Azure Machine Learning algorithms for clustering, classification, or regression](https://azure.microsoft.com/documentation/articles/machine-learning-algorithm-choice/)  
       

       
##  <a name="modules"></a> List of Modules  
 This category includes the following modules:  
  
|Module|Description|  
|------------|-----------------|  
|[One-Class Support Vector Machine](one-class-support-vector-machine.md)|Creates a one-class Support Vector Machine model for anomaly detection|  
|[PCA-Based Anomaly Detection](pca-based-anomaly-detection.md)|Creates an anomaly detection model using Principal Component Analysis|  

  
## See Also  
 [Regression](machine-learning-initialize-model-regression.md)   
 [Classification](machine-learning-initialize-model-classification.md)   
 [Clustering](machine-learning-initialize-model-clustering.md)   
 [Text Analytics](text-analytics.md)   
 [OpenCV Library Modules](opencv-library-modules.md)   
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)