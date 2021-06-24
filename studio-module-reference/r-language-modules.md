---
title: "ML Studio (classic): R Language Modules - Azure"
description: This article lists the modules in Machine Learning Studio (classic) that support running R code.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# R Language Modules

This article lists the modules in Machine Learning Studio (classic) that support running R code. These modules make it easier to publish R models in production, and to use the experience of the R language community to solve real-world problems.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

This article also describes some general requirements for using R in Machine Language Studio (classic), and lists known issues and tips.

## List of modules

The **R Language Modules** category includes the following modules:

+ [Execute R Script](execute-r-script.md): Runs an R script from a Machine Learning experiment.  
+ [Create R Model](create-r-model.md): Creates an R model by using custom resources.

## Requirements when using R

Before using R script in Machine Learning Studio (classic), observe the following requirements:

- If you imported data that uses CSV or other formats, you cannot read the data directly in CSV format from your R code. Instead, use [Convert to Dataset](convert-to-dataset.md) to prepare the data, before using it as input to an R module.

- When you attach any Machine Learning dataset as input to an R module, the dataset is automatically loaded into the R workspace as a data frame, with the variable name **dataset**.  

    However, you can define additional data frames, or change the name of the default dataset variable within your R script.

- The R modules run in a protected and isolated environment within your private workspace. Within your workspace, you can create data frames and variables for use by multiple modules.

    However, you cannot load R data frames from a different workspace, or read variables created in a different workspace, even if that workspace is open in an Azure session. Also, you cannot use modules that have a Java dependency, or that require direct network access.  

## Optimization for R scoring tasks

The implementation of R in the Machine Learning Studio (classic) and workspace environment includes two principal components. One component coordinates script execution, and the other provides high-speed data access and scoring. The scoring component is optimized to enhance scalability and performance. 

Therefore, R workspaces in Machine Learning Studio (classic) also support two kinds of scoring tasks, each optimized for different requirements. You typically use scoring on a file-by-file basis when you are building an experiment. You typically use the request response service (RRS) for very fast scoring, when you are scoring as part of a web service.

## R package and version support 

Machine Learning Studio (classic) includes over 500 of the most popular R packages. The R packages that you can select from depend on which R version you select for your experiment:

+ CRAN R
+ Microsoft R Open (MRO 3.2.2 or MRO 3.4.4)

Whenever you create an experiment, you must choose a single R version to run on, for all modules in your experiment.

## List of packages per version

For a list of the packages that are currently supported in Machine Learning, see [R Packages Supported by Machine Learning](r-packages-supported-by-azure-machine-learning.md). 

You can also add the following code to an [Execute R Script](execute-r-script.md) module in your experiment, and run it to get a dataset containing package names and versions. Be sure to set the R version in the module properties to generate the correct list for your intended environment.

```R
data.set <- data.frame(installed.packages())
maml.mapOutputPort("data.set")
```

> [!IMPORTANT]
> The packages that are supported in Machine Language Studio (classic) change frequently. If you have any doubts about whether an R package is supported, use the R code sample provided to get the complete list of packages in the current environment.

## Extend experiments by using the R language

There are many ways that you can extend your experiment by using custom R script or by adding R packages. Here are some ideas to get you started:

- Use R code to perform custom math operations. For example, there are R packages to solve differential equations, generate random numbers, or run Monte Carlo simulations.

- Apply custom transformations for data. For example, you might use an R package to perform interpolation on time series data, or perform linguistic analysis.

- Work with different data sources. The R script modules support an additional set of inputs, which can include data files, in zipped format. You might use zipped data files, along with R packages designed for such data sources, to flatten hierarchical data into a flat data table. You might also use these to read data from Excel and other file formats.

- Use custom metrics for evaluation. For example, rather than use the functions provided in [Evaluate](evaluate-model.md), you could import an R package, and then apply its metrics.  

The following example demonstrates the overall process for how you can install new packages and use custom R code in your experiment.

### Split columns by using R

Sometimes the data requires extensive manipulation to extract features. Suppose you have a text file that contains an ID followed by values and notes, all separated by spaces. Or suppose that your text file contains characters that are not supported by Machine Language Studio (classic).

There are several R packages that provide specialized functions for such tasks. The [splitstackshape library](https://cran.r-project.org/web/packages/splitstackshape/index.html) package contains several useful functions for splitting multiple columns, even if each column has a different delimiter.

The following sample illustrates how to install the needed packages, and split apart columns. You would add this code to the **Execute R Script** module.

```R
#install dependent packages  
install.packages("src/concat.split.multiple/data.table_1.9.2.zip", lib=".", repos = NULL, verbose = TRUE)  
(success.data.table <- library("data.table", lib.loc = ".", logical.return = TRUE, verbose = TRUE))  
  
install.packages("src/concat.split.multiple/plyr_1.8.1.zip", lib=".", repos = NULL, verbose = TRUE)  
(success.plyr <- library("plyr", lib.loc = ".", logical.return = TRUE, verbose = TRUE))  
  
install.packages("src/concat.split.multiple/Rcpp_0.11.2.zip", lib=".", repos = NULL, verbose = TRUE)  
(success.Rcpp <- library("Rcpp", lib.loc = ".", logical.return = TRUE, verbose = TRUE))  
  
install.packages("src/concat.split.multiple/reshape2_1.4.zip", lib=".", repos = NULL, verbose = TRUE)  
(success.reshape2 <- library("reshape2", lib.loc = ".", logical.return = TRUE, verbose = TRUE))  
  
#install actual packages  
install.packages("src/concat.split.multiple/splitstackshape_1.2.0.zip", lib=".", repos = NULL, verbose = TRUE)  
(success.splitstackshape <- library("splitstackshape", lib.loc = ".", logical.return = TRUE, verbose = TRUE))  
  
#Load installed library  
library(splitstackshape)  
  
#Use library method to split & concat  
data <- concat.split.multiple(maml.mapInputPort(1), c("TermsAcceptedUserClientIPAddress", "EmailAddress"), c(".", "@"))  
  
#Print column names to console  
colnames(data)  
  
#Redirect data to output port  
maml.mapOutputPort("data")  
```

## Additional resources

Begin with this tutorial that describes how to build a custom R module:

+ [Extend Your Experiment with R](/azure/machine-learning/classic/custom-r-modules) 

This article discusses the differences between the two scoring engines in detail, and explains how you can choose a scoring method when you deploy your experiment as a web service:

+ [Machine Learning: Consume Web Services](/azure/machine-learning/classic/consume-web-services)

This experiment in the Azure AI Gallery demonstrates how you can create a custom R module that does training, scoring, and evaluation:

 + [Create R Model with Evaluation](https://gallery.azure.ai/Experiment/Create-R-Model-with-Evaluation-1)

This article, published on R-Bloggers, demonstrates how you can create your own evaluation method in Machine Learning:

+ [How to evaluate R models in Machine Learning Studio (classic)](https://www.r-bloggers.com/how-to-evaluate-r-models-in-azure-machine-learning-studio/)

### More help with R

This site provides a categorized list of packages that you can search by keywords:

+ [R documentation](https://www.rdocumentation.org/)  

For additional R code samples and help with R and its applications, see these resources:

- [R Project](https://www.r-project.org/): The official site for the R language.

- [Rseek](https://www.rseek.org/): A search engine for R resources.

- [R-bloggers](https://www.r-bloggers.com/): An aggregation of blogs in the R community.

- [CRAN](https://cran.r-project.org/web/views/): The largest repository of R packages.

- [Quick-R](https://www.statmethods.net/): A good R tutorial.

- [Webinar: Learn How to Get Faster End Results from Your R Models](https://channel9.msdn.com/blogs/Cloud-and-Enterprise-Premium/Learn-How-to-Get-Faster-End-Results-from-Your-R-Models)

- [Bioconductor](https://bioconductor.org/): A large repository of R packages in bioinformatics.


## See also

- [Python Language Modules](python-language-modules.md)
- [Module Categories and Descriptions](machine-learning-module-descriptions.md)
