# 👁️ Ocular Rhythm Tracker 💤


This is a Python script that uses OpenCV, dlib, and facial landmarks detection to detect eye blinks in a video stream or file.

The script extracts the coordinates of the left and right eye from the facial landmarks and uses the eye aspect ratio (EAR) to determine if a blink has occurred. EAR is a mathematical formula that calculates the ratio between the vertical distance and the horizontal distance of the eye landmarks. When a person blinks, the eye aspect ratio drops below a threshold.

## 📋 Requirements
- Python 3.6 or above
- OpenCV
- dlib
- imutils
- scipy

## 📌 Usage
To use the script, you need to have a trained facial landmarks predictor. The predictor used in this script is the dlib's pre-trained facial landmarks detector, which can be downloaded from [here](https://github.com/davisking/dlib-models/blob/master/shape_predictor_68_face_landmarks.dat.bz2).

Run the script with the following command:
python eye_blink_detection.py --shape-predictor shape_predictor_68_face_landmarks.dat --video video_file.mp4

- `--shape-predictor`: path to the trained facial landmarks predictor file.
- `--video`: path to the video file to be processed. (optional if you want to use your webcam instead)

## 🛠️ How it works
The script reads a video stream or file, detects faces using dlib's face detector, and then extracts the coordinates of the left and right eye from the facial landmarks.

The script then calculates the eye aspect ratio for both eyes using the extracted coordinates. If the EAR value is below a certain threshold, the script increases a counter for the number of frames where the eyes have been closed. If the counter exceeds a predefined value, it is assumed that a blink has occurred, and the total blink count is incremented.

The script also visualizes the eyes' detected region using a green contour around the eyes in the video stream.

## 🚫 Limitations
The script's accuracy may vary based on several factors, such as lighting conditions, occlusions, and head poses. It is intended as a general-purpose algorithm and should not be used for medical purposes.


