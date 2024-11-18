# EX01 COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) Draw Shapes and Add Text.

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
1.  Draw a line from the top-left to the bottom-right of the image.

2.	Draw a circle at the center of the image.

3.	Draw a rectangle around a specific region of interest in the image.

4.	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
1.	Convert the image from RGB to HSV and display it.
2.	Convert the image from RGB to GRAY and display it.
3.	Convert the image from RGB to YCrCb and display it.
4.	Convert the HSV image back to RGB and display it.

### Step4:
1.	Access and print the value of the pixel at coordinates (100, 100).
2.	Modify the color of the pixel at (200, 200) to white.

### Step5:
Resize the original image to half its size and display it.
### Step6:
Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
1.	Flip the original image horizontally and display it.
2.	Flip the original image vertically and display it.

### Step8:
Save the final modified image to your local directory.


## Program:
### Developed By: Vignesh R
### Register Number: 212222230172


## Output:

### 1. Read and display the image
i.Load an image from your local directory and display it.
```
import cv2
image=cv2.imread('str.jpg',1)
cv2.imshow('STR',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 164724](https://github.com/user-attachments/assets/e750d9d4-9098-43c6-8ec9-7cb47d203034)



### Draw Shapes and Add Text
(1) Draw a line from the top-left to the bottom-right of the image.
```
import cv2
image = cv2.imread("str.jpg")
res = cv2.line(image, (0, 0), (image.shape[1], image.shape[0]), (255,0,0), 10)
cv2.imshow('WINDOW', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 164736](https://github.com/user-attachments/assets/023d01f1-04f6-44cb-ae1c-adf4588f2379)



2. Draw a circle at the center of the image.
```
import cv2
image = cv2.imread("str.jpg")
height, width, _ = image.shape
center_coordinates = (width // 2, height // 2)
res = cv2.circle(image, center_coordinates, 120, (0, 255, 0), 10)
cv2.imshow('WINDOW', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 164806](https://github.com/user-attachments/assets/0adc9c13-4cee-411d-b10c-1f215390e697)



3.Draw a rectangle around a specific region of interest in the image.
```
import cv2
image = cv2.imread("str.jpg")
start = (150, 100)
stop = (300, 200)
color = (255, 255, 100)
thickness = 10           
res_img = cv2.rectangle(image, start, stop, color, thickness)
cv2.imshow('WINDOW', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 164848](https://github.com/user-attachments/assets/ab780c84-0410-4ef7-bcff-baa4dc28585d)




4.Add the text "OpenCV Drawing" at the top-left corner of the image.
```
import cv2
image = cv2.imread("str.jpg")
text = "OpenCV Drawing"
position = (10, 50)
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
color = (255, 255, 255) 
thickness = 2
res = cv2.putText(image, text, position, font, font_scale, color, thickness, cv2.LINE_AA)
cv2.imshow('WINDOW', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 164927](https://github.com/user-attachments/assets/cca933ff-64b7-4758-945e-d78cb3ff1950)



### iii)Image Color Conversion
(i)Convert the image from RGB to HSV and display it
```
import cv2
image = cv2.imread('str.jpg',1)
cv2.imshow('ORIGINAL IMAGE',image)
hsv = cv2.cvtColor(image,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 175459](https://github.com/user-attachments/assets/7af3ec53-9933-49fe-becf-bb1c531adede)



(2) Convert the image from RGB to GRAY and display it.

```
import cv2
image = cv2.imread('str.jpg',1)
cv2.imshow('ORIGINAL IMAGE',image)
gray = cv2.cvtColor(image,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 175537](https://github.com/user-attachments/assets/31b5d182-06fa-48a0-8bac-cf2cd9a77ab7)



(3) Convert the image from RGB to YCrCb and display it.
```
import cv2
image = cv2.imread('str.jpg',1)
cv2.imshow('ORIGINAL IMAGE',image)
YCrCb = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 175608](https://github.com/user-attachments/assets/08f5f16b-7460-4d8f-907a-303e5d5a9960)



(4) Convert the HSV image back to RGB and display it.
```
import cv2
image = cv2.imread('str.jpg',1)
cv2.imshow('ORIGINAL IMAGE',image)
RGB = cv2.cvtColor(image,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',RGB)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 175648](https://github.com/user-attachments/assets/d882eb54-a51f-4887-a3e3-6a24fea31b39)



### iv)Access and Manipulate Image Pixels
(1) Access and print the value of the pixel at coordinates (100, 100)
```
pixel_value = image[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")
```
![365507960-53fb2f1a-8e20-4b3b-bdeb-cf314f0326fd](https://github.com/user-attachments/assets/ff8b8df7-0119-4196-93fa-cabaa5bb065a)


(2) Modify the color of the pixel at (200, 200) to white
```
import cv2
image = cv2.imread('str.jpg',1)
cv2.imshow('ORIGINAL IMAGE',image)
image[200, 200] = [255, 255, 255] 
cv2.imshow('MODIFIED IMAGE', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 175742](https://github.com/user-attachments/assets/4013cdf3-fed3-4875-993f-21bc05362679)



### v)Image Resizing:
Resize the original image to half its size and display it.
```
cv2.imshow('ORIGINAL IMAGE',image)
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('RESIZED IMAGE', resized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 175850](https://github.com/user-attachments/assets/10c28476-d301-4f1d-94be-0b9cdd13535b)


### vi)Image Cropping
Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
```
import cv2
image = cv2.imread('str.jpg',1)
image = cv2.resize(image,(400,300))
x, y = 50, 50
width, height = 100, 100
roi = image[y:y + height, x:x + width]
cv2.imshow('CROPPED IMAGE', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 175922](https://github.com/user-attachments/assets/09a124da-6f7f-47a4-930c-2cd39afe7e29)


### vii)Image Flipping:
(1) Flip the original image horizontally and display it.
```
import cv2
image = cv2.imread("str.jpg")
image = cv2.resize(image,(300,200))
res=cv2.rotate(image,cv2.ROTATE_180)
cv2.imshow('ORIGINAL IMAGE',image)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 175957](https://github.com/user-attachments/assets/a05bc110-cbd2-42bf-9625-dbd53ab07bf3)



(2) Flip the original image vertically and display it.
```
import cv2
image = cv2.imread("str.jpg")
image = cv2.resize(image,(300,200))
res=cv2.rotate(image,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('ORIGINAL IMAGE',image)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-11-18 180038](https://github.com/user-attachments/assets/7c47dd40-76df-453a-8cbc-e5d1e284cb24)


### viii)Write and Save the Modified Image
Save the final modified image to your local directory.
```
import cv2
img = cv2.imread("str.jpg")
img = cv2.resize(img,(300,200))
cv2.imwrite('str.jpg',img)
```
![365507222-874121bf-a1c9-4fb9-be27-e4613309ad2d](https://github.com/user-attachments/assets/46e9617a-1b08-499c-bd72-04097d65d94d)

## Result:

Thus the images are read, displayed, and written ,and color conversion was performed successfully using the python program.

