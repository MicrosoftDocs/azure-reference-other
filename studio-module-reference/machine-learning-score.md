---
title: "Machine Learning - Score | Microsoft Docs"
ms.custom: ""
ms.date: 05/31/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: be8a69b7-d1e3-4fa2-a174-7abe0bcce4e9
caps.latest.revision: 23
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Machine Learning - Score
This section lists the modules provided in Azure Machine Learning for *scoring*. 

Scoring is also called prediction, and is the process of generating values based on a trained machine learning model, given some new input data. The values or scores that are created can represent predictions of future values, but they might also represent a likely category or outcome. The meaning of the score depends on the type of data you provide, and the type of model that you created.  
  
For example, you can generate these types of scores in Azure Machine Learning:
  
- A list of recommended items
- A list of users who are similar, or items that are similar     
- Forecasts, for time series models    
-  Estimates of projected demand, volume, or other numeric quantity, for regression models    
- A category or cluster to which a new item is most similar, for clustering models    
-  A predicted class or outcome, for classification models  

> [!NOTE] 
> You might have also heard the word *score* used to mean a weight or value assigned as a result of data analysis. However, in this section, scoring means only the process of generating predicted values from new data.

## How to Use Scoring

When you use one of these modules in your experiment, you must attach an already trained machine learning model, and some new data. When you run the experiment or the selected module, the scoring module ingests the new data, computes scores based on the model, and returns the scores in a table. 

Azure Machine Learning provides different scoring modules, depending on the type of model you are using: 

+ Use [Score Matchbox Recommender](score-matchbox-recommender.md) if you want to generate recommendations, find related items or users, or predict ratings.  
+ Use [Assign Data to Clusters](assign-data-to-clusters.md) if you want to cluster new data based on an existing K-Means clustering model. 
+ Use [Score Model](score-model.md) for all other regression and classification models, as well as some anomaly detection models.  
+ Use [Apply Transformation](apply-transformation.md) module to apply a saved process to a set of data.

### Related Tasks

+ Special scoring modules are provided for Vowpal Wabbit. See [Text Analytics](text-analytics.md). 
+ Scoring for special classes of images on pretrained models can be performed using the [OpenCV Library](opencv-library-modules.md).  
+ The [Time Series Anomaly Detection](https://msdn.microsoft.com/library/mt775197.aspx) module generates scores that represent potential deviations from a trend. 

## Data used for Scoring

The new data that you provide as input generaly needs to have the same columns that were used to train the model, minus of course the label, or outcome column. Columns that are used solely as identifiers are usually excluded when training a model and thus should be excluded when scoring as well. 

However, identifiers such as primary keys can easily be re-combined with the scoring dataset later, by using the [Add Columns](add-columns.md) module. This module works without you having to specify a join key as long as the dataset size has not changed. 

> [!WARNING]
> Before you perform scoring on your dataset, check for missing values and nulls. When data used as input for scoring has missing values, the missing values are used as inputs. Because nulls are always propagated, the result is usually a missing value.  
  
## Examples  

The following articles provide real-world examples of how you can use a machine learning model for scoring:  
  
- [Develop a predictive solution](http://azure.microsoft.com/documentation/articles/machine-learning-walkthrough-develop-predictive-solution/)  
  
- [Survival Analysis](http://azure.microsoft.com/documentation/articles/machine-learning-r-csharp-survival-analysis/)  
  
- [Anomaly Detection](http://azure.microsoft.com/documentation/articles/machine-learning-apps-anomaly-detection/)  
  
- [Lexicon-based sentiment analysis](http://azure.microsoft.com/documentation/articles/machine-learning-r-csharp-lexicon-based-sentiment-analysis/)  

These examples in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com) demonstrate the process of scoring, from basic to advanced scenarios:

+ [Binary Classification for Direct Marketing](https://gallery.cortanaintelligence.com/Experiment/Binary-Classification-Direct-marketing-2). This experiment demonstrates the basic workflow for scoring, in a scenario where the predicted value is customer response to a marketing campaign.

+ [Predict Book Reviews](https://gallery.cortanaintelligence.com/Experiment/Predict-Book-Reviews-1). Demonstrates the proces of scoring on text data, using a logistic regression model.

+ [Learning with Counts](https://gallery.cortanaintelligence.com/Experiment/Learning-with-Counts-Binary-Classification-2): Shows you how to use count-based featurization for making predictions.  

+ [No-code batch scoring with Logic Apps and Azure Machine Learning](https://gallery.cortanaintelligence.com/Tutorial/No-code-Batch-Scoring-1): Illustrates the end-to-end process of training and scoring, automated with Azure Logic Apps.

##  <a name="modules"></a> List of Modules  

The Score category includes these modules.  
  
|Module|Description|  
|------------|-----------------|  
|[Apply Transformation](apply-transformation.md)|Applies a well-specified data transformation to a dataset|  
|[Assign Data to Clusters](assign-data-to-clusters.md)|Assigns data to clusters using an existing trained clustering model<br /><br /> This module replaces the [Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md) module, which has been deprecated but is still available for use in existing experiments.|  
|[Score Matchbox Recommender](score-matchbox-recommender.md)|Scores predictions for a dataset using the Matchbox recommender|  
|[Score Model](score-model.md)|Scores predictions for a trained classification or regression model|  
  
## See Also  

[Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [Train](machine-learning-train.md)   
 [Score](machine-learning-score.md)   
 [Evaluate](machine-learning-evaluate.md)