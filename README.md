# Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

## Learning Objectives

- Understand image segmentation using thresholding.
- Perform Global Thresholding.
- Apply Adaptive Mean and Adaptive Gaussian Thresholding.
- Implement Otsu's Thresholding.
- Compare different thresholding techniques.

## Software Used

- Anaconda – Python
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

1. Import the required libraries.
2. Read the input image using OpenCV.
3. Convert the image into grayscale.
4. Apply Global Thresholding.
5. Apply Adaptive Mean Thresholding.
6. Apply Adaptive Gaussian Thresholding.
7. Apply Otsu's Thresholding.
8. Display and compare all thresholding outputs.

## Program

### Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Step 2: Read the Image

```python
image_path = r"C:\Users\acer\images\Eagle_in_Flight.jpg"

img = cv2.imread(image_path)

if img is None:
    raise FileNotFoundError("Image not found. Check the image path.")

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.figure(figsize=(8, 5))
plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis("off")
plt.show()
```

### Step 3: Convert Image to Grayscale

```python
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(8, 5))
plt.imshow(gray, cmap="gray")
plt.title("Grayscale Image")
plt.axis("off")
plt.show()
```

### Step 4: Global Thresholding

```python
ret, global_thresh = cv2.threshold(
    gray, 127, 255, cv2.THRESH_BINARY
)

print("Global Threshold Value:", ret)

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.imshow(gray, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(global_thresh, cmap="gray")
plt.title("Global Thresholding")
plt.axis("off")

plt.show()
```

### Step 5: Adaptive Mean Thresholding

```python
adaptive_mean = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_MEAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.imshow(gray, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(adaptive_mean, cmap="gray")
plt.title("Adaptive Mean Thresholding")
plt.axis("off")

plt.show()
```

### Step 6: Adaptive Gaussian Thresholding

```python
adaptive_gaussian = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.imshow(gray, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(adaptive_gaussian, cmap="gray")
plt.title("Adaptive Gaussian Thresholding")
plt.axis("off")

plt.show()
```

### Step 7: Otsu's Thresholding

```python
otsu_value, otsu_thresh = cv2.threshold(
    gray,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

print("Otsu's Optimal Threshold Value:", otsu_value)

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.imshow(gray, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(otsu_thresh, cmap="gray")
plt.title("Otsu's Thresholding")
plt.axis("off")

plt.show()
```

### Step 8: Compare All Thresholding Techniques

```python
images = [
    ("Original Grayscale", gray),
    ("Global Thresholding", global_thresh),
    ("Adaptive Mean", adaptive_mean),
    ("Adaptive Gaussian", adaptive_gaussian),
    ("Otsu's Thresholding", otsu_thresh)
]

plt.figure(figsize=(14, 9))

for i, (title, result) in enumerate(images):
    plt.subplot(2, 3, i + 1)
    plt.imshow(result, cmap="gray")
    plt.title(title)
    plt.axis("off")

plt.tight_layout()
plt.show()
```

## Developed By

- **Name:** Shaajini N
- **Register No:** 212225040395

## Output

### 1. Original Grayscale Image

- The input image is converted into grayscale.
- This image is used as the input for thresholding techniques.

### 2. Global Thresholding

- A fixed threshold value of 127 is used.
- Pixels are separated into foreground and background.

### 3. Adaptive Mean Thresholding

- Threshold values are calculated based on the local neighbourhood.
- Useful for images with uneven illumination.

### 4. Adaptive Gaussian Thresholding

- Gaussian-weighted neighbourhood values are used to calculate thresholds.
- Provides locally adjusted segmentation.

### 5. Otsu's Thresholding

- The optimal threshold value is automatically calculated.
- No manual threshold value is required.

### 6. Comparison Output

- All thresholding techniques are displayed together for comparison.

## Result

Thus, image segmentation was successfully performed using Global Thresholding, Adaptive Mean Thresholding, Adaptive Gaussian Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

## Output Screenshots

Add your Jupyter Notebook screenshots below:

- **Output 1:** Original and Grayscale Images
- **Output 2:** Global Thresholding
- **Output 3:** Adaptive Mean Thresholding
- **Output 4:** Adaptive Gaussian Thresholding
- **Output 5:** Otsu's Thresholding
- **Output 6:** Comparison of All Techniques

## Instructions

1. Open Anaconda Navigator and launch Jupyter Notebook.
2. Run each program separately in the given order.
3. Check that the image is loaded correctly.
4. Capture screenshots of the outputs.
5. Copy this README content into your GitHub repository.
6. Commit the changes.

**Note:** Attach the lab report PDF separately in your LMS submission and mention your GitHub repository URL in the submission text.
