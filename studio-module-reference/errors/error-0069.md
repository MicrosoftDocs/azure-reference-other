---
title: "Error 0069 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 03/16/2017
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0069  
 Exception occurs if the specified SQL script is not correct.  
  
 This error in Azure Machine Learning occurs if the specified SQL script has syntax problems, or if the columns or table specified in the script is not valid. 
 
 You will receive this error if the SQL engine encounters any error while executing the query or script. The SQL error message is normally reported back in the Error Log so that you can take action based on the specific error.  
  
## Resolution  
 Revisit the module and inspect the SQL query for mistakes.  
  
 Verify that the query works correctly outside of Azure ML by logging in to the database server directly and running the query.  
  
 If there is a SQL generated message reported by the module exception, take action based on the reported error. For example, the error messages sometimes include specific guidance on the likely error:
+ *No such column or missing database*, indicating that you might have typed a column name wrong. If you are sure the column name is correct, try using brackets or quotation marks to enclose the column identifier.
+ *SQL logic error near \<SQL keyword\>*, indicating that you might have a syntax error before the specified keyword

  
|Exception Messages|  
|------------------------|  
|SQL script is incorrect.|  
|SQL query "{0}" is not correct.|  
|SQL query "{0}" is not correct: {1}|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
