# COLOR_CONVERSIONS_OF-IMAGE

## Aim:
To write a python program using OpenCV to do the following image manipulations.
i) Read, display, and write an image.
ii) Access the rows and columns in an image.
iii) Cut and paste a small portion of the image.
iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg 
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

## Program:
### Developed By: DELLI PRIYA L
### Register Number: 212222230029

## Output:
### i) Read and display the image
```
    import cv2
    image=cv2.imread('dog.jpg',1)
    image=cv2.resize(image,(300,300))
    cv2.imshow('leann',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/f843ee28-e879-475b-aa94-b8f26161cafc)

### ii)Write the image
```
    import cv2
    image=cv2.imread('dog.jpg',0)
    cv2.imwrite('demos.jpg',image)
```
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/e36ef7cd-ceb1-4c84-a1e8-c2d71e54c5e7)

### iii)Shape of the Image
```
    import cv2
    image=cv2.imread('dop.jpg',1)
    print(image.shape)
```
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/98e09552-d9d4-4e77-93d4-25211e0384fb)

### iv)Access rows and columns
```
import random
    import cv2
    image=cv2.imread('dog.jpg',1)
    image=cv2.resize(image,(500,500))
    for i in range (250,500):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/27a8e4b2-438b-4eeb-a390-48443bbd81ef)
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/8c531e41-2491-4da0-9932-35df73bbbfc2)

### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('dog.jpg',1)
image=cv2.resize(image,(300,300))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/bda25285-893b-4424-a960-1efb3f49e02c)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('dog.jpg',1)
img = cv2.resize(img,(200,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/8ebb8a26-033e-4b14-8420-757427e58054)
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/08ea41c8-0a21-43e5-ba04-6e1cf27ab156)

### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('dog.jpg')
img = cv2.resize(img,(200,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/d20f21e3-d42c-40fe-afcc-6996257c08c4)

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('dog.jpg')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/b60e990f-6384-478b-b36c-027bbcc5bcc4)

### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('dog.jpg',1)
img = cv2.resize(img,(200,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/9bcb1a96-da62-4f6d-b15a-efa10510133d)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("dog.jpg",1)
img = cv2.resize(img,(200,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Priya-Loganathan/COLOR_CONVERSIONS_OF-IMAGE/assets/121166075/e39a4765-b2ad-40ab-8645-ec15c7ac7dc2)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







