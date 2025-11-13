# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
Step 1: Start and Read the Image

Import the required libraries (cv2, numpy, matplotlib).

Read the input image using cv2.imread() and convert it to grayscale using cv2.cvtColor().

Step 2: Apply Global Thresholding

Use cv2.threshold() with a fixed threshold value to segment the image into foreground and background.

Step 3: Apply Adaptive Thresholding

Use cv2.adaptiveThreshold() to automatically calculate thresholds for different image regions, handling varying lighting conditions.

Step 4: Apply Otsu’s Thresholding

Use cv2.threshold() with the flag cv2.THRESH_OTSU to automatically find an optimal global threshold value.

Step 5: Display the Results

Show all the thresholded images using cv2.imshow() or matplotlib.pyplot and compare the outputs.

End the program with cv2.waitKey(0) and cv2.destroyAllWindows().


## Program

```python
# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
# Read the Image and convert to grayscale
``
image = cv2.imread('CoinsA.png')  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Original Image")
plt.axis('off')
plt.show()
```

# Use Global thresholding to segment the image
```
_, global_thresholded = cv2.threshold(gray_image, 101, 255, cv2.THRESH_BINARY)
# Global Thresholding
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
plt.show()
```

# Use Adaptive thresholding to segment the image
```
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 15, 3)
# Adaptive Thresholding
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
plt.show()
```



# Use Otsu's method to segment the image 
```
_, otsu_thresholded = cv2.threshold(gray_image, 1, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
# Otsu's Method
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
plt.show()
```

# Display the results
```

plt.tight_layout()
plt.show()
```

## Output

### Original Image
<img width="413" height="413" alt="image" src="https://github.com/user-attachments/assets/ff1b3fe0-b20c-4c52-9979-d8e9f8067e8c" />

### Global Thresholding
<img width="403" height="417" alt="image" src="https://github.com/user-attachments/assets/eab1e4aa-0c9d-4a26-82c5-18867ce9108c" />


### Adaptive Thresholding

<img width="451" height="410" alt="image" src="https://github.com/user-attachments/assets/ea4658b5-0cd0-4a51-95a4-70c9bb837e4f" />


### Optimum Global Thesholding using Otsu's Method
<img width="445" height="420" alt="image" src="https://github.com/user-attachments/assets/4bc71752-ff8e-44c0-8ee8-e2fa17097047" />



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
