# Hand Gesture Recognition (Python 3.13 Compatible)

A lightweight real-time hand gesture recognizer that uses classical OpenCV and NumPy image processing, so it works on Python 3.13 without MediaPipe.

## Features

- Runs entirely on OpenCV + NumPy (no external ML dependencies)
- Real-time finger counting for a single hand
- Generates an on-screen hand skeleton with palm center and finger joints
- Recognizes common gestures:
  - Fist (0 fingers)
  - One Finger
  - Victory (2 fingers)
  - Open Palm (5 fingers)
  - Thumbs Up (heuristic)
- Shows both the annotated camera feed and the skin-mask debug view

## Requirements

- Python 3.9 or newer (tested on 3.13)
- Webcam
- Packages listed in `requirements.txt`

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/hand-gesture-recognition.git
   cd hand-gesture-recognition
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

Run the main script:
```bash
python main.py
```

- A window named `Hand Gesture Recognition` will open with the live feed
- A second `Skin Mask` window helps tune skin detection thresholds
- Press `q` to exit both windows

## How It Works

1. Frames are blurred and converted to HSV to build a skin-color mask.
2. The largest contour in the mask is treated as the hand and outlined along with its convex hull.
3. Convexity defects are analyzed to estimate finger count, draw a finger skeleton, and identify simple gestures (thumbs-up included).

## Tips

- Good, even lighting improves skin segmentation.
- Adjust the HSV skin thresholds in `preprocess_frame` if detection is unstable for your environment.
- Keep the hand close to the camera and avoid cluttered backgrounds.
- Customize the skeleton colors and opacity inside `draw_hand_skeleton` if you want a different visual style.

## Author

Student Project - 5th Semester

