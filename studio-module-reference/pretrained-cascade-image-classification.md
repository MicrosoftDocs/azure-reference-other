---
title: "ML Studio (classic): Pretrained Cascade Image Classification - Azure"
description: Learn how to use the Pretrained Cascade Image Classification module to detect faces in images. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Pretrained Cascade Image Classification

*Creates a pretrained image classification model for frontal faces using the OpenCV Library*

Category: [OpenCV Library Modules](opencv-library-modules.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Pretrained Cascade Image Classification** module in Machine Learning Studio (classic), to detect faces in images. 

The model is based on the [OpenCV](https://opencv.org/) library. The OpenCV Library provides a list of predefined models, each optimized to detect a particular type of object.

### More about the pre-trained model

This image recognition model has already been trained on a large corpus of images that is widely used for image recognition tasks. This particular classification model has been optimized for facial detection, and uses the Viola-Jones object detection algorithm. The purpose of the model is to identify images that contain a human face in frontal view.

Although currently only one OpenCV image classification model is provided, additional pretrained models might be available in later releases.

### Using a pre-trained model

If you have a set of images that you would like to analyze, you provide them as input to the [Score Model](score-model.md) module as described in this topic, and attach this module, which provides the pretrained OpenCV library model.

The **Score Model** module uses the image classification model to determine whether the image contains a human face, and returns a probability score for each image used as input.

Models based on **Pretrained Cascade Image Classification** cannot be retrained on new image data.

The format in which the model is stored is incompatible with the [Train Model](train-model.md) and [Cross-Validate Model](cross-validate-model.md) modules.

## How to configure Pretrained Cascade Image Classification

The image classification model in Machine Learning has already been trained using a large dataset and is optimized for a specific image type. Therefore, all you need to do is provide a set of images as a *scoring dataset*. As an output, the module generates a score that indicates whether each image contains the target image type.

1. Prepare and import the dataset of images you plan to use in scoring. In general, all images in the dataset should be the same size.

    You add the images to your experiment by using the [Import Images](import-images.md) module. Read the help for [Import Images](import-images.md) closely to ensure that the images you use meet the requirements. You must also ensure that the images are accessible in the defined storage option.

2. Add the **Pretrained Cascade Image Classification** module to your experiment in Studio (classic). You can find this module in the **OpenCV Library** category.  

3. Select one of the pre-trained classifiers from the list in **Pre-trained classifier**.

    Currently, only one classifier is available: **Frontal face**, which is selected by default.

4. **Scale factor**: Type a value that specifies how much the image size is reduced at each image scale.

    In the OpenCV Library, the classifier is designed so that it can be easily “resized” in order to be able to find the objects of interest at different sizes. This is more efficient than resizing the image itself. Thus, to find an object of an unknown size in the image the scan procedure should be done several times at different scales.

    We recommend that you try different scaling factors to see which provides the best image classification results.

5. **Minimum number of neighbors**: Type a whole number that represents the minimum number of overlapping rectangles that are required to detect that a face is included in a region.

    In the OpenCV library, the classifier detects objects of different sizes in the input image. The detected objects are returned as a list of rectangles. The *neighbors* parameter controls how many possible matches are required to qualify as a detected face or feature. Thus, increasing this value tends to increase precision at the cost of coverage.

    For examples of how neighbors are calculated, see this article in the OpenCv Library documentation: [Eigenfaces in OpenCV](https://docs.opencv.org/modules/contrib/doc/facerec/facerec_tutorial.html?highlight=neighbor)

6. Optionally, you can use the following settings to specify image size to the model so that it can make better predictions. Images that do not fit the requirements are eliminated:

    - **Minimum height**: Type the pixel height of the smallest image. If you specify a value for this property, images smaller than this are ignored.

    - **Maximum height**. Type the pixel width of the largest image. If you specify a value for this property, images larger than this are ignored.

    - **Minimum width**: Type the pixel width of the smallest image. If you specify a value for this property, images smaller than this are ignored.

    - **Maximum width**: Type the pixel width of the largest image. If you specify a value for this property, images larger than this are ignored.

7. Connect the image dataset used for scoring.

8. Add the [Score Model](score-model.md) module to your experiment, and connect the pre-trained image classifier,  and your dataset of images.  

9.  Run the experiment.

### Results

The output of [Score Model](score-model.md) includes the image name, the scored label, and the probability score for the label (either 0 or 1). The classifier outputs a “1” if the image is likely to show the object (a face), and “0” otherwise. For example:

|Image name|Scored Labels|Scored Probabilities|  
|----------------|-------------------|--------------------------|  
|MAN001.png|TRUE|1|  
|TABLE001.PNG|FALSE|0|  
|CHAIR001.PNG|FALSE|0|  

> [!TIP]
> The output also contains the RGB values for all color channels in the dataset. Therefore, to view the data more easily, we recommend that in your experiment you use [Select Columns in Dataset](select-columns-in-dataset.md) to output just the result columns.

## Technical notes

The facial recognition model provided by this module is based on the Viola-Jones face detection algorithm. For more information, see these resources:

- This video explains the basic concepts of facial recognition, including a definition of *Haar features* and how they are used in facial detection: [Facial Detection - Part 1](https://youtu.be/sWTvK72-SPU)  

- This Wikipedia article describes the method used for the classifier, based on the paper by Navneet Dalal and Bill Triggs: [Histogram of oriented gradients](https://en.wikipedia.org/wiki/Histogram_of_oriented_gradients)

- For the documentation of the face recognition algorithm provided in the OpenCV library, see [Cascade Classifier](https://docs.opencv.org/modules/objdetect/doc/cascade_classification.html?highlight=detectmultiscale).

> [!NOTE]
> This module does not output the full collection of information produced by the OpenCV library. In particular, this module only outputs the prediction of whether a face is present or not, and does not include the coordinates of the face or any other information.
>   
> If you need this additional information, consider using other libraries, such as the [Face API](https://www.microsoft.com/cognitive-services/en-us/face-api) provided by [Microsoft Cognitive Services](https://www.microsoft.com/cognitive-services).  

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Pre-trained classifier|List|PretrainedClassifier|Frontal face|Pretrained classifier from standard OpenCV distribution.|  
|Scale factor|>=1.0000000000000002|Float|1.1|Parameter that specifies how much the image size is reduced at each image scale.|  
|Minimum number of neighbors|>=0|Integer|3|Parameter that specifies how many neighbors each candidate rectangle should have to retain it.|  
|Minimum height|>=1|Integer|100|Minimum possible object height (in pixels). Objects smaller than this are ignored.<br /><br /> The parameter is optional.|  
|Minimum width|>=1|Integer|100|Minimum possible object width (in pixels). Objects smaller than this are ignored.<br /><br /> The parameter is optional.|  
|Maximum height|>=1|Integer|200|Maximum possible object height (in pixels). Objects larger than this are ignored.<br /><br /> The parameter is optional.|  
|Maximum width|>=1|Integer|200|Maximum possible object width (in pixels). Objects larger than this are ignored.<br /><br /> The parameter is optional.|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained binary classification model|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0005](errors/error-0005.md)|Exception occurs if parameter is less than a specific value.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).

## See also

 [Import Images](import-images.md)   
 [Pretrained Cascade Image Classification](pretrained-cascade-image-classification.md)
 
