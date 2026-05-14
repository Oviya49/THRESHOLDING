# EXP- 08  THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using Python and OpenCV.

## Learning Objective
```
Understand image segmentation techniques
Learn Global Thresholding
Learn Adaptive Thresholding
Understand Otsu’s Thresholding Method
Visualize segmented images using OpenCV
```

## Software Required
```
Anaconda – Python 3.x
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
```

## Algorithm
```
Step 1:
Import the required libraries such as OpenCV, NumPy, and Matplotlib.

Step 2:
Read the input image using OpenCV and convert the image into grayscale.

Step 3:
Apply Global Thresholding using a fixed threshold value to segment the image.

Step 4:
Apply Adaptive Thresholding using the Gaussian method to segment different regions of the image.

Step 5:
Apply Otsu’s Thresholding method to determine the optimal threshold value automatically.

Step 6:
Display the original image and all thresholded output images using Matplotlib.
```

### Name: Oviya N
### Reg.No: 212223040140

## Program:
```
# Import required libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt


# Step 1: Read the image using OpenCV
image = cv2.imread('Qn8_thresholding.tif')


# Step 2: Convert the image into grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)


# Step 3: Apply Global Thresholding
# Threshold value = 127
_, global_thresholded = cv2.threshold(
    gray_image,
    127,
    255,
    cv2.THRESH_BINARY
)


# Step 4: Apply Adaptive Thresholding
# Gaussian adaptive thresholding
adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)


# Step 5: Apply Otsu's Thresholding
# Automatically calculates optimal threshold value
_, otsu_thresholded = cv2.threshold(
    gray_image,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)


# Step 6: Display Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')


# Display Global Thresholding Result
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')


# Display Adaptive Thresholding Result
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')


# Display Otsu's Thresholding Result
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')


# Adjust layout and display images
plt.tight_layout()
plt.show()
```

## Output

### Original Image:
Displays the original input image.

<img width="209" height="208" alt="image" src="https://github.com/user-attachments/assets/421a972a-955b-4de7-8c4c-eea51e68f5d8" />

### Global Thresholding:
Displays the segmented image using a fixed threshold value.

<img width="545" height="470" alt="image" src="https://github.com/user-attachments/assets/ae4290e6-8ab2-4e34-af24-47384f180887" />

### Adaptive Thresholding:
Displays the segmented image using local adaptive threshold values.

<img width="545" height="470" alt="image" src="https://github.com/user-attachments/assets/ea789850-9a83-4f21-88df-549e38ab5e73" />

### Otsu's Thresholding:
Displays the segmented image using automatically calculated threshold values.

<img width="545" height="470" alt="image" src="https://github.com/user-attachments/assets/3b4c9d43-93a8-44fc-ae86-7290b62cce3b" />

## Result
Thus, the images are successfully segmented using Global Thresholding, Adaptive Thresholding, and Otsu’s Thresholding using Python and OpenCV.


