# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.

### Step3:

Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.
### Step5:

Use Otsu's method to segment the image and display the results.

## Program

# Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```
image = cv2.imread('panda.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('panda.jpeg',0)
```

# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```


# Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
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
## Output

### Original Image
![image](https://github.com/user-attachments/assets/ee480927-91ec-4552-bf7c-c80acce75fed)


### Global Thresholding
![image](https://github.com/user-attachments/assets/5f37bb78-ba96-4d67-9385-8d87bc37d009)
![image](https://github.com/user-attachments/assets/abbd3744-bbf9-471b-a815-86b318753dc7)
![image](https://github.com/user-attachments/assets/814eb3d5-2249-4c83-9e14-1965704854f2)
![image](https://github.com/user-attachments/assets/f4d256cd-4a38-4abe-9d61-ac660dc98da1)
![image](https://github.com/user-attachments/assets/0fcdecf3-0873-4402-852f-e68be2b71c75)


### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/9a0b7c01-ef48-4331-b53b-5a0f485b9126)
![image](https://github.com/user-attachments/assets/f2e788dc-b195-48cc-8ffd-1e947c3365bb)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/1366a82f-a479-4403-ba5f-eb56e943b8cf)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
