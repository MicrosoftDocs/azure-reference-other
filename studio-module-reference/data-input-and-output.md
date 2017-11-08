---
title: "Data Input and Output | Microsoft Docs"
ms.custom: ""
ms.date: 09/21/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: f1050ce4-218a-4304-a4a7-57832be4cde0
caps.latest.revision: 27
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Data Input and Output
This article lists the modules available in Azure Machine Learning Studio for importing and exporting data and models.  

 Azure Machine Learning also supports directly uploading and downloading datasets from and to local files on your computer or on your network. For more information, see [Upload existing data into an Azure Machine Learning experiment](http://azure.microsoft.com/documentation/articles/machine-learning-walkthrough-2-upload-data/).  
 
- [Import Data](import-data.md): Get data from sources in the cloud, such as a Azure SQL database, Azure SQL Data Warehouse, Azure storage, and Azure DocumentDB. You can also import data provided as a public Web URL, get data from Hadoop using Hive query, or query an on-premises SQL Server.
  
- [Import Images](import-images.md): Load a collection of images from blob storage, for use in image classification tasks.

- [Unpack Zipped Datasets](unpack-zipped-datasets.md): Extract the data from zipped files you uploaded to Azure Machine Learning. Datasets can then be used in experiments.

- [Enter Data](enter-data-manually.md): Create small datasets by typing in the Studio UI. This can be handy for creating small test datsets.
  
- [Export Data](export-data.md): Save your results or intermediate data out to an Azure table, Azure blob storage, Azure SQL database, or Hive query.  

- [Load Trained Model](load-trained-model.md): Get a trained model from a URL or blob storage and use it in an experiment.
    
> [!NOTE]
>  The modules in this group only move data to or from Azure Machine Learning Studio, and you generally cannot use them to filter, cast, or transform the data during the import or export process. For more information about ways to transform and filter your data in Azure Machine Learning Studio, see [Data Transformation](data-transformation.md).  
  
## Resources  

The following articles describe some common data scenarios in machine learning:  
  
 **Get Started**  
  
-   [Microsoft Machine Learning blog: The Cloud Data Science Process](http://blogs.technet.com/b/machinelearning/archive/2015/04/15/the-cloud-data-science-process.aspx)  
  
     Learn how to manage data for machine learning in the cloud, based on CRISP-DM, an industry standard. Provides end-to-end walkthroughs that demonstrate integration of machine learning with cloud data solutions such as HDInsight and SQL Azure databases.  
  
-   [Import your training data into Azure Machine Learning Studio](https://docs.microsoft.com/azure/machine-learning/machine-learning-data-science-import-data)  
  
     This tutorial describes how to get your data into Azure and create an experiment.  
  
-   [Data preparation for machine learning using SSIS](http://blogs.msdn.com/b/ssis/archive/2015/06/25/data-preparation-for-azure-machine-learning-using-ssis.aspx)  
  
     Learn how to use ETL tools to integrate your data warehouse with Azure Machine Learning.  
  
 **Advanced**  
  
-   [Access datasets with Python using the Azure Machine Learning Python client library](https://docs.microsoft.com/azure/machine-learning/machine-learning-python-data-access)  
  
     Learn how to install the Machine Learning Python client library and use it to access metadata and work with datasets.  
  
 **Sample Experiments**  
  
-   [Data Processing](http://go.microsoft.com/fwlink/?LinkId=525733)  
  
-   [Download Data](http://go.microsoft.com/fwlink/?LinkId=525938)  
  
##  <a name="modules"></a> List of Modules  
 The **Data Input and Output** category includes the following modules:  
  
|Module|Description|  
|------------|-----------------|  
|[Enter Data Manually](enter-data-manually.md)|Lets you create small datasets by typing values|  
|[Export Data](export-data.md)|Writes a dataset to web URLs or to various forms of cloud-based storage in Azure, such as tables, blobs, and Azure SQL Database|  
|[Import Data](import-data.md)|Loads data from external sources on the web and from various forms of cloud-based storage in Azure such as Azure table or blob storage, Azure SQL Database and Azure SQL Data Warehouse, Hive query, and Azure DocumentDB. You can also import data from an on-premises SQL Server database.|   
|[Load Trained Model](load-trained-model.md)|Gets a trained model from a URL or blob storage for use in a scoring experiment|  
|[Unpack Zipped Datasets](unpack-zipped-datasets.md)|Decompresses a dataset that has been stored in zipped format and adds the dataset to your workspace|  
  
## See Also
  
[Data Format Conversions](data-format-conversions.md)   
 [Data Transformation](data-transformation.md)   
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)