# Implementation-of-filter
# Name: Markandeyan Gokul
# Reg: 212224240086
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



### 1. Smoothing Filters

#### i) Using Averaging Filter
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("taj.jpeg")
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
## Output
<img width="717" height="473" alt="image" src="https://github.com/user-attachments/assets/244de902-cdec-4e9f-b5dc-eb3e88fcff49" />

#### ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
## Output
<img width="531" height="348" alt="image" src="https://github.com/user-attachments/assets/073977d9-4427-4870-b590-6f2feaee60a5" />

#### iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
## Output
<img width="515" height="348" alt="image" src="https://github.com/user-attachments/assets/07cdabd9-7fdc-4632-92df-28d878d2822e" />

#### iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
## Output
<img width="717" height="473" alt="image" src="https://github.com/user-attachments/assets/375579b7-9f5f-4cca-9fed-9af7f8841d61" />

### 2. Sharpening Filters

#### i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
## Output
<img width="515" height="348" alt="image" src="https://github.com/user-attachments/assets/c0227e66-8feb-4550-9822-ff179e48103d" />

#### ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
## Output
<img width="515" height="348" alt="image" src="https://github.com/user-attachments/assets/2d1cccb4-43eb-49c2-a8e1-86fdc81fd335" />

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
