---
title: "Execute Python Script | Microsoft Docs"
ms.custom: ""
ms.date: 05/23/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cdb56f95-7f4c-404d-bde7-5bb972e6f232
caps.latest.revision: 12
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Execute Python Script
*Executes a Python script from an Azure Machine Learning experiment*  
  
 Category: [Python Language Modules](python-language-modules.md)  
  
## Module Overview  
 You can use the **Execute Python Script** module to run Python code from experiments in Azure Machine Learning.  
  
 By integrating your IPython notebooks with Azure Machine Learning, you can perform custom tasks, create visualizations, and share your models with the world. For example, you could:  
  
-   Visualize data using matplotlib  
  
-   Use Python client libraries to enumerate datasets and models in your workspace  
  
-   Read, load, and manipulate data  
  
 The **Execute Python Script** module contains sample Python code that you can use as a starting point when developing new code.  
  
## Examples  
 For examples of how to integrate Python script with Azure Machine Learning experiments, see these resources:  
  
-   [Execute Python scripts in Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/machine-learning-execute-python-scripts)  
  
-   [Creating an Azure VM, installing Jupyter, and running a Jupyter Notebook on Azure](https://docs.microsoft.com/azure/virtual-machines/linux/jupyter-notebook)  
  
-   [Access datasets with Python using the Azure Machine Learning Python client library](https://docs.microsoft.com/azure/machine-learning/machine-learning-python-data-access)  
  
 The following experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/) also use Python:  
  
-   The [Execute Python Script](http://go.microsoft.com/fwlink/p/?LinkId=525942) sample demonstrates how you can perform complex processing – in this case, text tokenization, stemming, and other processing – inside the **Execute Python Script** module.  
  
## How to Use Execute Python Script  
 To configure the **Execute Python Script** module, you provide a set of inputs, and type the Python code to execute in the **Python script** text box.  
  
1.  Add the **Execute Python Script** module to your experiment.  
  
2.  Connect any datasets that you want to use for input. You can also provide a zipped file containing custom resources.  
  
    -   **Dataset1**.   An optional dataset from your Machine Learning Studio workspace, containing input data or values. You can reference this in your Python script as DataFrame1. 
  
    -   **Dataset2**.   A second dataset, also optional. You can reference this in your Python script as DataFrame2. 
  
    -   **Script bundle**.   A zipped file containing custom resources. The file must have already been uploaded to your workspace. For more information about how to prepare and upload these resources, see the Technical Notes section.  
  
         Any file contained in the uploaded resource file will be available for use during execution time. If there is a directory structure present it will be preserved, with the only change being that you must prepend a directory called **src** to the path.  
  
3.  In the **Python script** text box, type or paste valid Python script. The **Python script** text box is pre-populated with the following sample code, which you can edit or replace. Note that Python conventions about indentation and casing must be observed. 
  
    ```  
    # The script must contain a function named azureml_main as the entry point for this module.  
    # The entry point function can contain up to two input arguments:  
    #   Param<dataframe1>: a pandas.DataFrame  
    #   Param<dataframe2>: a pandas.DataFrame  
    def azureml_main(dataframe1 = None, dataframe2 = None):  
  
        # Execution logic goes here  
        print('Input pandas.DataFrame #1:\r\n\r\n{0}'.format(dataframe1))  
  
        # If a zip file is connected to the third input port is connected,  
        # it is unzipped under ".\Script Bundle". This directory is added  
        # to sys.path. Therefore, if your zip file contains a Python file  
        # mymodule.py you can import it using:  
        # import mymodule  
  
        # Return value must be of a sequence of pandas.DataFrame  
        return dataframe1,  
  
    ```  
  
4.  For **Python Version**, select the version of the Python libraries and runtime to use in the script.  
  
    -   Anaconda 2.0 distribution for Python 2.7.7  
  
    -   Anaconda 4.0 distribution for Python 2.7.11 
  
    -   Anaconda 4.0 distribution for Python 3.5  
  
    > [!NOTE]
    >  If you use multiple instances of the **Execute Python Script** module in your experiment, you must choose a single version of Python for all modules in the experiment.  
  
5.  Run the experiment, or select the module and click **Run selected** to run just the Python script.  
  
6.  The module returns these outputs:  
  
-   **Results Dataset**.   A dataset with the results of any computations performed by the embedded Python code.  
  
     The output data is provided in  the Azure Machine Learning dataset format. For more information, see [Data Table](data-table.md).  
  
-   **Python Device**.    This output supports both console output and display of PNG graphics using the Python interpreter.  
  
##  <a name="bkmk_TechnicalNotes"></a> Technical Notes  
 Before you can connect the Script Bundle to the **Execute Python Script** module, the ZIP file must be already present in the Studio workspace. To upload a ZIP file to your workspace, click **New**, click **Dataset**, and then select **From local file** and the **Zip file** option.  
  
### Adding Python Script as a Custom Resource  
 The **Execute Python Script** module supports the use of arbitrary Python script files as inputs, provided they are prepared in advance and uploaded to your workspace as part of a ZIP file.  
  
##### To upload a ZIP file containing Python code to your workspace  
  
1.  In the experiment area of Azure Machine Learning Studio, click **Datasets**, and then click **New**.  
  
2.  Select the  option, **From local file**.  
  
3.  In the **Upload a new dataset** dialog box,  click the dropdown list for **Select a type for the new dataset**, and select the **Zip file (.zip)** option.  
  
4.  Click **Browse** to locate the zipped file.  
  
5.  Type a new name for use in the workspace. The name you assign to the dataset will become the name of the folder in your workspace to which the contained files will be extracted.  
  
     All files that are contained in the ZIP file will be available for use during run time. If there was a directory structure present, it will be preserved. However, you must alter your code to prepend the directory **src** to the path.  
  
6.  After you have uploaded the zipped package to Studio, verify that the zipped file is available in the **Saved Datasets** list, and then connect the dataset to the **Script Bundle** input port.  
  
7.  If your zipped file contains any libraries that are not already installed in Azure Machine Learning Studio, you must install the Python library package as part of your custom script.  
  
## See Also  
 [Python Language Modules](python-language-modules.md)   
 [R Language Modules](r-language-modules.md)