# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```python

#Developed By: Lokesh Krishnaa M
#Register No: 212220230030
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("hinata.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("hinata.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(5,5))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```

## OUTPUT:

### Original Image and Grayscale Image

![001](https://user-images.githubusercontent.com/75234646/169647396-0ca0617d-0b4e-4b75-8162-2a46dd79c1e8.png)


### Global Thresholding

![002](https://user-images.githubusercontent.com/75234646/169647398-2621ca60-e319-4ac2-9dbc-627edfdf5cc5.png)

![003](https://user-images.githubusercontent.com/75234646/169647400-5bb41958-c519-43c8-b331-7c94edb648bf.png)

![004](https://user-images.githubusercontent.com/75234646/169647402-11560331-e493-4b52-9ede-ecda487fa854.png)

![005](https://user-images.githubusercontent.com/75234646/169647406-58bfcc9d-58b5-4324-b3e3-ea12c017c266.png)

![006](https://user-images.githubusercontent.com/75234646/169647524-e590db31-8335-407b-bb97-c709868360d9.png)


### Adaptive Thresholding

![otsu](https://user-images.githubusercontent.com/75234646/169647525-9a170a93-0700-4d7b-aa2a-a7b5714b9f2f.png)

![1](https://user-images.githubusercontent.com/75234646/169647528-570484b4-8271-4288-b052-34cc82afb30a.png)

![2](https://user-images.githubusercontent.com/75234646/169647531-e11df725-9390-4a00-a7c7-693a7d3d9cb9.png)

### Optimum Global Thesholding using Otsu's Method




## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
