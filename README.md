# COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) 	Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o	Draw a line from the top-left to the bottom-right of the image.
o	Draw a circle at the center of the image.
o	Draw a rectangle around a specific region of interest in the image.
o	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
o	Convert the image from RGB to HSV and display it.
o	Convert the image from RGB to GRAY and display it.
o	Convert the image from RGB to YCrCb and display it.
o	Convert the HSV image back to RGB and display it.

### Step4:
o	Access and print the value of the pixel at coordinates (100, 100).
o	Modify the color of the pixel at (200, 200) to white.

### Step5:
o	Resize the original image to half its size and display it.
### Step6:
o	Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o	Flip the original image horizontally and display it.
o	Flip the original image vertically and display it.

### Step8:
o	Save the final modified image to your local directory.


##### Program:
### Developed By: VIGNESH R
### Register Number: 212222230172


## Output:

### i)Read and Display an Image
```
import cv2
# Read the image
image = cv2.imread('Lokesh.JPG')
# Display the image in a window
cv2.imshow('Image Window', image)
# Wait indefinitely for a key press
cv2.waitKey(0)
# Destroy all windows created by OpenCV
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/0b00653c-adbc-440b-9a0f-ac7fa91c08a9)


### ii)Draw Shapes and Add Text

```
import cv2

img = cv2.imread("Lokesh.jpg")
res = cv2.line(img,(10,10),(500-25,500-25),(200,100,205),10)

# Display the HSV image
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/6f76ae03-923f-46d4-8aa8-2f6e692543eb)
```
import cv2

# Load the image
img = cv2.imread("Lokesh.jpg")

# Parameters for line drawing
start_point = (0, 0)  # Top-left corner
end_point = (img.shape[1] - 1, img.shape[0] - 1)  # Bottom-right corner
color = (200, 100, 205)  # Line color (BGR format)
thickness = 10  # Thickness of the line

# Draw a line from top-left to bottom-right
res_img1= cv2.line(img, start_point, end_point, color, thickness)

# Convert the result image from BGR to RGB for displaying with matplotlib
res_img_rgb = cv2.cvtColor(res_img1, cv2.COLOR_BGR2RGB)
cv2.imshow('Image Window', res_img1)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/69e7d8bd-593e-40f6-890e-dfcb9e208acb)

```
import cv2

img = cv2.imread("Lokesh.jpg")
start=(0,0)
stop=(409,529)
color=(100,255,100)
thickness=10

res_img=cv2.rectangle(img,start,stop,color,thickness)

# Display the HSV image
cv2.imshow('Image Window', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/10ceab47-51fa-40a1-a3db-f49b67b401ee)


### iii)Image Color Conversion
```
# Read the image
image = cv2.imread("Lokesh.JPG")

# Convert to HSV color space
img_hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
# Convert to grayscale
img = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)


# Display the HSV image
cv2.imshow('Image Window (HSV)', img_hsv)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Convert the image from RGB to YCrCb and display it
ycrcb_image = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
cv2.imshow('YCrCb Image', ycrcb_image)
cv2.waitKey(0)

# Convert the HSV image back to RGB and display it
hsv_to_rgb_image = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
cv2.imshow('HSV to RGB Image', hsv_to_rgb_image)
cv2.waitKey(0)
```
### Convert the image from RGB to HSV and display it:
![image](https://github.com/user-attachments/assets/11fba484-92b6-455d-9d7f-5eaa041fdab7)
### Convert the image from RGB to GRAY and display it:
![image](https://github.com/user-attachments/assets/1266f03f-2b91-42b2-b51b-af22a8096460)

### Convert the image from RGB to YCrCb and display it:

![image](https://github.com/user-attachments/assets/2aa53c3c-a413-4530-a269-394c57335cc5)

### Convert the HSV image back to RGB and display it:
![image](https://github.com/user-attachments/assets/e303507c-1b77-4137-aaef-fe483b8bad72)

### iv)Access and Manipulate Image Pixels
```
# Step 4: Access and Manipulate Image Pixels
# Access and print the value of the pixel at coordinates (100, 100)
pixel_value = image[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")

# Modify the color of the pixel at (200, 200) to white
image[200, 200] = [255, 255, 255]
print(f"Modified pixel value at (200, 200): {image[200, 200]}")

```
![image](https://github.com/user-attachments/assets/0fb50cf6-24d4-4503-bbe7-64b2338eabea)

### v)Image Resizing
```
# Image Resizing
# Resize the original image to half its size and display it
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('Resized Image', resized_image)
cv2.waitKey(0)
```
![image](https://github.com/user-attachments/assets/f2e6c584-0945-426c-bd26-0e18afc19068)

### vi)Image Cropping
```
# Image Cropping
# Crop a region of interest (100x100 pixels starting at (50, 50)) and display it
roi = image[50:150, 50:150]
cv2.imshow('Cropped ROI Image', roi)
cv2.waitKey(0)
```
![image](https://github.com/user-attachments/assets/d8425f36-d66b-47a8-a203-f880ecec9fca)


### vii)Image Flipping
```
# Flip the original image horizontally and display it
flipped_horizontally = cv2.flip(image, 1)
cv2.imshow('Horizontally Flipped Image', flipped_horizontally)
cv2.waitKey(0)

# Flip the original image vertically and display it
flipped_vertically = cv2.flip(image, 0)
cv2.imshow('Vertically Flipped Image', flipped_vertically)
cv2.waitKey(0)
```
### Flip the original image horizontally and display it:
![image](https://github.com/user-attachments/assets/ce3ba5d9-13f5-445f-9f0c-600821934162)

### Flip the original image vertically and display it:
![image](https://github.com/user-attachments/assets/5b32a17a-cf94-4b7e-8327-bdc06b13daeb)


### viii)Write and Save the Modified Image
```
# Step 8: Write and Save the Modified Image
output_path = 'output.jpg'
cv2.imwrite(output_path, image_with_text)
print(f"Modified image saved as {output_path}")
```
![image](https://github.com/user-attachments/assets/c7102281-b6a6-4d60-9217-f28479b12f61)







## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.







