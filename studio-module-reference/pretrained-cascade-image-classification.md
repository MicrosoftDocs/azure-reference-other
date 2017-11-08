---
title: "Pretrained Cascade Image Classification | Microsoft Docs"
ms.custom: ""
ms.date: 02/16/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 403eb35a-83b2-4191-a212-7716292c7a5b
caps.latest.revision: 22
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Pretrained Cascade Image Classification
*Creates a pretrained image classification model for frontal faces using the OpenCV Library*  
  
 Category: [OpenCV Library Modules](opencv-library-modules.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **Pretrained Cascade Image Classification** module to detect faces in images. The model is based on the [OpenCV](http://opencv.org/) library. The OpenCV Library provides a list of predefined models, each optimized to detect a particular type of object.    
 
 ### What is a pre-trained model?
 
 This image recognition model has already been trained on a large corpus of images that is widely used for image recognition tasks. This particular classification model has been optimized for facial detection, and uses the Viola-Jones object detection algorithm. The purpose of the model is to identify images that contain a human face in frontal view.  

 Although currently only one OpenCV image classification model is provided, additional pretrained models might be available in later releases.    

### Using a pre-trained model
    
 If you have a set of images that you would like to analyze, you provide them as input to the [Score Model](score-model.md) module as described in this topic, and attach the pretrained OpenCV library model. The **Score Model** module uses the image classification model to determine whether the image contains a human face, and returns a probability score for each image used as input.
 
Models based on **Pretrained Cascade Image Classification** cannot be retrained on new image data.   

The format in which the model is stored is incompatible with the [Train Model](train-model.md) and [Cross-Validate Model](cross-validate-model.md) modules.   
  
## How to Use Pretrained Image Classification  

 The image classification model in Azure Machine Learning has already been trained using a large dataset and is optimized for a specific image type. Therefore, all you need to do is provide a set of images as a *scoring dataset*. As an output, the module generates a score that indicates whether each image contains the target image type.  
  
1.  Add the **Pretrained Cascade Image Classification** module to your experiment.  
  
2.  Select one of the pre-trained classifiers from the list in **Pre-trained classifier**.  
  
     Currently, only one classifier is available (**Frontal face**, selected by default), but more might be available in future.  
  
3.  In **Scale factor**, type a value that specifies how much the image size is reduced at each image scale.  
  
     In the OpenCV Library, the classifier is designed so that it can be easily “resized” in order to be able to find the objects of interest at different sizes, which is more efficient than resizing the image itself. So, to find an object of an unknown size in the image the scan procedure should be done several times at different scales.  
  
     We recommend that you try different scaling factors to see which provides the best image classification results.  
  
4.  in **Minimum number of neighbors**, type an integer that represents the minimum number of overlapping rectangles that are required to detect that a face is included in a region.  
  
     In the OpenCV library, the classifier detects objects of different sizes in the input image. The detected objects are returned as a list of rectangles. The *neighbors* parameter controls how many possible matches are required to qualify as a detected face or feature. Thus, increasing this value tends to increase precision at the cost of coverage.  
  
     For examples of how neighbors are calculated, see this article in the OpenCv Library documentation: [Eigenfaces in OpenCV](http://docs.opencv.org/modules/contrib/doc/facerec/facerec_tutorial.html?highlight=neighbor)  
  
5.  Optionally, you can use the following settings to specify image size to the model so that it can make better predictions, and eliminate images that do not fit the requirements:  
  
    -   **Minimum height**. Type the pixel height of the smallest image. If you specify a value for this property, images smaller than this are ignored.  
  
    -   **Maximum height**. Type the pixel width of the largest image. If you specify a value for this property, images larger than this are ignored.  
  
    -   **Minimum width**. Type the pixel width of the smallest image. If you specify a value for this property, images smaller than this are ignored.  
  
    -   **Maximum width**. Type the pixel width of the largest image. If you specify a value for this property, images larger than this are ignored.  
  
6.  Add an image dataset for scoring. To do this, add the [Import Images](import-images.md) module to your experiment.  
  
    > [!TIP]
    >  In general, all images in the dataset should be the same size. Be sure to read the help for [Import Images](import-images.md) to ensure that the images you use meet the requirements, and for help in configuring access to the images.  
  
7.  Add the [Score Model](score-model.md) module to your experiment.  
  
     Connect the pre-trained image classifier to the left input of the [Score Model](score-model.md) module, and connect your dataset of images to the right input of  the [Score Model](score-model.md) module.  
  
8.  Run the experiment.  
  
9. The output of [Score Model](score-model.md) includes the image name, the scored label, and the probability score for the label (either 0 or 1). The classifier outputs a “1” if the image is likely to show the object (a face), and “0” otherwise. For example:  
  
    |Image name|Scored Labels|Scored Probabilities|  
    |----------------|-------------------|--------------------------|  
    |MAN001.png|TRUE|1|  
    |TABLE001.PNG|FALSE|0|  
    |CHAIR001.PNG|FALSE|0|  
  
    > [!TIP]
    >  The output also contains the RGB values for all color channels in the dataset, so we recommend that in your experiment you use [Select Columns in Dataset](select-columns-in-dataset.md) to output just the result columns.  
  
## Technical Notes  
 The facial recognition model provided by this module is based on the Viola-Jones face detection algorithm. For more information, see these resources:  
  
-   This video explains the basic concepts of facial recognition, including a definition of *Haar features* and how they are used in facial detection: [Facial Detection - Part 1](https://youtu.be/sWTvK72-SPU)  
  
-   This Wikipedia article describes the method used for the classifier, based on the paper by Navneet Dalal and Bill Triggs: [Histogram of oriented gradients](https://en.wikipedia.org/wiki/Histogram_of_oriented_gradients)  
  
-   For the documentation of the face recognition algorithm provided in the OpenCV library, see [Cascade Classifier](http://docs.opencv.org/modules/objdetect/doc/cascade_classification.html?highlight=detectmultiscale).  
  
> [!NOTE]
>  This module does not output the full collection of information produced by the OpenCV library. In particular, this module only outputs the prediction of whether a face is present or not, and does not include the coordinates of the face or any other information.  
>   
>  If you need this additional information, consider using other libraries, such as the [Face API](https://www.microsoft.com/cognitive-services/en-us/face-api) provided by [Microsoft Cognitive Services](https://www.microsoft.com/cognitive-services).  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Pre-trained classifier|List|PretrainedClassifier|Frontal face|Pretrained classifier from standard OpenCV distribution.|  
|Scale factor|>=1.0000000000000002|Float|1.1|Parameter that specifies how much the image size is reduced at each image scale.|  
|Minimum number of neighbors|>=0|Integer|3|Parameter that specifies how many neighbors each candidate rectangle should have to retain it.|  
|Minimum height|>=1|Integer|100|Minimum possible object height (in pixels). Objects smaller than this are ignored.<br /><br /> The parameter is optional.|  
|Minimum width|>=1|Integer|100|Minimum possible object width (in pixels). Objects smaller than this are ignored.<br /><br /> The parameter is optional.|  
|Maximum height|>=1|Integer|200|Maximum possible object height (in pixels). Objects larger than this are ignored.<br /><br /> The parameter is optional.|  
|Maximum width|>=1|Integer|200|Maximum possible object width (in pixels). Objects larger than this are ignored.<br /><br /> The parameter is optional.|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Trained model|[ILearner interface](ilearner-interface.md)|Trained binary classification model|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all error messages, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0005](errors/error-0005.md)|Exception occurs if parameter is less than a specific value.|  
  
## See Also  
 [Import Images](import-images.md)   
 [Pretrained Cascade Image Classification](pretrained-cascade-image-classification.md)