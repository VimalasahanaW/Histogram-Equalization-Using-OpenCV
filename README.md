# EXP-3-Record-Histogram-processing
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
Read the image `parrot image.jpg` in grayscale format.

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
**Name: VIMALA SAHANA W**  
### Register No: 212223040241

---

## Import Python necessary libraries

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

```
## Histogram Equalization for Grayscale Images
```
img = cv2.imread('parrot image.jpg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

```
## Output

<img width="493" height="567" alt="image" src="https://github.com/user-attachments/assets/7d9f8b7f-f271-46a2-bb21-288581bb4346" />



```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
## Output

<img width="780" height="566" alt="image" src="https://github.com/user-attachments/assets/4a9902fa-6659-48da-918d-37fa8fc414cd" />



```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
## Output

<img width="753" height="591" alt="image" src="https://github.com/user-attachments/assets/0bdf193d-3642-48a9-92df-d0d1085dee74" />



```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
## Output

<img width="470" height="570" alt="image" src="https://github.com/user-attachments/assets/3d2684fc-7c73-4bf3-8a42-b7ea160fdbce" />



## Histogram Equalization for Color Images

```
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
 plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show() 
```
## Output

<img width="406" height="545" alt="image" src="https://github.com/user-attachments/assets/dd788ed0-75bb-4eb3-bd14-c54fcd6332ba" />


```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
## Output

<img width="406" height="545" alt="image" src="https://github.com/user-attachments/assets/b06b4eae-e198-4629-968d-8db1a00c2289" />


```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
## Output

<img width="1367" height="512" alt="image" src="https://github.com/user-attachments/assets/1c088a15-1e61-42ec-a521-4f0b7ac79f00" />


```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

<img width="1377" height="443" alt="image" src="https://github.com/user-attachments/assets/e1b0b036-60d5-44ec-8072-0c93afcc67ea" />


### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution 

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
