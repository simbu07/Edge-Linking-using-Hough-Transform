## Ex-8  Edge-Linking-using-Hough-Transform
**Date: 19/04/2023**
### Aim:
To write a Python program to detect the lines using Hough Transform.

### Software Required:
Anaconda - Python 3.7

### Algorithm:
### Step 1:
Import all the necessary packages required for the program.

### Step 2:
Load a image using imread() from cv2 module.

### Step 3:
Convert the image to grayscale image.

### Step 4:
Using Canny edge operator from cv2, detect the edges of the image.

### Step 5:
Using the HoughLinesP(), detect the line co-ordinates for every points in the images. Using For loop, draw the lines on the found co-ordinates.

### Step 6:
Display the image found by the HoughLinesP() and end the program.


### Program:
```
Name : Silambarasan K
Reg No : 212221230101
```
```Python

# Read image and convert it to grayscale image:

import numpy as np
import matplotlib.pyplot as plt
import cv2
image = cv2.imread("twin-towers.jpg",0)
img = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(img)
plt.show()

```py

# Find the edges in the image using canny detector and display:

edge = cv2.Canny(img,50,100)
plt.imshow(edge,cmap='gray')
plt.title('Edged Image after applying Canny Edge Detector')
plt.xticks([])
plt.yticks([])
plt.show()

```
```py

# Detect points that form a line using HoughLinesP:

lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)

```
```py

# Draw lines on the image:

for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(250,0,0),3)
    
```

```py

# Display the result:

plt.imshow(edge)
plt.axis('off')
plt.show()

```
### Output

### Input image 
![Screenshot 2023-04-24 192953](https://user-images.githubusercontent.com/94525786/234019343-7ec27546-7643-49a1-bb16-89160378eb36.png)

### grayscale image
![Screenshot 2023-04-24 192152](https://user-images.githubusercontent.com/94525786/234018196-a86aa871-a894-4b3d-ad04-ad0a0da8328f.png)

### Canny Edge detector output
![Screenshot 2023-04-24 192202](https://user-images.githubusercontent.com/94525786/234018226-d9b4c518-b0fe-439f-a35d-41063a5824d2.png)


### Display the result of Hough transform

![Screenshot 2023-04-24 192211](https://user-images.githubusercontent.com/94525786/234018233-06db5df8-152a-4a63-bcb6-bf8f34013051.png)

### Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
