# Implementation-of-filter
## Aim :
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required :
Anaconda - Python 3.7

## Algorithm :
### Step 1 :
Read the image and convert it from BGR to RGB color space.
### Step 2 :
Apply average filtering using a normalized 11x11 kernel.
### Step 3 :
Apply weighted average filtering using a Gaussian-like 3x3 kernel.
### Step 4 :
Apply Gaussian and Median blur to reduce noise and smooth the image.
### Step 5 :
Apply custom Laplacian kernel and built-in Laplacian operator for edge detection.

## Program :
```
Developed By : NITHYA D
Register Number : 212223240110
```
### 1. Smoothing Filters
#### i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("img.jpg")
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
#### ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
#### iii) Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
#### iv)Using Median Filter
```Python
median = cv2.medianBlur(image2, 13)
plt.imshow(cv2.cvtColor(median, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct color display
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

### 2. Sharpening Filters
#### i) Using Laplacian Linear Kernal
```Python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

#### ii) Using Laplacian Operator
```Python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## OUTPUT :
### 1. Smoothing Filters :

#### i) Using Averaging Filter
<img width="717" height="253" alt="image" src="https://github.com/user-attachments/assets/67ebcfe0-078c-43d2-a747-5db364053082" />

#### ii)Using Weighted Averaging Filter
<img width="515" height="372" alt="image" src="https://github.com/user-attachments/assets/addef154-dc44-43f8-9de8-163abe163a09" />


#### iii)Using Gaussian Filter
<img width="515" height="372" alt="image" src="https://github.com/user-attachments/assets/dfc4157c-c165-42d1-930e-30f7459b37de" />


#### iv) Using Median Filter
<img width="515" height="372" alt="image" src="https://github.com/user-attachments/assets/4a8c7a70-9600-4396-b3ad-442dcc804718" />


### 2. Sharpening Filters :
#### i) Using Laplacian Kernal
<img width="515" height="372" alt="image" src="https://github.com/user-attachments/assets/0234b3d2-7e30-49a7-b5fe-6e503bc1bcb4" />

#### ii) Using Laplacian Operator
<img width="515" height="372" alt="image" src="https://github.com/user-attachments/assets/8834a5aa-a2be-4d6e-b9b8-8e90efaa656d" />

## Result :
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
