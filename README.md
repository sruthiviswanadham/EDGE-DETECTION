# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

## Program:

```python
Developed By: Viswanadham Venkata Sai Sruthi
Reg.No: 212223100061

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('HappyFish.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(12, 12))

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

```
### Original Image:
![image](https://github.com/user-attachments/assets/ae8dc561-010c-4010-8c2d-a6b46ed90ad5)
<br>

```python
# Apply Sobel edge detector
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions

# Sobel Edge Detection
plt.subplot(2, 2, 2)
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
### SOBEL EDGE DETECTOR
![image](https://github.com/user-attachments/assets/10c25fcc-cf0e-4078-a8c8-e62fb4d4cd6c)
<br>

```python
# Apply Laplacian edge detector
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

# Laplacian Edge Detection
plt.subplot(2, 2, 3)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```
### LAPLACIAN EDGE DETECTOR
![image](https://github.com/user-attachments/assets/89769489-cdc5-4b86-a701-c5f0829db69f)

<br>

```python
# Apply Canny edge detector
canny_edges = cv2.Canny(gray_image, 50, 150)

# Canny Edge Detection
plt.subplot(2, 2, 4)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

# Show all results
plt.tight_layout()
plt.show()

```
### CANNY EDGE DETECTOR
![image](https://github.com/user-attachments/assets/cad1a03a-fc99-485e-8c0b-a8a99bc08cd6)

<br>

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
