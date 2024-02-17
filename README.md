# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
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

##### Program:
### Developed By:YUVARAJ B
### Register Number:212222230182




### i) Read and display the image
```
import cv2
import matplotlib.pyplot as plt

img=cv2.imread("duck.jpeg",1)
cv2.imshow("display window",img)
cv2.waitKey(0)
cv2.destroyAllWindows()
print(img.shape)
```

## output:
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/909323c5-5439-4e7a-a48a-d8f7b220394e)

### ii)Write the image
```
img1=cv2.imread("duck.jpeg",0)
cv2.imshow("display window",img1)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imwrite('greyscale.jpeg',img1)
```
## output:
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/df0765c6-234b-4901-9424-05c8b66dd695)


### iii)Shape of the Image
```
import cv2
img1=cv2.imread("duck.jpeg",1)
print(img1.shape)
```
## output:
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/65c5df6b-6164-43f2-b543-4ce62114e623)

### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('duck.jpeg',1)
#image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                    random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## output:
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/c454eccd-8cd4-45c2-b20f-082fb57c250c)


### v)Cut and paste portion of image
```
import cv2

img2 = cv2.imread("duck.jpeg")

x = 0
y = 200
x1 = 160
y1 = 450
x2 = 0
y2 = 0

cropimg = img2[x:x1+x2, y:y1+y2]

cv2.imshow("Original Image", img2)
cv2.imshow("Cropped Image", cropimg)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## output:
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/c2e35f23-58b2-4b9f-8bbe-46cc87e09587)

![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/1f5faec3-f032-4570-b44f-68581014b796)


### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('duck.jpeg',1)
img = cv2.resize(img,(300,200))
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
## output:
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/96279901-b446-4957-b4ee-a1387040a916)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/55400087-2b69-4826-89a5-624819110457)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/8441996a-3158-4ac5-8387-d74d0bc26c30)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/15df8073-c891-4d29-8bfa-8b1f4e47ecc6)


### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('duck.jpeg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

## output:
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/a9ac8927-51f3-47c8-8d09-44950e2e224c)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/a99f5b80-1d15-4ab2-80a6-08d3a6345d83)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/f962895c-18f9-4b14-ae8c-06a360dcbefd)




### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('duck.jpeg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

## output:
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/2aca872e-afbf-4382-9b0d-09ae55d5619f)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/83580444-a0f8-4c29-8536-d3c27aab3ab9)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/19d211d0-a54a-4690-af54-1163a88fc829)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('duck.jpeg',1)
img = cv2.resize(img,(300,200))

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

## output:
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/d741d43c-de15-4ce2-82f8-83151d120985)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/a0d74b65-2029-4027-8bfc-452f9874a67a)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/a213b6bc-33d2-4a54-b943-21ba72e9fcb9)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/a25ee8ab-8e48-4d74-97f5-b0525dc4801a)



### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("duck.jpeg",1)
img = cv2.resize(img,(300,200))
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

## output:
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/3da85971-a88b-4c7d-b389-24e2b5244d76)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/97631364-9311-4d80-b116-35421f9dca1d)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/26f51a2d-f37c-4889-9222-2849e2fe6daa)
![image](https://github.com/Ragu-123/COLOR_CONVERSIONS_OF-IMAGE/assets/113915622/2f3a5c19-0306-4ada-a63b-c810bb53e5f3)







## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
