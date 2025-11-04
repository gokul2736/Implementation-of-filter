# Implementation-of-filter  EXP-5
# Name: Markandeyan Gokul
# Register no:212224240086
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2

Convert the image from BGR to RGB.
### Step3

Apply the required filters for the image separately.
### Step4

Plot the original and filtered image by using matplotlib.pyplot.
### Step5

End the program.

## Program:
### Developed By   : Dharshan V
### Register Number: 212224240035
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("img0.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()



```
ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()


```
iii) Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

```
iv)Using Median Filter
```Python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()




```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python

kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()



```
ii) Using Laplacian Operator
```Python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()

```

## OUTPUT:
## original image:
<img width="456" height="634" alt="image" src="https://github.com/user-attachments/assets/6c002f9c-78e6-44ec-8b8f-2a24efccbcfc" />

### 1. Smoothing Filters

## i) Using Averaging Filter

<img width="458" height="629" alt="image" src="https://github.com/user-attachments/assets/eb6f61be-7a74-4832-b69d-99c8fbf71f9e" />

## ii)Using Weighted Averaging Filter
<img width="394" height="498" alt="image" src="https://github.com/user-attachments/assets/d8f2434c-aec9-4131-852e-5128a4b35e51" />


## iii)Using Gaussian Filter
<img width="394" height="505" alt="image" src="https://github.com/user-attachments/assets/547936d7-c71e-456b-8321-53962c0a9cdc" />


## iv) Using Median Filter

<img width="467" height="643" alt="image" src="https://github.com/user-attachments/assets/abedc9f6-7d97-4412-84e9-c15b66def08e" />

### 2. Sharpening Filters
## i) Using Laplacian Kernal

<img width="458" height="633" alt="image" src="https://github.com/user-attachments/assets/2d566db8-7b94-42e4-abff-4b190bea1514" />


## ii) Using Laplacian Operator

<img width="372" height="501" alt="image" src="https://github.com/user-attachments/assets/153bbf00-6151-4006-953e-b6545ef74eef" />

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
