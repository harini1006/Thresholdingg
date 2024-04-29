# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>
Load the necessary packages.

### Step2:
<br>
Read the Image and convert to grayscale.

### Step3:
<br>
Use Global thresholding to segment the image.

### Step4:
<br>
Use Adaptive thresholding to segment the image.

### Step5:
<br>
Use Otsu's method to segment the image and display the results.

### Program
```
Developed By : HARINI V
Register Number : 212222230044
```

### Load the necessary packages:
```PY
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```PY
image = cv2.imread('kitty.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('kitty.jpeg',0)
```
# Use Global thresholding to segment the image
```PY
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```PY
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```PY
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```PY
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
### Output

### Original Image
![image](https://github.com/harini1006/Thresholdingg/assets/113497405/319d9b7a-1b47-4f87-b732-ce440cf57dcb)



### Global Thresholding

![image](https://github.com/harini1006/Thresholdingg/assets/113497405/0b70f9fe-0aed-4502-8401-e553756c964f)

![image](https://github.com/harini1006/Thresholdingg/assets/113497405/0ed0e16b-138c-481e-96f3-a4d3df09bc8b)


![image](https://github.com/harini1006/Thresholdingg/assets/113497405/8e7666bb-56dd-4753-801b-40195e81bbe1) 

![image](https://github.com/harini1006/Thresholdingg/assets/113497405/2182ed44-c81d-4182-a8eb-89d59d59056b)

![image](https://github.com/harini1006/Thresholdingg/assets/113497405/ee86eb76-b1c7-4c7e-8a31-ac6b6e77e740)


### Adaptive Thresholding

![image](https://github.com/harini1006/Thresholdingg/assets/113497405/3ad1d874-be00-4cf1-9575-c7ef03b68a86)

![image](https://github.com/harini1006/Thresholdingg/assets/113497405/a5dcb661-8a83-44fc-b95c-4bd27f3d44b5)


### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/harini1006/Thresholdingg/assets/113497405/77325ad0-666f-4f80-bf03-7ef3ed68596d)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
