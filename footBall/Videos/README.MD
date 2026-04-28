The names of the videos (after removing suffixes like .mp4 and .avi) correspond one-to-one with the folder names under the 'footBall/Labels/' directory which are from https://doi.org/10.5061/dryad.3bk3j9m13. Those folders contain the annotation information for each image frame of the videos with the same names.

The label and Video Index are from 0, here is a example to get corresponding image of the label:

```
import cv2
# Suppose Now We Have a.mp4 and a_index.txt, the index in real are 0,1,2,...,999 .etc
with open("a_index.txt",'r') as f:
	labels = f.readlines()
	f.close()
frameIndex = int("a_index.txt".split("_")[-1][0:-4])
cap = cv2.VideoCapture("a.mp4")
cap.set(cv2.CAP_PROP_POS_FRAMES, frameIndex) # Please Use set
ret,frame = cap.read()

# Now frame,label has get matched
```

