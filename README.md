# Image_Acqusition-_using_Web_Camera
## Aim 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
## vStep 1:

Import the cv2 and numpy package.

## Step 2:

Read the Video frame using the cv2.VideoCapture(0)
## Step 3:

Write the image using imwrite().

## Step 4:

Display the frame using the imshow().
## Step 5:

Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().

## Program:


## i)Write the frame as JPG file
```
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("pic.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()

```
## ii) Display the video
```

import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('pic',frame)
    cv2.imwrite("nature.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()

```

## iii) Display the video by resizing the window


```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('PIC',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```


## iv) Rotate and display the video


```
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('NATURE_PIC', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()





```
## Output

### i) Write the frame as JPG image
![image](https://github.com/naren2704/Image_Acqusition-_using_Web_Camera/assets/118706984/f906a1cb-cf46-4030-a28e-bf5cc77a929f)

### ii) Display the video
![image](https://github.com/naren2704/Image_Acqusition-_using_Web_Camera/assets/118706984/822d6ddf-6a26-49c9-9cb9-2afd3906befd)


### iii) Display the video by resizing the window
![image](https://github.com/naren2704/Image_Acqusition-_using_Web_Camera/assets/118706984/83a82964-ae7a-4b17-a8f1-4b47c04d7479)



### iv) Rotate and display the video
![image](https://github.com/naren2704/Image_Acqusition-_using_Web_Camera/assets/118706984/8ef3211f-ca98-4516-b116-b0fdcfbbf698)




## Result:
Thus the image is accessed from webcamera and displayed using openCV.
