# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

# PROGRAM:

# Input image
```python
import cv2
import matplotlib.pyplot as plt
image = cv2.imread('Eagle.png')  # Replace with your image path
# Display Input Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.show()
```

# Grayscale image
```python
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display Grayscale Image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```

# Canny Edge detector output
```python
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
# Display Canny Edge Detection Output   
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
plt.show()
```

# Display the result of Hough transform
```python
import numpy as np
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Display Hough Transform Result
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
plt.show()
```

## Output:

### Input image 
![image](https://github.com/user-attachments/assets/4eadeb7e-197b-4b11-a191-78a78b435e6d)

# grayscale image
![image](https://github.com/user-attachments/assets/9f2acf62-a933-4d35-81db-e867edfd0d0d)


### Canny Edge detector output
![image](https://github.com/user-attachments/assets/36e2deb5-802c-4ba2-a6fd-1edce4024723)


### Display the result of Hough transform
![image](https://github.com/user-attachments/assets/7c22f7a4-7ff8-4eca-839a-80a8da210730)

## RESULT:
Thus the python program to detect the lines using Hough Transform was successfully completed.

