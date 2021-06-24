---
title: "ML Studio (classic): Machine Learning Scoring - Azure"
description: This section lists the modules provided in Machine Learning Studio (classic) for scoring.
ms.date: 03/05/2020
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Machine Learning - Score

This section lists the modules provided in Machine Learning Studio (classic) for *scoring*.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

Scoring is also called prediction, and is the process of generating values based on a trained machine learning model, given some new input data. The values or scores that are created can represent predictions of future values, but they might also represent a likely category or outcome. The meaning of the score depends on the type of data you provide, and the type of model that you created.

## Create and use models in Machine Learning Studio (classic)

The typical workflow for machine learning includes these phases:

- Choosing a suitable algorithm, and setting initial options.
- Training the model on compatible data.
- Creating predictions using new data, based on the patterns in the model.
- Evaluating the model to determine if the predictions are accurate, how much error there is, and if there is any overfitting.

Machine Learning Studio (classic) supports a flexible, customizable framework for machine learning. Each task in this process is performed by a specific type of module, which can be modified, added, or removed, without breaking the rest of your experiment. 

The modules in this section include tools for scoring. In this phase of machine learning, you apply a trained model to new data, to generate predictions. You can either send those predictions to an application that consumes machine learning results, or use the results of scoring to evaluate the accuracy and usefulness of the model.

## More about scoring 

Scoring is widely used in machine learning to mean the process of generating new values, given a model and some new input. The generic term "score" is used, rather than "prediction," because the scoring process can generate so many different types of values:

- A list of recommended items and a similarity score.
- Numeric values, for time series models and regression models.
- A probability value, indicating the likelihood that a new input belongs to some existing category.
- The name of a category or cluster to which a new item is most similar.
- A predicted class or outcome, for classification models.

> [!NOTE] 
> You might have also heard the word *score* used to mean a weight or value assigned as a result of data analysis. However, in Machine Learning Studio (classic), scoring usually denotes the process of generating predicted values from new data.

When you add one of these modules in your experiment, you must attach an already trained machine learning model, and some new data. When you run the experiment or the selected module, the scoring module ingests the new data, computes scores based on the model, and returns the scores in a table.

### Data used for scoring

The new data that you provide as input generally needs to have the same columns that were used to train the model, minus the label, or outcome column. 

Columns that are used solely as identifiers are usually excluded when training a model, and thus should be excluded when scoring as well. However, identifiers such as primary keys can easily be re-combined with the scoring dataset later, by using the [Add Columns](add-columns.md) module. This module works without you having to specify a join key, as long as the dataset size has not changed. 

Before you perform scoring on your dataset, always check for missing values and nulls. When data used as input for scoring has missing values, the missing values are used as inputs. Because nulls are propagated, the result is usually a missing value.

## List of scoring modules

Machine Learning Studio (classic) provides many different scoring modules. You select one depending on the type of model you are using, or the type of scoring task you are performing: 

+ [Apply Transformation](apply-transformation.md): Applies a well-specified data transformation to a dataset.   

    Use this module to apply a saved process to a set of data.

+ [Assign Data to Clusters](assign-data-to-clusters.md): Assigns data to clusters by using an existing trained clustering model.

    Use this module if you want to cluster new data based on an existing K-Means clustering model. 

    This module replaces the Assign to Clusters (deprecated) module, which has been deprecated but is still available for use in existing experiments.  

+ [Score Matchbox Recommender](score-matchbox-recommender.md): Scores predictions for a dataset by using the Matchbox recommender.  

    Use this module if you want to generate recommendations, find related items or users, or predict ratings.  

+ [Score Model](score-model.md): Scores predictions for a trained classification or regression model.

    Use this module for all other regression and classification models, as well as some anomaly detection models.  

### Related tasks

+ Special scoring modules are provided for Vowpal Wabbit. See [Text Analytics](text-analytics.md). 
+ You can score for special classes of images on pretrained models by using the [OpenCV Library](opencv-library-modules.md).  
+ The [Time Series Anomaly Detection](https://msdn.microsoft.com/library/mt775197.aspx) module generates scores that represent potential deviations from a trend. 

## Examples

These examples in the [Azure AI Gallery](https://gallery.azure.ai) demonstrate the process of scoring, from basic to advanced scenarios:

+ [Binary Classification for Direct Marketing](https://gallery.azure.ai/Experiment/Binary-Classification-Direct-marketing-2): Demonstrates the basic workflow for scoring, in a scenario where the predicted value is customer response to a marketing campaign.

+ [Predict Book Reviews](https://gallery.azure.ai/Experiment/Predict-Book-Reviews-1): Scoring on text data. Uses a logistic regression model.

+ [Learning with Counts](https://gallery.azure.ai/Experiment/Learning-with-Counts-Binary-Classification-2): Shows you how to use count-based featurization for making predictions.

+ [No-code batch scoring with Logic Apps and Machine Learning](https://gallery.azure.ai/Tutorial/No-code-Batch-Scoring-1): Illustrates the end-to-end process of training and scoring, automated with the Logic Apps feature of Azure App Service.

The following articles provide real-world examples of how you can use a machine learning model for scoring:

- [Develop a predictive solution](/azure/machine-learning/classic/tutorial-part1-credit-risk)  
  
- [Survival analysis](https://azure.microsoft.com/documentation/articles/machine-learning-r-csharp-survival-analysis/)  
  
- [Anomaly detection](https://azure.microsoft.com/documentation/articles/machine-learning-apps-anomaly-detection/)  
  
- [Lexicon-based sentiment analysis](https://azure.microsoft.com/documentation/articles/machine-learning-r-csharp-lexicon-based-sentiment-analysis/)  

## See also  

- [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
- [Train](machine-learning-train.md)   
- [Score](machine-learning-score.md)   
- [Evaluate](machine-learning-evaluate.md)
