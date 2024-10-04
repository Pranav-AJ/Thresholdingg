# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the required libraries like OpenCV, NumPy, and Matplotlib.

### Step2:
Read the input image from the file and convert it to grayscale using OpenCV.

### Step3:
Apply different thresholding techniques: Global thresholding (binary, binary inverse, truncate, to zero, to zero inverse). Otsu’s thresholding. Adaptive thresholding (mean, Gaussian).
### Step4:
Store the results of each thresholding operation in a list for easy visualization.

### Step5:
Display the original grayscale image and the thresholded images side by side using Matplotlib to compare results.

## Program

```python
# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt



# Read the Image and convert to grayscale

image = cv2.imread('leaf.jpeg')
plt.imshow(image)
plt.title('Original Image')
plt.xticks([]), plt.yticks([])
plt.show()
# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display the original grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()



# Use Global thresholding to segment the image

ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()


# Use Adaptive thresholding to segment the image


th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()

# Use Otsu's method to segment the image 

ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()

```
## Output

### Original Image

![image](https://github.com/user-attachments/assets/02723164-4340-49f8-b805-a9da9282e627)

### Grayscale Image

![image](https://github.com/user-attachments/assets/01138ada-55ae-456e-aa7b-b4a9783052a6)


### Global Thresholding
![image](https://github.com/user-attachments/assets/9d036d2a-8f33-40d4-963d-afcb6686891d)


### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/bf7601e1-3d90-4f9a-9cf6-9a1a0916ca08)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/46f52a9b-0c69-462e-910e-425b960590ac)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
