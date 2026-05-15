# edge-detection-opencv

## Aim
To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

## Software Required
- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  
## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

## Developed By

- **Name:** NANDIKA S
- **Register No:** 212224230175

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('tiger.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off') 

## Output

- ORIGINAL IMAGE
<img width="702" height="488" alt="image" src="https://github.com/user-attachments/assets/b4370e1b-f91c-49bb-90a3-01031c37dc91" />

- SOBEL EDGE DETECTION
<img width="688" height="483" alt="image" src="https://github.com/user-attachments/assets/4d9c19cb-15e8-45a5-a332-be5ece1243fa" />

- LAPLACIAN EDGE DETECTION
<img width="689" height="481" alt="image" src="https://github.com/user-attachments/assets/4fd0057f-4eea-4b83-a659-ee372c32f25c" />

- CANNY EDGE DETECTION
<img width="680" height="482" alt="image" src="https://github.com/user-attachments/assets/cddeb1bf-bca9-4e8a-aef7-babc814ce7d1" />

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
