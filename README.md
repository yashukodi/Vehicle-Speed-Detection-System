# Vehicle-Speed-Detection-System


This Project implements a vehicle tracking system using OpenCV and Dlib libraries in Python. It uses a trained classifier to detect cars in a video file and tracks their movement across frames. 

The code initializes the necessary libraries and loads the Haar cascade classifier for car detection. It then proceeds to read the video file frame by frame and applies the detection and tracking algorithms. The system maintains a collection of car trackers and their corresponding locations in each frame. It updates the trackers based on their tracking quality and creates new trackers for newly detected cars. The estimated speed of the cars is calculated by measuring the distance traveled between frames. The speed is then displayed on the frame, and the resulting frames with tracked cars are written to an output video file.

The code outlines the main function responsible for tracking multiple cars. It sets up the necessary variables, including counters, car IDs, and speed calculations. The function utilizes a loop to iterate through the frames of the video. Within the loop, it updates the car trackers, detects cars using the Haar cascade classifier, matches the detected cars with existing trackers, and creates new trackers as needed. The positions of the tracked cars are updated, and their speeds are estimated and displayed on the frames. The resulting frames are displayed and written to an output video file. The process continues until the end of the video or until the user interrupts it.


METHODOLOGY
We utilize the following methodology and techniques:

Cascade Classifier: It employs the cv2.CascadeClassifier class to detect cars in the video frames using a trained classifier file ("vech.xml"). This classifier is based on the Haar-like features and utilizes the Viola-Jones algorithm.

Object Tracking: We use the object tracking algorithm implemented in the Dlib library. Specifically, it employs the correlation tracker (dlib.correlation_tracker) to track multiple vehicles across frames. The tracker uses a correlation filter to estimate the position and size of the vehicles.

Speed Estimation: It implements the estimateSpeed function to estimate the speed of each tracked vehicle. It calculates the distance traveled by a vehicle between two consecutive frames and converts it into speed using a predetermined pixels-per-meter (ppm) ratio and the frame rate.

Frame Processing: It processes each frame of the video by resizing it to a predefined width and height. It converts the frame to grayscale before detecting cars using the cascade classifier.

Visualization: It visualizes the tracked vehicles by drawing bounding boxes around them using the cv2.rectangle function. It also displays the estimated speed of the vehicles on the output video using the cv2.putText function.

Video Writing: It utilizes the cv2.VideoWriter class to create an output video writer. It saves the annotated frames with the tracked vehicles and their speeds into an output video file.

These methodology and techniques collectively enable the vehicle tracking system to detect and track multiple vehicles, estimate their speeds, and provide visual annotations in the output video.


ALGORITHMS
The algorithm used in the code is as follows:

1.	Import the required libraries and load the Haar cascade classifier for car detection.
2.	Open the video file for processing and define constants for frame width and height.
3.	Define a function estimateSpeed to calculate the estimated speed of a car based on its position changes between frames.
4.	Define the main function trackMultipleObjects for tracking multiple cars.
5.	Initialize variables for tracking, including car trackers, IDs, and speed calculations.
6.	Start a loop to read frames from the video.
7.	Update existing car trackers by removing trackers with low tracking quality.
8.	Every 10 frames, detect cars in the frame using the Haar cascade classifier.
9.	For each detected car, check if it matches an existing car tracker based on its position.
10.	If a match is found, update the tracker with the new car position. If no match is found, create a new tracker for the car.
11.	Update the positions of the tracked cars and draw rectangles around them on the frame.
12.	Calculate the estimated speed of the cars based on their position changes and store the speeds.
13.	Display the estimated speeds on the frame.
14.	Write the resulting frame with the visualized information to an output video file.
15.	Continue the loop until all frames have been processed or until the user interrupts the program.
16.	Release resources, close windows, and clean up.
17.	Call the trackMultipleObjects function to start the car tracking process.

The algorithm involves a combination of car detection using the Haar cascade classifier, object tracking using correlation trackers, and frame-by-frame processing to track multiple cars in a video. The algorithm continuously updates the trackers, detects new cars, matches them with existing trackers, updates their positions, and estimates their speeds. The resulting frames with tracked cars and estimated speeds are written to an output video file.
