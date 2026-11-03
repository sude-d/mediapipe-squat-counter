# MediaPipe Squat Counter

A computer vision project that detects squat movements and counts repetitions using **Python, OpenCV, and MediaPipe Pose**.

The application analyzes video frames, detects human body landmarks, calculates knee angles, classifies body positions, and tracks completed squat repetitions.

## Features

- Human pose estimation using MediaPipe Pose
- Real-time video frame processing with OpenCV
- Knee angle calculation using NumPy
- Squat position classification
- Automatic squat repetition counting
- Visual display of body landmarks and exercise statistics

## Technologies Used

- Python
- OpenCV
- MediaPipe
- NumPy

## How It Works

1. The input video is processed frame by frame using OpenCV.
2. MediaPipe Pose detects body landmarks.
3. Right hip, right knee, and right ankle coordinates are extracted.
4. The knee angle is calculated using the three landmark coordinates.
5. The current body position is classified based on the knee angle.
6. A squat repetition is counted when the user moves from the down position back to the standing position.

## Project Structure

```text
mediapipe-squat-counter/
│
├── squat_counter.py
├── squat_test1.avi
├── requirements.txt
└── README.md
```

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/mediapipe-squat-counter.git
cd mediapipe-squat-counter
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\activate
```

Activate it on Linux/macOS:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Requirements

Create a `requirements.txt` file containing:

```text
opencv-python
mediapipe
numpy
```

## Usage

Place your input video in the project directory and run:

```bash
python squat_counter.py
```

Press **Q** to close the video window.

## Angle-Based Classification

| Knee Angle | Classification |
|---|---|
| Below 100° | Squatting |
| 100°–160° | Transition |
| Above 160° | Standing |

The repetition counter uses separate down and up thresholds to identify completed squat movements.

## Notes

- The current implementation uses the right leg landmarks.
- A side-view camera angle is recommended for more consistent knee angle measurements.
- The input video must be available in the project directory.
- Angle thresholds may require adjustment depending on camera position and individual movement patterns.
- This project demonstrates basic pose-based movement tracking and is not a medical or professional exercise assessment system.

## Future Improvements

- Live webcam support
- Left and right leg analysis
- Squat form feedback
- Movement quality assessment
- Additional exercise recognition
- Real-time performance dashboard

## Acknowledgements

Built with [MediaPipe](https://developers.google.com/edge/mediapipe/solutions/vision/pose_landmarker), [OpenCV](https://opencv.org/), and [NumPy](https://numpy.org/).
