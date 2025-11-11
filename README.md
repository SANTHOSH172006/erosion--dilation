# Ex 9: implement Erosion and Dilation
# Name: SANTHOSH D
# Reg No: 212223220099
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
## Step-1:
Create a black image of size 100x600 pixels.

## Step-2:
Use a specified font to write the word "Lifestyle" on the image at a defined position.

## Step-3:
Show the image containing the text without axis labels.

## Step-4:
Define a structuring element for morphological operations (e.g., a cross-shaped kernel).

## Step-5:
Apply erosion to the image using the defined structuring element to reduce the size of white regions.

## Step-6:
Apply dilation to the original image using the same structuring element to increase the size of white regions.

 
## Program:

# Import the necessary packages
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
```

# Create the Text using cv2.putText
```
img = np.zeros((100, 600, 3), dtype='uint8')  # Black background (RGB: 0, 0, 0)
font = cv2.FONT_HERSHEY_COMPLEX
text_color = (255, 255, 255)  # White text (RGB: 255, 255, 255)
cv2.putText(img, 'SANTHOSH', (60, 70), font, 2, text_color, 5, cv2.LINE_AA)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.axis('off')
plt.show()
```


# Create the structuring element

```
kernel = np.ones((5,5),np.uint8)
kernel1 = cv2.getStructuringElement(cv2.MORPH_CROSS,(5,5))
cv2.erode(img,kernel)
```

# Erode the image
```
img_erode = cv2.erode(img,kernel1)
plt.imshow(img_erode)
plt.axis('off')
```



# Dilate the image

```
img_dilate = cv2.dilate(img,kernel1)
plt.imshow(img_dilate)
plt.axis('off')



```
## Output:

### Display the input Image
<br>
<br>
<img width="474" height="514" alt="image" src="https://github.com/user-attachments/assets/74bfb23e-a5b7-4f31-b1a6-059beaae0706" />


<br>
<br>
<br>

### Display the Eroded Image
<br>
<br>
<img width="458" height="504" alt="image" src="https://github.com/user-attachments/assets/27786733-4a52-46de-bff4-f5d02043524d" />


<br>
<br>
<br>

### Display the Dilated Image
<br>
<br>
<img width="488" height="511" alt="image" src="https://github.com/user-attachments/assets/b2adca05-e699-4ff4-92e4-035e5f4a1d7f" />


<br>
<br>
<br>

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
