# EXP 02: Image Acquisition using Web Camera

## Aim
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.<br>
i) Write the frame as JPG <br>
ii) Display the video <br>
iii) Display the video by resizing the window<br>
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1: 
Start the webcam using cv2.VideoCapture(0) and begin reading frames.
<br>

### Step 2: 
Capture and save a frame as a JPG file using cv2.imwrite().
<br>

### Step 3: 
Display the live video continuously in a window.
<br>

### Step 4:
Resize the frame to half its original size and display the smaller video.
<br>

### Step 5:
Rotate the resized frame (180°) and display it along with the normal frames.
<br>

### Step 6: 
Stop the webcam and close all windows when the user presses ‘q’.
<br>

## Program

### Developed By: gokul prakash M
### Register No: 212223240041

## i) Write the frame as JPG file
```python
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('photo.jpg',frame)
    cv2.imwrite("pic.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
```



## ii) Display the video
```python
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('video',frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```python
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
    cv2.imshow('resizedvideo',smaller_frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video
```python
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
    cv2.imshow('rotatedvideo', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

### Developed By: GOKUL PRAKASH M
### Register No: 212223240041


## Output

### i) Write the frame as JPG image
</br>
<img width="508" height="399" alt="image" src="https://github.com/user-attachments/assets/7daee1f8-9447-4859-a44f-b6a9316dabd0" />

</br>


### ii) Display the video
</br>
<img width="496" height="373" alt="image" src="https://github.com/user-attachments/assets/6e155420-d51b-4dca-b167-7cd79bf29f22" />

</br>


### iii) Display the video by resizing the window
</br>
<img width="254" height="374" alt="image" src="https://github.com/user-attachments/assets/fde7ec5c-1ce2-461c-95fb-a8de5f8d34d8" />

</br>



### iv) Rotate and display the video
</br>
<img width="297" height="374" alt="image" src="https://github.com/user-attachments/assets/91f15610-bd8f-46d8-b471-68e1bb9a98e1" />

</br>





## Result
The image was successfully captured from the webcam, saved as a JPG file, and displayed as live video. The video was also shown in resized form and rotated, thus achieving all four image acquisition processes using OpenCV.
