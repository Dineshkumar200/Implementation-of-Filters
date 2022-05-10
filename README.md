# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the necessary modules


### Step2
For performing smoothing operation on a image.

Average filter:
```python

avg_kernel=np.ones((13,13),np.float32)/169
average_filter_image=cv2.filter2D(image,-1,avg_kernel)
```
Weighted average filter :
```python
wt_avg_kernel=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
wt_average_filter_image=cv2.filter2D(image,-1,wt_avg_kernel)
```
Gaussian Blur:
```python
gaussian_blur=cv2.GaussianBlur(image,(31,31),0,0)
```
Median filter:
```python
median_blur=cv2.medianBlur(image,11)
```


### Step3
For performing sharpening on a image.

Laplacian Kernel:
```python
lap_kernel=np.array([[-1,-1,-1],[-1,8,-1],[-1,-1,-1]])
lap_image=cv2.filter2D(image,-1,lap_kernel)
```
Laplacian Operator:
```python
Lap_sharp=cv2.Laplacian(image,cv2.CV_64F)
```




### Step4
Display all the images with their respective filters. 

## Program:
### Developed By   : Dineshkumar V
### Register Number: 212220230013
</br>

```Python

import cv2
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread('k.jpg')
img1=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)

```

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
kernel=np.ones((13,13),np.float32)/169
image=cv2.filter2D(img1,-1,kernel)
plt.figure(figsize=(10,10))

plt.subplot(1,2,1)

plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(image)


```
ii) Using Weighted Averaging Filter
```Python

kernel2=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image1=cv2.filter2D(img1,-1,kernel2)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(image1)


```
iii) Using Gaussian Filter
```Python

img4=cv2.GaussianBlur(src=img1,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)

plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img4)


```

iv) Using Median Filter
```Python
img5=cv2.medianBlur(src=img1,ksize=11)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img4)


```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
img6=cv2.filter2D(img1,-1,kernel3)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img6)



```
ii) Using Laplacian Operator
```Python

img7=cv2.Laplacian(img1,cv2.CV_64F)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img1)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Average Filter image')
plt.imshow(img7)



```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter

![f1](https://user-images.githubusercontent.com/75235789/167658716-83b5ba29-65b6-43e4-a496-cf2dd2a69af7.jpg)


ii) Using Weighted Averaging Filter

![f2](https://user-images.githubusercontent.com/75235789/167658713-38b1b6e4-5237-4890-bb5d-777a87b02bb9.jpg)


iii) Using Gaussian Filter

![f3](https://user-images.githubusercontent.com/75235789/167658708-9cdd3d3e-0ac5-4c0b-86fe-fea29ebe9a3f.jpg)



iv) Using Median Filter
![f4](https://user-images.githubusercontent.com/75235789/167658699-9efda682-e02a-461d-b9c8-4d4dee9c80f1.jpg)


### 2. Sharpening Filters


i) Using Laplacian Kernal

![f5](https://user-images.githubusercontent.com/75235789/167658726-a3ed6e1b-ecc7-4027-8e01-eed12088df64.jpg)



ii) Using Laplacian Operator
![f6](https://user-images.githubusercontent.com/75235789/167658721-28c9588a-d223-4b72-8429-a03006346749.jpg)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
