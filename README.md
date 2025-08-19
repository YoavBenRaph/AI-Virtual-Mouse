# AI-Virtual-Mouse

## ☝️🖱️ Gesture-Controlled Cursor with OpenCV & MediaPipe

- This project turns your webcam into a motion-sensing input device, allowing you to control your computer's mouse cursor and perform actions like clicking using only your hand gestures. It provides a touch-free and innovative way to interact with your digital environment.


## 📌 Features

- Real-Time Cursor Control: Move your index finger to control the on-screen mouse cursor.
- Clicking Functionality: Perform a "click" action by bringing your index and middle fingers together.
- Smoothened Movement: The cursor's motion is smoothened to reduce jitter and improve control.
- Dynamic Feedback: Visual cues, such as a rectangle showing the active frame and circles highlighting fingertips, provide clear feedback.
- Frame Rate Display: Shows the FPS for real-time performance monitoring.

## 🔋 How It Works

The program utilizes a combination of computer vision and system automation to function:

1. **Hand Landmark Detection**  
   - The `HandTrackingModule` tracks a single hand and its key landmarks from the webcam feed.
2. **Coordinate Mapping**  
   - The `x` and `y` coordinates of the index fingertip are mapped from the webcam's frame to the dimensions of your computer screen. This is done using NumPy's `np.interp` function.
3. **Gesture Recognition**  
   The `fingersUp()` function checks which fingers are extended.
   - **Moving Mode**  
     When only the index finger is up, the code enters "moving mode," updating the mouse cursor's position based on the fingertip's location.
   - **Clicking Mode**  
     When both the index and middle fingers are up, the code measures the distance between them. If this distance falls below a certain threshold, the program triggers a mouse click using the `autopy` library.
4. **Mouse Automation**  
   - The `autopy` library is used to programmatically move the system's mouse and perform clicks, translating your hand gestures into cursor actions.

## 📑 Requirements

To run this project, you need the following Python libraries:

- opencv-python
- numpy
- autopy
- **HandTrackingModule**: A custom module that contains the functions for hand tracking and landmark detection
