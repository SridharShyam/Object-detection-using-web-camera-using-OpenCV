# Object Detection using Web Camera and OpenCV

This repository contains a Jupyter Notebook implementation for real-time object detection using a webcam, powered by YOLOv4 and OpenCV.

## Overview
The project leverages the YOLOv4 (You Only Look Once) deep learning model to accurately identify and draw bounding boxes around multiple objects in a real-time video feed captured from your computer's webcam.

## Prerequisites
- Python 3.x
- Jupyter Notebook
- OpenCV (`cv2`)
- NumPy

## Files Needed Locally
To keep the repository clean and small, the YOLOv4 weights and configuration files are excluded from version control. You will need to make sure the following files are in the same directory as the notebook:
- `yolov4.weights`
- `yolov4.cfg`
- `coco.names`

## Usage
1. Clone this repository.
2. Ensure you have the required YOLO weights and config files in the project directory.
3. Open `Object detection using web camera.ipynb` in Jupyter Notebook.
4. Run the cells to initialize the webcam and start detecting objects in real-time.
