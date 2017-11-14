---
title: "Cognitive Capabilities in U-SQL | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-02"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f9cb1046-3a79-4818-bf9a-2e584cc19075
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Cognitive Capabilities in U-SQL
Building intelligent features into applications requires some form of prediction capability. There are two ways to go: either build your own model or using a pre-trained model for scoring.  Training a good model requires a lot of data and machine-learning expertise, both of which are rare commodities. To help, U-SQL packages many of the machine-learning models that power the [Microsoft Cognitive Services](https://azure.microsoft.com/services/cognitive-services/). Built by some of the leading minds in the industry, these models are trained against massive data sets, and are highly performant and accurate. This integration of the cognitive models in U-SQL lets you easily add intelligent features, such as emotion detection, face and speech recognition; language understanding and sentiment analysis to applications that work on massive amounts of data. 

## Supported Cognitive Models
U-SQL provides built-in support for the following cognitive models, allowing you to build applications with powerful algorithms using just few lines of code:  

Cognitive Model        |Description  
---------------|---------
[Image Tagging (U-SQL)](image-tagging-u-sql.md)     |Image tagging returns information about visual content found in an image. It can be used along with descriptions and domain-specific models to identify content in an image.
[Emotion Extraction (U-SQL)](emotion-extraction-u-sql.md)     |Emotion analyzes facial expressions in an image to detect a range of emotions, currently including anger, contempt, disgust, fear, happiness, neutrality, sadness, and surprise.    
[Face Detection (U-SQL)](face-detection-u-sql.md)     |Face detects one or more human faces in an image, along with face attributes that contain machine learning-based predictions based on features such as age, emotion, and gender.          
[Optical Character Recognition (U-SQL)](optical-character-recognition-u-sql.md)     |Optical character recognition (OCR) detects and extracts handwritten text from images of notes, letters, whiteboards and so forth, and returns a machine-readable character stream.         
[Key Phrases Extraction (U-SQL)](key-phrases-extraction-u-sql.md)     |Key phrases extraction identifies key phrases, topics, and language from the input text.         
[Sentiment Analysis (U-SQL)](sentiment-analysis-u-sql.md)     |Sentiment analysis detects sentiment using classification techniques based on the input text.  

## <a name="registeringExtensions"></a>Registering Cognitive Extensions in U-SQL
To get started with the Cognitive extensions, complete the following steps:

1. Navigate to the [Azure Portal](http://portal.azure.com/) and log in.
2. Navigate to your Azure Data Lake Analytics Account.
3. Select **Sample Scripts** near the top.
4. Select **...More** and then **Install U-SQL Extensions** in the **Sample Scripts** tile.
5. Review the pop-up and then click **OK**.

Once you’ve chosen to install the extensions, the system will copy U-SQL extension-related files into the default Azure Data Lake Store (ADLS) associated with your ADLA account. A notification that files are being copied will appear near the Notification icon in the upper right of the page. When the files are copied, you’ll see an updated notification that the file copying was successful and that a special U-SQL Job was submitted to finish the registration. You can find the special job and its status by using View All Jobs in the upper-left corner of the Azure Portal. The Job normally will take a few minutes to complete.  

At that point, you can discover what the job did by browsing the catalog for the master database. The job simply registers advanced analytic cognitive assemblies in the master database, which you can see by using the Data Explorer.  

Seeing these assemblies in the master database is evidence that your ADLA account is setup correctly and you can now write a U-SQL script that uses cognitive functions to build intelligent applications.  





### See Also
* [Built-in U-SQL System Objects and Extensions](built-in-u-sql-system-objects-and-extensions.md)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
* [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/)
* [Microsoft Cognitive Services](https://azure.microsoft.com/services/cognitive-services/)