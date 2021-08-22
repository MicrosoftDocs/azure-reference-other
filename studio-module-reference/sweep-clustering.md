---
title: "ML Studio (classic): Sweep Clustering - Azure"
description: Learn how to use the Sweep Clustering module to train a model by using a parameter sweep to find the best hyperparameters for a model.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Sweep Clustering

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Performs a parameter sweep to determine the optimum settings for a clustering model*  

Category: [Machine Learning / Train](machine-learning-train.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the [Sweep Clustering](sweep-clustering.md) module in Machine Learning Studio (classic), to train a model using a parameter sweep. A parameter sweep is a way of finding the best hyperparameters for a model, given a set of data.

The [Sweep Clustering](sweep-clustering.md) module is designed specifically for clustering models. You provide a clustering model as input, together with a dataset. The module iterates over a set of parameters you specify, building and testing models with different parameters, until it finds the model with the best set of clusters. It automatically computes the best configuration, and then trains a model using that configuration.

It also returns a set of metrics describing the models that were tested, and a set of cluster assignments based on the best model.

## How to configure Sweep Clustering

1. Add the [Sweep Clustering](sweep-clustering.md) module to your experiment in Studio (classic). You can find this module under **Machine Learning**, in the **Train** category.

2. Add the [K-Means Clustering](k-means-clustering.md) module and your training dataset to the experiment, and connect them both to the [Sweep Clustering](sweep-clustering.md) module.  

3. Configure the [K-Means Clustering](k-means-clustering.md) module to use a parameter sweep as follows:

    1. Set **Create trainer mode** to **Parameter Range**.

    2. Use the **Range Builder** (or manually type multiple values) for each parameter to set the range of values to iterate over.

    3. **Initialization for sweep**: Specify how the K-means algorithm should find the initial cluster centroids. Multiple algorithms are provided for randomly initializing and then testing centroids.

        If your training dataset contains a label column, even with partial values, you can use those values for centroids. Use the **Assign Label Mode** option to indicate how the label values are used.

        > [!TIP]
        > Your label column must be marked as such in advance. If you get an error, try using [Edit Metadata](edit-metadata.md) to identify the column containing labels.

    4. **Number of seeds to sweep**: Indicate how many different random starting seeds to try when doing the parameter sweep.
  
    5. Choose the metric to use when measuring cluster similarity. For more information, see the [K-Means Clustering](k-means-clustering.md) topic.

    6. **Iterations**: Specify the total number of iterations that the K-means algorithm should perform. These iterations are used to optimize the selection of the cluster centroids.

    7. If you are using a label column to initialize the sweep, use the **Assign Label Mode** option to specify how the values in the label column should be handled.

        - **Fill missing values**: If your label column contains some missing values, use this option to impute categories based on the cluster the data point is assigned to.  
  
        - **Overwrite from closest to center**: Generates label values for all data points assigned to a cluster, using the label of the point that is closest to the center of the cluster.

        - **Ignore label column**: Select this option if you don’t want to perform either of the above operations.  

4. In the [Sweep Clustering](sweep-clustering.md) module, use the option, For **Metric for measuring clustering result**, to specify the mathematical method to use when estimating the fit of the trained clustering model:

    - **Simplified Silhouette**: This metric captures the tightness of data points within each cluster. It is computed as a combination of the similarity of each row with its cluster and its similarity with next closest cluster. If the cluster has only 1 row, the prorated distance to next closest centroid is calculated instead, to avoid getting 0 as the result. “Simplified” refers to the fact that the distance to cluster centroid is used as a simple similarity measure. In general, a higher score is better. The average value over the dataset indicates how well the data has been clustered. If there are too many or too few clusters, some clusters will have lower silhouette values than the rest. For more information, see [this Wikipedia article](https://en.wikipedia.org/wiki/Silhouette_\(clustering\)).
  
    - **Davies-Bouldin**: This metric aims to identify the smallest set of clusters with the least scatter. Because the metric is defined as a ratio of scatter within each cluster over cluster separation, a lower value means that clustering is better. The best clustering model minimizes this metric.  To calculate the Davies-Bouldin metric, the average row to centroid distance is computed per cluster. For each pair of clusters, the sum of those averages is divided by the distance between centroids.  Maximal value over all other clusters is selected for each cluster and averaged over all clusters. For more information, see [this Wikipedia article](https://en.wikipedia.org/wiki/Davies%E2%80%93Bouldin_index).  

    - **Dunn**: This metric aims to identify the smallest set of most compact clusters. Generally, a higher value for this metric indicates better clustering. To calculate the Dunn metric, the minimal centroid-to-centroid distance is divided by the maximal distance of each data point to its cluster center.  For more information, see [this Wikipedia article](https://en.wikipedia.org/wiki/Dunn_index).  
  
    - **Average deviation**:  This metric is computed by taking the average distance from each data point to its cluster center. The value decreases as the number of centroids increases; therefore, it is not useful when sweeping to find the number of centroids. This metric is recommended for use when you are choosing the best centroid initialization seed. 

5. **Specify parameter sweeping mode**: Select an option that defines the combinations of values that are used when training, and how they are chosen:
  
    - **Entire grid**:  All values within the given range are tried and evaluated. This option is usually more computationally expensive.
  
    - **Random sweep**: Use this option to limit the number of runs.   The clustering model is built and evaluated using a combination of values chosen randomly from the allowed range of parameter values.
  
6. **Maximum number of runs on random sweep**: Set this option if you choose the **Random sweep** option. Type a value to limit the maximum number of iterations when testing sets of randomly chosen parameters.

    > [!WARNING]
    > The **Iterations** parameters of the [K-Means Clustering](k-means-clustering.md) module has a different purpose and is not affected by this setting: it limits the number of passes over the data made to improve clusters, by minimizing the average distance from each data point to its cluster centroids. In contrast, the iterations defined by the [Sweep Clustering](sweep-clustering.md) module parameter are performed in order to try different random centroid initializations. This minimization problem is known to be NP-hard; therefore, trying several random seeds could produce better results.  
  
    If you select a random sweep, use the **Random seed** option to specify the initial random seed values, on which to begin creating the centroids. One advantage of using a parameter sweep to create a clustering model is that you can easily test multiple seed values to mitigate the known sensitivity of clustering models to the initial seed value.  

7. Click **Column Set**, and choose the columns to use when building the clusters. By default, all feature columns are used when building and testing the clustering model.

    You can include a label column, if present in your dataset.  If a label is present, you can use it to guide selection of centroids, use the label as a feature, or ignore the label. Set these options for label handling the **Kmeans Clustering** module as described in Step 3 above.

8. **Check for Append or Uncheck for Result Only**: Use this option to control which columns are returned in the results. 

    By default, the module returns the original columns of the training dataset together with the results.  If you deselect this option. only the cluster assignments are returned.

9. Add the [Assign Data to Clusters](assign-data-to-clusters.md) module to your experiment. 

10. Connect the output labeled **Best Trained Model** to the **Trained Model** input of [Assign Data to Clusters](assign-data-to-clusters.md).  

11. Add the dataset intended for evaluation, and connect it to the **Dataset** port of the [Assign Data to Clusters](assign-data-to-clusters.md) module.

12. Add the [Evaluate Model](evaluate-model.md) module, and connect it to [Assign Data to Clusters](assign-data-to-clusters.md). Optionally, you can connect an evaluation dataset.

13. Run the experiment.

### Results  

The [Sweep Clustering](sweep-clustering.md) module outputs three different results:

- **Best Trained Model**. A trained model that you can use for scoring and evaluation. Right-click and select **Save as Trained Model** to capture the optimized clustering model and use it for scoring.

- **Results dataset**. A set of cluster assignments, based on the optimized model.  
  
    |Column name|Description|  
    |-----------------|-----------------|  
    |**Assignments**|This value indicates the cluster to which each data point has been assigned. The clusters in the trained model are labeled with 0-based indexes.|  
    |**DistancesToClusterCenter no.1**<br /><br /> **DistancesToClusterCenter no.n**|This value indicates how close the data point is to the center of each cluster.<br /><br /> A column is created for each cluster created in the optimized model.<br /><br /> You can constrain the number of clusters by using the **Number of centroids** option.|  
  
    By default, you can return the columns from the training dataset along with the results, to make it easier to review and interpret the cluster assignments.  

- **Sweep results**. A dataset containing the following evaluation metrics for the clusters:

    |Column name|Description|  
    |-----------------|-----------------|  
    |**Cluster metric**|A value that indicates the average cluster quality for that run. The runs are ordered by the best score. |  
    |**Number of centroids**|The number of clusters that were created in this particular iteration of the sweep|  
    |**Index of run**|An identifier for each iteration|  

    > [!TIP]
    > The values returned for the cluster metric should be interpreted differently, depending on which metric you chose when you set up the sweep. For the default metric, **Simplified silhouette**, a higher score is better. For **Davies-Bouldin**, a lower score is better.

## Examples  

To see examples a parameter sweep with K-means clustering, see the [Azure AI Gallery](https://gallery.azure.ai/):  

- [Clustering sweep using the Diabetes dataset](https://gallery.cortanaanalytics.com/Experiment/Clustering-sweep-diabetes-dataset-1)

## Technical notes

This section contains tips and implementation details.
### Optimizing clustering models

The quality and accuracy of clustering models can be strongly affected by the choice of initial parameters, such as the number of centroids and the seed value used to initialize cluster. To mitigate this sensitivity to the initial parameters, the [Sweep Clustering](sweep-clustering.md) module helps you find the best combination of parameters. You specify a range of parameters to test, and the module automatically builds and tests multiple models, and finally selects the optimum number of clusters.

To create a parameter sweep, you must also configure the [K-Means Clustering](k-means-clustering.md) module to use a parameter sweep. You can specify that the sweep iterate over all possible combinations of parameters, or use a random combination of parameters.  You can also choose one of several standard metrics for measuring the accuracy of the centroids during the iterative model building and testing process. After the specified number of iterations has completed, the module selects the best number of clusters, based on the selected metric, and outputs reports that you can use to assess the results.

### Usage tips

- In some cases, you might already know how many clusters you expect to find. For example, your data might have class labels that could be used in guiding the selection of the centroids. In that case, you can configure the [K-Means Clustering](k-means-clustering.md) module to use the label column to guide selection of the initial centroids.  

- If you know some of the expected clusters but are not sure how many clusters are optimal, set the number of centroids to a number that is greater than the number of known label values. The [Sweep Clustering](sweep-clustering.md) module creates clusters for the known data points and then determines the optimal number of extra clusters for the remaining data points.

### Handling missing values in the label column

There are several ways to handle missing values in your label column. For example, suppose that you have an image classification task and only some of the images have been labeled.

You can use the label column to guide selection of the centroids but specify that any missing labels be filled in by using the cluster assignments.  In other words, existing label values are not changed, but missing labels are filled in.

Alternatively, for all data points assigned to a cluster, you can overwrite even the existing labels, using a single label that best represents the cluster. To understand how this option be helpful, imagine that you are using image data with very detailed labels, such as different dog breeds. Using this option, you could replace all the detailed labels with a single category label, "dog".  

### Seed values in the log

The log file generated by the [Train Clustering Model](train-clustering-model.md) module appears to indicate that the same seed is used for all iterations of the K-means clustering algorithm, regardless of the seed that was provided  in the **Random Seed** property.

In fact, the implementation uses the user-supplied seed to generate a sequence of random numbers that are different for every run. Thus, only one seed is needed to create all randomly generated numbers.

The intent of the log is indicate which seed the module uses when the user does not specify a seed in the **Properties** pane.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ICluster interface](icluster-interface.md)|Untrained clustering model|  
|Dataset|[Data Table](data-table.md)|Input data source|  

## Module parameters

|Name|Type|Values|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Metric for measuring clustering result|Cluster Metric|Simplified Silhouette, Davies-Bouldin, Dunn, Average Deviation|Required|Simplified Silhouette|Select the metric used for evaluating regression models|  
|Specify parameter sweeping mode|Sweep Methods|Entire grid or Random sweep|Required|Random sweep|Sweep entire grid on parameter space, or sweep with using a limited number of sample runs|  
|Column Set|ColumnSelection||Required||Column selection pattern|  
|Maximum number of runs on random sweep|Integer|[1;10000]|Available only when SweepingMode is set to Random sweep|5|Set maximum number of runs to execute when using random sweep|  
|Random seed|Integer||Available only when SweepingMode is set to Random sweep|0|Provide a value to seed the random number generator for random sweep|  
|Check for Append or Uncheck for Result Only|Boolean||Required|True|Select to indicate that output dataset must contain input dataset with assignments column appended. Deselect to indicate that only  assignments column should be output.|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Best Trained model|[ICluster interface](icluster-interface.md)|Trained clustering model|  
|Results dataset|[Data Table](data-table.md)|Input dataset appended by data column of assignments or assignments column only|  
|Sweep results|[Data Table](data-table.md)|Resulting metric log for cluster sweep runs|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [K-Means Clustering](k-means-clustering.md)   
 [Assign Data to Clusters](assign-data-to-clusters.md)   
 [Machine Learning / Train](machine-learning-train.md)   
 [Machine Learning / Initialize Model / Clustering](machine-learning-initialize-model-clustering.md)
