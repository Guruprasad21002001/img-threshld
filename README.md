# Thresholding-of-Images

## Aim:

To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required:

1. Anaconda - Python 3.7,

2. OpenCV.

## Algorithm:

### Step1:

Load the necessary packages requiured for the processing the threshold of the image.

### Step2:

Read the Image using the cv2 instructions and convert it to a grayscale image.

### Step3:

Apply global thresholding on the grayscale image and store the results in threshold variables. Use different thresholding methods to segment the image.

### Step4:

Apply adaptive thresholding on the grayscale image and store the results in the variables th1 and th2. Use different adaptive thresholding methods to segment the immage. 

### Step5:

Apply Otsu's method on the grayscale image and store the result in variable th3.

### Step6:

Create a list titles containing the titles of each image and a list images containing the corresponding images.

### Step7:

Loop through the images list to display each image alongside its title using plt.subplot(), plt.title(), plt.imshow(), plt.axis(), and plt.show().        

## Program:

```python

Developed By: Guru Prasad.B
Register Number: 212221230032
Program to segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

# Load the necessary packages:

import cv2
import matplotlib.pyplot as plt
import numpy as np

# Read the Image and convert to grayscale:

image=cv2.imread("harley.jpg")
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Use Global thresholding to segment the image:

ret, thresh1 = cv2.threshold(image1,100,220,cv2.THRESH_BINARY)
ret, thresh2 = cv2.threshold(image1,90,160, cv2.THRESH_BINARY_INV)
ret, thresh3 = cv2.threshold(image1,140,220,cv2.THRESH_TRUNC)
ret, thresh4 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO)
ret, thresh5 = cv2.threshold(image1,225,270,cv2.THRESH_TOZERO_INV)

# Use Adaptive thresholding to segment the image:

th1 = cv2.adaptiveThreshold(image1, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 3)
th2 = cv2.adaptiveThreshold(image1, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 3)

# Use Otsu's method to segment the image:

ret2, th3 = cv2.threshold(image1, 150, 255, cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results:

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (Truncate)",
       "Threshold Image (To Zero)","Threshold Image (To Zero-Inverse)","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)","Otsu"]
images=[image1,thresh1,thresh2,thresh3,thresh4,thresh5,th1,th2,th3]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```


## Output:

### Original Image:

![i1](https://user-images.githubusercontent.com/95342910/235991861-12a1431c-793a-4950-be86-f02bc2990fdd.png)

### Global Thresholding:

![i2](https://user-images.githubusercontent.com/95342910/235991877-5a87acab-b848-45d6-a4df-107e7c28d6db.png)

### Adaptive Thresholding:

![i3](https://user-images.githubusercontent.com/95342910/235991898-34e4aa23-9951-4a75-addb-b595a937c47c.png)

### Optimum Global Thesholding using Otsu's Method:

![i4](https://user-images.githubusercontent.com/95342910/235991919-34359d89-1801-46e7-862b-77016d50765f.png)

## Result

Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

