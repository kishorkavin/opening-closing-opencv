# Opening and Closing Operations Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 7:

Compare the original, opened, and closed images.

## Program

## Developed By

### Name: Kailash V

### Register No: 212224240067
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = np.zeros((400, 600), dtype=np.uint8)

cv2.putText(img, "IMAGE PROCESSING", (80, 200),
            cv2.FONT_HERSHEY_SIMPLEX, 1.5, 255, 3)

kernel = np.ones((5, 5), np.uint8)

opening = cv2.morphologyEx(img, cv2.MORPH_OPEN, kernel)

closing = cv2.morphologyEx(img, cv2.MORPH_CLOSE, kernel)

plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.imshow(img, cmap="gray")
plt.title("Original")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(opening, cmap="gray")
plt.title("Opening")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(closing, cmap="gray")
plt.title("Closing")
plt.axis("off")

plt.tight_layout()
plt.show()
```

## Output

### Original Image

- The input image is displayed.
- The image serves as the source for morphological processing.


<img width="370" height="264" alt="image" src="https://github.com/user-attachments/assets/8c4abdbf-3a47-4aec-8dd3-2a1dd1372257" />


### Opening Operation

- Original image is displayed.
- Opened image is displayed.
- Small foreground noise is removed.
- Thin protrusions and isolated pixels are eliminated.
- Object boundaries become smoother.

<img width="357" height="265" alt="image" src="https://github.com/user-attachments/assets/2589845a-13fb-40d5-abb2-26b89becaf74" />


### Closing Operation

- Original image is displayed.
- Closed image is displayed.
- Small holes and gaps inside objects are filled.
- Broken regions are connected.
- Object boundaries become more continuous.


<img width="377" height="257" alt="image" src="https://github.com/user-attachments/assets/eb20fa0a-a27e-4a40-bba7-6481dd17bc44" />


## Applications

### Opening

- Noise removal in binary images.
- Separation of connected objects.
- Preprocessing for object detection.



### Closing

- Filling small holes in objects.
- Connecting nearby components.
- Enhancing segmented regions.

## Advantages

### Opening

- Removes unwanted foreground noise.
- Preserves major object structures.
- Improves segmentation quality.

### Closing

- Restores object continuity.
- Eliminates small background gaps.
- Improves object representation.

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV. 
