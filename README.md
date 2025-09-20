# EX 04: IMAGE-TRANSFORMATIONS
## NAME:vignesh R
## REG NO:212223240177
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

## Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

## Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis. 2.Scaling resizes the image by scaling factors. 3.Shearing distorts the image along one axis. 4.Reflection flips the image horizontally or vertically. 5.Rotation rotates the image by a given angle.

## Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

## Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
````
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Chennai_Central.jpg')
image.shape

# Display the images.
plt.imshow(image[:,:,::-1])
plt.title('Original Image')
plt.show()

# i) Image Translation
tx, ty = 100, 200  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
translated_image = cv2.warpAffine(image, M_translation, (636, 438))
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis('on')
plt.show()

# Image Scaling
fx, fy = 2.0, 1.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(scaled_image[:,:,::-1]) 
plt.title("Scaled Image") 
plt.axis('on')
plt.show()

# Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (636, 438))
plt.imshow(sheared_image[:,:,::-1])
plt.title("Sheared Image") 
plt.axis('on')
plt.show()

# Image Reflection
reflected_image = cv2.flip(image, 2)
# Show original image 
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('off')

# Show reflected image 
plt.subplot(1, 2, 2)
plt.imshow(reflected_image[:,:,::-1])
plt.title("Reflected Image")
plt.axis('off')

plt.tight_layout()
plt.show()

# Image Rotation
(height, width) = image.shape[:2] 
angle = 45  
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  
plt.title("Rotated Image")  
plt.axis('off')

image .shape
angle = 145  
center = (636 // 2, 438 // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))

 # Display the rotated image
plt.imshow(rotated_image[:,:,::-1])
plt.title("Rotated Image")  # Set title
plt.axis('off')
plt.show()

# Image Cropping
x, y, w, h = 0, 0, 200, 150  
cropped_image = image[y:y+h, x:x+w]
# Show original image 
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('on')

# Show reflected image 
plt.subplot(1, 2, 2)
plt.imshow(cropped_image[:,:,::-1])
plt.title("Cropped Image")
plt.axis('on')

plt.tight_layout()
plt.show() 



``````
## Output:
## ORIGINAL IMAGE
<img width="655" height="368" alt="image" src="https://github.com/user-attachments/assets/4a18e62c-b9c6-4af5-8b60-87d6d37b5823" />

### i)Image Translation
<br>
<img width="610" height="370" alt="image" src="https://github.com/user-attachments/assets/bea6ab79-1e38-4a3e-9b8d-910dc61fcf75" />

<br>
<br>
<br>

### ii) Image Scaling
<br>
<img width="639" height="196" alt="image" src="https://github.com/user-attachments/assets/2614090c-d16f-4d31-9f2e-a29f0f56131e" />


<br>
<br>
<br>


### iii)Image shearing
<br>
<img width="616" height="385" alt="image" src="https://github.com/user-attachments/assets/cd883275-4fc7-4664-bec3-8a758721cf15" />



<br>
<br>
<br>


### iv)Image Reflection
<br>
<img width="577" height="377" alt="image" src="https://github.com/user-attachments/assets/b768713d-fc63-4a37-8c40-89b9a6bc63aa" />

<br>
<br>
<br>



### v)Image Rotation
<img width="611" height="392" alt="image" src="https://github.com/user-attachments/assets/59bb2cfc-1ec8-4e9f-86bb-ef251c4bf57a" />

<br>
<br>
<br>



### vi)Image Cropping
<br>
<img width="608" height="480" alt="image" src="https://github.com/user-attachments/assets/9fa679b0-bb7a-46ef-a7fa-092a82ae2083" />


<br>
<br>
<br>


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
