---
title: "ML Studio (classic): Anomaly Detection - Azure"
description: "Learn about the modules you can use for anomaly detection in Machine Learning Studio (classic)."
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"
author: xiaoharper
ms.author: amlstudiodocs 
manager: cgronlun
---

# Anomaly Detection

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

This article introduces the modules provided in Machine Learning Studio (classic) for anomaly detection. Anomaly detection encompasses many important tasks in machine learning:  
  
-   Identifying transactions that are potentially fraudulent.
-   Learning patterns that indicate that a network intrusion has occurred.
-   Finding abnormal clusters of patients.
-   Checking values entered into a system.
  
Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling. The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.
  
## Anomaly detection modules

Machine Learning Studio (classic) provides the following modules that you can use to create an anomaly detection model. Just drag the module into your experiment to begin working with the model.

- [One-Class Support Vector Machine](one-class-support-vector-machine.md)
- [PCA-Based Anomaly Detection](pca-based-anomaly-detection.md)

After setting model parameters, you must train the model by using a labeled data set and the [Train Anomaly Detection Model](train-anomaly-detection-model.md) training module. The result is a trained model that you can use to test new data. To do this, use the all-purpose [Score Model](score-model.md) module.

For an example of how these modules work together, see the [Anomaly Detection: Credit Risk](https://gallery.azure.ai/Experiment/Anomaly-Detection-Credit-Risk-5) experiment in the Cortana Intelligence Gallery.

### Related tasks
 
[Time Series Anomaly Detection](time-series-anomaly-detection.md) is a new module that's a bit different from the other anomaly detection models. The Time Series Anomaly Detection module is designed for time series data. It's intended to use to analyze trends over time. The algorithm identifies potentially anomalous trends in the time series data. It flags deviations from the trend's direction or magnitude.

Azure also provides the [Machine Learning Anomaly Detection API](/azure/machine-learning/machine-learning-apps-anomaly-detection-api), which you can call as a web service.


## List of modules

The **Anomaly Detection** category includes the following modules:

- [One-Class Support Vector Machine](one-class-support-vector-machine.md): Creates a one-class support vector machine model for anomaly detection.
- [PCA-Based Anomaly Detection](pca-based-anomaly-detection.md): Creates an anomaly detection model by using Principal Component Analysis.

## See also

- [Regression](machine-learning-initialize-model-regression.md)
- [Classification](machine-learning-initialize-model-classification.md)
- [Clustering](machine-learning-initialize-model-clustering.md)
- [Text Analytics](text-analytics.md)
- [OpenCV Library Modules](opencv-library-modules.md)
- [Module categories and descriptions](machine-learning-module-descriptions.md)
