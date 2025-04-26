
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

### Load the necessary packages
```py
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```py
image = cv2.imread("disney.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("disney.jpg",0)
```
### Use Global thresholding to segment the image
```py
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```py
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```py
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
#### ORIGIONAL IMAGE
```py


plt.axis("off")
plt.title("Original Image")
plt.imshow(image)

```
![image](https://github.com/user-attachments/assets/9a8a2575-be6b-4648-bac6-9fe66ba76f9f)

#### GREY IMAGE
```py


plt.axis("off")
plt.title("Gray Image")
plt.imshow(cv2.cvtColor(image_gray, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/43ead477-1f7a-41fa-901c-fd40295eeae6)

#### Threshold Image (Binary)
```py


plt.axis("off")
plt.title("Threshold Image (Binary)")
plt.imshow(cv2.cvtColor(thresh_img1, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/f4066704-ffb6-44c5-837c-b8119ee1440b)


#### Threshold Image (Binary Inverse)
```py


plt.axis("off")
plt.title("Threshold Image (Binary Inverse)")
plt.imshow(cv2.cvtColor(thresh_img2, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/b082d0ba-8fed-4d8d-becb-b78f026a397c)


#### Threshold Image (To Zero)
```py


plt.axis("off")
plt.title("Threshold Image (To Zero)")
plt.imshow(cv2.cvtColor(thresh_img3, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/6f502494-fdbf-401e-9b9c-cb0a53f79654)

#### Threshold Image (To Zero-Inverse)
```py


plt.axis("off")
plt.title("Threshold Image (To Zero-Inverse)")
plt.imshow(cv2.cvtColor(thresh_img4, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/78cc7b0c-2a38-4640-8db2-4e42e01d11fd)


#### Threshold Image (Truncate)
```py

plt.axis("off")
plt.title("Threshold Image (Truncate)")
plt.imshow(cv2.cvtColor(thresh_img5, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/d1dd5019-c868-4225-a5da-1fa0f01df018)

#### Otsu
```py
plt.axis("off")
plt.title("Otsu")
plt.imshow(cv2.cvtColor(thresh_img6, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/a43fffee-b508-4538-ad4f-104aaa1a0f38)

#### Adaptive Threshold (Mean)
```py

plt.axis("off")
plt.title("Adaptive Threshold (Mean)")
plt.imshow(cv2.cvtColor(thresh_img7, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/dcc6ad22-d47c-4721-88b0-98b8c636a651)

#### Adaptive Threshold (Gaussian)
```py
plt.axis("off")
plt.title("Adaptive Threshold (Gaussian)")
plt.imshow(cv2.cvtColor(thresh_img8, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/aee614da-b075-48a3-9fed-29e80e71325c)






## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
