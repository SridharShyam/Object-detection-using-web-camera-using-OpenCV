# Real-Time Object Detection using YOLOv4 and OpenCV

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green.svg)
![YOLOv4](https://img.shields.io/badge/YOLO-v4-orange.svg)

This repository contains a Jupyter Notebook implementation for object detection using a webcam. It uses the YOLOv4 deep learning model running via OpenCV's `dnn` module.

---

## Features

- **Real-Time Inference:** Processes video feed from a webcam.
- **YOLOv4 Architecture:** Utilizes the YOLOv4 model for object detection.
- **COCO Dataset Classes:** Detects objects based on the 80 classes provided by the pre-trained COCO dataset.
- **Visual Bounding Boxes:** Draws bounding boxes with confidence scores and class labels on the video stream.

---

## Prerequisites & Setup

Ensure you have Python installed along with the following libraries:

```bash
pip install opencv-python numpy jupyter notebook
```

### Required Model Files (Excluded from Git)
Due to size constraints, the pre-trained weights and configuration files are excluded from this repository via `.gitignore`. You must download them manually and place them in the root directory:

1. **`yolov4.cfg`**: The YOLOv4 network configuration file.
   - [Download yolov4.cfg](https://raw.githubusercontent.com/AlexeyAB/darknet/master/cfg/yolov4.cfg)
2. **`yolov4.weights`**: The pre-trained weights file.
   - [Download yolov4.weights](https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights)
3. **`coco.names`**: The file containing the 80 COCO class labels.
   - [Download coco.names](https://raw.githubusercontent.com/AlexeyAB/darknet/master/cfg/coco.names)

---

## How to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/SridharShyam/Object-detection-using-web-camera-using-OpenCV.git
   cd Object-detection-using-web-camera-using-OpenCV
   ```
2. **Download Model Files:** Ensure `yolov4.cfg`, `yolov4.weights`, and `coco.names` are placed inside the project folder alongside the notebook.
3. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```
4. **Run the Code:** Open `Object detection using web camera.ipynb` and run all cells. A new window will display the webcam feed with detections.
5. **Exit:** Press the `q` or `ESC` key while focusing on the webcam window to close the application.

---

## How it Works

1. **Video Capture:** OpenCV captures frames from the default camera (`cv2.VideoCapture(0)`).
2. **Preprocessing:** Each frame is converted into a Blob, resizing to standard dimensions (e.g., 416x416).
3. **Forward Pass:** The blob is passed into the YOLOv4 network using `cv2.dnn.readNetFromDarknet()`.
4. **Post-processing:** The network outputs predictions, and Non-Maximum Suppression (NMS) is applied to filter out overlapping bounding boxes.
5. **Rendering:** Bounding boxes, labels, and confidence percentages are overlaid onto the original frame.

---

## Troubleshooting

- **Webcam not turning on:** Ensure your webcam is not being used by another application. Change `cv2.VideoCapture(0)` to `cv2.VideoCapture(1)` if you have multiple cameras.
- **Model loading errors:** Verify that `yolov4.cfg` and `yolov4.weights` are in the same directory as the notebook.

---

## Acknowledgements
- [Darknet (AlexeyAB)](https://github.com/AlexeyAB/darknet) for the YOLOv4 implementation.
- [OpenCV](https://opencv.org/) for the DNN module.
