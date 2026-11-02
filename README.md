# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
## Name: POOJA SRI P
## Register No: 212224230197  
```.PY

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read image in grayscale
img = cv2.imread('pic.jpeg', cv2.IMREAD_GRAYSCALE)

# Display Original Image
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

# Display Original Histogram
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')
plt.show()

# Histogram Equalization
img_eq = cv2.equalizeHist(img)

# Display Equalized Histogram
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

# Display Equalized Image
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

# Read Color Image
img = cv2.imread('pic.jpeg', cv2.IMREAD_COLOR)

# Convert BGR to HSV
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Apply Histogram Equalization to V channel
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Convert HSV to BGR
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# Display Equalized Image
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()

# Display Histogram Equalized
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()

# Display Original and Equalized Images
plt.figure(figsize=(20, 10))

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()

# Display Original and Equalized Histograms
plt.figure(figsize=[15, 4])

plt.subplot(121)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')

plt.subplot(122)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')

plt.show()

```
##  Output

### Grayscale Histogram Equalization

<img width="562" height="530" alt="image" src="https://github.com/user-attachments/assets/04260737-8af0-41fe-ac82-6bc7f2c74dde" />

<img width="843" height="537" alt="image" src="https://github.com/user-attachments/assets/70b7e9f8-b58f-4406-b21e-2f654fcf6be4" />

<img width="808" height="542" alt="image" src="https://github.com/user-attachments/assets/181a04ac-3cc2-4903-9fdd-58b6ebb55be2" />

<img width="608" height="537" alt="image" src="https://github.com/user-attachments/assets/8195c83b-e5b2-4c35-b501-9cd23b49a2d9" />

### Color Image Histogram Equalization

<img width="536" height="540" alt="image" src="https://github.com/user-attachments/assets/de0a5fa0-3583-4ac7-a27a-d1826293791b" />

<img width="886" height="560" alt="image" src="https://github.com/user-attachments/assets/1ed9f57f-ba1f-482c-9a67-75ad106369a0" />

<img width="1392" height="487" alt="image" src="https://github.com/user-attachments/assets/cfe8cfb1-7444-4b84-98b4-7d5614b748e3" />

<img width="1427" height="412" alt="image" src="https://github.com/user-attachments/assets/3116b15e-a76f-4356-86f1-20babbe16a21" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
