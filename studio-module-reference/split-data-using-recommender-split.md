---
title: "ML Studio (classic): Split Data using Recommender Split - Azure"
description: Learn how to prepare training and testing datasets for use with a recommendation model with the Recommender Split option in the Split Data module
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Split Data using Recommender Split

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes how to use the **Recommender Split** option in the [Split Data](split-data.md) module of Machine Learning Studio (classic). This option is useful when you need to prepare training and testing datasets for use with a recommendation model. Not only do these models require a specific format, but it can be very difficult to divide up ratings, users, and items in a balanced way without special tools.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

The **Recommender split** option makes this process easier by asking for the type of recommendation model you are working with: for example, are you recommending items, suggesting a rating, or finding related users? It then divides the dataset by criteria you specify, such as how to handle cold users or cold items.

When you split the datasets, the module returns two datasets, one intended for training and the other for testing or model evaluation.  If the input dataset contains any extra data per instance (such as ratings), it is preserved in the output.

For general information about data partitioning for machine learning experiments, see 

## Related tasks

Other options in the **Split Data** module support different ways to divide the data:

+ [Split data using regular expressions](split-data-using-regular-expression.md): Apply a regular expression to  a single text column, and divide the dataset based on the results 

+ [Split recommender datasets](split-data-using-recommender-split.md): Divide datasets t+ [Split data using relative expressions](split-data-using-relative-expression.md): Apply an expression to numeric data. 

+ [Split by percentage of dataset](split-data-using-split-rows.md)

##  Divide a dataset used by a recommendation model

The **Recommender Split** option is provided specifically for data used to train recommendation systems. 

Before you use this option, make sure that your data is in a compatible format. The recommender splitter works under the assumption the dataset consists only of **user-item pairs** or **user-item-rating** triples. For details, see [Input data requirements](#bkmk_Data) in this article.

1. Add the [Split Data](split-data.md) module to your experiment, and connect it as input to the dataset you want to split.

2. For **Splitting mode**, select **Recommender split**.

3. Set the following options to control how values are divided. Specify a percentage represented as a number between 0 and 1.

    + **Fraction of training only users**: Specify the fraction of users that should be assigned only to the training data set. This means the rows would never be used to test the model.
  
    + **Fraction of test user ratings for training**: Specify that some portion of the user ratings you have collected can be used for training.  
  
    + **Fraction of cold users**: Cold users are users that the system has not previously encountered. Typically, because the system has no information on these users, they are valuable for training, but predictions might be less accurate.
  
    + **Fraction of cold items**: Cold items are items that the system has not previously encountered. Because the system has no information about these items, they are valuable for training, but predictions might be less accurate.
  
    + **Fraction of ignored users**: This option allows the recommender to ignore some users, which lets you train the model on a subset of data. This might be useful for performance reasons. You specify the percentage of users that should be ignored.
  
    + **Fraction of ignored items**: The recommender splitter can ignore some items and 
    train the model on a subset of data. This might be useful for performance reasons. You specify the percentage of items to ignore.  

9. **Remove occasionally produced cold items**: This option is typically set to zero, to ensure that all entities in the test set are included in the training set.

    An item is said to be "occasionally cold" if it is covered only by the test set and it wasn't explicitly chosen as cold. Such items can be produced by steps (4) and (6) in the algorithm described in the [How Recommender Data is Split](#algorithm) section.

10. **Random seed for recommender**: Specify a seed value if you want to split the data the same way every time. Otherwise, by default the input data is randomly split, using a system clock value as the seed.

11. Run the experiment.

##  Examples

For examples of how to divide a set of ratings and features used for training or testing a recommendation model, we recommend that you review the walkthrough provided with this sample experiment in the [Azure AI Gallery](https://gallery.azure.ai/): [Movie Recommendation](https://gallery.azure.ai/Experiment/3a02931f94114f47b4512dd9179b515e?share=1)  

##  Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### <a name="bkmk_Data"></a> Requirements for input data

The recommender splitter works under the assumption the dataset consists only of user-item pairs or user-item-rating triples. Therefore, the [Split Data](split-data.md) module cannot work on datasets that have more than three columns, to avoid confusion with feature-type data. 

If your dataset contains too many columns, you might get this error:  

*Error 0022: Number of selected columns in input dataset does not equal to x*  

As a workaround, you can use [Select Columns in Dataset](select-columns-in-dataset.md) to remove some columns. You can always add the columns back later, by using the [Add Columns](add-columns.md) module. 

Alternatively, if your dataset has many features that you want to use in the model, divide the dataset using a different option, and train the model using [Train Model](train-model.md) rather than [Train Matchbox Recommender](train-matchbox-recommender.md). 

For detailed information about the supported data formats, see [Train Matchbox Recommender](train-matchbox-recommender.md). 

### Usage tips

-   An error is raised if the dataset does not contain at least two rows.    
  
-   If you specify a number as a percentage, or if you use a string that contains the "%" character, the value is interpreted as a percentage.
  
     All percentage values must be within the range (0, 100), not including the values 0 and 100.  
  
-   If you specify a number or percentage that is a floating point number less than one, and you do not use the percent symbol (%), the number is interpreted as a proportional value.

###  <a name="algorithm"></a> Implementation details 

The following algorithm is used when splitting data into training and test sets for use with a recommendation model:  

1.  The requested fraction of ignored items is removed with all associated observations.  
  
2.  The requested fraction of cold items is moved to the test set with all associated observations.  
  
3.  The requested fraction of ignored users that remain after the first two steps is removed with all associated observations.  
  
4.  The requested fraction of cold users that remain after the first two steps is moved to the test set with all associated observations.  
  
5.  The requested fraction of training-only users that remain after the first two steps is moved to the training set with all associated observations.  
  
6.  For each user that remains after all the previous steps, the requested fraction of test user ratings for training is moved to the training set, and the remainder is moved to the test set.  
  
     At least one observation is always moved to the training set for each user.  
  
7.  If requested, instances that are associated with the occasionally produced cold items can be removed from the test set.  
  
     An item is said to be "occasionally cold" if it is covered only by the test set, and it wasn't explicitly chosen as cold. Such items can be produced by steps (4) and (6).  
  
     The anticipated use of this option is that the requested number of cold users and items is set to zero. This ensures that all entities in the test set are included in the training set.  

## See also

[Split Data](split-data.md)
[Partition and Split](partition-and-sample.md)
