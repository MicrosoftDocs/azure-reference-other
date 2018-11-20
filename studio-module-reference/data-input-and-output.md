---
title: "Data Input and Output | Microsoft Docs"
description: "Learn about the modules you can use to import and export data and models in Azure Machine Learning Studio."
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/16/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: f1050ce4-218a-4304-a4a7-57832be4cde0
caps.latest.revision: 27
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Data Input and Output

This article lists the modules that you can use for importing and exporting data and models in Azure Machine Learning Studio.

In addition to using modules, you can directly upload and download datasets from local files on your computer or network. For more information, see [Upload existing data into an Azure Machine Learning experiment](https://docs.microsoft.com/azure/machine-learning/studio/walkthrough-2-upload-data).

Here are some of the sources you can use to import and export data and models in Machine Learning Studio:
 
- Get data from sources in the cloud, such as Azure SQL Database, Azure SQL Data Warehouse, Azure Storage, and Azure Cosmos DB. You can also import data that's provided as a public web URL, get data from Hadoop by using a Hive query, or query an on-premises SQL server.
- Load a collection of images from Azure Blob storage to use in image classification tasks.
- Extract the data from zipped files that you uploaded to Machine Learning. You can use the datasets in experiments.
- Create small datasets by typing in the Machine Learning Studio UI. This can be handy for creating small test datasets.
- Save your results or intermediate data to Azure Table storage, Blob storage, a SQL database, or a Hive query.
- Get a trained model from a URL or Blob storage, and then use it in an experiment.
    
> [!NOTE]
> The modules in this group only move data to or from Machine Learning Studio. You can't use the modules to filter, cast, or transform the data during the import or export process.
> 
> For more information about how to transform and filter your data in Machine Learning Studio, see [Data Transformation](data-transformation.md).
  
## Resources

The following articles introduce common data scenarios in machine learning:
  
### Get started
  
-   [Microsoft Machine Learning blog: The Cloud Data Science Process](http://blogs.technet.com/b/machinelearning/archive/2015/04/15/the-cloud-data-science-process.aspx)
  
  Learn how to manage data for machine learning in the cloud. The information in this article is based on CRISP-DM, an industry standard. The article provides end-to-end walkthroughs that demonstrate the integration of machine learning with cloud data solutions such as Azure HDInsight and SQL Database.
  
-   [Import your training data into Machine Learning Studio](https://docs.microsoft.com/azure/machine-learning/machine-learning-data-science-import-data)
  
  This article describes how to get your data into Azure, and then create an experiment.
  
-   [Data preparation for machine learning by using SQL Server Integration Services](http://blogs.msdn.com/b/ssis/archive/2015/06/25/data-preparation-for-azure-machine-learning-using-ssis.aspx)
  
  Learn how to use ETL tools to integrate your data warehouse with Machine Learning.
  
### Advanced data science
  
-   [Access datasets with Python by using the Azure Machine Learning Python client library](https://docs.microsoft.com/azure/machine-learning/machine-learning-python-data-access)
  
  Learn how to install the Machine Learning Python client library, and then use it to access metadata and work with datasets.
  
### Sample experiments
  
-   [Data processing](http://go.microsoft.com/fwlink/?LinkId=525733)
-   [Download data](http://go.microsoft.com/fwlink/?LinkId=525938)
  
## List of modules

The **Data Input and Output** category includes the following modules:

- [Enter Data Manually](enter-data-manually.md): Lets you create small datasets by typing values.
- [Export Data](export-data.md): Writes a dataset to web URLs or to various forms of cloud-based storage in Azure, such as tables, blobs, or a SQL database.
- [Import Data](import-data.md): Loads data from external sources on the web and from various forms of cloud-based storage in Azure, such as Table storage, Blob storage, SQL Database, SQL Data Warehouse, Azure Cosmos DB, or a Hive query. You can also import data from an on-premises SQL Server database.
- [Load Trained Model](load-trained-model.md): Gets a trained model from a URL or Blob storage to use in a scoring experiment.
- [Unpack Zipped Datasets](unpack-zipped-datasets.md): Decompresses a dataset that's been stored in zipped format, and then adds the dataset to your workspace.

## See also
  
- [Data Format Conversions](data-format-conversions.md)
- [Data Transformation](data-transformation.md)
- [Module categories and descriptions](machine-learning-module-descriptions.md)
