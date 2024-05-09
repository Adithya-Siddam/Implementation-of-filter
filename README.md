# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1 :- Import the required modules.

Step2 :- Convert the image from BGR to RGB.

Step3:- Apply the required filters for the image separately.

Step4:- Plot the original and filtered image by using matplotlib.pyplot

Step5:- End the program.

## Program:
```
Developed By   : S Adithya Chowdary.
Register Number: 212221230100.
```
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("car.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)

kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")


```
ii) Using Weighted Averaging Filter
```Python
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")


```
iii) Using Gaussian Filter
```Python
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")


```

iv) Using Median Filter
```Python
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")

```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")

```
ii) Using Laplacian Operator
```Python
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")

```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter
</br>
![image](https://github.com/Adithya-Siddam/Implementation-of-filter/assets/93427248/2371ce56-9364-4a7a-9834-d2052a45d077)

</br>

ii) Using Weighted Averaging Filter
</br>
![image](https://github.com/Adithya-Siddam/Implementation-of-filter/assets/93427248/a3c10cf6-f4ab-462c-9fec-dd7b4ff75d2d)

</br>

iii) Using Gaussian Filter
</br>
![image](https://github.com/Adithya-Siddam/Implementation-of-filter/assets/93427248/4a78f6ee-1cf3-4f8a-a50e-bcd492836f0a)

</br>

iv) Using Median Filter
</br>
![image](https://github.com/Adithya-Siddam/Implementation-of-filter/assets/93427248/93192fbc-076e-436e-8204-6a554ec7527f)

</br>

### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal
</br>
![image](https://github.com/Adithya-Siddam/Implementation-of-filter/assets/93427248/5f84c35a-5ca8-4b17-8b8e-656ad9adf16e)
</br>

ii) Using Laplacian Operator
</br>
![image](https://github.com/Adithya-Siddam/Implementation-of-filter/assets/93427248/aa292857-e755-40f1-9510-c0464ba31888)

</br>

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
