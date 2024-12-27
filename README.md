# Driver-Drowsiness_Detection_System-
This Python script implements a Driver Drowsiness Detection System using computer vision techniques. The system utilizes facial landmarks and eye aspect ratio to monitor a driver's level of drowsiness in real-time. Here's a breakdown of the code:


# Library Imports:

The script starts by importing necessary libraries, including scipy for spatial distance calculations, imutils for convenience in working with OpenCV, pygame.mixer for audio alerts, dlib for face detection and facial landmarks, and cv2 for image processing.
Alarm Initialization:

The mixer is initialized, and an alarm sound ("alarm.wav") is loaded using pygame.mixer.
Eye Aspect Ratio Calculation:

The eye_aspect_ratio function is defined, which calculates the eye aspect ratio based on the Euclidean distances between specific facial landmarks. This ratio is used as an indicator of eye openness.
Thresholds and Parameters:

Threshold values (thresh) and parameters for face detection, facial landmarks, and drowsiness checks are set, such as the frame check value (frame_check) to trigger an alert after a certain number of consecutive frames with low eye aspect ratio.
Video Capture Initialization:

Video capture is initiated using cv2.VideoCapture(0), where 0 represents the default camera.
Main Loop:

The script enters a continuous loop where it captures frames from the camera.
Each frame is resized for efficient processing, converted to grayscale, and faces are detected using the dlib face detector.
For each detected face, facial landmarks are predicted, and the eye aspect ratio is calculated.
Contours are drawn around the eyes on the frame for visualization.
If the average eye aspect ratio falls below the specified threshold for a certain number of consecutive frames, an alert is triggered. The alert includes displaying warning text on the frame and playing an alarm sound using pygame.mixer.
The processed frame is displayed, and the loop continues until the "q" key is pressed.
Cleanup:

The OpenCV windows are destroyed, and video capture resources are released.
