![image](https://github.com/user-attachments/assets/651de0d6-729c-4efa-b823-9770e1460b50)# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.


### Step3:

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.
2.Scaling resizes the image by scaling factors.
3.Shearing distorts the image along one axis.
4.Reflection flips the image horizontally or vertically.
5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
### Developed by: Pavithra R
### Reg no: 212222230106

```python

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('img2.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)


plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/25af2a36-19cc-4507-9948-0387bcdb1792)

```python
# 1. Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]]) 
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))


plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/aeb1a035-d45d-4415-9e38-6c8d5aa6328d)


```python
# 2. Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)


 plt.imshow(scaled_image)
 plt.title("Scaled Image")
 plt.axis('off')
```

![image](https://github.com/user-attachments/assets/9926237c-5f84-4fbb-bdb8-246ff3a32790)


```python
# 3. Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))



plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```

![image](https://github.com/user-attachments/assets/beae12e3-686b-4f41-8884-fbddd91e54e8)

```python
# 4. Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)


plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off') 
```

![image](https://github.com/user-attachments/assets/e96be6e8-1891-40b9-a15b-bc0e5a13e13c)


```python
# 5. Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))


plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```

![image](https://github.com/user-attachments/assets/89f5a3aa-2d4a-44f6-a2c6-5df0d56e5393)

```python
# 6. Cropping
cropped_image = image_rgb[50:300, 100:400]


plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()  

# Plot the original and transformed images
plt.figure(figsize=(12, 8))

```

![image](https://github.com/user-attachments/assets/05d97994-405a-4fae-8ed4-9b7e9c671635)




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
