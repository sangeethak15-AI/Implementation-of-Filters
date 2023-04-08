# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().

### Step2
Convert the saved BGR image to RGB using cvtColor().

### Step3
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

### Step4
Apply the filters using cv2.filter2D() for each respective filters.

### Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().
## Program:
### Developed By   :Sangeetha.K
### Register Number:212221230085
</br>

### 1. Smoothing Filters
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread('imagee.jpg')
img2=cv2.cvtColor (img,cv2.COLOR_BGR2RGB) 
kernel = np.ones ((9,9), np.float32)/121
img3=cv2.filter2D(img2,-1, kernel)
```
i) Using Averaging Filter
```Python
plt.figure(figsize = (10,10))
plt.subplot(1,2,1)
plt.imshow(img2)
plt.title('Orignal') 
plt.axis('off')
plt.subplot(1,2,2)
plt.imshow(img3)
plt.title('Filtered')
plt.axis('off')



```
ii) Using Weighted Averaging Filter
```Python
k2=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
img3=cv2.filter2D(img2,-1,k2)
plt.figure(figsize = (10,10))
plt.subplot(1,2,1) 
plt.imshow(img2)
plt.title('Orignal') 
plt.axis('off')
plt.subplot(1,2,2)
plt.imshow(img3)
plt.title('2Dfilter') 
plt.axis('off')
```
iii) Using Gaussian Filter
```Python
gauss_blur=cv2.GaussianBlur(src=img2,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.imshow(gauss_blur)
plt.title('Gauss_blur') 
plt.axis('off')
```

iv) Using Median Filter
```Python
median=cv2.medianBlur(src=img2,ksize=11)
plt.imshow(median)
plt.title('Median') 
plt.axis('off')
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python

k3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
img3=cv2.filter2D(img2,-1,k3)
plt.figure(figsize = (8,8))
plt.imshow(img3)
plt.title('Laplace_kernel') 
plt.axis('off')

```
ii) Using Laplacian Operator
```Python

new_img=cv2.Laplacian(img2,cv2.CV_64F)
plt.imshow(new_img)
plt.title('Laplace') 
plt.axis('off')
```

## OUTPUT:
### 1. Smoothing Filters


i) Using Averaging Filter
![pic1](https://user-images.githubusercontent.com/93992063/230704670-d55a0a43-fd42-4e12-b197-14215b766699.png)


ii) Using Weighted Averaging Filter
![Screenshot 2023-04-08 104246](https://user-images.githubusercontent.com/93992063/230704680-44a72a31-b042-4dbc-9b6e-d33b683f22a8.png)


iii) Using Gaussian Filter

![Screenshot 2023-04-08 104313](https://user-images.githubusercontent.com/93992063/230704685-cc0ddb29-0850-4244-aac1-da71cc70cbe4.png)

iv) Using Median Filter
![Screenshot 2023-04-08 104338](https://user-images.githubusercontent.com/93992063/230704695-ef33e67f-0185-4e04-bf77-9f091fbbd985.png)


### 2. Sharpening Filters


i) Using Laplacian Kernal
![Screenshot 2023-04-08 104400](https://user-images.githubusercontent.com/93992063/230704700-3d00a13b-d037-497a-9c66-e502fa856684.png)


ii) Using Laplacian Operator
![Screenshot 2023-04-08 104420](https://user-images.githubusercontent.com/93992063/230704710-a49fd1fc-5b18-4c16-b806-017ed0842e43.png)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
