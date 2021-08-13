---
title: "ML Studio (classic): Score Matchbox Recommender - Azure"
description: Learn  how to use the Score Matchbox Recommender module to create predictions from a trained recommendation model, based on the Matchbox algorithm from Microsoft Research.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Score Matchbox Recommender

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Scores predictions for a dataset using the Matchbox recommender*

Category: [Machine Learning / Score](machine-learning-score.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Score Matchbox Recommender** module in Machine Learning Studio (classic), to create predictions based on a trained recommendation model, based on the Matchbox algorithm from Microsoft Research.

The Matchbox recommender can generate four different kinds of predictions:

- [Predict ratings for a given user and item](#RatingPredictionOptions)

- [Recommend items to a given user](#ItemRecommendationOptions)

- [Find users related to a given user](#RelatedUsers)

- [Find items related to a given item](#RelatedItemsOptions)

When creating the latter three kinds of predictions, you can operate in either *production mode* or *evaluation mode*.

- **Production mode** considers all users or items, and is typically used in a web service.

    You can create scores for new users, not just users seen during training. For more information, see [this section](#bkmk_NewUsers). 

- **Evaluation mode** operates on a reduced set of users or items that can be evaluated, and is typically used during experimentation.

> [!TIP]
> Learn everything you need to know about the end-to-end experience of building a recommendation system in this tutorial from the .NET development team. Includes sample code and discussion of how to call Machine Learning from an application.
> 
> [Building recommendation engine for .NET applications using Machine Learning](https://blogs.msdn.microsoft.com/dotnet/2017/06/26/dot-net-recommendation-system-for-net-applications-using-azure-machine-learning/)

## More about the Matchbox recommender

The goal of creating a recommendation system is to recommend one or more "items" to "users" of the system. Examples of an item could be a movie, restaurant, book, or song. A user could be a person, group of persons, or other entity with item preferences.

There are two principal approaches to recommender systems. The first is the **content-based** approach, which makes use of features for both users and items. Users may be described by properties such as age and gender, and items may be described by properties such as author and manufacturer. Typical examples of content-based recommendation systems can be found on social matchmaking sites. The second approach is **collaborative filtering**, which uses only identifiers of the users and the items and obtains implicit information about these entities from a (sparse) matrix of ratings given by the users to the items.  We can learn about a user from the items they have rated and from other users who have rated the same items.

The Matchbox recommender combines collaborative filtering with a content-based approach. It is therefore considered a **hybrid recommender**. When a user is relatively new to the system, predictions are improved by making use of the feature information about the user, thus addressing the well-known "cold-start" problem. However, once there are a sufficient number of ratings from a particular user, it is possible to make fully personalized predictions for them based on their specific ratings rather than on their features alone. Hence, there is a smooth transition from content-based recommendations to recommendations based on collaborative filtering. Even when user or item features are not available, Matchbox still works in its collaborative filtering mode.

More details on the Matchbox recommender and its underlying probabilistic algorithm can be found in the relevant research paper:  

+ [Matchbox: Large Scale Bayesian Recommendations](https://www.microsoft.com/research/publication/matchbox-large-scale-bayesian-recommendations/#)

## Examples

 For examples of how to create scores from a recommendation engine, see the [Azure AI Gallery](https://gallery.azure.ai/).  

- [Recommender: Movie recommendation](https://gallery.azure.ai/Experiment/Recommender-Movie-recommendation-3): This sample demonstrates item recommendation, where the items are movies, and also demonstrates rating prediction.

- [Recommender: Restaurant ratings](https://gallery.azure.ai/Experiment/Recommender-Restaurant-ratings-2): This sample demonstrates item recommendations using both item features and user features.

+ [Recommendations Everywhere](https://blogs.technet.com/b/machinelearning/archive/2014/07/09/recommendations-everywhere.aspx): This blog post provides a high-level introduction to recommender systems with lots of visual aids. 

## How to configure Score Matchbox Recommender

This module supports different types of recommendations, each with different requirements. Click the link for the type of data you have and the type of recommendation you want to create.

+ [Predict ratings](#RatingPredictionOptions)
+ [Recommend items](#ItemRecommendationOptions)
+ [Find related users](#RelatedUsers)
+ [Find related items](#RelatedItemsOptions)

###  <a name="RatingPredictionOptions"></a> Predict ratings

When you predict ratings, the model calculates how a given user will react to a particular item, given the training data. Therefore, the input data for scoring must provide both a user and the item to rate.

1. Add a trained recommendation model to your experiment, and connect it to **Trained Matchbox recommender**.  You must create the model by using [Train Matchbox Recommender](train-matchbox-recommender.md).

2. **Recommender prediction kind**: Select **Rating Prediction**. No further parameters are required.

3. Add the data for which you wish to make predictions, and connect it to **Dataset to score**.

    To predict ratings, the input dataset must contain user-item pairs.

    The dataset can contain an optional third column of ratings for the user-item pair in the first and second columns, but the third column will be ignored during prediction.

4.  (Optional). If you have a dataset of user features, connect it to **User features**.

    The dataset of user features should contain the user identifier in the first column. The remaining columns should contain values that characterize the users, such as their gender, preferences, location, etc.
  
    Features of users who have rated items are ignored by **Score Matchbox Recommender**, because they have already been learned during training. Therefore,  filter your dataset in advance to include only *cold-start users*, or users who have not rated any items.

    > [!WARNING]
    > If the model was trained without using user features, you cannot introduce user features during scoring.

5. If you have a dataset of item features, you can connect it to **Item features**.

    The item features dataset must contain an item identifier in the first column. The remaining columns should contain values that characterize the items.

    Features of rated items are ignored by **Score Matchbox Recommender** as they have already been learned during training. Therefore, restrict your scoring dataset to *cold-start items*, or items that have not been rated by any users.

    > [!WARNING]
    > If the model was trained without using item features, you cannot introduce item features during scoring.

6. Use the optional fifth input port, named **Training Dataset**, to remove items that have already been rated from the prediction results.

    To apply this filter, connect the original training dataset to the input port.

7. Run the experiment.

### Results for rating predictions 

The output dataset contains three columns, containing the user, the item, and the predicted rating for each input user and item.

Additionally, the following changes are applied during scoring:

-  Missing values in a user or item feature columns are automatically replaced with the **mode** of its non-missing training set values.

- All user and item features are rescaled by the corresponding maximum absolute values seen in training.

- No translation is applied to the feature values, to maintain their sparsity.

- String-valued features are converted into a set of binary-valued indicator features.

###  <a name="ItemRecommendationOptions"></a> Recommend 

To recommend items for users, you provide a list of users and items as input. From this data, the model uses its knowledge about existing items and users to generate a list of items with probable appeal to each user. You can customize the number of recommendations returned, and set a threshold for the number of previous recommendations that are required in order to generate a recommendation.

1. Add a trained recommendation model to your experiment, and connect it to **Trained Matchbox recommender**.  You must create the model by using [Train Matchbox Recommender](train-matchbox-recommender.md).

2. To recommend items for a given list of users, set **Recommender prediction kind** to **Item Recommendation**.

3. **Recommended item selection**: Indicate whether you are using the scoring module in production or for model evaluation, by choosing one of these values:

    - **From Rated Items (for model evaluation)**: Select this option if you are developing or testing a model. This option enables **evaluation mode**, and the module makes recommendations only from those items in the input dataset that have been rated.

    - **From All Items**: Select this option if you are setting up an experiment to use in a Web service or production.  This option enables **production mode**, and the module makes recommendations from all items seen during training.

4. Add the dataset for which you want to make predictions, and connect it to **Dataset to score**.

    - If you choose the option, **From All Items**, the input dataset should consist of one and only one column, containing the identifiers of users for which to make recommendations.

        If the dataset contains more than one column, an error is raised. Use the [Select Columns in Dataset](select-columns-in-dataset.md) module to remove extra columns from the input dataset.  

    - If you choose the option, **From Rated Items (for model evaluation)**, the input dataset should consist of **user-item pairs**. The first column should contain the **user** identifier. The second column should contain the corresponding **item** identifiers.

        The dataset can include a third column of user-item ratings, but this column is ignored.

5. (Optional). If you have a dataset of **user features**, connect it to **User features**.

    The first column in the user features dataset should contain the user identifier. The remaining columns should contain values that characterize the user, such as their gender, preferences, location, etc.

    Features of users who have rated items are ignored by **Score Matchbox Recommender**, because these features have already been learned during training. Therefore, you can filter your dataset in advance to include only *cold-start users*, or users who have not rated any items.

    > [!WARNING]
    >  If the model was trained without using user features, you cannot use apply features during scoring.

6. (Optional) If you have a dataset of **item features**, you can connect it to **Item features**.

    The first column in the item features dataset must contain the item identifier. The remaining columns should contain values that characterize the items.

    Features of rated items are ignored by **Score Matchbox Recommender**, because these features have already been learned during training. Therefore, you can restrict your scoring dataset to *cold-start items*, or items that have not been rated by any users.

    > [!WARNING]
    >  If the model was trained without using item features, do not use item features when scoring.  

7. **Maximum number of items to recommend to a user**: Type the number of items to return for each user. By default, 5 items are recommended.

8. **Minimum size of the recommendation pool per user**: Type  a value that indicates how many prior recommendations are required.  By default, this parameter is set to 2, meaning the item must have been recommended by at least two other users.

    This option should be used only if you are scoring in evaluation mode. The option is not available if you select **From All Items**.

9. Run the experiment.
### Results of item recommendation

The scored dataset returned by **Score Matchbox Recommender** lists the recommended items for each user.

- The first column contains the user identifiers.
- A number of additional columns are generated, depending on the value you set for **Maximum number of items to recommend to a user**. Each column contains a recommended item (by identifier). The recommendations are ordered by user-item affinity, with the item with highest affinity put in column, **Item 1**.

> [!WARNING]
> This scored dataset cannot be evaluated using the [Evaluate Recommender](evaluate-recommender.md) module.

### <a name="RelatedUsers"></a> Find related users

The option to find related users is useful if you are recommending "people like you", or if you are creating a pool of similar users on which to base other types of predictions.

1. Add a trained recommendation model to your experiment, and connect it to **Trained Matchbox recommender**.  You must create the model by using [Train Matchbox Recommender](train-matchbox-recommender.md).

2. **Recommender prediction kind**: Select **Related Users**.

3. **Related user selection**: Indicate how you will be using the model for scoring, and specify the pool of users on which to base the scores as follows:

    - **From All Users**: Select this option if you are setting up an experiment to use in a Web service or production, or if you need to make predictions for new users.  This option enables **production mode**, and the module bases its recommendation only on users seen during training.

    - **From Users That Rated Items (for model evaluation)**: Select this option if you are developing or testing a model. This option enables **evaluation mode**, and the model bases its recommendations on the users in the test set who have rated some common items.

4. Connect a dataset that contains the users for which to generate predictions. The format for this dataset depends on whether you are using the scoring module in production mode or evaluation mode.

    - Production mode, using **From All Items**
  
        The dataset to score must consist of **users** for which you wish to find related users. The first and only column should contain the user identifiers. If other columns are included, an error is raised. Use the [Select Columns in Dataset](select-columns-in-dataset.md) module to remove unnecessary columns.  

    - Evaluation mode, using **From Rated Items (for model evaluation)**

        The dataset to score should consist of 2-3 columns, containing user-item pairs. The first column should contain user identifiers. The second column should contain item identifiers. The dataset can include a third column of ratings (by the user in column 1 for the item in column 2), but the ratings column will be ignored.

5. **Maximum number of related users to find for a user**:   Type a number that indicates the maximum number of predictions you want for each user. The default is 5, meaning that at most five related users can be returned, but in some cases there might be fewer than 5.

6. In evaluation mode (**From Users That Rated Items**), configure these additional parameters:

    - **Minimum number of items that the query user and the related user must have rated in common**: This value sets a threshold for recommendations. The number that you type represents the minimum number of items that your target user and the potential related user must have rated. The default value is 2, meaning that, at minimum, two items must have been rated by both users.

    - **Minimum size of the related user pool for a single user**: This value controls the minimum number of similar users needed to create a recommendation. By default, the value is 2, meaning that if you have as few as two users who are related by virtue of rating the same items, you can consider them related and generate a recommendation.

7. (Optional). If you have a dataset of user features, connect it to **User features**.

    The first column in the user features dataset should contain the user identifier. The remaining columns should contain values that characterize the user, such as gender, preferences, location, etc.

    Features of users who have rated items are ignored by **Score Matchbox Recommender** as these features have already been learned during training. Therefore, filter your dataset in advance to include only *cold-start users*, or users who have not rated any items.

    > [!WARNING]
    > If the model was trained without using user features, you cannot apply user features during scoring.

8. (Optional) If you have a dataset of item features, connect it to **Item features**.

    The first column in the item features dataset must contain the item identifier. The remaining columns should contain values that characterize the items.  

    Features of rated items are ignored by **Score Matchbox Recommender** as these features have already been learned during training. Therefore, you can restrict your scoring dataset to *cold-start items*, or items which have not been rated by any users.

    > [!WARNING]
    >  If the model was trained without using item features, do not use item features when scoring.

9. Run the experiment.

### Results for related users

The scored dataset returned by **Score Matchbox Recommender** lists the users who are related to each users in the input dataset.

For each user specified in the input dataset, the result dataset contains a set of related users.

- The first column contains the identifier of the target user (the user provided as input).
- Additional columns are generated containing the identifiers of related users. The number of additional columns depends on the value you set in the option, **Maximum number of related users to find for a user**. 

    Related users are ordered by the strength of the relation to the target user, with the most strongly related user in the column, **Related User 1**.

### <a name="RelatedItemsOptions"></a> Find related items

By predicting related items, you can generate recommendations for users based on items that have already been rated.

1. Add a trained recommendation model to your experiment, and connect it to  **Trained Matchbox recommender**. You must create the model by using [Train Matchbox Recommender](train-matchbox-recommender.md).

2. **Recommender prediction kind**: Select **Related Items**. 

3. Connect a dataset that contains the users for which to generate predictions.  The format for this dataset depends on whether you are using the scoring module in production mode or evaluation mode.

    - Production mode, using **From All Items**
  
        The dataset to score must consist of items for which you wish to find related users.
  
        The first and only column should contain the item identifiers. If other columns are included, an error is raised. Use the [Select Columns in Dataset](select-columns-in-dataset.md) module to remove unnecessary columns.
  
    - Evaluation mode, using **From Rated Items (for model evaluation)**
  
        The dataset to score should consist of 2-3 columns, containing user-item pairs. The first column should contain user identifiers. The second column should contain item identifiers.
  
        The dataset can include a third column of ratings (by the user in column 1 for the item in column 2), but the ratings column are ignored.  

4. **Maximum number of related items to find for an item**>:  Type a number that indicates the maximum number of predictions you want for each item.

    The  default is 5, meaning that at most five related items can be returned, but there might be fewer than 5.

5. If you are using evaluation mode (**From Users That Rated Items**), configure these additional parameters:

    - **Minimum number of items that the query item and the related item must have been rated by in common**: This value sets a threshold for recommendations. The number that you type represents the minimum number of items that have been rated by the target user and some related user. The default value is 2, meaning that, at minimum, two items must have been rated by the target user and the related user.

    - **Minimum size of the related item pool for a single item**: This value controls the minimum number of similar items needed to create a recommendation. By default, the value is 2, meaning that, if you have as few as two items that are related by virtue of having been rated by the same users, you can consider them related and generate a recommendation.

6. (Optional). If you have a dataset of user features, connect it to **User features**.

    The first column in the user features dataset should contain the user identifier. The remaining columns should contain values that characterize the user, such as their gender, preferences, location, etc.

    Features of users who have rated items are ignored by **Score Matchbox Recommender**, because these features have already been learned during training. Therefore, you can filter your dataset in advance to include only *cold-start users*, or users who have not rated any items.

    > [!WARNING]
    > If the model was trained without using user features, you cannot apply user features during scoring.

7. (Optional) If you have a dataset of item features, you can connect it to **Item features**.

    The first column in the item features dataset must contain the item identifier. The remaining columns should contain values that characterize the item.

    Features of rated items are ignored by **Score Matchbox Recommender**, because these features have already been learned during training. Therefore, you can restrict your scoring dataset to *cold-start items*, or items which have not been rated by any users.

    > [!WARNING]
    > If the model was trained without using item features, do not use item features when scoring.

8. (Optional) In a predictive experiment, you can use a fifth input port, named **Training Dataset**, to remove existing users that were included in the model training data from the prediction results.

    To apply this filter, connect the original training dataset to the input port.

9. Run the experiment.

### Results for related items

The scored dataset returned by **Score Matchbox Recommender** lists the related items for each item in the input dataset.  

- The first column contains the identifier of the target item (the item provided as input).  
-  Additional columns are generated containing the identifiers of related items. The number of additional columns depends on the value you set in the option, **Maximum number of related items to find for an item**.

    The related items are ordered by the strength of the relation to the target item, with the most strongly related item in the column, **Related Item 1**.  

##  Technical notes

This section contains answers to some common questions about using the recommender to create predictions.  

###  <a name="bkmk_NewUsers"></a> Cold-start users and recommendations

Typically, to create recommendations, the **Score Matchbox Recommender** module requires the same inputs that you used when training the model, including a user ID. That is because the algorithm needs to know if it has learned something about this user during training. 

However, for new users, you might not have a user ID, only some user features such as age, gender, and so forth.

You can still create recommendations for users who are new to your system, by handling them as *cold-start users*. For such users, the recommendation algorithm does not use past history or previous ratings, only user features.

For purposes of prediction, a cold-start user is defined as a user with an ID that has not been used for training. To ensure that IDs do not match IDs used in training, you can create new identifiers. For example, you might generate random IDs within a specified range, or allocate a series of IDs in advance for cold-start users.

However, if you do not have any collaborative filtering data, such as a vector of user features, you are better of using a classification or regression learner.

###  Production use of the Matchbox recommender

If you have experimented with the Matchbox recommender and then move the model to production, be aware of these key differences when using the recommender in evaluation mode and in production mode:

- Evaluation, by definition, requires predictions that can be verified against the *ground truth* in a test set. Therefore, when you evaluate the recommender, it must predict only items that have been rated in the test set. This necessarily restricts the possible values that are predicted.

    However, when you operationalize the model, you typically change the prediction mode to make recommendations based on all possible items, in order to get the best predictions. For many of these predictions, there is no corresponding ground truth, so the accuracy of the recommendation cannot be verified in the same way as during experimentation.

- If you do not provide a user ID in production, and provide only a feature vector, you might get as response a list of all recommendations for all possible users. Be sure to provide a user ID.

    To limit the number of recommendations that are returned, you can also specify the maximum number of items returned per user.

- It is not possible to generate predictions only for items that have not previously been rated. This is by design.

    The reason is that, in order to recommend only the items that have not been rated, the recommender would need to store the entire training data set with the model, which would increase your use of storage.

    If you want to recommend only items that have not been seen by your user, you can request more items to recommend, and then manually filter out the rated ones.

### Continuous update of the recommender

Online updating (or continuous training) of a recommendation model is not currently supported in Machine Learning. If you want to capture user responses to recommendations and use those for improving the model, we suggest retraining the complete model periodically. Incremental training is not possible, but you can apply a sliding window to the training data to ensure that data volume is minimized while using the most recent data.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained Matchbox recommender|[ILearner](ilearner-interface.md)|Trained Matchbox recommender|  
|Dataset to score|[Data Table](data-table.md)|Dataset to score|  
|User features|[Data Table](data-table.md)|Dataset containing features that describe users<br /><br /> This data is optional|  
|Item features|[Data Table](data-table.md)|Dataset containing features that describe items<br /><br /> This data is optional|  

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Recommender prediction kind|List|Prediction kind|Item Recommendation|Specify the type of prediction the recommender should output|  
|Recommended item selection|List|Item selection|From Rated Items (for model evaluation)|Select the set of items to make recommendations from|  
|Related user selection|List|User selection|From Users That Rated Items (for model evaluation)|Select the set of users to use when finding related items|  
|Related item selection|List|[Item selection|From Rated Items (for model evaluation)|Select the set of items to use when finding related items|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Scored dataset|[Data Table](data-table.md)|Scored dataset|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0022](errors/error-0022.md)|Exception occurs if number of selected columns in input dataset does not equal to the expected number.|  
|[Error 0036](errors/error-0036.md)|Exception occurs if multiple feature vectors were provided for a given user or item.|  
|[Error 0013](errors/error-0013.md)|Exception occurs if passed to module learner has invalid type.|  
|[Error 0035](errors/error-0035.md)|Exception occurs if no features were provided for a given user or item.|  
|[Error 0053](errors/error-0053.md)|Exception occurs in the case when there are no user features or items for Matchbox recommendations.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Train Matchbox Recommender](train-matchbox-recommender.md)   
 [Evaluate Recommender](evaluate-recommender.md)   
 [Score](machine-learning-score.md)   
