---
title: "A-Z List of Machine Learning Studio Modules | Microsoft Docs"
ms.custom: ""
ms.date: 06/02/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: dfdcb393-0285-4a60-a2bd-7c79f80e4d20
caps.latest.revision: 41
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# A-Z List of Machine Learning Studio Modules
This topic provides an alphabetized list of the modules provided in Azure Machine Learning Studio Machine Learning Studio.  

The modules in Azure Machine Learning modules cover a wide range of features and functions necessary for machine learning tasks, including data conversion and transformation functions, modules for executing R or Python script, and a variety of algorithms such as decision trees and decision forests, clustering, time series, recommendation models, and anomaly detection. 

+ Use this [table](#modules) as an index to quickly find a specific module or algorithm, if you know the name.  

+ For a list of the modules by functional category, see [Module Categories and Descriptions](machine-learning-module-descriptions.md).  
  
+ If you don't know which module you might need, see this article: [How to choose algorithms for Microsoft Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/machine-learning-algorithm-choice/).  
  
##  <a name="modules"></a> Modules Reference  
  
|Module|Description|  
|------------|-----------------|  
|[Add Columns](add-columns.md)|Adds a set of columns from one dataset to another|  
|[Add Rows](add-rows.md)|Appends a set of rows from an input dataset to the end of another dataset|  
|[Apply Filter](apply-filter.md)|Applies a filter to specified columns of a dataset|  
|[Apply Math Operation](apply-math-operation.md)|Applies a mathematical operation to column values|  
|[Apply SQL Transformation](apply-sql-transformation.md)|Runs a SQLite query on input datasets to transform the data|  
|[Apply Transformation](apply-transformation.md)|Applies a well-specified data transformation to a dataset|  
|[Assign to Clusters (deprecated)](assign-to-clusters-deprecated.md)|Assigns data to clusters using an existing trained clustering model<br /><br /> This module has been deprecated, but is available for use with existing experiments. For new experiments, use [Assign Data to Clusters](assign-data-to-clusters.md).|  
|[Assign Data to Clusters](assign-data-to-clusters.md)|Assigns data to clusters using an existing trained clustering model|  
|[Bayesian Linear Regression](bayesian-linear-regression.md)|Creates a Bayesian linear regression model|  
|[Boosted Decision Tree Regression](boosted-decision-tree-regression.md)|Creates a regression model using the Boosted Decision Tree algorithm|  
|[Build Count Table (deprecated)](build-count-table-deprecated.md)|Creates counts to use in building features|  
|[Build Counting Transform](build-counting-transform.md)|Creates counts to use in building features|  
|[Clean Missing Data](clean-missing-data.md)|Specifies how to handle the values missing from a dataset|  
|[Clip Values](clip-values.md)|Detects outliers and then clips or replaces their values|  
|[Compute Elementary Statistics](compute-elementary-statistics.md)|Calculates specified summary statistics for selected dataset columns|  
|[Detect Languages](detect-languages.md)|Detects the language of each line in the input file|   
|[Compute Linear Correlation](compute-linear-correlation.md)|Calculates the linear correlation between column values in a dataset|  
|[Convert To Arff](convert-to-arff.md)|Converts data input to the attribute relation file format used by the Weka toolset|  
|[Convert to CSV](convert-to-csv.md)|Converts data input to a comma-separated values format|  
|[Convert to Dataset](convert-to-dataset.md)|Converts data input to the internal Dataset format used by Microsoft Azure Machine Learning|  
|[Convert to Indicator Values](convert-to-indicator-values.md)|Converts categorical values in columns to indicator values|  
|[Convert to SVMLight](convert-to-svmlight.md)|Converts data input to the format used by the SVM-Light framework|  
|[Convert to TSV](convert-to-tsv.md)|Converts data input to the tab-delimited format|  
|[Count Featurizer (deprecated)](count-featurizer-deprecated.md)|Generates a set of compact features based on a count table|  
|[Create R Model](create-r-model.md)|Creates an R model using custom resources|  
|[Cross-Validate Model](cross-validate-model.md)|Cross-validates parameter estimates for classification or regression models by partitioned the data|  
|[Decision Forest Regression](decision-forest-regression.md)|Creates a regression model using the decision forest algorithm| 
|[Detect Languages](detect-languages.md)| Detects the language of each line in the input file|
|[Edit Metadata](edit-metadata.md)|Edits metadata associated with columns in a dataset|  
|[Enter Data Manually](enter-data-manually.md)|Enables entering and editing small datasets by typing values|  
|[Evaluate Model](evaluate-model.md)|Evaluates a scored classification or regression model with standard metrics|  
|[Evaluate Probability Function](evaluate-probability-function.md)|Fits a specified probability distribution function to a dataset|  
|[Evaluate Recommender](evaluate-recommender.md)|Evaluates the accuracy of recommender model predictions|  
|[Execute Python Script](execute-python-script.md)|Executes a Python script from an Azure Machine Learning experiment|  
|[Execute R Script](execute-r-script.md)|Executes an R script from an Azure Machine Learning experiment|
|[Export Count Table](export-count-table.md)|Exports counts from a count transform|  
|[Export Data](export-data.md)|Writes a dataset to web URLs or to various forms of cloud-based storage in Azure, such as tables, blobs, and Azure SQL databases<br /><br /> This module was formerly named **Writer**.|  
|[Extract Key Phrases from Text](extract-key-phrases-from-text.md)| Extracts key words and phrases from a text column|
|[Extract N-Gram Features from Text](extract-n-gram-features-from-text.md)|Creates N-Gram dictionary features and does feature selection on them|
|[Fast Forest Quantile Regression](fast-forest-quantile-regression.md)|Creates a quantile regression model|  
|[Feature Hashing](feature-hashing.md)|Converts text data to integer-encoded features using the Vowpal Wabbit library|  
|[Filter Based Feature Selection](filter-based-feature-selection.md)|Identifies the features in a dataset with the greatest predictive power|  
|[FIR Filter](fir-filter.md)|Creates a finite impulse response filter for signal processing|  
|[Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md)|Identifies the linear combination of feature variables that can best group data into separate classes|  
|[Group Categorical Values](group-categorical-values.md)|Groups data from multiple categories into a new category|  
|[Group Data into Bins](group-data-into-bins.md)|Puts numerical data into bins|  
|[IIR Filter](iir-filter.md)|Creates an infinite impulse response filter for signal processing|  
|[Import Count Table](import-count-table.md)|Imports counts from an existing count table|  
|[Import Data](import-data.md)|Loads data from external sources on the web; from various forms of cloud-based storage in Azure such as tables, blobs, and SQL  databases; and from on-premises SQL Server databases<br /><br /> This module was formerly named **Reader**.|  
|[Import Images](import-images.md)|Loads images from Azure BLOB storage into a dataset|  
|[Join Data](join-data.md)|Joins two datasets|  
|[K-Means Clustering](k-means-clustering.md)|Configures and initializes a K-means clustering model|  
|[Latent Dirichlet Allocation](latent-dirichlet-allocation.md)|Performs topic modeling using the Vowpal Wabbit library for LDA|  
|[Linear Regression](linear-regression.md)|Creates a linear regression model|  
|[Load Trained Model](load-trained-model.md)|Gets a trained model so that you can use it in an experiment for scoring|  
|[Median Filter](median-filter.md)|Creates a median filter used to smooth data for trend analysis|  
|[Merge Count Transform](merge-count-transform.md)|Merges two sets of count tables|  
|[Missing Values Scrubber (deprecated)](missing-values-scrubber-deprecated.md)|Specifies how to handle values that are missing from a dataset|  
|[Modify Count Table Parameters](modify-count-table-parameters.md)|Builds a compact set of count-based features from count tables|  
|[Moving Average Filter](moving-average-filter.md)|Creates a moving average filter that smooths data for trend analysis|  
|[Multiclass Decision Forest](multiclass-decision-forest.md)|Creates a multiclass classification model using the decision forest algorithm|  
|[Multiclass Decision Jungle](multiclass-decision-jungle.md)|Creates a multiclass classification model using the decision jungle algorithm|  
|[Multiclass Logistic Regression](multiclass-logistic-regression.md)|Creates a multiclass logistic regression classification model|  
|[Multiclass Neural Network](multiclass-neural-network.md)|Creates a multiclass classification model using a neural network algorithm|  
|[Named Entity Recognition](named-entity-recognition.md)|Recognizes named entities in a text column|  
|[Neural Network Regression](neural-network-regression.md)|Creates a regression model using a neural network algorithm|  
|[Normalize Data](normalize-data.md)|Rescales numeric data to constrain dataset values to a standard range|  
|[One-Class Support Vector Machine](one-class-support-vector-machine.md)|Creates a one-class Support Vector Machine model for anomaly detection|  
|[One-vs-All Multiclass](one-vs-all-multiclass.md)|Creates a multiclass classification model from an ensemble of binary classification models| 
|[Ordinal Regression](ordinal-regression.md)|Creates an ordinal regression model|  
|[Partition and Sample](partition-and-sample.md)|Creates multiple partitions of a dataset based on sampling|  
|[Permutation Feature Importance](permutation-feature-importance.md)|Computes the permutation feature importance scores of feature variables given a trained model and a test dataset|  
|[PCA-Based Anomaly Detection](pca-based-anomaly-detection.md)|Creates an anomaly detection model using Principal Component Analysis|  
|[Poisson Regression](poisson-regression.md)|Creates a regression model that assumes data has a Poisson distribution|  
|[Preprocess Text](preprocess-text.md)|Performs cleaning operations on text|  
|[Pretrained Cascade Image Classification](pretrained-cascade-image-classification.md)|Creates a pretrained image classification model for frontal faces using the OpenCV Library|  
|[Principal Component Analysis](principal-component-analysis.md)|Computes a set of features with reduced dimensionality for more efficient learning|  
|[Remove Duplicate Rows](remove-duplicate-rows.md)|Removes the duplicate rows from a dataset|  
|[Replace Discrete Values](replace-discrete-values.md)|Replaces discrete values from one column with numeric values based on another column|  
|[Score Matchbox Recommender](score-matchbox-recommender.md)|Scores predictions for a dataset using the Matchbox recommender|  
|[Score Model](score-model.md)|Scores predictions for a trained classification or regression model|  
|[Score Vowpal Wabbit 7-4 Model](score-vowpal-wabbit-version-7-4-model.md)|Scores data using the Vowpal Wabbit machine learning system<br /><br /> Requires a trained model built using VW versions 7-4 and 7-6|  
|[Score Vowpal Wabbit 7-10 Model](score-vowpal-wabbit-version-7-10-model.md)|Scores data using the Vowpal Wabbit machine learning system<br /><br /> Requires a trained model built using VW version 7-10|  
|[Score Vowpal Wabbit 8 Model](score-vowpal-wabbit-version-8-model.md)|Scores data using the Vowpal Wabbit machine learning system from the command line interface<br /><br /> Requires a trained model built using VW version 8|  
|[Select Columns in Dataset](select-columns-in-dataset.md)|Selects columns to include or exclude from a dataset in an operation|  
|[SMOTE](smote.md)|Increases the number of low incidence examples in a dataset using synthetic minority oversampling|  
|[Split Data](split-data.md)|Partitions the rows of a dataset into two distinct sets|  
|[Summarize Data](summarize-data.md)|Generates a basic descriptive statistics report for the columns in a dataset|  
|[Sweep Clustering](sweep-clustering.md)|Performs a parameter sweep on a clustering model to determine the optimum parameter settings|  
|[Test Hypothesis Using t-Test](test-hypothesis-using-t-test.md)|Compares means from two datasets using a t-test|  
|[Threshold Filter](threshold-filter.md)|Creates a threshold filter that constrains values| 
|[Time Series Anomaly Detection](time-series-anomaly-detection.md)|Learns a trend in time series data and uses it to detect anomalies|   
|[Train Anomaly Detection Model](train-anomaly-detection-model.md)|Trains an anomaly detector model and labels data from the training set|  
|[Train Clustering Model](train-clustering-model.md)|Trains a clustering model and assigns data from the training set to clusters|  
|[Train Matchbox Recommender](train-matchbox-recommender.md)|Trains a Bayesian recommender using the Matchbox algorithm|  
|[Train Model](train-model.md)|Trains a classification or regression model in a supervised manner|  
|[Train Vowpal Wabbit 7-4 Model](train-vowpal-wabbit-version-7-4-model.md)|Trains a model from the Vowpal Wabbit machine learning system<br /><br /> This module is for compatibility with VW versions 7-4 and 7-6|  
|[Train Vowpal Wabbit 7-10 Model](train-vowpal-wabbit-version-7-10-model.md)|Trains a model from the Vowpal Wabbit machine learning system<br /><br /> This module is for the current VW version, 7-10|  
|[Train Vowpal Wabbit 8 Model](train-vowpal-wabbit-version-8-model.md)|Trains a model using version 8 of the Vowpal Wabbit machine learning system<br /><br /> This module is for the VW version 8|  
|[Tune Model Hyperparameters](tune-model-hyperparameters.md)|Performs a parameter sweep on a regression or classification model to determine the optimum parameter settings|  
|[Two-Class Averaged Perceptron](two-class-averaged-perceptron.md)|Creates an averaged perceptron binary classification model|  
|[Two-Class Bayes Point Machine](two-class-bayes-point-machine.md)|Creates a Bayes point machine binary classification model|  
|[Two-Class Boosted Decision Tree](two-class-boosted-decision-tree.md)|Creates a binary classifier using a boosted decision tree algorithm|  
|[Two-Class Decision Forest](two-class-decision-forest.md)|Creates a two-class classification model using the decision forest algorithm|  
|[Two-Class Decision Jungle](two-class-decision-jungle.md)|Creates a two-class classification model using the decision jungle algorithm|  
|[Two-Class Locally Deep Support Vector Machine](two-class-locally-deep-support-vector-machine.md)|Creates a binary classification model using the locally deep Support Vector Machine algorithm|  
|[Two-Class Logistic Regression](two-class-logistic-regression.md)|Creates a two-class logistic regression model|  
|[Two-Class Neural Network](two-class-neural-network.md)|Creates a binary classifier using a neural network algorithm|  
|[Two-Class Support Vector Machine](two-class-support-vector-machine.md)|Creates a binary classification model using the Support Vector Machine algorithm|  
|[Unpack Zipped Datasets](unpack-zipped-datasets.md)|Unpacks datasets from a zip package in user storage|  
|[User-Defined Filter](user-defined-filter.md)|Creates a custom finite or infinite impulse response filter|  
  
## See Also  
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [Module Data Types](machine-learning-module-data-types.md)