# Project description
## About
It is a package having pre-built codes of Hand Tracking. You can implement with just single line of code.

## Function
`handTracker(image,draw=True)`

**Function Parameter** : This function takes image (a single frame) as input and a variable draw with default value False. You can change the value of parameter draw to True if you want to the mapping of hands over the image frame.
**Output** : This function returns a nested list of length 2. The element at index 1 is the frame and a list of handLandmarks. Know more about these handLandmarks on this link. The list of handLandmarks consist of 21 lists containing data of all 21 points. Each list is in the format of [indexOfPoint, xCoordinate, yCoordinate, zCoordinate] for all 21 points. NOTE that the function will return [0] at index 1 in the list if no hands are detected.
## Usage
`handTracker(image,draw=False)`

> Mapping over the hands directly from function.
```
from lkhandmapping import handTracker
import cv2

cap = cv2.VideoCapture(0)
while True:
    success, image = cap.read()
    functionValues = handTracker(image,draw=True)
    image = functionValues[0]
    handLms = functionValues[1]
    print(handLms)
    cv2.imshow('Hands', image)
    cv2.waitKey(1)
cap.release()
```


>Track hands without mapping.
```
from lkhandmapping import handTracker
import cv2
    
cap = cv2.VideoCapture(0)
while True:
    success, image = cap.read()
    functionValues = handTracker(image,draw=False)
    image = functionValues[0]
    handLms = functionValues[1]
    print(handLms)
    cv2.imshow('Hands', image)
    cv2.waitKey(1)
cap.release()
```
## Developer
This package is developed by [Lakshay Kumar](lakshaykumar.tech) an enthusiastic AI Researcher. This is developed keeping in mind the pain to write lengthy lines of code just to detect faces. This will enable other developers to focus more on implementation part rather than spending time on coding the face detection module.
Feel free to share your feedback via [mail](mailto:contact@lakshaykumar.tech)
