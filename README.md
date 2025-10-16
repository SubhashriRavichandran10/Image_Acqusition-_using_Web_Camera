
# Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import the cv2 and numpy package.

### Step 2:
Read the Video frame using the cv2.VideoCapture(0)

### Step 3:

Write the image using imwrite()
### Step 4:

Display the frame using the imshow().
### Step 5:

Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().
## Program:

### Developed By:R.SUBHASHRI
### Register No:212223230219

## i) Write the frame as JPG file

```

import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()


```


## ii) Display the video

```

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


```


## iii) Display the video by resizing the window


```


cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (320, 240))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()





```



## iv) Rotate and display the video


```


cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()




```







## Output

### i) Write the frame as JPG image



<img width="673" height="545" alt="image" src="https://github.com/user-attachments/assets/e0b71d31-6ece-404b-bf73-a5e8709a2e32" />





### ii) Display the video


<img width="701" height="528" alt="image" src="https://github.com/user-attachments/assets/90921a82-142e-41ce-9aaf-dd0cd3f05c3f" />



### iii) Display the video by resizing the window


<img width="685" height="523" alt="image" src="https://github.com/user-attachments/assets/c5fcc1a6-83b3-4b8b-8266-12cafff7a2d7" />


### iv) Rotate and display the video


<img width="530" height="535" alt="image" src="https://github.com/user-attachments/assets/ac6c01c5-4d53-4e02-b9c9-9881d4bd0f31" />




## Result:
Thus the image is accessed from webcamera and displayed using openCV.
