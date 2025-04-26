# Implementation-of-filter
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
End the program

## Program:
### Developed By   : SANDHIYA R
### Register Number: 212223240146
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as 
image = cv2.imread('pcb.webp', cv2.IMREAD_GRAYSCALE)
kernel = np.ones((4, 4), np.float32) / 9
averaged_image = cv2.filter2D(image, -1, kernel)
plt.imshow(averaged_image, cmap='gray')
plt.title("Averaging Filter")
plt.axis('off')
plt.show()



```
ii) Using Weighted Averaging Filter
```Python
weighted_kernel = np.array([[1, 2, 1], 
                            [2, 4, 2], 
                            [1, 2, 1]], np.float32)

weighted_kernel = weighted_kernel / weighted_kernel.sum() 
weighted_image = cv2.filter2D(image, -1, weighted_kernel)  

plt.imshow(weighted_image, cmap='gray')
plt.title("Weighted Averaging Filter")
plt.axis('off')
plt.show()

```
iii) Using Gaussian Filter
```Python

gaussian_image = cv2.GaussianBlur(image, (3, 3), 1)
plt.imshow(gaussian_image, cmap='gray')
plt.title("Gaussian Filter")
plt.axis('off')
plt.show()


```
iv)Using Median Filter
```Python

median_image = cv2.medianBlur(image, 3)
plt.imshow(median_image, cmap='gray')
plt.title("Median Filter")
plt.axis('off')
plt.show()


```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python

laplacian_kernel = np.array([[0, 1, 0], [1, -4, 1], [0, 1, 0]], np.float32)
laplacian_image = cv2.filter2D(image, -1, laplacian_kernel)

sharpened_laplacian_image = cv2.add(image, laplacian_image)
plt.imshow(sharpened_laplacian_image, cmap='gray')
plt.title("Laplacian Kernel")
plt.axis('off')
plt.show()
```
ii) Using Laplacian Operator
```Python

laplacian_operator_image = cv2.Laplacian(image, cv2.CV_64F)  # Laplacian operator
laplacian_operator_image = cv2.convertScaleAbs(laplacian_operator_image)  # Convert to absolute values
sharpened_operator_image = cv2.add(image, laplacian_operator_image)

plt.imshow(sharpened_operator_image, cmap='gray')
plt.title("Laplacian Operator")
plt.axis('off')
plt.show()

```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

![image](https://github.com/user-attachments/assets/0b7d26aa-43e2-460a-90ca-223327eabda5)


ii)Using Weighted Averaging Filter

![image](https://github.com/user-attachments/assets/c671c4d4-0f2a-4d7e-affb-5d9390b1b9b8)


iii)Using Gaussian Filter

![image](https://github.com/user-attachments/assets/616d8830-fb79-4f9b-8d8b-b4e8f2f401a2)



iv) Using Median Filter

![image](https://github.com/user-attachments/assets/f5fd2b68-8d8f-42c3-b7ae-b6a643103bd9)



### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

![image](https://github.com/user-attachments/assets/af27b02f-088f-4930-9d6b-f18baebfd19f)



ii) Using Laplacian Operator


![image](https://github.com/user-attachments/assets/7138b866-7c79-4872-b83f-5d4dc6eeb8cc)



## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
