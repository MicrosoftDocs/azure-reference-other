---
title: "ImageOutputter (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/18/2017"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1a266a35-c38a-41e7-ab0c-7a182a139080
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# ImageOutputter (U-SQL)
The `ImageOutputter` function from the `ImageCommon` assembly is used to output an image. `ImageOutputter` takes a row and output stream as inputs, and its job is to stuff the row into the output stream. The row has one column, which is the representation of the image as a byte[].  Currently, U-SQL outputs to only one stream (which is ultimately a single file) in a U-SQL statement, which means only a single row can be practically processed, and so a single image is written to a single image file. The AtomicFileProcessing flag set to true. 



### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- Ensure you have installed the cognitive assemblies, see [Registering Cognitive Extensions in U-SQL](../USQL/cognitive-capabilities-in-u-sql.md#registeringExtensions) for more information.
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally) if you first download the assemblies locally, see [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/) for more information.
An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- You will need images accessible to you ADLA or Local account.
- The examples utillize the table `myImages` from the example [Load images to a table](../USQL/imageextractor-u-sql.md#loadImages).
- For simplicity, the example(s) with user-defined code make use of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) for assembly management.  The main advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically.  To use Assembly registration instead of Code-Behind, see [Using Assemblies: Code-Behind vs. Assembly Registration Walkthrough](../USQL/extending-u-sql-expressions-with-user-code.md#usingAssemblies).


**Output a previously stored image to a file**
```
REFERENCE ASSEMBLY ImageCommon;

@image_out =
    SELECT ImgData
    FROM dbo.myImages 
    WHERE FileName == "panda";

OUTPUT @image_out
TO @"/ReferenceGuide/Cognition/Vision/panda2.jpg"
USING new Cognition.Vision.ImageOutputter();
```

--------------------------------------------------

<a name="imageOps">**User Defined Function - scaleImageBy and others**</a>   
c# code is placed in the associated [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) .cs file. Code is taken from [https://github.com/Azure/usql/blob/master/Examples/ImageApp/Image/ImageOps.cs](https://github.com/Azure/usql/blob/master/Examples/ImageApp/Image/ImageOps.cs).  See usage in next section, **below**.
```csharp
using System;
using System.IO;
using System.Drawing;           // Ensure System.Drawing is added as a REFERENCE
using System.Drawing.Imaging;
using System.Drawing.Drawing2D;

namespace Images
{
    // Helper class that binds together a stream and an image so that they can be disposed together.
    // It is needed because the stream must stay open for as long as the image is being used.
    public class StreamImage : IDisposable
    {
        private MemoryStream mMemoryStream;
        public Image mImage;

        public StreamImage(byte[] inBytes)
        {
            mMemoryStream = new MemoryStream(inBytes);
            mImage = null;
            try
            {
                mImage = Image.FromStream(mMemoryStream);
            }
            finally
            {
                if (mImage == null)
                {
                    mMemoryStream.Dispose();
                }
            }
        }

        public void Dispose()
        {
            try
            {
                mImage.Dispose();
            }
            finally
            {
                mMemoryStream.Dispose();
            }
        }

        public string getStreamImageProperty(int propertyId)
        {
            foreach (PropertyItem propItem in mImage.PropertyItems)
            {
                if (propItem.Id == propertyId)
                {
                    return (propItem.Type == 2) ? System.Text.Encoding.UTF8.GetString(propItem.Value) : propItem.Value.ToString();
                }
            }
            return null;
        }

        // Utility: draw the input image to the output image within the given region (at high quality).
        private static void drawImage(Image inImage, Bitmap outImage, Rectangle region)
        {
            outImage.SetResolution(inImage.HorizontalResolution, inImage.VerticalResolution);
            using (Graphics g = Graphics.FromImage(outImage))
            {
                // Clear background pixels, if any will remain after the drawing below.
                if ((region.X != 0) ||
                    (region.Y != 0) ||
                    (region.Height != outImage.Height) ||
                    (region.Width != outImage.Width))
                {
                    g.Clear(Color.Black);
                }
                // Draw image at high quality.
                g.CompositingMode = CompositingMode.SourceCopy;
                g.CompositingQuality = CompositingQuality.HighQuality;
                g.InterpolationMode = InterpolationMode.HighQualityBicubic;
                g.SmoothingMode = SmoothingMode.HighQuality;
                g.PixelOffsetMode = PixelOffsetMode.HighQuality;
                using (ImageAttributes attributes = new ImageAttributes())
                {
                    attributes.SetWrapMode(WrapMode.TileFlipXY);
                    g.DrawImage(inImage, region, 0, 0, inImage.Width, inImage.Height, GraphicsUnit.Pixel, attributes);
                }
            }
        }

        public byte[] scaleStreamImageBy(float scaleFactor)
        {
            int outWidth = (int)(mImage.Width * scaleFactor);
            int outHeight = (int)(mImage.Height * scaleFactor);
            using (Bitmap outImage = new Bitmap(outWidth, outHeight))
            {
                drawImage(mImage, outImage, new Rectangle(0, 0, outWidth, outHeight));
                return ImageOps.imageToByteArray(outImage);
            }
        }
        public byte[] scaleStreamImageTo(int outWidth, int outHeight)
        {
            int x, y, w, h;
            int iWoH = mImage.Width * outHeight;
            int iHoW = mImage.Height * outWidth;
            if (iWoH < iHoW)
            {
                w = (int)((double)(iWoH) / mImage.Height);
                h = outHeight;
                x = (int)((outWidth - w) / 2.0);
                y = 0;
            }
            else
            {
                w = outWidth;
                h = (int)((double)(iHoW) / mImage.Width);
                x = 0;
                y = (int)((outHeight - h) / 2.0);
            }
            using (Bitmap outImage = new Bitmap(outWidth, outHeight))
            {
                drawImage(mImage, outImage, new Rectangle(x, y, w, h));
                return ImageOps.imageToByteArray(outImage);
            }
        }

    }

    // Sample image utilities and operations.
    public class ImageOps
    {
        // The quality setting for generated JPEG files.
        private const long JPEG_QUALITY = 90;

        // Utility: convert a byte array into an image.
        private static StreamImage byteArrayToImage(byte[] inBytes)
        {
            return new StreamImage(inBytes);
        }

        // Utility: convert an image into a byte array containing a JPEG encoding of the image.
        public static byte[] imageToByteArray(Image inImage)
        {
            using (MemoryStream outStream = new MemoryStream())
            {
                ImageCodecInfo jpegCodec = null;
                foreach (ImageCodecInfo codec in ImageCodecInfo.GetImageEncoders())
                {
                    if (codec.FormatID == ImageFormat.Jpeg.Guid)
                    {
                        jpegCodec = codec;
                        break;
                    }
                }
                if (jpegCodec == null)
                {
                    throw new MissingMemberException("Cannot find JPEG encoder");
                }
                using (EncoderParameters ep = new EncoderParameters(1))
                {
                    using (EncoderParameter p = new EncoderParameter(Encoder.Quality, JPEG_QUALITY))
                    {
                        ep.Param[0] = p;
                        inImage.Save(outStream, jpegCodec, ep);
                        return outStream.ToArray();
                    }
                }
            }
        }

        // Operation: return the value of an image property (provided it's a string or integer).
        // Use property ID 8298 for copyright.
        // See https://msdn.microsoft.com/en-us/library/ms534416.aspx for additional IDs.
        public static string getImageProperty(byte[] inBytes, int propertyId)
        {
            return byteArrayToImage(inBytes).getStreamImageProperty(propertyId);
        }

        // Operation: rotate an image by 90, 180, or 270 degrees.
        public static byte[] rotateImage(byte[] inBytes, int rotateType)
        {
            RotateFlipType rotateFlipType;
            switch (rotateType)
            {
                case 1:
                    rotateFlipType = RotateFlipType.Rotate90FlipNone;
                    break;
                case 2:
                    rotateFlipType = RotateFlipType.Rotate180FlipNone;
                    break;
                case 3:
                    rotateFlipType = RotateFlipType.Rotate270FlipNone;
                    break;
                default:
                    throw new ArgumentException("Invalid type");
            }
            using (StreamImage inImage = byteArrayToImage(inBytes))
            {
                inImage.mImage.RotateFlip(rotateFlipType);
                return imageToByteArray(inImage.mImage);
            }
        }

        // Operation: scale an image by a scale factor.
        public static byte[] scaleImageBy(byte[] inBytes, float scaleFactor)
        {
            return byteArrayToImage(inBytes).scaleStreamImageBy(scaleFactor);
        }

        // Operation: scale an image to the given dimensions.
        public static byte[] scaleImageTo(byte[] inBytes, int outWidth, int outHeight)
        {
            return byteArrayToImage(inBytes).scaleStreamImageTo(outWidth, outHeight);
        }


        public static byte[] GetByteArrayforImage(Stream input)
        {
            try
            {
                var image = Image.FromStream(input);
                MemoryStream ms = new MemoryStream();
                image.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);
                return ms.ToArray();
            }
            catch (Exception)
            {
                return null;
            }
        }

        public static string[] ConvertTiffToJpeg(string fileName)
        {
            using (Image imageFile = Image.FromFile(fileName))
            {
                FrameDimension frameDimensions = new FrameDimension(
                    imageFile.FrameDimensionsList[0]);

                // Gets the number of pages from the tiff image (if multipage) 
                int frameNum = imageFile.GetFrameCount(frameDimensions);
                string[] jpegPaths = new string[frameNum];

                for (int frame = 0; frame < frameNum; frame++)
                {
                    // Selects one frame at a time and save as jpeg. 
                    imageFile.SelectActiveFrame(frameDimensions, frame);
                    using (Bitmap bmp = new Bitmap(imageFile))
                    {
                        jpegPaths[frame] = String.Format("{0}\\{1}{2}.jpg",
                            Path.GetDirectoryName(fileName),
                            Path.GetFileNameWithoutExtension(fileName),
                            frame);
                        bmp.Save(jpegPaths[frame], ImageFormat.Jpeg);
                    }
                }

                return jpegPaths;
            }

        }
    }
}
```

**Using User Defined Functions  - scaleImageBy and others**   
Various user defined functions are used to perform various manipulations to a stored file.  Using the Code-Behind **above**.  The advantage of [Code-Behind](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-code-behind-1) is that the tooling will register the assembly file and add the REFERENCE ASSEMBLY statement automatically. 

```U-SQL
REFERENCE ASSEMBLY ImageCommon;
USING Images;

// C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework\.NETFramework\v4.5.2\System.Drawing.dll

// Scaled down image by 50%
@image_manipulated1 =
  SELECT ImageOps.scaleImageBy(ImgData, .50f) AS thumbnail_image
  FROM dbo.myImages WHERE FileName == "mountain";

// Scaled down image by specified pixels
@image_manipulated2 =
  SELECT ImageOps.scaleImageTo(ImgData, 192, 108) AS thumbnail_image
  FROM dbo.myImages WHERE FileName == "mountain";

// 180 degree roated image
@image_manipulated3 =
  SELECT ImageOps.rotateImage(ImgData, 2) AS rotated_image
  FROM dbo.myImages WHERE FileName == "mountain";

OUTPUT @image_manipulated1
TO @"/ReferenceGuide/Cognition/Vision/manipulatedImages/mountain_scaled1.jpg"
USING new Cognition.Vision.ImageOutputter();

OUTPUT @image_manipulated2
TO @"/ReferenceGuide/Cognition/Vision/manipulatedImages/mountain_scaled2.jpg"
USING new Cognition.Vision.ImageOutputter();

OUTPUT @image_manipulated3
TO @"/ReferenceGuide/Cognition/Vision/manipulatedImages/mountain_rotated.jpg"
USING new Cognition.Vision.ImageOutputter();
```

--------------------------------------------------


### See Also
* [Built-in U-SQL System Objects and Extensions](../USQL/built-in-u-sql-system-objects-and-extensions.md)
* [Extending U-SQL Expressions with User-Code](../USQL/extending-u-sql-expressions-with-user-code.md)
* [Cognitive Capabilities in U-SQL](../USQL/cognitive-capabilities-in-u-sql.md)
