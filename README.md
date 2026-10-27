## Record-Image-Acquisition-using-Web-Camera-Completion-requirements

## Aim:

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

* Write the frame as a JPG file
* Display the video
* Display the video by resizing the window
* Rotate and display the video

## Software Used:

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)

## Algorithm:

Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2:
Capture frames continuously from the webcam.

Step 3:
Save a frame as a JPG image using cv2.imwrite().

Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

## Program:

Developed By: Logeshwaran.R

Register No: 212225040205

## 1. Capture the image:
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```
```
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
```
```
captured_image = cv2.imread('captured_frame.jpg')
```
```
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
## 2. Display the video:
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

## 3. Display the video by resizing the window:
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

```

## 4. Rotate and display the video:

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

## Output:

## 1. Capture the image:

<img width="661" height="540" alt="image" src="https://github.com/user-attachments/assets/e0d4d875-9928-41c3-81ee-c6da1b14b527" />

## 2. Display the video:

<img width="690" height="517" alt="image" src="https://github.com/user-attachments/assets/c3616ca8-b939-406f-9e1c-51f3c90adc18" />

## 3. Display the video by resizing the window:

<img width="372" height="507" alt="image" src="https://github.com/user-attachments/assets/42c7f588-9fc3-4ee6-9f97-52ce581d6699" />

## 4. Rotate and display the video:

<img width="367" height="482" alt="image" src="https://github.com/user-attachments/assets/38e62d67-eea7-4027-8406-45c5e96524f5" />

## Result:
           
  Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
