# Image-Acquisition-from-Web-Camera
## AIM:

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## SOFTWARE USED:
Anaconda - Python 3.7
## ALGORITHM:
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## PROGRAM:
``` Python
### Developed By: SRI KARTIHCKEYAN GANAPATHY
### Register No:212222240102

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("srikarthi.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video
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
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()








```
## OUTPUT:

### i) Write the frame as JPG image
![Screenshot 2024-02-27 111450](https://github.com/srikarthickeyanganapathy/Image_Acqusition-_using_Web_Camera/assets/119393842/bb1b5cf4-6607-4293-9c4a-0a2e2a5f8866)

</br>
</br>

### ii) Display the video
![Screenshot 2024-02-27 113444](https://github.com/srikarthickeyanganapathy/Image_Acqusition-_using_Web_Camera/assets/119393842/475454a9-b5b0-4935-907a-4e5fe43a6200)

</br>
</br>

### iii) Display the video by resizing the window
![Screenshot 2024-02-27 113507](https://github.com/srikarthickeyanganapathy/Image_Acqusition-_using_Web_Camera/assets/119393842/0c5bd9c1-5680-48d8-9a1e-c5823a54f5e6)

</br>
</br>

### iv) Rotate and display the video
![Screenshot 2024-02-27 113530](https://github.com/srikarthickeyanganapathy/Image_Acqusition-_using_Web_Camera/assets/119393842/e5e82f2b-993f-4d4f-8aa2-c8af6b10ecc0)

</br>
</br>

## RESULT: 
Thus the image is accessed from webcamera and displayed using openCV.
