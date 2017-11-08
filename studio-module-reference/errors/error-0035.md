---
title: "Error 0035 | Microsoft Docs"
ms.custom: ""
ms.date: 06/14/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0035-d185d1509344
caps.latest.revision: 8
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0035
**Error 0035**  
  
 Exception occurs if no features were provided for a given user or item.  
  
 This error in Azure Machine Learning occurs you are trying to use a recommendation model for scoring but a feature vector cannot be found.  
  
## Resolution  

The Matchbox recommender has certain requirements that must be met when using either item features or user features.  This error indicates that a feature vector is missing for a user or item that you provided as input.  You must ensure that a vector of features is available in the data for each user or item.  
  
 For example, if you trained a recommendation model using features such as the user's age, location, or income, but now want to create scores for new users who were not seen during training, you must provide some equivalent set of features (namely, age, location and income values) for the new users in order to make appropriate predictions for them. 
 
 If you do not have any features for these users, consider feature engineering to generate appropriate features.  For example, if you do not have individual user age or income values, you might generate approximate values to use for a group of users. 
 
When you are scoring from a recommendation mode, you can use item or user features only if you previously used item or user features during training. For more information, see [Score Matchbox Recommender](score-matchbox-recommender.md).
 
For general information about how the Matchbox recommendation algorithm works, and how to prepare a dataset of item features or user features, see [Train Matchbox Recommender](train-matchbox-recommender.md).  
  
 > [!TIP]
 > Resolution not applicable to your case? You are welcome to send feedback on this article and provide information about the scenario, including the module and the number of rows in the column. We will use this information to provide more detailed troubleshooting steps in future.
   
|Exception Messages|  
|------------------------|  
|No features were provided for a required user or item.|  
|Features for {0} required but not provided.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](machine-learning-module-error-codes.md)