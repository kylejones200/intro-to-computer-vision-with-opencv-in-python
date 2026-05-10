---
author: "Kyle Jones"
date_published: "January 3, 2024"
date_exported_from_medium: "November 10, 2025"
canonical_link: "https://medium.com/@kyle-t-jones/intro-to-computer-vision-with-opencv-in-python-628eb9fca2db"
---

# Intro to Computer Vision with OpenCV in Python

OpenCV (Open Source Computer Vision Library) is an open-source computer vision and machine learning software library. It is written in C++...

### Intro to Computer Vision with OpenCV in Python
#### OpenCV (Open Source Computer Vision Library) is an open-source computer vision and machine learning software library. It is written in C++ and has interfaces for multiple programming languages including Python, Java, and MATLAB.

OpenCV provides a wide range of functions and algorithms that can be used for various computer vision tasks such as image and video processing, object detection, object recognition, face detection, tracking, and more.\ The library was initially developed by Intel in 1999 and has since been maintained by a community of developers. It is widely used in academic research, industry, and hobbyist projects due to its versatility, ease of use, and availability.

OpenCV is released under the BSD license, which means it is free to use and distribute, even in commercial applications.

OpenCV is important for computer vision applications because it provides a rich set of tools and algorithms that can be used to process and analyze images and videos, extract meaningful information from them, and make decisions based on that information.

Here are some reasons why OpenCV is important for computer vision applications:

- Versatility: OpenCV provides a wide range of functions and algorithms that can be used for various computer vision tasks. Whether you want to perform simple image processing tasks like filtering and thresholding, or more advanced tasks like object detection and recognition, OpenCV has the tools to do SO.
- Speed: OpenCV is written in C++ and optimized for performance, which means it can process images and videos quickly and efficiently. This makes it ideal for real-time applications such as video surveillance, autonomous vehicles, and robotics.
- Cross-platform: OpenCV has interfaces for multiple programming languages including Python, Java, and MATLAB. This makes it easy to use across different platforms and integrate with other software tools.
- Community support: OpenCV has a large and active community of developers who contribute to the library, provide support, and share their knowledge through online forums, blogs, and tutorials. This makes it easier for developers to learn and use the library, and to get help when needed.

Overall, OpenCV is an important tool for computer vision applications because it provides a powerful and flexible platform for processing and analyzing images and videos. It has become a standard tool in the field of computer vision and is widely used in research, industry, and hobbyist projects.

You can install and set up OpenCV in Python by following these steps.

- [Install Python: If Python is not already installed on your system, you can download and install it from the official website [https://www.python.org/downloads/](https://www.python.org/downloads/)]
- Install OpenCV: OpenCV can be installed using pip, which is a package manager for Python.

You can install OpenCV by running the following command in the terminal.

``` 
pip install opencv-pythonb
```

Note: you may need to restart the kernel to use updated packages.\ This will install the latest version of OpenCV along with its dependencies. Requirements are already satisfied in my system.

#### Verify the installation
After installing OpenCV, you can verify the installation by running the following code:

```python
import cv2
print (cv2. _version__)
# Output: 4.7.0
```

This code should print the version of OpenCV installed on your system.\ Install additional dependencies: Depending on the tasks you want to perform using OpenCV, you may need to install additional dependencies. For example, if you want to use OpenCV for deep learning, you will need to install TensorFlow or PyTorch.

Set up the environment: Depending on your operating system and Python environment, you may need to set up additional configurations to use OpenCV. For example, on Windows, you may need to add the OpenCV installation directory to the PATH environment variable.

With these steps, you should now have OpenCV installed and set up in your Python environment. You can start using OpenCV by importing the cv2 module in your Python code.

This tutorial assumes that you have prior knowledge of the Python programming language, as well as popular libraries like Matplotlib and NumPy. Our primary focus will be on the OpenCV package and its various functionalities for computer vision applications.

#### Basic Image Processing with OpenCV
You can read and display images in OpenCV using the following steps:\ Import the necessary modules:\ We will use the cv2 module to read and process the image and the matplotlib module to display the image.

The steps to read and display an image in OpenCV are:\ Load an image using the imread() function in OpenCV.\ Create a window using the namedWindow() function and display the image using the imshow() function.

Use the waitKey(0) function to hold the image window on the screen for a specified number of seconds (or until the user closes it by pressing any key). Close the image window using the destroyAllWindows() function to release it from memory.

Syntax: cv2.imread(path,flag)\ Parameters:

- path: A string representing the path of the image to be read.
- flag: It specifies the way in which image should be read. It's default value is cv2.IMREAD_COLOR
- Return Value: This method returns an image that is loaded from the specified file.

```python
import cv2
import matplotlib.pyplot as plt
# Load the image
img = cv2.('imread images/icon.png', cv2.IMREAD_COLOR)
plt.imshow(img)
plt.show()
```

The cv2.imread() function reads the image from the specified file path and returns a NumPy array that represents the image. Following types of files are supported in OpenCV library: Windows bitmaps : .bmp, .dib; JPEG files: .jpeg, .jpg; Portable Network Graphics: .png; WebP: .webp; Sun rasters: .sr, .ras; TIFF files: .tiff, .tif; Raster and Vector geospatial data supported by GDAL.

By default, OpenCV stores colored images in BGR(Blue Green and Red) format. The following are the three types of flags used in OpenCV for reading images:

- cv2.IMREAD_COLOR: This flag is used to load a color image, and any transparency in the image will be ignored. It is the default flag used when no flag is specified. Alternatively, we can pass the integer value 1 to indicate this flag.
- cv2.IMREAD_GRAYSCALE: This flag is used to load an image in grayscale mode. Alternatively, we can pass the integer value 0 to indicate this flag.
- cv2.IMREAD_UNCHANGED: This flag is used to load an image as-is, including any alpha channel information. Alternatively, we can pass the integer value --- -1 to indicate this flag.

Example, changing "Grayscale" and "unchanged" flags will display the image like this

``` 
# Perform any image processing operations on the image if necessary
plt.imshow (cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.show()
```

If the image cannot be read (because of missing file, improper permissions, unsupported or invalid format) then this method returns an empty matrix.

The "plt.imshow()" function displays the image using matplotlib. The "cv2.cvtColor()" function converts the color space of the image from BGR to RGB, which is the format expected by matplotlib. OpenCV reads images in BGR color space by default, while most other image processing libraries use RGB color space.

You can see the displayed image. You can also save the image using the cv2.imwrite("pathtoimage/icon.jpg" img)" function. The code below will convert the read image file to .png or .jpg file according to the format given and will save in the same directory. you can save to your required path / directory.

Syntax: cv2.imwrite(filename, image)\ Parameters:

- filename: A string representing the file name. The filename must include image format like .jpg, .png, etc.
- image: It is the image that is to be saved.
- Return Value: It returns true if image is saved successfully.

``` 
# Write the image to a file
cv2.imwrite('images/newicon.jpg', img)

# Load the image
img = cv2.imread('images/newicon.jpg')
# Perform any image processing operations on the image if necessary
plt.imshow(cv2.cvtColor(img, cv2.COLOR_RGB2BGR())
# Display the image
plt.show()
```

### Color Spaces in OpenCV
Color spaces refer to the ways in which colors are represented and manipulated in an image. In OpenCV, the most commonly used color spaces are RGB, HSV, and BGR. In this tutorial, we'll cover these color spaces and how to convert between them.

#### RGB Color Space
RGB (Red Green Blue) is the most common color space used for displaying images on screens. In this color space, each pixel in an image is represented as a combination of red, green, and blue color intensities, with values ranging from 0 to 255. To read an image in RGB color space using OpenCV, we can use the cv2.imread() function with the cv2.IMREAD_COLOR flag, which is the default flag:

```python
import cv2
import matplotlib.pyplot as plt
# Load the image in RGB color space
img = cv2.imread('images/Apple.png', cv2. IMREAD_COLOR)
# Display the image
newimg = plt.imshow(img)
plt.show()
```

What is the difference between BGR and RGB color space BGR and RGB are two common color spaces used in image processing and computer vision, with BGR being the default color space in OpenCV. BGR stands for blue-green-red, and it is the color space used by OpenCV to represent color images.

RGB, on the other hand, stands for red-green-blue, and it is the color space used by most computer systems and cameras to represent color images.\ The difference between BGR and RGB color space lies in the order of color channels. In BGR, the order of color channels is blue-green-red, while in RGB, it is red-green-blue. Therefore, if you want to convert an image from BGR to RGB, you need to swap the first and the third channel of the image.

In OpenCV, you can use the cv2.cvtColor() function to convert an image from one color space to another. For example, to convert an image from BGR to RGB, you can use the following code:

```python
import cv2
import matplotlib.pyplot as plt
# Read an image in BGR color space
img_bgr = cv2.imread('images/Apple.png')
# Convert BGR to RGB
img_rgb = cv2. cvtColor(img_bgr, cv2.COLOR_BGR2RGB)
fig, axs = plt.subplots(1, 2)
# Display the RGB and BGR images in subplots
axs[0].imshow(img_bgr)
axs[0].set_title('BGR Image')
axs[1].imshow(img_rgb)
axs[1].set_title('RGBImage')

# Hide X and ticks for all subplots
for ax in axs.flat:
  ax.set_xticks([])
  ax.set_yticks([])
# Display the subplots
plt. show()
```

In this code, we first read an image in BGR color space using the cv2.imread() function. We then use the cv2.cvtColor() function to convert the image from BGR to RGB color space by passing the cv2.COLOR_BGR2RGB flag as the second argument. The resulting image is stored in the img_rgb variable.

#### HSV Color Space
HSV (Hue Saturation Value) is a color space that separates the color information (hue) from the brightness and saturation information. In this color space, the hue value represents the actual color, while the saturation and value values represent the intensity of the color.

To convert an image from RGB to HSV color space using OpenCV, we can use the cv2.cvtColor() function:\ To display the HSV image, we need to convert it back to RGB color space using the cv2.cvtColor() function:

```python
import cv2
# Load the image in RGB color space
img = cv2.imread('images/Apple.png', CV2.IMREAD_COLOR)
# Convert the image from BGR to HSV color space
hsv_img = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
# Convert the image back to BGR color space
bgr_img = cv2. cvtColor(hsv_img, cv2.COLOR_HSV2BGR)
# Create a 2x2 grid of subplots
fig, axs = plt.subplots(1,2)
# Display the HSV and BGR images in subplots
axs[0].imshow(hsv_img)
axs[0].set_title('HSV Image')
axs[1].imshow(rgb_img
axs[1].set_title('BGRImage')
# Hide X and y ticks for all subplots
for ax in axs.flat:
  ax.set_xticks([])
  ax.set_yticks([])
# Display the subplots
plt.show()
```

In OpenCV, you can perform basic image processing operations such as\ resizing, cropping, and rotating images using various functions.

#### Resizing an image
```python
# Import the necessary modules:
import cv2
import matplotlib.pyplot as plt

# Load the image
img = cv2.imread('images/icon.png')
# check the size of an image
height, width, channels = img.shape()
print("Image size: {} x {} x {} pixels".format(width, height, channels))

# resize the image
# cv2. resize(img, (new_width, new_height))
resized_img = cv2.resize(img, (400, 500))

# check the size of resized image
height, width, channels = resized_img.shape
print("Resized Image: {} x {} x {} pixels".format(width, height, channels))

# Perform any image processing operations on the image if necessary
plt.imshow(cv2.cvtColor(resized_img, cv2.COLOR_RGB2BGR))
# Display the image
plt.show()
```

Replace 'new_width' and 'new_height' with the desired dimensions for the resized image. The "cv2.resize()" function takes two arguments: the input image and the new size for the image. You can also specify the interpolation method to use for resizing using the interpolation parameter.

In above code, we loaded the image, printed the dimension of original image, resized the image and printed the dimension of resized image.

#### Cropping the Image
Replace X, y, W, and h with the coordinates and dimensions of the region of interest (ROI) in the image that you want to crop.

``` 
# Load the image
img = cv2.imread ('images/icon.png')
y=0;x=0; w=200;h = 200
cropped_img = img[y:y+h, x:x+w]
# Perform any image processing operations on the image if necessary
plt. imshow (cv2. cvtColor (cropped_img, cv2.COLOR_RGB2BGR))
# Display the image
plt. show()
```

#### Rotate the image
Replace 'angle" with the desired rotation 'angle in degrees', and scale with the desired 'scaling factor' for the rotated image. The 'cv2.getRotationMatrix2D()' function calculates the transformation matrix for rotating the image around the center point. The 'cv2.warpAffine()' function applies the transformation matrix to the image to perform the rotation.

``` 
rows, cols img.shape[: :2]
angle = 45; scale = 1.0
# Perform any image processing operations on the image if necessary
M = cv2.getRotationMatrix2D((cols/2, rows/2), angle, scale)
rotated_img = cv2.warpAffine(img, M, (cols, rows))
plt. imshow (cv2. cvtColor(rotated_img cv2.COLOR_RGB2BGR))
# Display the image
plt. show()

cv2.imwrite('images/resized_image.jpg', resized_img)
cv2.imwrite('images/cropped_image.jpg', cropped_img)
cv2.imwrite('images/rotated_image.jpg', rotated_img)
```

Below you can find the complete code for resizing, cropping and rotating the image.

```python
import cv2
import matplotlib.pyplot as plt
# Load the image
img = 2.imread('images/icon.png')
# Resize the image
new_width = 400
new_height = 500
resized_img = cv2.resize(img, (new_width, new_height))
# Crop the image
x = 0
y=0
W=200
h=200
cropped_img = img[y:y+h, x:x+w]
# Rotate the image
angle = 45
scale = 1.0
rows, cols = img.shape[:2]
M = cv2.getRotationMatrix2D((cols/2, rows/2), angle, scale)
rotated_img = cv2.warpAffine(img, M, (cols, rows))

# Save the processed images
cv2.imwrite('images/resized_image.jpg', resized_img)
cv2.imwrite('images/cropped_image.jpg', cropped_img)
cv2.imwrite('images/rotated_image.jpg', rotated_img)
```

#### Image Filtering and Enhancement
Enhancing image quality is important because it can improve the overall appearance and clarity of an image, making it easier to interpret and analyze.

In computer vision and image processing applications, images may contain noise, blur, or other artifacts that can make it difficult to extract meaningful information. By applying techniques such as denoising, sharpening, and blurring, the quality of the image can be improved, which\ can ultimately lead to more accurate and reliable results in downstream analyses.

Additionally, in fields such as photography and graphic design, image enhancement can be used to make images more aesthetically pleasing and visually appealing to the viewer.

#### Blurring
Image blurring refers to the process of reducing the clarity or distinction of an image. It is achieved by applying various low pass filter kernels. Blurring offers several advantages, such as removing noise, smoothing the image, and hiding unnecessary details. OpenCV provides various denoising or blurring filters, including the Gaussian filter, Median filter, and Bilateral filter.

Gaussian blurring is a widely used technique that involves blurring an image using a Gaussian function. This method is commonly used to reduce image noise and detail. It is also used as a preprocessing step before applying machine learning or deep learning models. An example of a Gaussian kernel is a 3x3 matrix with a value of 1/16 in the middle and 1/8 in the surrounding cells.

Median blur is a non-linear digital filtering technique used to remove noise from an image or signal. It is widely used in digital image processing because it preserves edges while removing noise. It is particularly effective in removing salt and pepper noise.

Bilateral blur is a non-linear, edge-preserving, and noise-reducing smoothing filter for images. It replaces the intensity of each pixel with a weighted average of intensity values from nearby pixels. This weight can be based on a Gaussian distribution. Bilateral blur is effective in preserving sharp edges while discarding weaker ones.

Image Blurring refers to making the image less clear or distinct. It is done with the help of various low pass filter kernels.

#### Advantages of blurring
It helps in Noise removal. As noise is considered as high pass signal SO by the application of low pass filter kernel we restrict noise.\ It helps in smoothing the image.\ Low intensity edges are removed.\ It helps in hiding the details when necessary. For e.g. in many cases police deliberately want to hide the face of the victim, in such cases blurring is required.

```python
import cv2
import matplotlib.pyplot as plt
# Load the image
img = cv2.imread('images/icon.png')
# Apply Gaussian blur
# Syntax: CV2. GaussianBLur(image, shapeOfTheKernel, sigmaX )
img_gaussian = cv2.GaussianBlur(img, (5,5), 0)
# Apply Median blur
# Syntax: CV. medianBlur (image, kernel size)
img_median = cv2.medianBlur(img, 5)
# Apply Bilateral filter
# Syntax: 2.bilateralFilter (image, diameter, sigmaColor, sigmaSpace)
img_bilateral = cv2.bilateralFilter(img, 9, 75, 75)
# Create a 2x2 grid of subplots
fig, axs = plt. subplots(2) 2)
# Display the original and filtered images in subplots
axs[0, 0] imshow(img)
axs[0, 0].set_title('Original Image' )
axs[0, 1].imshow(img_gaussian)
axs[0, 1].set_title('Gaussian Image')
axs[1, 0].imshow(img_median)
axs[1, 0].set_title('Median Image')
axs[1, 1].imshow(img_bilateral)
axs[1, 1].set_title('Bilateral Image')
# Hide X and y ticks for all subplots
for ax in axs.flat:
ax.set_xticks([])
ax.set_yticks([])
# Display the subplots
plt.show( )
```

#### Eroding an Image
cv2.erode() is a morphological operation that is used to remove small white noises from the image, detach two connected objects, and shrink the object boundaries. It requires two inputs:\ the original image and a kernel (structuring element) that decides the nature of the operation.\ Here's an example of using cv2.erode() method:\ Suppose we have an image of a letter 'X' in white color with a black background. We want to erode this image to remove small white noise from the image. First, we need to convert the image into grayscale and threshold it to get a binary image.

Here's the code to achieve this\ Parameters:

- src: It is the image which is to be eroded.
- kernel: A structuring element used for erosion. If element = Mat(), a 3 x 3 rectangular structuring element is used. Kernel can be created using getStructuringElement.
- dst: It is the output image of the same size and type as src.
- anchor: It is a variable of type integer representing anchor point and it's default value Point is (-1, -1) which means that the anchor is at the kernel center.
- borderType: It depicts what kind of border to be added. It is defined by flags like cv2.BORDER_CONSTANT, cv2.BORDER_REFLECT, etc.
- iterations: It is number of times erosion is applied.\ borderValue: It is border value in case of a constant border.
- Return Value: It returns an image.

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Load the image
img = cv2.imread('images/LetterX.png', cv2. IMREAD_COLOR)
# Creating kernel
kernel = np.ones((3, 3), np.uint8)
kernel2 = np.ones((6, 6), np.uint8)
# Using cv2.erode() method
eroded = cv2.erode(img, kernel)
eroded2 = cv2.erode(img, kernel2, cv2.BORDER_REFLECT)

# Create a 2x2 grid of subplots
fig, axs = plt. subplots(1, 3)
# Display the original and eroded images in subplots
axs[0].imshow(img)
axs[0].set_title('Original Image')
axs[1].imshow(eroded)
axs[1].set_title('Eroded Image')
axs[2].imshow(eroded2)
axs[2].set_title('2nd Eroded Image')
# Hide X and ticks for all subplots
for ax in axs.flat:
  ax.set_xticks([])
  ax.set_yticks([])
# Display the subplots
plt. show()
```

### Related Stories
- [[Image Segmentation for Computer Vision with Python and CV2](https://medium.com/@kylejones_47003/image-segmentation-for-computer-vision-with-python-and-cv2-a07a0f70b79d)]
- [[Object Detection with Python using OpenCV: Introduction to computer vision](https://medium.com/@kylejones_47003/object-detection-with-python-using-open-cv-introduction-to-computer-vision-74508c39191d)]
- [[Introduction to Deep Learning for computer vision with Python](https://medium.com/@kylejones_47003/introduction-to-deep-learning-for-computer-vision-with-python-85f94acc3a6b)]
