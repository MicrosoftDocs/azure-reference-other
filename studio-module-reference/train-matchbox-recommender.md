---
title: "ML Studio (classic): Train Matchbox Recommender - Azure"
description: Learn how to use the Train Matchbox Recommender module to train a recommendation model. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Train Matchbox Recommender
*Trains a Bayesian recommender using the Matchbox algorithm*  
  
 Category: [Machine Learning / Train](machine-learning-train.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  
 
This article describes how to use the **Train Matchbox Recommender** module in Machine Learning Studio (classic), to train a recommendation model. 

The recommendation algorithm in Machine Learning is based on the **Matchbox** model, developed by [Microsoft Research](https://research.microsoft.com/projects/). To download a paper that describes the algorithm in detail, click this link on the [Microsoft Research site](https://research.microsoft.com/pubs/79460/www09.pdf).  

The **Train Matchbox Recommender** module reads a dataset of user-item-rating triples and, optionally, some user and item features. It returns a trained Matchbox recommender.  You can then use the trained model to generate recommendations, find related users, or find related items, by using the [Score Matchbox Recommender](score-matchbox-recommender.md) module.  

> [!TIP]
> Learn everything you need to know about the end-to-end experience of building a recommendation system in this tutorial from the .NET development team. Includes sample code and discussion of how to call Machine Learning from an application.
> 
> [Building recommendation engine for .NET applications using Machine Learning](https://blogs.msdn.microsoft.com/dotnet/2017/06/26/dot-net-recommendation-system-for-net-applications-using-azure-machine-learning/)
  
## More about recommendation models and the Matchbox recommender  
 
The main aim of a recommendation system is to recommend one or more *items* to *users* of the system. Examples of an item could be a movie, restaurant, book, or song. A user could be a person, group of persons, or other entity with item preferences.  
  
There are two principal approaches to recommender systems. 

+ The first is the **content-based** approach, which makes use of features for both users and items. Users may be described by properties such as age and gender, and items may be described by properties such as author and manufacturer. Typical examples of content-based recommendation systems can be found on social matchmaking sites. 
+ The second approach is **collaborative filtering**, which uses only identifiers of the users and the items and obtains implicit information about these entities from a (sparse) matrix of ratings given by the users to the items. We can learn about a user from the items they have rated and from other users who have rated the same items.  

The Matchbox recommender combines these approaches, using collaborative filtering with a content-based approach. It is therefore considered a **hybrid recommender**. 

How this works: When a user is relatively new to the system, predictions are improved by making use of the feature information about the user, thus addressing the well-known "cold-start" problem. However, once you have collected a sufficient number of ratings from a particular user, it is possible to make fully personalized predictions for them based on their specific ratings rather than on their features alone. Hence, there is a smooth transition from content-based recommendations to recommendations based on collaborative filtering. Even if user or item features are not available, Matchbox will still work in its collaborative filtering mode.  

More details on the Matchbox recommender and its underlying probabilistic algorithm can be found in the relevant research paper: [Matchbox: Large Scale Bayesian Recommendations Recommendations](https://research.microsoft.com/pubs/79460/www09.pdf).  In addition, the [Machine Learning Blog](https://blogs.technet.com/b/machinelearning/) has an article titled [Recommendations Everywhere](https://blogs.technet.com/b/machinelearning/archive/2014/07/09/recommendations-everywhere.aspx) that provides a high-level introduction to recommendation algorithms.  
  
## How to configure Train Matchbox Recommender  

+ [Prepare the training data](#bkmk_prepData)
+ [Train the model](#bkmk_Train)

### <a name="bkmk_prepData"></a> Prepare data

Before trying to use the module, it is essential that your data be in the format expected by the recommendation model. A training data set of **user-item-rating triples** is required, but you can also include user features and item features (if available), in separate datasets.

To divide source data into training and testing datasets, use the **Recommender Split** option in the [Split Data](split-data.md) module.

#### Required dataset of user-item-ratings

It is very important that the input data used for training contain the right type of data in the correct format: 

+ The first column must contain user identifiers.
+ The second column must contain item identifiers.
+ The third column contains the rating for the user-item pair. Rating values must be either numeric or categorical.  

During training, the rating values cannot all be the same. Moreover, if numeric, the difference between the minimum and the maximum rating values must be less than 100, and ideally not greater than 20.  

The **Restaurant ratings** dataset in Machine Learning Studio (classic) (click **Saved Datasets** and then **Samples**) demonstrates the expected format:

|userID|placeID|rating|  
|------------|-------------|------------|  
|U1077|135085|2|  
|U1077|135038|2|  

From this sample, you can see that a single user has rated two separate restaurants. 

#### User features dataset (optional)

The dataset of **user features** must contain identifiers for users, and use the same identifiers that were provided in the first column of the users-items-ratings dataset. The remaining columns can contain any number of features that describe the users.  
  
For an example, see the **Restaurant customer** dataset in Machine Learning Studio (classic). A typical set of user features looks like this:  

|userID|ambience|Dress_preference|transport|smoker|  
|------------|--------------|-----------------------|---------------|------------|  
|U1004|family|informal|On foot|FALSE|  
|U1005|friends|No preference|Car owner|TRUE|  

#### Item features dataset (optional)

The dataset of item features must contain item identifiers in its first column. The remaining columns can contain any number of descriptive features for the items.  
  
For an example, see the Restaurant feature data dataset, provided in Machine Learning Studio (classic) (click **Saved Datasets** and then **Samples**). A typical set of item features (in this case, the item is a restaurant) might look like this:  

|placeID|alcohol|Smoking_area|price|Rambience|  
|-------------|-------------|-------------------|-----------|---------------|  
|135106|Wine-Beer|none|low|family|  
|132667|No_Alcohol_Served|permitted|medium|casual|  

### <a name="bkmk_Train"></a> Train the model

1.  Add the **Train Matchbox Recommender** module to your experiment in Studio (classic), and connect it to the training data.  
  
2. If you have a separate dataset of either user features and/or item features, connect them to the **Train Matchbox Recommender** module.  
  
    - **User features dataset**: Connect the dataset that describes users to the second input.

    - **Item features dataset**: Connect the dataset that describes items to the third input.  
  
3.  For **Number of training batches**, type the number of batches for dividing the data during training.  
  
     Based on this value, the dataset of user-item-rating triples is divided into multiple parts or batches during training.
     
     Because **Train Matchbox Recommender** runs batches in parallel, we recommend that the number of training batches be set to the number of available cores, if the entire training data fits into memory. Otherwise, the number of training batches should be set to the lowest multiple of the number of available cores for which the training data does fit into memory.
  
     By default, the training data is split into four (4) batches. Only the dataset of user-item-rating triples is split. User or item features are not split because features do not need to be split.
  
5.  For **Number of traits**, type the number of latent traits that should be learned for each user and item.  
  
     The higher the number of traits, the more accurate the predictions will typically be; however, training will be slower. The number of traits usually lies in the range 2 - 20.  
  
6.  For **Number of recommendation algorithm iterations**, indicate how many times the algorithm should process the input data.  
  
     The Matchbox recommender is trained using a message-passing algorithm that can iterate multiple times over the input data. The higher this number, the more accurate the predictions; however, training is slower. Usually, the number of iterations is in the range 1 - 10.  
  
7.  Run the experiment, or select just the **Train Matchbox Recommender** module and select **Run selected**.  
  
## Examples

For examples of how recommendation models are used in Machine Learning, see these sample experiments in the [Azure AI Gallery](https://gallery.azure.ai/):  
  
- [Movie recommender sample](https://go.microsoft.com/fwlink/?LinkId=525276): Demonstrates how to train, evaluate, and score using a recommendation model.  
  
## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Usage tips

-   If a feature column has missing values, the mode of the non-missing values will be used as replacement for the missing values.  
  
-   All user and item features are re-scaled to have unit length, so that their maximum absolute value is 1.  No translation is applied to the feature values, so as to maintain their sparsity.  

### Restrictions

Online update (or continuous training) of a recommendation model is not currently supported in Machine Learning. If you want to capture user responses to recommendations and use those for improving the model, we suggest retraining the complete model periodically. Incremental training is not possible, but you can apply a sliding window to the training data to ensure that data volume is minimized while using the most recent data.

### Estimating recommender memory usage  

Currently, the lower bound of Matchbox's memory footprint is `16 * N\(4\T + 2\R)` bytes, where _N_ refers to the number of user-item-rating triples in the training dataset, _T_ to the number of latent traits, and _R_ to the difference between the minimum and maximum rating (in the training dataset).  
  
The size of a serialized Matchbox recommender model is approximately `16 * T\(U\R + I + X + Y)` bytes, where _U_ refers to the number of users, _I_ to the number of items, _X_ to the number of user features, and _Y_ to the number of item features.
  
##  Expected inputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Training dataset of user-item-rating triples|[Data Table](data-table.md)|Ratings of items by users, expressed as a triple (User, Item, Rating)|  
|Training dataset of user features|[Data Table](data-table.md)|Dataset containing features that describe users (optional)|  
|Training dataset of item features|[Data Table](data-table.md)|Dataset containing features that describe items (optional)|  

##  Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Number of traits|>=0|Integer|10|Specify the number of traits to use with the recommender (optional)|  
|Number of recommendation algorithm iterations|>=1|Integer|5|Specify the maximum number of iterations to perform while training the recommendation model (optional)|  
|Number of training batches|>=1|Integer|4|Specify the number of training batches to use with the recommender (optional)|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained Matchbox recommender|[ILearner interface](ilearner-interface.md)|Trained Matchbox recommender|  
  
##  Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0022](errors/error-0022.md)|Exception occurs if number of selected columns in input dataset does not equal to the expected number.|  
|[Error 0036](errors/error-0036.md)|Exception occurs if multiple feature vectors were provided for a given user or item.|  
|[Error 0018](errors/error-0018.md)|Exception occurs if input dataset is not valid.|  
|[Error 0035](errors/error-0035.md)|Exception occurs if no features were provided for a given user or item.|  
|[Error 0034](errors/error-0034.md)|Exception occurs if more than one rating exists for a given user-item pair.|  
|[Error 0053](errors/error-0053.md)|Exception occurs in the case when there are no user features or items for Matchbox recommendations.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  


## See also  
 [Cross-Validate Model](cross-validate-model.md)   
 [Evaluate Recommender](evaluate-recommender.md)   
 [Train](machine-learning-train.md)   
 [Score Matchbox Recommender](score-matchbox-recommender.md)
