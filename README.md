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
 Developed By : LOKESH RAHUL V V
 Register Number : 212222100024
```

### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```python
image = cv2.imread('dog.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('dog.jpg',0)
```
### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```python
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
![Screenshot 2024-05-01 183136](https://github.com/lokeshrahulv/Thresholdingg/assets/118423842/5b59dbed-6233-4623-a671-69f2d7b87b9e)

### Global Thresholding
![Screenshot 2024-05-01 183240](https://github.com/lokeshrahulv/Thresholdingg/assets/118423842/74c9a5c8-2a09-4370-8166-d48db5650531)
![image](https://github.com/lokeshrahulv/Thresholdingg/assets/118423842/086a257b-ea0c-4dd6-9754-f3335e27fbb4)

### Adaptive Thresholding
![image](https://github.com/lokeshrahulv/Thresholdingg/assets/118423842/6aa8780c-2d6e-404b-81c0-ea18eca81315)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/lokeshrahulv/Thresholdingg/assets/118423842/8c8ece0c-c242-4b8a-9506-6ef1093756a4)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
