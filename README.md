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
**Name:** KAVYA T 
**Register No:** 2305003004
  ### Ex. No. 02

#### 1. import libraries.
```python
import cv2
import matplotlib.pyplot as plt

```
#### 2. Read grayscale image.
```python
Gray_image = cv2.imread("WhatsApp Image 2026-05-12 at 14.16.29.jpeg", 0)

```
#### 3. Display Gray Scale Image.
```python
plt.figure(figsize=(6,6))
plt.imshow(Gray_image, cmap='gray')
plt.title("Gray Scale Image")
plt.axis("off")
plt.show()

```
#### 4. Read color image.
```python
Color_image = cv2.imread("WhatsApp Image 2026-05-12 at 14.32.43.jpeg")

```
#### 5.Convert BGR to RGB.
```python
Color_rgb = cv2.cvtColor(Color_image, cv2.COLOR_BGR2RGB)

```
#### 6.Display Color Image.
```python
plt.figure(figsize=(6,6))
plt.imshow(Color_rgb)
plt.title("Color Image")
plt.axis("off")
plt.show()

```
#### 7.Histogram of Gray Scale Image.
```python
hist_gray = cv2.calcHist([Gray_image], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Gray Scale Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_gray, color='black')
plt.xlim([0,256])
plt.show()

```
#### 8.Histogram of Blue Channel.
```python
hist_blue = cv2.calcHist([Color_image], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Blue Channel")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_blue, color='blue')
plt.xlim([0,256])
plt.show()

```
#### 9.Histogram Equalization.
```python
equalized = cv2.equalizeHist(Gray_image)
```
#### 10.Histogram of Equalized Image
```python
hist_equalized = cv2.calcHist([equalized], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.title("Histogram of Equalized Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.plot(hist_equalized, color='green')
plt.xlim([0,256])
plt.show()
```


##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed
<img width="671" height="453" alt="image" src="https://github.com/user-attachments/assets/5fa35b66-c11e-405d-8848-6e36ddc08cee" />


- Histogram of original grayscale image is plotted
<img width="757" height="482" alt="image" src="https://github.com/user-attachments/assets/4a0f41f9-ee3b-4a85-a26a-161715b3c3b1" />


### Color Image Histogram Equalization

- Original color image is displayed
<img width="750" height="495" alt="image" src="https://github.com/user-attachments/assets/fd2a2d76-66f0-4985-98dd-4ce77bd71014" />

- Histogram of B, G, R channels is plotted
- <img width="832" height="480" alt="image" src="https://github.com/user-attachments/assets/353113cb-fbab-4ced-a2be-0927b4aa35b6" />

  

### Equalization Image 

- Display Equalized Image
- <img width="717" height="448" alt="image" src="https://github.com/user-attachments/assets/3d89370e-99f9-46c3-80b8-ae5630192c83" />


- Histogram of Equalized Image
- <img width="739" height="513" alt="image" src="https://github.com/user-attachments/assets/435f416c-f9d0-45a0-b371-f874aabd1819" />




## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
