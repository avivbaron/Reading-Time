# Reading-Time - Computer Vision

The essence of the project is to make it easier for the reader on the computer while reading so that he does not have to use the mouse to scroll down the page when he reaches the bottom of the sequel. The computer camera will detect when the reader looks at the bottom of the screen and scroll the screen for him.

How it works:

1.To be able to follow the gaze of a person looking at the screen, we will first need to identify his face. To identify the face I used a face classifier with trained data (machine learning) of the face of haarcascade.

2.And finally, once we have identified the eye area, we will need to find the pupils. The pupils are found by processing the image of the eyes and at the end, we will use SimpleBlobDetector, which detects circles. As part of the image processing, we will also lower the eyebrows to make it easier to find the pupil.

3.After we got to the point where we were recognizing the pupil, the problematic part came, figuring out by what data one could identify where the pupil was looking. I lingered for lots and lots of time finding a way to identify the correct look, and finally started checking what changes in my key data (keypoints) when I look down and saw that according to the Y of the coordinates, you can see that when I look down the number goes above 15 and goes down when I look at the middle and according to This works my code.
For the part of scrolling the screen, I used a pynput library that allows access to control the mouse and access commands like using the mouse scroll, which scrolls down when Y exceeds 15.5.
