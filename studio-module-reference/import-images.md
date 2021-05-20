---
title: "ML Studio (classic): Import Images - Azure"
description: Learn how to use the Import Images module to get multiple images from Azure Blob storage and create an image dataset from them.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Import Images

*Loads images from Azure BLOB Storage into a dataset*

Category: [OpenCV Library Modules](opencv-library-modules.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the [Import Images](import-images.md) module in Azure Machine Learning Studio (classic), to get multiple images from Azure Blob storage and create an image dataset from them.

When you use this module to load images from blob storage into your workspace, each image is converted to a series of numeric values for the red, green, and blue channels, together with the image file name.  A dataset of such images consists of multiple rows in a table, each with a different set of RGB values and corresponding image file names. For instructions about how to prepare your images and connect to blob storage, see [How to Import Images](#HowToImportImages). 

After you have converted all your images, you can then pass this dataset to the [Score Model](score-model.md) module, and connect a pre-trained image classification model to predict the image type.  

You can import any kind of images used for machine learning; however, there are limitations, including the types and size of images that can be processed, see the [Technical notes](#bkmk_Notes) section.

## <a name="HowToImportImages"></a> How to use Import Images

This example assumes that you have uploaded multiple images to your account in Azure blob storage. The images are in a container designated for that purpose only.  As a rule, each image must be fairly small and have the same dimensions and color channels. For a detailed list of requirements that apply to images, see the [Technical notes](#bkmk_Notes) section.

1. Add the [Import Images](import-images.md) module to your experiment in Studio (classic).

2. Add the [Pretrained Cascade Image Classification](pretrained-cascade-image-classification.md) and the [Score Model](score-model.md) module.

3. In the [Import Images](import-images.md) module, configure the location of the images, and provide the authentication method, private or public:

    - If the image set is in a blob that has been configured for public access through [Shared Access Signatures](https://azure.microsoft.com/documentation/articles/storage-dotnet-shared-access-signature-part-1/)(SAS), type the URL to the container that holds the images.

    - If the images are stored in a private account in Azure storage, select **Account**, and then type the account name as it appears in the management portal.  Then, paste in the primary or secondary account key.

    - For **Path to container**, type just the container name, and no other path elements.

4. Connect the output of [Import Images](import-images.md) to the [Score Model](score-model.md) module.

5. Run the experiment.

### Results

Each row of the output dataset contains data from one image. The rows are sorted alphabetically by image name, and the columns contain the following information, in this order:

- The first column contains image names.
- All other columns contain flattened data from the red, green, and blue color channels, in that order.
- The transparency channel is ignored.

Depending on the color depth of the image and the image format, there could be many thousands of columns for a single image. Therefore, to view the results of the experiment, we recommend that you add the [Select Columns in Dataset](select-columns-in-dataset.md) module, and select only these columns:

- Image Name
- Scored Labels
- Scored Probabilities

## <a name="bkmk_Notes"></a> Technical notes

This section contains implementation details, tips, and answers to frequently asked questions

### Supported image formats

The **Import Images** module determines the type of an image by reading the first few bytes of the content, not by the file extension. Based on that information, it determines whether the image is one of the supported image formats.

- Windows bitmap files: .bmp, .dib
- JPEG files: .jpeg, .jpg, .jpe
- JPEG 2000 files: .jp2
- Portable Network Graphics: .png
- Portable image format: .pbm, .pgm, .ppm
- Sun Raster: .sr, .ras
- TIFF files: .tiff, .tif

### Image requirements

The following requirements apply to images processed by the [Import Images](import-images.md) module:

- All images must be the same shape.
- All images must have the same color channels. For example, you cannot mix grayscale images with RBG images.
- There is a limit of 65536 pixels per image. However, the number of images is not limited.
- If you specify a blob container as the source, the container must not contain other types of data. Ensure that the container contains only images before running the module.

### Other restrictions

- If you intend to use the [Pretrained Cascade Image Classification](pretrained-cascade-image-classification.md) module, be aware that it currently supports only recognition of faces in frontal view; other image classifiers are not yet available.

- You cannot use image datasets with these modules:  [Train](machine-learning-train.md), [Cross-Validate Model](cross-validate-model.md). 

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Please specify authentication type|List|AuthenticationType|Account|Public or Shared Access Signature (SAS) URI or user credentials|  
|URI|Any|String|none|Uniform Resource Identifier with SAS or public access|  
|Account name|Any|String|none|Name of the Azure Storage account|  
|Account key|Any|SecureString|none|Key associated with the Azure Storage account|  
|Path to container, directory or blob|Any|String|none|Path to blob or name of table|  

## Output

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with downloaded images|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more inputs are null or empty.|  
|[Error 0029](errors/error-0029.md)|Exception occurs when invalid URI is passed.|  
|[Error 0009](errors/error-0009.md)|Exception occurs if the Azure storage account name or container name is specified incorrectly.|  
|[Error 0015](errors/error-0015.md)|Exception occurs if the database connection has failed.|  
|[Error 0030](errors/error-0030.md)|Exception occurs when it is not possible to download a file.|  
|[Error 0049](errors/error-0049.md)|Exception occurs when it is not possible to parse a file.|  
|[Error 0048](errors/error-0048.md)|Exception occurs when it is not possible to open a file.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Pretrained Cascade Image Classification](pretrained-cascade-image-classification.md)   
 [A-Z Module List](a-z-module-list.md)
