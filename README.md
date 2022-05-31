# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## Program

```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread("hehe.jpeg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("hehe.jpeg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
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
## Output

### Original Image
![download](https://user-images.githubusercontent.com/93427208/171128704-d29eadae-9bb0-4313-b0bb-6cc97f524e68.png)


### Global Thresholding
![download](https://user-images.githubusercontent.com/93427208/171128728-df68e3bd-613c-468a-80f4-2433239ed983.png)

![download](https://user-images.githubusercontent.com/93427208/171128742-dd05225a-a2dd-4c01-96fd-d732cf87d0c8.png)

![download](https://user-images.githubusercontent.com/93427208/171128772-32403c32-a323-415d-973e-5f86ee7c3422.png)

![download](https://user-images.githubusercontent.com/93427208/171129144-da2f72d3-c209-40c6-96cc-e5fa5c5466ae.png)
![download](https://user-images.githubusercontent.com/93427208/171129351-cdf736ac-32ef-42cc-9c99-89eb22493c0f.png)



### Adaptive Thresholding
<br>![download](https://user-images.githubusercontent.com/93427208/171129244-7c8d6eb0-eaa0-4046-814c-3e2aadde3ea1.png)


![download](https://user-images.githubusercontent.com/93427208/171129220-8aefe4d0-1c71-4f7a-b960-e45d45e5e22c.png)



### Optimum Global Thesholding using Otsu's Method


<br>![download](https://user-images.githubusercontent.com/93427208/171129208-0d2d588f-e409-4df6-a02d-302d159a9c22.png)

<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

