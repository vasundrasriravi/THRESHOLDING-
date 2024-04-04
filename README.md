# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program
```
Developed by: VASUNDRA SRI R
Register no: 212222230168
```
# Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
# Read the Image and convert to grayscale
```
image = cv2.imread("lion.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("lion.jpg",0)
```
# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```
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
![Screenshot 2024-04-04 114350](https://github.com/vasundrasriravi/THRESHOLDING-/assets/119393983/726c1229-b77e-42b8-b066-9196ddfd9f89)

### Global Thresholding
![Screenshot 2024-04-04 114645](https://github.com/vasundrasriravi/THRESHOLDING-/assets/119393983/ea464692-7672-4bc8-b5a2-d70d3e64fb21)
![Screenshot 2024-04-04 114705](https://github.com/vasundrasriravi/THRESHOLDING-/assets/119393983/02f5c9a1-d533-4ab5-b201-854b65f242b4)
![Screenshot 2024-04-04 114724](https://github.com/vasundrasriravi/THRESHOLDING-/assets/119393983/ecc15c7b-a3f0-4667-be8f-53edeb332262)
![Screenshot 2024-04-04 114902](https://github.com/vasundrasriravi/THRESHOLDING-/assets/119393983/73c177e1-7633-4b79-9c4f-ade6c9138267)
![Screenshot 2024-04-04 114922](https://github.com/vasundrasriravi/THRESHOLDING-/assets/119393983/6dc5e7a7-f5ba-4d59-8735-5edf993c9cd4)

### Adaptive Thresholding
![Screenshot 2024-04-04 115044](https://github.com/vasundrasriravi/THRESHOLDING-/assets/119393983/a4e2a20b-2f12-48c1-a880-7664587d2622)
![Screenshot 2024-04-04 115118](https://github.com/vasundrasriravi/THRESHOLDING-/assets/119393983/6c47b67b-1776-419e-a3da-b08ac6513fde)

### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-04 115142](https://github.com/vasundrasriravi/THRESHOLDING-/assets/119393983/f0f2cef9-52fa-49a5-b031-688016938a04)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
