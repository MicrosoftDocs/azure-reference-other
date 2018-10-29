---
title: "Execute Python Script | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/24/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cdb56f95-7f4c-404d-bde7-5bb972e6f232
caps.latest.revision: 12
author: rastala
ms.author: roastala
manager: cgronlun
---
# Execute Python Script

*Executes a Python script from an Azure Machine Learning experiment*

Category: [Python Language Modules](python-language-modules.md)

## Module overview

This article describes how to use the **Execute Python Script** module in Azure Machine Learning Studio, to run Python code as part of your Studio experiments.

By using Python, you can perform custom tasks, create visualizations, and share your models with the world. For example:

+ Visualize data using `matplotlib`
+ Use Python client libraries to enumerate datasets and models in your workspace
+ Read, load, and manipulate data from sources not supported by the [Import Data](import-data.md) module

The **Execute Python Script** module contains sample Python code that you can use as a starting point when developing new code.

## Examples

For examples of how to integrate Python script with Azure Machine Learning experiments, see these resources:

- [Execute Python scripts in Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/machine-learning-execute-python-scripts)

- [Creating an Azure VM, installing Jupyter, and running a Jupyter Notebook on Azure](https://docs.microsoft.com/azure/virtual-machines/linux/jupyter-notebook)

- [Access datasets with Python using the Azure Machine Learning Python client library](https://docs.microsoft.com/azure/machine-learning/machine-learning-python-data-access)  

The following experiments in the [Azure AI Gallery](https://gallery.cortanaintelligence.com/) use Python:

- [Execute Python Script](http://go.microsoft.com/fwlink/p/?LinkId=525942): This sample demonstrates text tokenization, stemming, and other processing using the **Execute Python Script** module.
- [Custom R and Python scripts in Azure ML](https://gallery.cortanaintelligence.com/Tutorial/5-Custom-Scripts-R-and-Python-in-AML-1): Walks you through the process of adding custom code a(either R or Python), processing data, and visualizing the results.
- [Analyzing PyPI Data to Determine Python 3 Support](https://gallery.cortanaintelligence.com/Notebook/Analyzing-PyPI-Data-to-Determine-Python-3-Support-2): This fun sample uses Python code and Python data to estimate the point when demand for Python 3 outstrips that for Python 2.7.

## How to use Execute Python Script

To configure the **Execute Python Script** module, you provide a set of inputs, and type the Python code to execute in the **Python script** text box.

1. Add the **Execute Python Script** module to your experiment.

2. Scroll to the bottom of the **Properties** pane, and for **Python Version**, select the version of the Python libraries and runtime to use in the script.

    + Anaconda 2.0 distribution for Python 2.7.7
    + Anaconda 4.0 distribution for Python 2.7.11
    + Anaconda 4.0 distribution for Python 3.5 (default)

    We recommend that you set the version before typing any new code. If you change the version later, a prompt asks you to acknowledge the change.

    > [!IMPORTANT]
    > If you use multiple instances of the **Execute Python Script** module in your experiment, you must choose a single version of Python for all modules in the experiment.

3. Add and connect on **Dataset1** any datasets from Studio that you want to use for input. Reference this dataset in your Python script as **DataFrame1**.

    Use of a dataset is optional, if you want to generate data using Python, or use Python code to import the data directly into the module.

    This module supports addition of a second Studio dataset on **Dataset2**. Reference this in your Python script as DataFrame2.

    Datasets stored in Studio are automatically converted to **pandas** data.frames when loaded with this module.

4. To include new Python packages or code, add the zipped file containing these custom resources  on **Script bundle**. The input to **Script bundle** must be a zipped file already uploaded to your workspace. For more information about how to prepare and upload these resources, see [Unpack Zipped Data](unpack-zipped-datasets.md).

    Any file contained in the uploaded zipped archive can be used during experiment execution. If the archive includes a directory structure, the structure is preserved, but you must prepend a directory called **src** to the path.

5. In the **Python script** text box, type or paste valid Python script.

    The **Python script** text box is pre-populated with some instructions in comments, and sample code for data access and output. **You must edit or replace this code.** Be sure to follow Python conventions about indentation and casing.

    + The script must contain a function named `azureml_main` as the entry point for this module.
    + The entry point function can contain up to two input arguments: `Param<dataframe1>` and `Param<dataframe2>`
    + Zipped files connected to the third input port are unzipped and stored in the directory, `.\Script Bundle`, which is also added to the Python `sys.path`. 

    Therefore, if your zip file contains `mymodule.py`, import it using `import mymodule`.

    + A single dataset can be returned to Studio, which must be a sequence of type `pandas.DataFrame`. You can create other outputs in your Python code and write them directly to Azure storage, or create visualizations using the **Python device**.

6. Run the experiment, or select the module and click **Run selected** to run just the Python script.

    All of the data and code is loaded into a virtual machine, and run using the specified Python environment.

### Results

The module returns these outputs:  
  
- **Results Dataset**. The results of any computations performed by the embedded Python code must be provided as a pandas data.frame, which is automatically converted to the Azure Machine Learning dataset format, so that you can use the results with other modules in the experiment. For more information, see [Data Table](data-table.md).

- **Python Device**. This output supports both console output and display of PNG graphics using the Python interpreter.

##  Technical notes

This section contains additional technical details and frequently asked questions.

For more information about the architecture, inception, and common uses of Python script in Azure Machine Learning, see [Azure Machine Learning and Python](https://blogs.msdn.microsoft.com/uk_faculty_connection/2016/04/22/azure-machine-learning-and-python/)

### How to attach script resources

The **Execute Python Script** module supports the use of arbitrary Python script files as inputs, provided they are prepared in advance and uploaded to your workspace as part of a .ZIP file. The module is generally limited to a single dataset as output. 

#### Upload a ZIP file containing Python code to your workspace

1. In the experiment area of Azure Machine Learning Studio, click **Datasets**, and then click **New**.

2. Select the option, **From local file**.

3. In the **Upload a new dataset** dialog box,  click the dropdown list for **Select a type for the new dataset**, and select the **Zip file (.zip)** option.  

4. Click **Browse** to locate the zipped file.

5. Type a new name for use in the workspace. The name you assign to the dataset becomes the name of the folder in your workspace where the contained files are extracted.

6. After you have uploaded the zipped package to Studio, verify that the zipped file is available in the **Saved Datasets** list, and then connect the dataset to the **Script Bundle** input port.

    All files that are contained in the ZIP file are available for use during run time: for example, sample data, scripts, or new Python packages.

    If your zipped file contains any libraries that are not already installed in Azure Machine Learning Studio, you must install the Python library package as part of your custom script.

    If there was a directory structure present, it is preserved. However, you must alter your code to prepend the directory **src** to the path.

> [!NOTE]
> Because the zip file mechanism is the only way to add custom Python modules, it might be difficult to work with large modules or many modules. In such cases, we recommend the new [Azure ML Workbench](https://docs.microsoft.com/azure/machine-learning/preview/how-to-configure-your-ide), a preview feature that greatly expands support for Python environments.

### My run failed.  How do I debug Python code and fix it?

The **Execute Python Script** module works best when the code has been factored as a function with clearly defined inputs and outputs, rather than a sequence of loosely related executable statements.

This Python module does not support features such as Intellisense and debugging. If the module fails at runtime, you can view some error details in the output log for the module. However, the full Python stack trace is not available. Thus we recommend that users develop and debug their Python scripts in a different environment and then import the code into the module. 

Some common problems that you can look for:

- Check the data types in the data frame you are returning back from `azureml_main`. Errors are likely if columns contains data types other than numeric types and strings. 

- Remove NA values from your dataset, using `dataframe.dropna()` on export from Python script. When preparing your data, use the [Clean Missing Data](clean-missing-data.md) module.

- Check your embedded code for indentation and whitespace errors. If you get the error, "IndentationError: expected an indented block", see these resources for guidance: 

   + [Python Reference - Indentation](https://docs.python.org/2/reference/lexical_analysis.html#indentation)

   + [Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)

### Known limitations

+ The Python runtime is sandboxed and does not allow access to the network or to the local file system in a persistent manner. 

+ All files saved locally are isolated and deleted once the module finishes. The Python code cannot access most directories on the machine it runs on, the exception being the current directory and its sub-directories.

    When you provide a zipped file as resource, the files are copied from your workspace to the experiment execution space, unpacked, and then used. Copying and unpacking resources can consume memory. 

+ The module can output a single data frame. It is not possible to return arbitrary Python objects such as trained models directly back to the Azure Machine Learning runtime. 

    However, you can write objects to storage or to the workspace. Another option is to use `pickle` to serialize multiple objects into a byte array and then return the array inside a data frame.

### How can I determine which Python packages are installed in Azure ML?

Azure Machine Learning Studio uses the Anaconda distribution, which includes the most important Python libraries for machine learning. 

### How does this relate to Jupyter notebooks?

Jupyter Notebooks support multiple Python environments, and can be run from Azure Machine Learning Studio, under the name **Azure Notebooks**. The datasets that you use in experiments can easily be accessed from a notebook, and the notebooks can interact with Azure ML experiments.

+ [Use Jupyter notebooks with Azure ML Workbench](https://docs.microsoft.com/azure/machine-learning/preview/how-to-use-jupyter-notebooks)

+ [Channel 9 video - Using Jupyter notebooks in Azure ML](https://channel9.msdn.com/blogs/Cloud-and-Enterprise-Premium/Using-JupyterIPython-Notebooks-in-Azure-ML)

## See also

 [Python Language Modules](python-language-modules.md)   
 [R Language Modules](r-language-modules.md)
