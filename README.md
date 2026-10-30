# Implementation-of-filter
## Aim

To implement filters for smoothing and sharpening images in the spatial domain.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import the required libraries.

### Step 2
Read the image and convert it from BGR to RGB.

### Step 3
Apply the required smoothing and sharpening filters to the image separately.

### Step 4
Plot and display the original and filtered images using matplotlib.pyplot.

### Step 5
End the program.

## Program

*Developed By:* Rithesh S

*Register Number:* 212225220084


## 1. Smoothing Filters

### i) Using Averaging Filter

python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("sv.jpeg")
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


### ii) Using Weighted Averaging Filter

python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show())


### iii) Using Gaussian Filter

python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()


### iv) Using Median Filter

python
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


## 2. Sharpening Filters

### i) Using Laplacian Linear Kernel

python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()


### ii) Using Laplacian Operator

python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()


## Output

### 1. Smoothing Filters

#### i) Using Averaging Filter

<img width="717" height="604" alt="download" src="https://github.com/user-attachments/assets/dfaf90f6-7336-4d86-8af1-cb12a2e86b4e" />


#### ii) Using Weighted Averaging Filter

<img width="524" height="410" alt="download" src="https://github.com/user-attachments/assets/fa56ccff-860e-4f42-98a5-7753322d70d8" />


#### iii) Using Gaussian Filter
<img width="498" height="410" alt="download" src="https://github.com/user-attachments/assets/fcaf1b1d-108a-43b5-9f7a-003746694567" />

#### iv) Using Median Filter

<img width="717" height="604" alt="download" src="https://github.com/user-attachments/assets/65c940a9-9671-4635-893b-57c1d9f9c0db" />


### 2. Sharpening Filters

#### i) Using Laplacian Kernel

<img width="498" height="410" alt="download" src="https://github.com/user-attachments/assets/accca461-e6d6-4eb1-80d0-9388dceb29a6" />


#### ii) Using Laplacian Operator

<img width="498" height="410" alt="download" src="https://github.com/user-attachments/assets/65430e52-015a-42ad-b5ef-b9d68cb8a6ed" />

## Result

Thus, filters were implemented for smoothing and sharpening images in the spatial domain using OpenCV and Python.
