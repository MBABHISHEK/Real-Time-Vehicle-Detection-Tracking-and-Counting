# Vehicle Tracking and Counting System

This project implements a vehicle tracking and counting system using YOLOv8 for object detection and DeepSORT for object tracking. The system processes a video to detect vehicles, track their movements, and count the number of vehicles crossing specific lines.

## Features
- Object detection using YOLOv8.
- Multi-object tracking with DeepSORT.
- Vehicle counting across specified lines.
- Frame overlay with bounding boxes, labels, tracking IDs, and counters.
- Displays FPS for real-time performance monitoring.

## Requirements

### Libraries and Frameworks
- Python 3.8+
- OpenCV
- NumPy
- Ultralytics YOLO
- DeepSORT
- TensorFlow

### Files and Models
- YOLOv8 model weights (`yolov8s.pt`).
- DeepSORT model (`mars-small128.pb`).
- COCO class names file (`coco.names`).
- Input video file (`1.mp4`).

### Install Dependencies
```bash
pip install numpy opencv-python-headless ultralytics tensorflow
```

### Directory Structure
```plaintext
.
├── config
│   ├── mars-small128.pb
│   ├── coco.names
├── helper.py
├── 1.mp4
├── output.mp4
└── main.py  # This script
```

## Usage

### Run the Script
```bash
python main.py
```

### Output
- The script generates an annotated video named `output.mp4`.
- It displays the video with overlays in a window titled `Output`. Press `q` to exit.

### Key Functions
1. **Object Detection**:
   - YOLOv8 detects vehicles and outputs bounding boxes, confidence scores, and class IDs.
2. **Object Tracking**:
   - DeepSORT assigns unique IDs to detected vehicles and tracks them across frames.
3. **Vehicle Counting**:
   - Tracks vehicle positions relative to predefined lines and counts crossings.

## Customization
- **Adjust Confidence Threshold**: Modify `conf_threshold` for detection sensitivity.
- **Define Lines**:
  Update `start_line_X` and `end_line_X` coordinates to change line positions.
- **Input/Output Files**: Change `video_cap` for input video and `create_video_writer` for output video.

## Helper Scripts

### `helper.py`
Contains utility functions like `create_video_writer` for initializing video output.

## Notes
- Ensure `mars-small128.pb` and `coco.names` are in the `config` directory.
- The input video must match the system's intended resolution and frame rate for optimal performance.

## References
- [YOLOv8 Documentation](https://github.com/ultralytics/ultralytics)
- [DeepSORT GitHub Repository](https://github.com/nwojke/deep_sort)
- [OpenCV Documentation](https://docs.opencv.org/)

## Acknowledgments
Special thanks to the developers of YOLO and DeepSORT for their powerful models.

