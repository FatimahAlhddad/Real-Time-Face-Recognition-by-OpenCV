# Real-Time-Face-Recognition-by-OpenCV
This repository shows the steps taken to make real-time face detection by OpenCV.

## Requirements:
This task is done under Windows 8 - 64Bit (Please install the suitable version of these apps):
1. Python 3.6.4
2. PyCharm Community Edition 2021.1.1

## (1) Install OpenCV:
Open cmd and write:
```
pip install opencv-python
```
## (2) Download haarcascades Files:
Extract the folder in your program Scripts folder:

https://drive.google.com/file/d/1pomC9Zw178nxgNOrpemaQfSH8rSVyMBD/view


## (3) Run the code below in PyCharm:
```
import cv2

cap = cv2.VideoCapture(0)
cascade_classifier = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')

while True:

    ret, frame = cap.read()
    gray = cv2.cvtColor(frame, 0)
    detections = cascade_classifier.detectMultiScale(gray, scaleFactor=1.3, minNeighbors=5)

    if(len(detections) > 0 ):
        (x, y, w, h) = detections[0]
        frame = cv2.rectangle(frame, (x,y), (x+w, y+h), (255,0,0), 2)

    cv2.imshow('frame', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

## (3-1) In case you had a red line under **import cv2** do the following:
1. Open PyCharm and click on the file to select setting.
2. Click Project:-Project Name- to enter Project Interpreter.
3. Click the + sign.
4. Then type opencv-python in the search box and select the opencv-python.
5. Click on Install package below


## The Resulte 
![image](https://user-images.githubusercontent.com/85858256/128096998-2965c205-8486-4c14-8d48-19fca951429e.png)



Resource:
https://www.youtube.com/watch?v=PLKLsPDZ1t0
