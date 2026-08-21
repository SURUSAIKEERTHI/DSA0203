# Real-Time Blink-Detection Drowsiness Alert System

## Aim

To design a real-time blink-detection system that identifies prolonged
eye closure and generates a drowsiness alert.

## Input

Live video stream from a camera.

## Output

Blink count, eye status, and drowsiness alert.

## Structured Pseudocode

1. START

2. Initialize the camera.

3. Load the face detection model.

4. Load the facial landmark and eye detection model.

5. Set the Eye Aspect Ratio (EAR) threshold.

6. Set the minimum number of consecutive frames required
   to identify prolonged eye closure.

7. Initialize blink_count = 0.

8. Initialize closed_eye_frames = 0.

9. WHILE the camera is active:

   9.1 Capture the current video frame.

   9.2 Convert the frame to grayscale.

   9.3 Detect the face in the frame.

   9.4 IF a face is detected:

       9.4.1 Detect facial landmarks.

       9.4.2 Identify the left and right eye landmarks.

       9.4.3 Calculate the Eye Aspect Ratio (EAR).

       9.4.4 Calculate the average EAR of both eyes.

       9.4.5 IF the average EAR is below the threshold:

              Increment closed_eye_frames.

       9.4.6 ELSE:

              IF the eye was closed only for a short duration:

                  Increment blink_count.

              Reset closed_eye_frames to zero.

       9.4.7 IF closed_eye_frames reaches the predefined limit:

              Set status = "DROWSY".

              Generate an alert.

       9.4.8 ELSE:

              Set status = "NORMAL".

       9.4.9 Display EAR, blink count and status.

   9.5 ELSE:

       Display "FACE NOT DETECTED".

   9.6 Display the processed video frame.

   9.7 IF the user presses the exit key:

       Stop the video processing.

10. Release the camera.

11. Close the display.

12. STOP
## Revision 2 – Blink Detection Enhancement

The second revision improves the initial design by introducing
Eye Aspect Ratio (EAR) based blink detection.

### Added Features

- EAR threshold definition
- Left and right eye analysis
- Consecutive closed-eye frame counting
- Blink counting
- Reset mechanism after eye opening
