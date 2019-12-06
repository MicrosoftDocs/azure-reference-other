---
title: "Evaluate Model | Microsoft Docs"
titleSuffix: ML Studio (classic) - Azure
description: Learn how to use the Evaluate Model module to measure the accuracy of a trained model. 
ms.custom: "formulas"
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Evaluate Model
*Evaluates the results of a classification or regression model with standard metrics*  
  
 Category: [Machine Learning / Evaluate](machine-learning-evaluate.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the **Evaluate Model** module in Azure Machine Learning Studio (classic) to measure the accuracy of a trained model. You provide a dataset containing scores generated from a model, and the **Evaluate Model** module computes a set of industry-standard evaluation metrics.
  
 The metrics returned by **Evaluate Model** depend on the type of model that you are evaluating:  
  
-   **[Classification Models](#bkmk_classification)**    
-   **[Regression Models](#bkmk_regression)**    
-   **[Clustering Models](#bkmk_clustering)**  

For recommendation models, use the [Evaluate Recommender](evaluate-recommender.md) module.  

> [!TIP]
> If you are new to model evaluation, we recommend these samples in the Azure AI Gallery, which build a model and then explain how to use the related metrics:
> 
> + [Compare regression models](https://gallery.azure.ai/Experiment/Compare-Regressors-5)
> + [Compare binary classifiers](https://gallery.azure.ai/Experiment/Compare-Binary-Classifiers-2)
> + [Compare multiclass classifiers](https://gallery.azure.ai/Experiment/Compare-Multi-class-Classifiers-Letter-recognition-2)
> 
> We also recommend the video series by Dr. Stephen Elston, as part of the [machine learning course](https://blogs.technet.microsoft.com/machinelearning/2015/09/08/new-edx-course-data-science-machine-learning-essentials/) from EdX. 

## How to use Evaluate Model

There are three ways to use the **Evaluate Model** module:

+ Generate scores over your training data, and evaluate the model based on these scores
+ Generate scores on the model, but compare those scores to scores on a reserved testing set
+ Compare scores for two different but related models, using the same set of data

### Use the training data

To evaluate a model, you must connect a dataset that contains a set of input columns and scores.  If no other data is available, you can use your original dataset.

1. Connect the **Scored datset** output of the [Score Model](score-model.md) to the input of **Evaluate Model**. 
2. Click **Evaluate Model** module, and select **Run selected** to generate the evaluation scores.

### Use testing data

A common scenario in machine learning is to separate your original data set into training and testing datasets, using the [Split](split-data.md) module, or the [Partition and Sample](partition-and-sample.md) module. 

1. Connect the **Scored dataset** output of the [Score Model](score-model.md) to the input of **Evaluate Model**. 
2. Connect the output of the Split Data module that contains the testing data to the right-hand input of **Evaluate Model**.
2. Click **Evaluate Model** module, and select **Run selected** to generate the evaluation scores.

### Compare scores from two models

You can also connect a second set of scores to **Evaluate Model**.  The scores might be a shared evaluation set that has known results, or a set of results from a different model for the same data.

This feature is useful because you can easily compare results from two different models on the same data. Or, you might compare scores from two different runs over the same data with different parameters.

1. Connect the **Scored datset** output of the [Score Model](score-model.md) to the input of **Evaluate Model**. 
2. Connect the output of the Score Model module for the second model to the right-hand input of **Evaluate Model**.
3. Right-click **Evaluate Model**, and select **Run selected** to generate the evaluation scores.

## Results

After you run **Evaluate Model**, right-click the module and select **Evaluation results** to see the results. You can:

+ Save the results as a dataset, for easier analysis with other tools
+ Generate a visualization in the Studio (classic) interface

If you connect datasets to both inputs of **Evaluate Model**, the results will contain metrics for both set of data, or both models.
The model or data attached to the left port is presented first in the report, followed by the metrics for the dataset or model attached on the right port.  

For example, the following image represents a comparison of results from two clustering models that were built on the same data, but with different parameters.  

![AML&#95;Comparing2Models](media/aml-comparing2models.png "AML_Comparing2Models")  

Because this is a clustering model, the evaluation results are different than if you compared scores from two regression models, or compared two classification models. However, the overall presentation is the same. 

### Metrics

This section describes the metrics returned for the specific types of models supported for use with **Evaluate Model**:

+ [classification models](#bkmk_classification)
+ [regression models](#bkmk_regression)
+ [clustering models](#bkmk_clustering)

####  <a name="bkmk_classification"></a> Metrics for classification models

The following metrics are reported when evaluating classification models. If you compare models, they are ranked by the metric you select for evaluation.  
  
-   **Accuracy** measures the goodness of a classification model as the proportion of true results to total cases.  
  
-   **Precision** is the proportion of true results over all positive results.  
  
-   **Recall** is the fraction of all correct results returned by the model.  
  
-   **F-score** is computed as the weighted average of precision and recall between 0 and 1, where the ideal F-score value is 1.  
  
-   **AUC** measures the area under the curve plotted with true positives on the y axis and false positives on the x axis. This metric is useful because it provides a single number that lets you compare models of different types.  
  
- **Average log loss** is a single score used to express the penalty for wrong results. It is calculated as the difference between two probability distributions – the true one, and the one in the model.  
  
- **Training log loss** is a single score that represents the advantage of the classifier over a random prediction. The log loss measures the uncertainty of your model by comparing the probabilities it outputs to the known values (ground truth) in the labels. You want to minimize log loss for the model as a whole.

###  <a name="bkmk_regression"></a> Metrics for regression models
 
The metrics returned for regression models are generally designed to estimate the amount of error.  A model is considered to fit the data well if the difference between observed and predicted values is small. However, looking at the pattern of the residuals (the difference between any one predicted point and its corresponding actual value) can tell you a lot about potential bias in the model.  
  
 The following metrics are reported for evaluating regression models. When you compare models, they are ranked by the metric you select for evaluation.  
  
- **Mean absolute error (MAE)** measures how close the predictions are to the actual outcomes; thus, a lower score is better.  
  
- **Root mean squared error (RMSE)** creates a single value that summarizes the error in the model. By squaring the difference, the metric disregards the difference between over-prediction and under-prediction.  
  
- **Relative absolute error (RAE)** is the relative absolute difference between expected and actual values; relative because the mean difference is divided by the arithmetic mean.  
  
- **Relative squared error (RSE)** similarly normalizes the total squared error of the predicted values by dividing by the total squared error of the actual values.  
  
- **Mean Zero One Error (MZOE)** indicates whether the prediction was correct or not.  In other words: `ZeroOneLoss(x,y) = 1` when `x!=y`; otherwise `0`.
  
- **Coefficient of determination**, often referred to as R<sup>2</sup>, represents the predictive power of the model as a value between 0 and 1. Zero means the model is random (explains nothing); 1 means there is a perfect fit. However, caution should be used in interpreting  R<sup>2</sup> values, as low values can be entirely normal and high values can be suspect.
  
###  <a name="bkmk_clustering"></a> Metrics for clustering models

Because clustering models differ significantly from classification and regression models in many respects, [Evaluate Model](evaluate-model.md) also returns a different set of statistics for clustering models.  
  
 The statistics returned for a clustering model describe how many data points were assigned to each cluster, the amount of separation between clusters, and how tightly the data points are bunched within each cluster.  
  
 The statistics for the clustering model are averaged over the entire dataset, with additional rows containing the statistics per cluster.  
  
 For example, the following results show a portion of the results from a sample experiment that clusters the data in the PIMA Indian Diabetes Binary Classification dataset, which is available in Azure Machine Learning Studio (classic).  
  
|Result description|Average Distance to Cluster Center|Average Distance to Other Center|Number of Points|Maximal Distance To Cluster Center|  
|------------------------|----------------------------------------|--------------------------------------|----------------------|----------------------------------------|  
|Combined Evaluation|55.915068|169.897505|538|303.545166|  
|Evaluation For Cluster No.0|0|1|570|0|  
|Evaluation For Cluster No.1|0|1|178|0|  
|Evaluation For Cluster No.2|0|1|178|0|  
  
 From these results, you get the following information:  
  
-   The **Sweep Clustering** module creates multiple clustering models, listed in order of accuracy. For simplicity, we've shown only the best-ranked model here. Models are measured using all possible metrics, but the models are ranked by using the metric that you specified. If you changed the metric, a different model might be ranked higher.  
  
-   The **Combined Evaluation** score at the top of the each section of results lists the averaged scores for the clusters created in that particular model.  
  
     This top-ranked model happened to create three clusters; other models might create two clusters, or four clusters. Therefore, this combined evaluation score helps you compare models with different number of clusters.  
  
-   The scores in the column, **Average Distance to Cluster Center**, represent the closeness of all points in a cluster to the centroid of that cluster.  
  
-   The scores in the column, **Average Distance to Other Center**, represent how close, on average, each point in the cluster is to the centroids of all other clusters.  
  
     You can choose any one of four metrics to measure this distance, but all measurements must use the same metric.  
  
-   The **Number of Points** column shows how many data points were assigned to each cluster, along with the total overall number of data points in any cluster.  
  
     If the number of data points assigned to clusters is less than the total number of data points available, it means that the data points could not be assigned to a cluster.  
  
-   The scores in the column, **Maximal Distance to Cluster Center**, represent the sum of the distances between each point and the centroid of that point’s cluster.  
  
     If this number is high, it can mean that the cluster is widely dispersed. You should review this statistic together with the **Average Distance to Cluster Center** to determine the cluster’s spread.  
  
## Examples

For examples of how to generate, visualize, and interpret evaluation metrics, see these sample experiments in the [Azure AI Gallery](https://gallery.azure.ai). These experiments demonstrate how to build multiple models and use **Evaluate Model** to determine which model is the best.  
  
- [Compare Binary Classifiers](https://go.microsoft.com/fwlink/?LinkId=525729): Explains how to compare the performance of different classifiers that were built using the same data.
  
- [Compare Multi-class Classifiers](https://go.microsoft.com/fwlink/?LinkId=525730): Demonstrates how to compare the accuracy of different classification models that were built on the letter recognition dataset.
  
- [Compare Regressors](https://go.microsoft.com/fwlink/?LinkId=525731): Walks you through the process of evaluating different regression models.

- [Demand estimation](https://go.microsoft.com/fwlink/?LinkId=525271): Learn how to combine evaluation metrics from multiple models.  
  
-  [Customer relationship prediction](https://go.microsoft.com/fwlink/?LinkId=525941): Demonstrates how to evaluate multiple related models.
  
##  Expected inputs
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Scored dataset|[Data Table](data-table.md)|Scored dataset|  
|*Scored dataset to compare*|[Data Table](data-table.md)|Scored dataset to compare (optional)|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Evaluation results|[Data Table](data-table.md)|Data evaluation result|  
  
##  Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0013](errors/error-0013.md)|Exception occurs if passed to module learner has invalid type.|  
|[Error 0020](errors/error-0020.md)|Exception occurs if number of columns in some of the datasets passed to the module is too small.|  
|[Error 0021](errors/error-0021.md)|Exception occurs if number of rows in some of the datasets passed to the module is too small.|  
|[Error 0024](errors/error-0024.md)|Exception occurs if dataset does not contain a label column.|  
|[Error 0025](errors/error-0025.md)|Exception occurs if dataset does not contain a score column.|  
  
## See also  
 [Cross-Validate Model](cross-validate-model.md)   
 [Evaluate Recommender](evaluate-recommender.md)   
 [Evaluate](machine-learning-evaluate.md)   
 [Score Model](score-model.md)   
