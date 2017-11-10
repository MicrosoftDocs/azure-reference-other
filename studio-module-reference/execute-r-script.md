---
title: "Execute R Script | Microsoft Docs"
ms.custom: ""
ms.date: 04/26/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "R"
ms.assetid: 30806023-392b-42e0-94d6-6b775a6e0fd5
caps.latest.revision: 39
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Execute R Script
*Executes an R script from an Azure Machine Learning experiment*  
  
 Category: [R Language Modules](r-language-modules.md)  
  
## Module Overview  
 You can use the **Execute R Script** module to embed R code into experiments in Azure Machine Learning.  By adding R code to this module, you can perform a variety of customized tasks that are not available in Studio. For example, you could:  
  
-   Create custom data transformations  
  
-   Formulate your own metrics for evaluating predictions  
  
-   Build models using algorithms that are not implemented as standalone modules in Studio  

### R Version

Azure Machine Learning supports both the typical distribution of R that is available from CRAN, and Microsoft R Open (MRO), which includes all the basse R packages, plus the ScaleR packages. You can specify which version to use in an experiment. However, you cannot install any other version of R into your workspace.

We recommend that you determine which packages you'll need, before choosing a distribution of R. Some packages are not compatible with both CRAN R and Microsoft R Open. 

This topic lists the packages that are supported in Azure Machine Learning, and their compatibility with CRAN R and Microsoft R Open, see [R Packages Supported by Azure Machine Learning](r-packages-supported-by-azure-machine-learning.md).

> [!NOTE]
> Currently, the [Create R Model](create-r-model.md) module is limited to use of CRAN R 3.1.0.  Therefore, if you use a custom R model in your experiment, any **Execute R Script** modules in the same experiment must also use CRAN R 3.1.0.  
  
### Supported R Packages  

The R environment in Azure Machine Learning has over 500 R packages already installed. Of course, not all are loaded by default, but you can easily load them as part of your R code.

This topic lists the packages as of April 2017, and the supported versions.

+ [R Packages in Azure machine Learning](r-packages-supported-by-azure-machine-learning.md)

Alternatively, you can add the following code to an **Execute R Script** module and run the module to get a list of current packages, as a dataset. 
  
```R  
data.set <- data.frame(installed.packages())  
maml.mapOutputPort("data.set")    
```  
### Installing New Packages
  
You can install new packages into your workspace using the **Execute R Script** module. The packages must be uploaded in zipped format, and are unpacked and loaded into the R environment when you run the module. For more information, see [How to Install New R Packages](#bkmk_AddingANewPackage) 

Packages are not persisted in the workspace when the experiment is not running. For this reason, any additional R packages that you plan to use must be available in your workspace in zipped format, so that the packages can be installed into your workspace. The entire workspace will then be deployed to the virtual container that runs your experiment.

Packages cannot be shared across modules. However, you can share R objects between modules by exposing them as datasets. For more information, see [Pass R Objects between Modules](#bkmk_PassRObj).
  
## Sample Experiments  
 There are many examples of custom R script in the [Cortana Analytics Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Student Performance sample](http://go.microsoft.com/fwlink/?LinkId=525727) uses custom R script to combine the results of evaluations for multiple models into a single dataset. This sample also uses R code in the **Execute R Script** module to compute 16 time-dependent columns.  
  
-   The [Breast Cancer sample](http://go.microsoft.com/fwlink/?LinkId=525726) uses custom code in the **Execute R Script** module to replicate positive examples and to combine metrics.  
  
-   The [Time Series Forecasting](http://go.microsoft.com/fwlink/?LinkId=525273) sample uses **Execute R Script** to generate custom metrics, and then combines them into a single table by using the [Add Rows](add-rows.md) module.  

  
## How to Use Execute R Script  
 To configure the **Execute R Script** module, you provide a set of optional inputs and the R code that is to be run in the workspace. The R code should be provided in zipped format. 
 
 > [!TIP]
 > If you need to install any additional packages, you can include them in this zipped file as well. 
  
1.  Add the **Execute R Script** module to your experiment.  You can find this module in Azure Machine Learning Studio, in the **R Language Modules** group.
  
2.  Connect any inputs needed by the script.  Inputs can include data, R packages that you added to your workspace in zipped file format, and additional R code.  
  
    -   **Dataset1**: The first input is where you attach your main dataset (optional).  
  
         The input dataset must be formatted as a CSV, TSV, or ARFF file, or you can connect  an Azure Machine Learning dataset.  
  
    -   **Dataset2**: The second input (optional) supports addition of a second dataset.  
  
         This dataset also must be formatted as a CSV, TSV, or ARFF file, or you can connect an Azure Machine Learning dataset.  
  
    -   **Script Bundle**: The third input, which is optional, takes a file in the .ZIP format. The zipped file can contain multiple files and multiple file types. For example, the zipped archive might contain R code in a script file, R objects for use by the script, an R package that itself was included in .ZIP format, or datasets in one of the supported formats.  
  
3.  Type R script into the **R Script** text box to use the datasets on the input nodes, or load an R library or R script provided as input.  
  
     To help you get started, the **R Script** text box is prepopulated with the following sample code, which you can edit or replace.  
  
    ```  
    # Map 1-based optional input ports to variables
    dataset1 <- maml.mapInputPort(1) # class: data.frame
    dataset2 <- maml.mapInputPort(2) # class: data.frame
    
    # Contents of optional Zip port are in ./src/
    # source("src/yourfile.R");
    # load("src/yourData.rdata");
    
    # Sample operation
    colnames(dataset2) <- c(dataset1['nombre_columna'])$nombre_columna;
    data.set = dataset2;
    
    # You'll see this output in the R Device port.
    # It'll have your stdout, stderr and PNG graphics device(s).   
    
    # Select data.frame to be sent to the output Dataset port
    maml.mapOutputPort("data.set"); 
    ```  
  
     For more information about how to use inputs and write to outputs, see [R Code Samples](#bkmk_RCodeSamples) in this topic. 
     
     > [!NOTE]
     >  R code that runs fine in external tools might need small changes to run in an Azure ML experiment. For example, input data that you provide in CSV format should be explicitly converted to a dataset before you can use it in your code.  Data and column types used in the R language also differ in some ways from the data and column types used in Azure Machine Learning. For details, see the [Technical Notes](#bkmk_Conversion) section.  
  
4.  For **Random Seed**, type a value to use inside the R environment as the random seed value. This parameter is equivalent to calling `set.seed(value)` in R code.  
  
5.  For **R Version**, specify the version of R to load in the workspace.  Azure Machine Learning supports multiple versions of R, but only one version can be used in any experiment.  
  
    -   **CRAN R 3.1.0**. The Comprehensive R Archive Network Web site is the repository for the open source R language.  For more information, see the [CRAN Web site](https://cran.r-project.org/).  
  
    -   **Microsoft R Open 3.2.2**. MRO is the enhanced distribution of R from Microsoft Corporation. It is an open source platform based on the open source R engine and fully compatible with all R packages, scripts and applications that work with the same version of R. However, MRO provides improved performance in comparison to the standard R distribution due to its use of high-performance, multi-threaded math libraries.  For more information, see [Microsoft R Open](https://msdn.microsoft.com/microsoft-r/index#mro).  

    -   You cannot install any other version of R into your workspace.
    
6.  Run the experiment, or select the **Execute R Script** module and click **Run selected**.  
  
### Results

The module returns multiple outputs. Typically you will generate a tabular result set for use in the experiment, but you can aso create images or other objects, save objects to the workspace, and view the standard messages and errors from R.  
  
#### **(1) Result Dataset**

This output contains the data frame that is generated by the R code in the module.  
  
You can output only one data frame. Other tabular objects must be converted to a data frame using R functions. The data frame output by the module's R code is then automatically converted to the internal [Data Table](data-table.md) format.  
  
> [!WARNING]
>  To check the returned object, use `is.data.frame`, which must return True. To return other R objects, try serializing the object into a byte array, or use a function that returns the desired data as a `data.frame`.  
  
#### **(2) R Device**

The R device supports both console output (standard output and standard error) and display of PNG graphics using the R interpreter. 
 
+ To view messages sent to the R console (Standard Output and Standard Error), right-click the module after it has finished running, select **R Device**, and select **Visualize**. 

     
+ To view graphics generated on the R Device port, right-click the module after it has finished running, select **R Device**, and select **Visualize**. 

    For example, the following image is generated by just a few lines of R code. 
    
    ![aml-execrscript-wordcloud](media/aml-execrscript-wordcloud.JPG)
    
    You can find this and related samples in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/browse?s=twitter).      

+ To save images generated by the **Execute R Script** module, you can right-click the image and save a local copy. Or, you can use a call to one of the R graphics device functions to write the image file to the Azure blob storage account associated with the experiment, as described in [this example](#bkmk_WriteGraphics).
  
## <a name = "bkmk_RCodeSamples"></a>Sample R Scripts and R Tips

There are many ways that you can extend your experiment by using custom R script.  This section provides sample code for some common tasks.
  
 To get started using R in the **Execute R Script** module, see this video: [Using R in Azure Machine Learning Studio](http://channel9.msdn.com/Blogs/Windows-Azure/R-in-Azure-ML-Studio)  

### Add an R Script as Input  

 The **Execute R Script** module supports the use of arbitrary R script files as inputs, provided they are prepared in advance and uploaded to your workspace as part of the ZIP file  
  
1. To upload a ZIP file containing R code to your workspace, click **New**, click **Dataset**, and then select **From local file** and the **Zip file** option.  
  
2. After you have uploaded the zipped package to Studio, verify that the zipped file is available in the **Saved Datasets** list, and then connect the dataset to the **Script Bundle** input port.  
  
3. If your zipped file contains any R package that is not already installed in Azure Machine Learning Studio, you must install the R package as part of the custom code in the **Execute R Script** module.  
  
    If you use this option, all files that are contained in the ZIP file will be available for use during run time. 
    
    If there was a directory structure present, it will be preserved. However, you must alter your code to prepend the directory **src** to the path.  
  
### Generate Images, Models, and Other Objects  
 
 + If you need to generate an image, or any other arbitrary R object, you can serialize it into a byte array and then as a data.frame as shown in this example:
  
    ```  
    as.data.frame(as.integer(serialize(g,con=NULL)));   
    ```  
  
+ Graph data frames from the [http://igraph.org/r/](http://igraph.org/r/) library do not support serialization as a data frame. 
 
    Instead, use the `get.data.frame` function in the `igraph` package to put the edge and vertex information into a data frame.  
  
    ```  
    vertices <- get.data.frame(g, what="vertices")   
    ```  
   You could then return the graph object as a data.frame that you can get from the **Execute R Script** module.  
  
    ```  
    edges <- get.data.frame(g, what="edges")  
    ```  
  
  
### Read from Input and Write to Output  

 The following example demonstrates how to use input and output ports.
 
 It reads the input data as a table, and appends a copy of the table to itself, effectively doubling the size of the table. The result is then sent to the output port.  
  
```  
# Map existing dataset to first input port  
dataset1 <- maml.mapInputPort(1) # class: data.frame  
# Concatenate dataset1 to dataset 1  
newdataset = rbind(dataset1, dataset1)  
# Send the combined dataset to the output port  
maml.mapOutputPort("newdataset");  
```  
  
### Read a ZIP File as Input  
 
 This example demonstrates how to add a dataset to Azure Machine Learning Studio in zipped format and then use the data as an input to the **Execute R Script** module.
 
1. Create the data file in CSV format, and name it “mydatafile.csv”.
2. Create a .ZIP file and add the CSV file to the archive.
3. Upload the zipped file to your Azure Machine Learning workspace as described here: [Unpack Zipped Datasets](unpack-zipped-datasets.md). 
4. Connect the resulting dataset to the **ScriptBundle** input of your **Execute R Script** module. In other words, do not unpack it yet!
5. Using the following code, read the CSV data from the zipped file.  Specify the encoding that is used in the data file if necessary, to avoid errors later.
  
    ```R   
    mydataset=read.csv("src/newdata.csv",encoding="UTF-8");  
    nrow(mydataset);  
    ncol(mydataset);  
    # Map new dataset to the first output port  
    maml.mapOutputPort("mydataset");  
    ```  
  
> [!NOTE]
> All data that is passed to the **Execute R Script** module will be converted to the `data.frame` format for use with your R code. This applies to any data that is compatible with the `DataTable format` used by Azure Machine Learning, including CSV files, ARFF files, and so on.  
  
### Replicate Rows  

Here's an easy way to replicate the positive samples in a dataset by a factor of 20 to balance the sample.  
  
```R  
dataset <- maml.mapInputPort(1)   
  
data.set <- dataset[dataset[,1]==-1,]  
pos <- dataset[dataset[,1]==1,]  
for (i in 1:20) data.set <- rbind(data.set,pos)  
row.names(data.set) <- NULL  
  
maml.mapOutputPort("data.set")  
```  
  
### Call a Custom Learner – R Arules Package  
 
 You can install new R packages to your Azure Machine Learning workspace by uploading them as a .ZIP file, as described [here](#bkmk_AddingANewPackage). The following code demonstrates how to use the uploaded package. 
 
 1. Assume that the `arules` and `arulesViz` packages have already been added to the workspace.
 2. Connect the uploaded .ZIP file to the third input port of the **Execute R Script**module. 
 3. In the **R Script** text box, use the following to call the *a priori* association rules algorithm provided by the R language package `Arules`, and apply the learner in a market basket analysis task.  
  
    ```R  
    library("arules")  
    library("arulesViz")  
    dataset <- read.transactions(file="src/SalesReport.csv", rm.duplicates= TRUE,     format="single",sep=",",cols =c(1,2))  
    #dataset <- sapply(dataset,as.factor)  
    basket <- apriori(dataset,parameter = list(sup = 0.5, conf = 0.9,target="rules"));  
    inspect(basket)  
    plot(basket)  # if this is not NULL i.e. if there are rules    
    ```  
  
### Call a Custom Learner – Naïve Bayes  
 
 Here is another example of how you can call an R library that is not included in Studio. 
 
 1. Upload a zipped file containing the `e1071` library to your workspace.  
 2. Connect the uploaded .ZIP file to the third input port of the **Execute R Script**module. 
 3. In the **R Script** text box, use the following code to implement the Naïve Bayes learner. 
  
    ```R  
    library(e1071)  
    features <- get.feature.columns(dataset)  
    labels   <- get.label.column(dataset)  
    train.data <- data.frame(features, labels)  
    feature.names <- get.feature.column.names(dataset)  
    names(train.data) <- c(feature.names, "Class")  
    model <- naiveBayes(Class ~ ., train.data)    
    ``  
4. Suppose you need to use a custom scorer provided by the `e1071` library?
    
    If you perform scoring in a separate instance of the **Execute R Script** module, you must provide the zipped file containing the `e1071` library as an input to the scoring module, and specify that the library be loaded.  
  
    ```R  
    library(e1071)  
    features <- get.feature.columns(dataset)  
    scores <- predict(model, features)  
    ```  
    
    That is because each module runs independently in a container.
    
    However, all R modules that are included inside a single experiment must use the same version of the R runtime. You cannot mix version of R, such as using CRANR in one module and Microsoft R Open in another.
      
### <a name="bkmk_WriteGraphics"></a>Write a Graphics File  
 
  Although Studio supports the display of PNG files using the **R Device** output port, you might want to generate the results as a PDF file in a blob in Azure Storage to use for reporting.  
  
  This example demonstrates how to use the **Execute R Script** to generate a chart as a PDF file. 
  
1. Add the **Execute R Script** to the experiment.
2. Create the basic PDF file as part of your R script, and return the Base64-encoded string of the PDF file from the **Execute R Script** module. 

    ```R  
    d <- maml.mapInputPort(1)  
    d$dteday <- as.numeric(d$dteday)  
    pdf()  
    plot(d)  
    dev.off()  
    library(caTools)  
    b64ePDF <- function(filename) {  
                maxFileSizeInBytes <- 5 * 1024 * 1024 # 5 MB  
                return(base64encode(readBin(filename, "raw", n = maxFileSizeInBytes)))  
    }  
      
    d2 <- data.frame(pdf = b64ePDF("Rplots.pdf"))  
      
    maml.mapOutputPort("d2");    
    ```

3. Pass this output to a [Export Data](export-data.md) module, and save the binary values to Azure blob storage.  

   
### <a name="bkmk_PassRObj"></a>Pass R Objects Between Execute R Script Modules  

 You can pass R objects between instances of the **Execute R Script** module by using the internal serialization mechanism. Assume that you want o move the R object named `A` between two **Execute R Script** modules.  
  
1. Add the first **Execute R Script** module to your experiment, and type the following code in the **R Script** text box to create a serialized object `A` as a column in the module’s output Data Table:  
  
    ```  
    serialized <- as.integer(serialize(A,NULL))  
    data.set <- data.frame(serialized,stringsAsFactors=FALSE)  
    maml.mapOutputPort("data.set")    
    ```  
  
     The explicit conversion to integer type is required because the serialization function outputs data in the R `Raw` format, which is not supported by Azure Machine Learning.  
  
2. Add a second instance of the **Execute R Script** module, and connect it to the output port of the previous module.

3. Type the following code in the **R Script** text box to extract object `A` from the input Data Table. 
  
    ```  
    dataset <- maml.mapInputPort(1)  
    A <- unserialize(as.raw(dataset$serialized))  
    ```  

##  <a name="bkmk_AddingANewPackage"></a> How to Install New R Packages  
 You can add R packages that are not installed by default in Azure Machine Learning. Adding new packages requires these steps:  
  
-   Obtain the Windows binaries in zipped format.  
  
-   Zip the desired package and any dependencies into a new single compressed archive  file with the .ZIP format.  
  
-   Upload the zipped file as a dataset to your workspace.  
  
-   Connect the new dataset to the **Execute R Script** module.  
  
-   Install the package using R script in a module.  
  
 The following procedure describes in detail how to add  a new package together with  its dependencies.  
  
1.  Download the zipped file for the package that you want to import to Azure Machine Learning. Be sure to get the Windows version of the zipped file. Other versions will not work.  
  
    > [!NOTE]
    >  If you have already extracted the R package that you want to use in your workspace, you must either re-zip the package, or provide the original ZIP file when you can upload the R package to Studio.  
  
     Check for any dependencies and if the package needs other packages that are not already in Azure ML Studio, download them in zipped format.  
  
2.  Right-click the zipped files for the package you want to upload, as well as its dependencies, and select **Send to\*\* and then select \*\*Compressed (zipped) folder\*\*.  
  
    > [!TIP]
    >  You have to create a compressed folder containing at least one zipped file with the target package, plus additional  zip files containing required packages -- in other words, a .zip of a .zip.  
  
3.  Upload the ZIP file containing the package to your workspace. You do this like you would upload a dataset: Click **New**, click **Dataset**, and then select **From local file** and the **Zip file** option.  
  
     Open the **Saved Datasets** list, click **My Datasets**, and verify that the zipped file is available.  
  
4.  Drag it into your experiment, right-click the dataset, and select **Visualize** to view the files included in the zipped folder. The file names that you see in the **Contents** list are the names that you must reference when you install the package.  
  
     For example, suppose you had uploaded a file named `NewRPackage.zip`, which contains three R packages named `001.zip`, `002.zip`, and `003.zip`. In the **Datasets** list, the name of the dataset would be `NewRPackage.zip`, with  contents  `001.zip`, `002.zip`, and `003.zip`.  
  
5.  Connect the dataset (`NewRPackage.zip`) to the **Script Bundle** input port.  
  
     At this point, the outer zipped folder  will be extracted into the workspace sandbox, in the path `src`. You would now have the following packages available to you:  
  
    -   `src\001.zip`  
  
    -   `src\002.zip`  
  
    -   `src\003.zip`  
  
6.  To install the R packages, you extract each package from its zip file, and then load the contained library.  
  
     For example, assuming the file `src\001.zip` contains the custom R package `code001`, you would run the following script:  
  
    ```  
    # install R package contained in src\001.zip  
    install.packages("src/001.zip", lib = ".", repos = NULL, verbose = TRUE)  
    library(code001, lib.loc=".", verbose=TRUE)  
  
    ```  
  
7.  Repeat for any required packages.  
  
    ```  
    # install R package contained in src\002.zip  
    install.packages("src/002.zip", lib = ".", repos = NULL, verbose = TRUE)  
    library(code002, lib.loc=".", verbose=TRUE)  
    # install R package contained in src\003.zip  
    install.packages("src/003.zip", lib = ".", repos = NULL, verbose = TRUE)  
    library(code003, lib.loc=".", verbose=TRUE)  
    ```  
  
    > [!NOTE]
    >  If there are any dependencies among multiple packages being installed, be sure to install required packages first, or you might get an error.  
  
 Note that installation of the R packages must be performed as part of the experiment to ensure that all required packages are included in the workspace that is sent to the Azure job queue when your experiment is executed.  
  
 Packages in a workspace are not persisted after the experiment has run or after you have closed your session. However, any packages that you have uploaded as zipped files can be quickly extracted and used when you re-run the experiment.  
  
## Technical Notes  
  
### Optimizing R Performance in Azure Machine Learning Studio  
 The current default memory is 14 GB. You might encounter an out-of-memory error message if you attempt to manipulate very large data frames by using the **Execute R Script** module.  
  
 To increase the amount of memory that is used by R script, you can use a line similar to this at the beginning of the script:  
  
```  
memory.limit(56000)  
```  
  
 User-specified R code is run by a 64-bit R interpreter that runs in Azure using an A8 virtual machine with 56 GB of RAM. To increase the speed of your R code, you can use the just-in-time compiler provided in the preinstalled **Compiler** package.  
  
###  <a name="bkmk_Conversion"></a> Converting Column Data Types Between R and Studio  
 The following table shows how the data types in R correspond to the data types in Azure Machine Learning:  
  
|R type|Studio type|  
|------------|-----------------|  
|Integer|Integer|  
|Double|Double|  
|Complex|Complex<br /><br /> This type is supported by only a subset of modules.|  
|Logical|Boolean|  
|Character|String|  
|Raw|Not supported|  
|Difftime|TimeSpan|  
|factor|categorical|  
|data.frame|dataset|  
  
 Columns of data type `lists` in R cannot be converted because the elements in such columns potentially are of different types and sizes. For example, the following valid R code will fail if used in the **Execute R Script** module:  
  
```  
data.set <- data.frame(r=I(list(list(1,2,3),list(4,5))))  
maml.mapOutputPort("data.set")  
  
```  
  
### Converting DateTime Values  
 Azure Machine Learning Studio uses different datetime types than does R. If the data that you are analyzing contains date or time data, you should be aware of the following conversion requirements when porting existing R code into Studio:  
  
 **To convert from Azure Machine Learning Studio to R:**  
  
 DateTime columns are converted to POSIXct vectors. However, each individual element of the resulting vector is a number of seconds since 1970-01-01T00:00:00. No time zone adjustments are made in this conversion.  
  
 **To convert from R to Azure Machine Learning Studio:**  
  
 POSIXct vectors are converted to DateTime columns in the UTC time zone.  
  
 For example, 2011-03-27 01:30:00 PDT will be converted to 2011-03-27T08:30:00Z, where the Z indicates that the time is in UTC.  
  
> [!TIP]
>  When using times inside the **Execute R Script** module, you must specify time stamps explicitly. The R interpreter hosted in the **Execute R Script** module does not have access to local time zone definitions.  

  
### Networking  
 For security reasons, all networking from or to R code in **Execute R Script** modules is blocked by Azure. Also, with very few exceptions, access to local ports from the **Execute R Script** is blocked.  
  
### Parallel Execution  
 Currently parallel execution with multiple threads is not supported.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|*Dataset1*|[Data Table](data-table.md)|Input dataset 1|  
|*Dataset2*|[Data Table](data-table.md)|Input dataset 2|  
|*Script Bundle*|Zip|Set of R sources|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|R Script|Any|StreamReader||Specify a `StreamReader` that points to the R script sources.|  
|Random Seed|>=0|Integer||Define a random seed value for use inside the R environment.<br /><br /> Equivalent to `\"set.seed(value)\"`.<br /><br /> This parameter is optional.|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Result Dataset|[Data Table](data-table.md)|Output dataset|  
|R Device|[Data Table](data-table.md)|Console output and PNG graphics device from the R interpreter|  
  
## See Also  
 [R Language Modules](r-language-modules.md)   
 [Create R Model](create-r-model.md)   
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [Python Language Modules](python-language-modules.md)   
 [A-Z Module List](a-z-module-list.md)