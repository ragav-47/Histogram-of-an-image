# Histogram and Histogram Equalization of an image
## AIM:
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### Step 1:
Import the necessary libraries and read two images, Color image and Gray Scale image.
### Step 2:
Calculate the Histogram of Gray scale image and any one channel of the color image.
### Step 3:
Display the histograms.
### Step 4:
Equalize the grayscale image.
### Step 5:
Display the equalized grayscale image.

## Program:
```python
# Developed By: Vijayaragavan ARR
# Register Number: 212220230059

import cv2
import matplotlib.pyplot as plt
gray_img=cv2.imread("img1.jpg",0)
color_img=cv2.imread("img.jpg",-1)
gray_img=cv2.cvtColor(gray_img,cv2.COLOR_BGR2RGB)
color_img=cv2.cvtColor(color_img,cv2.COLOR_BGR2RGB)
plt.subplot(1,2,1)
plt.title("Color Image")
plt.axis("off")
plt.imshow(color_img)
plt.subplot(1,2,2)
plt.title("Gray Scale Image")
plt.axis("off")
plt.imshow(gray_img)
plt.show()

# Write your code to find the histogram of gray scale image and color image channels.

hist=cv2.calcHist([gray_img],[0],None,[256],[0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel("grayscale value")
plt.ylabel("pixel count")
plt.stem(hist)
plt.show()

# Display the histogram of gray scale image and any one channel histogram from color image

hist=cv2.calcHist([color_img],[0],None,[256],[0,256])
plt.title("Histogram of Color Image:Red Channel")
plt.xlabel("Intensity value")
plt.ylabel("pixel count")
plt.stem(hist)
plt.show()

# Write the code to perform histogram equalization of the image. 

equ=cv2.equalizeHist(cv2.imread('img1.jpg',0))
equ=cv2.cvtColor(equ,cv2.COLOR_BGR2RGB)
plt.title("Equalised Image")
plt.axis("off")
plt.imshow(equ)
plt.show()

```
## Output:
### Input Grayscale Image and Color Image

![output1](https://user-images.githubusercontent.com/75235488/166112973-9c7dda80-d7b5-4428-b9c1-70639f55ae7c.png)

![output2](https://user-images.githubusercontent.com/75235488/166112985-4ad437ec-f308-4796-b3da-4fd1249c671c.png)

### Histogram of Grayscale Image and any channel of Color Image

![output3](https://user-images.githubusercontent.com/75235488/166112991-9e2110f7-6a42-4f19-9e92-58176cf77c8f.png)

![output4](https://user-images.githubusercontent.com/75235488/166113001-eecd3443-5594-4336-aa1a-3aa748509661.png)

### Histogram Equalization of Grayscale Image

![output5](https://user-images.githubusercontent.com/75235488/166113007-3b5896dc-6fe0-484a-8238-fac7f3005e80.png)

## Result:

Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
