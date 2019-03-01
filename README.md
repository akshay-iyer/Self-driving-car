# Self-driving-car
This project includes two tasks :

1) **Predict the speed of a car from a video, captured from dashboard cam. ( a challenge released by [Comma.ai](https://github.com/commaai) )**

**Challenge Description from Comma.ai**

*Basically, your goal is to predict the speed of a car from a video.*
*data/train.mp4 is a video of driving containing 20400 frames. Video is shot at 20 fps.*
*data/train.txt contains the speed of the car at each frame, one speed on each line.*

*data/test.mp4 is a different driving video containing 10798 frames. Video is shot at 20 fps.
Your deliverable is test.txt*

*We will evaluate your test.txt using mean squared error. <10 is good. <5 is better. <3 is heart*

Dataset can be downloaded from  [Comma.ai speed challenge](https://github.com/commaai/speedchallenge)


**Methodology and Model used**

*First Attempt*

The first impression was to use the images/frames (frames converted from the video) and feed some CNN model to map with the numbers (speed) . However, after a fre trials, it was clear that single images can't be used to predict speed as single images have no features that can be related with speed. 

*Second Attempt*

The second attempt( and successful one :) ) was to estimate the speed using two frames. I used optical [Optical flow](https://docs.opencv.org/3.4/d7/d8b/tutorial_py_lucas_kanade.html) to get the pattern of apparent motion of objects between two consecutive frames caused by the movemement of object. It comes intuetively too that movement of objects is more when the speed is high and less when the speed is low. Hence, Optical flow seems to be the perfect choice in order to predict speed.

*Architecture used*

The Task is done using "End to End Learning for Self-Driving Cars archtecture" ( published in 2016). I have incorporated a few changes (such as introduced dropout) in the architecture to improve the results. 


