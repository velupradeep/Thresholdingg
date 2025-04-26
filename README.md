# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
<br>

### Step2:
Read the Image and convert to grayscale.
<br>

### Step3:
Use Global thresholding to segment the image.
<br>

### Step4:
Use Adaptive thresholding to segment the image.
<br>

### Step5:
Use Otsu's method to segment the image and display the results.
<br>

## Program

```python
# Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2

```





# Read the Image and convert to grayscale

```
image = cv2.imread("disney.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("disney.jpg",0)

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






## Output

### Original Image
```


plt.axis("off")
plt.title("Original Image")
plt.imshow(image)

```
![image](https://github.com/user-attachments/assets/bffb81b8-73d4-452a-bb9b-563e1ae561c7)

## GREY IMAGE
```


plt.axis("off")
plt.title("Gray Image")
plt.imshow(cv2.cvtColor(image_gray, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/50f660ed-db8a-4539-9e54-6cccca54dcb3)


## Threshold Image (Binary)
```


plt.axis("off")
plt.title("Threshold Image (Binary)")
plt.imshow(cv2.cvtColor(thresh_img1, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

````
![image](https://github.com/user-attachments/assets/f1b18d8e-fd5d-4915-99e0-f409d14b24ca)


## Threshold Image (Binary Inverse)

```


plt.axis("off")
plt.title("Threshold Image (Binary Inverse)")
plt.imshow(cv2.cvtColor(thresh_img2, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/31b19e66-463f-4467-824b-a98f2c9faebd)


## Threshold Image (To Zero)
```


plt.axis("off")
plt.title("Threshold Image (To Zero)")
plt.imshow(cv2.cvtColor(thresh_img3, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/32affebd-48d1-49ab-b357-97a00de4e268)


## Threshold Image (To Zero-Inverse)

```


plt.axis("off")
plt.title("Threshold Image (To Zero-Inverse)")
plt.imshow(cv2.cvtColor(thresh_img4, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/9fd69672-cf9e-45cb-a546-f7e93fec7883)




## Threshold Image (Truncate)

```


plt.axis("off")
plt.title("Threshold Image (Truncate)")
plt.imshow(cv2.cvtColor(thresh_img5, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/e392f1d2-3a0b-4d73-83c9-925455c264fc)


## Otsu

```
plt.axis("off")
plt.title("Otsu")
plt.imshow(cv2.cvtColor(thresh_img6, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/50dad46c-faf6-4b11-8c34-9ef8e76bb18a)



## Adaptive Threshold (Mean)
```

plt.axis("off")
plt.title("Adaptive Threshold (Mean)")
plt.imshow(cv2.cvtColor(thresh_img7, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/8be252be-0529-42d4-b637-3be4edf3876b)



## Adaptive Threshold (Gaussian)
```
plt.axis("off")
plt.title("Adaptive Threshold (Gaussian)")
plt.imshow(cv2.cvtColor(thresh_img8, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/3b67e7f2-ab52-4465-964c-ff452a8f3e57)












## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
