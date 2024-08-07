# mediapipe_hand 

For Mac users, there is no opencv-python version to use video write and picture-write.

https://github.com/air-gh/opencv-video-mac

mediapipe developed by Google is a useful library for detecting the target objects 
including hands, faces, iris, pose...

This repository shows how mediapipe can be used to recognize the two-dimensional coordinates (X and Y axes) of a 21-point hand skeleton.

# How to install mediapipe

tensorflow and opencv library must be installed before installing mediapipe.

$ pip install tensorflow

$ pip install opencv-python

$ pip install mediapipe

# How to run fingerv0.py


A right hand can be detected and 2D (x,y) coordinates of 21 points of 
five fingers can be recognized:

<img src="hand.png" height=260 width=770 >

handLandmarks[ ][ ] can determine a position of 21 points by the first index and an axis of x or y by the second index.
For example, 
handLandmarks[4][1] indicates Thumb-finger-tip by "4" in x-axis by "1".

handLandmarks[8][2] indicates Index-finger-tip by "8" in y-axis by "2".

What is handLandmarks[20][2]?

What is handLandmarks[4][3]?

$ python fingerv0.py

<img src="https://github.com/ytakefuji/mediapipe_hand/raw/main/result3.gif" width=320 height=240>


# Exercises for students

1.Build a stone-paper-scissors or rock-paper-scissors detection system (Janken recognition).

1.1 recognized hand shape string name (stone, paper or scissors) should be displayed.

$ python fingerv2.py

<img src="fingerv2.gif" width=320 height=240>

1.2 recognized shape (image) should be overlayed on the screen.

$ python fingerv3.py

<img src="fingerv3.gif" width=320 height=240>

Hint:
Overlay images program can be used.

1.3 Build a 10-second recoding program of fingerv3.py

Hint:
out=cv2.VideoWriter('r.mp4',cv2.VideoWriter_fourcc(*'mp4v'),24,size)

out.write(imageframe)

2.Build a finger-gesture counting program.

For example, 050505 => "5" x 3 time

0404040404 -> "4" x5 times

3.Build a drawing-in-the-air program, fingerpic.py .

$ python fingerpic.py

Hint is given below demos.

4.Use firmata library to turn LED on and off with conditions such as one of finger position.

<img src='vsw.gif' width=240 height=180>

# How to overlay two images using cv2
<pre>
Hints:
import cv2
g=cv2.imread('goo.png') 
bg=cv2.imread('background.png')
# locating goo.png on background.png at x=10 and y=20
x=10
y=20
bg[y:y+g.shape[1],x:x+g.shape[0]]=g
cv2.imshow("testing",bg)
cv2.waitKey(1)
</pre>

# how to run fingerpic.py
<pre>
$ python fingerpic.py

0-finger moves the pen without drawing.
1-finger draws by index-finger-tip.
2-finger moves the pen without drawing.
4-finger can save a drawn picture as r.png.
5-finger moves the pen without drawing.
Option: 3-finger can terminate this program.
</pre>

# result
<pre>
Gestures                                saved results
</pre>
<img src='A.gif' width=320 height=240> <img src='A.png' width=320 height=240>

<img src='no.gif' width=320 height=240> <img src='no.png' width=320 height=240>

<img src='4ji.gif' width=320 height=240> <img src='4ji.png' width=320 height=240>

<img src='heno.gif' width=320 height=180> <img src='heno.png' width=320 height=180>

<img src='take.gif' width=320 height=180> <img src='take.png' width=320 height=180>




