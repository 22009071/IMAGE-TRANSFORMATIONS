# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import numpy module as np and pandas as pd.

### Step2:
Assign the values to variables in the program.

### Step3:
Get the values from the user appropriately.
### Step4:
Continue the program by implementing the codes of required topics.
### Step5:
Thus the program is executed in google colab.

## Program:
```python
Developed By:
Register Number:
i)Image Translation
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = '/content/grayscale.png'  
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)


ii) Image Scaling
 #Install OpenCV library if not already installed
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'pexels-pixabay-56866.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis

# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("pexels-pixabay-56866.jpg:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)


iii)Image shearing
# Install OpenCV library if not already installed
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = '/content/im 04.png'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)




iv)Image Reflection

# Install OpenCV library if not already installed
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = '/content/image 8.png'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

# Display original and reflected images
print("Original Image:")
show_image(image)
print("Reflected Horizontally:")
show_image(reflected_image_horizontal)
print("Reflected Vertically:")
show_image(reflected_image_vertical)
print("Reflected Both:")
show_image(reflected_image_both)



v)Image Rotation
# Install OpenCV library if not already installed
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = '/content/im 03.png'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)



vi)Image Cropping
# Install OpenCV library if not already installed
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = '/content/im 05.png'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)




```
## Output:
### i)Image Translation
<br><img width="673" alt="Screenshot 2024-03-08 141859" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/96d4b904-f49d-4bfb-b4c1-6843b2f92511">

<br><img width="240" alt="Screenshot 2024-03-08 141934" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/19c86ea8-5246-4d87-80e9-f2e9f75d4e36">

<br>
<br>

### ii) Image Scaling
<br><img width="404" alt="Screenshot 2024-03-08 143639" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/c7741b41-4636-45b5-88a2-e667ade02d72">

<br><img width="238" alt="Screenshot 2024-03-08 143716" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/dea810be-0479-47a9-9965-569946f5a7f8">

<br>
<br>


### iii)Image shearing
<br><img width="781" alt="Screenshot 2024-03-08 170536" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/f3e592ff-316a-45ad-a766-530632197746">

<br><img width="201" alt="Screenshot 2024-03-08 170557" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/59f92efd-f70b-4c95-b50e-5cd8bc900540">

<br>
<br>


### iv)Image Reflection
<br><img width="780" alt="Screenshot 2024-03-08 171816" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/0dceb9e1-2428-4fee-b751-a05a7b6d56f7">

<br><img width="211" alt="Screenshot 2024-03-08 171854" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/8165dc85-b93d-438d-99b9-abf6b974b430">

<br><img width="200" alt="Screenshot 2024-03-08 171906" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/71542e35-b5de-4a72-94cd-bfa604636385">

<br>



### v)Image Rotation
<br><img width="778" alt="Screenshot 2024-03-08 172807" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/7d1f1729-4bd4-4ea0-bc1e-77a941d29a5d">

<br><img width="139" alt="Screenshot 2024-03-08 172819" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/c02962bd-67d3-4eea-9be0-445083c76378">

<br>
<br>



### vi)Image Cropping
<br><img width="779" alt="Screenshot 2024-03-08 173441" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/44cd4d65-6b51-4799-b659-8bc94c9280e0">

<br><img width="137" alt="Screenshot 2024-03-08 173619" src="https://github.com/22009071/IMAGE-TRANSFORMATIONS/assets/120206067/aa513f60-6e90-4efc-8bc3-5b8d6b1c9b69">

<br>
<br>




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
