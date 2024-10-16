# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
<br> Initialize a black image of size 300x600 with 3 color channels (for RGB) using np.zeros.

### Step2:
<br> Use cv2.putText to add the text "OpenCV Demo" to the image, specifying the font, size, color, and thickness.

### Step3:
<br> Create a 5x5 rectangular structuring element using cv2.getStructuringElement to be used for erosion and dilation operations.

### Step4:
<br> Use cv2.erode to shrink the white areas (text) of the image, and cv2.dilate to expand them.

### Step5:
<br> Convert the images from BGR to RGB for proper display in Matplotlib, and use plt.subplot to visualize the original, eroded, and dilated images side by side.

 
## Program:
```
# Import the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Create a blank image
image = np.zeros((300, 600, 3), dtype="uint8")


# Step 2: Create the text using cv2.putText
text = "OpenCV Demo"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)

# Step 3: Create a structuring element (5x5 rectangular)
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))

# Step 4: Erode the image
eroded_image = cv2.erode(image, kernel, iterations=1)

# Step 5: Dilate the image
dilated_image = cv2.dilate(image, kernel, iterations=1)

# Convert images from BGR to RGB for Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
eroded_image_rgb = cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB)
dilated_image_rgb = cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB)

# Plot the original, eroded, and dilated images using Matplotlib
plt.figure(figsize=(10, 5))

#Original Image:
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")

#Eroded Image:
plt.imshow(eroded_image_rgb)
plt.title("Eroded Image")
plt.axis("off")

#Dilated Image:
plt.imshow(dilated_image_rgb)
plt.title("Dilated Image")
plt.axis("off")

plt.tight_layout()
plt.show()

```
## Output:

### Display the input Image
![image](https://github.com/user-attachments/assets/e070d3d5-673d-45d7-9cb9-d6300568aa7c)


### Display the Eroded Image
![image](https://github.com/user-attachments/assets/a7e31df5-c12c-4bbb-8d43-4f9cca998225)


### Display the Dilated Image
![image](https://github.com/user-attachments/assets/1fcac408-487b-4579-9784-d3374d1f7293)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
