# Real-Time Object Detection using YOLOv4 and OpenCV 📷🚀

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green.svg)
![YOLOv4](https://img.shields.io/badge/YOLO-v4-orange.svg)

This repository contains a simple, yet powerful implementation for **real-time object detection** using your computer's webcam. The project is built in a Jupyter Notebook and leverages the highly accurate and fast **YOLOv4** (You Only Look Once) deep learning model running via OpenCV's `dnn` module.

---

## ✨ Features

- **Real-Time Inference:** Process live video feed from your webcam seamlessly.
- **High Accuracy & Speed:** Uses the YOLOv4 architecture which provides an excellent balance between detection speed and accuracy.
- **80+ Object Classes:** Capable of detecting a wide variety of everyday objects (people, cars, animals, furniture, etc.) out-of-the-box using the pre-trained COCO dataset.
- **Visual Bounding Boxes:** Draws colored bounding boxes with confidence scores and class labels dynamically on the video stream.

---

## 🛠️ Prerequisites & Setup

Ensure you have Python installed. You will need the following libraries:

```bash
pip install opencv-python numpy jupyter notebook
```

### Required Model Files (Excluded from Git)
Due to size constraints, the pre-trained weights and configuration files are intentionally excluded from this repository via `.gitignore`. You must download them manually and place them in the root directory:

1. **`yolov4.cfg`**: The YOLOv4 network configuration file.
   - [Download yolov4.cfg](https://raw.githubusercontent.com/AlexeyAB/darknet/master/cfg/yolov4.cfg)
2. **`yolov4.weights`**: The pre-trained weights file.
   - [Download yolov4.weights](https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights)
3. **`coco.names`**: The file containing the 80 COCO class labels.
   - [Download coco.names](https://raw.githubusercontent.com/AlexeyAB/darknet/master/cfg/coco.names)

---

## 🚀 How to Run

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
4. **Run the Code:** Open the `Object detection using web camera.ipynb` notebook and run all cells. A new window will pop up showing your webcam feed with real-time detections!
5. **Exit:** Press the `q` or `ESC` key while focusing on the webcam window to safely close the application and release the camera.

---

## 🧠 How it Works

1. **Video Capture:** OpenCV captures frames sequentially from the default camera (`cv2.VideoCapture(0)`).
2. **Preprocessing (Blob Generation):** Each frame is converted into a binary large object (Blob) which involves resizing to a standard dimension (e.g., 416x416), scaling pixel values, and swapping Red and Blue channels.
3. **Forward Pass:** The blob is fed into the YOLOv4 network loaded via OpenCV's `cv2.dnn.readNetFromDarknet()`.
4. **Post-processing:** The network outputs predictions. We apply **Non-Maximum Suppression (NMS)** to filter out overlapping, low-confidence bounding boxes, keeping only the most accurate predictions.
5. **Rendering:** Bounding boxes, labels, and confidence percentages are overlaid onto the original frame and displayed.

---

## ⚠️ Troubleshooting

- **Webcam not turning on:** Ensure your webcam is not being used by another application. Try changing `cv2.VideoCapture(0)` to `cv2.VideoCapture(1)` if you have multiple cameras.
- **Model loading errors:** Double-check that the `yolov4.cfg` and `yolov4.weights` files are exactly in the same directory as the notebook and are not corrupted.

---

## 🙏 Acknowledgements
- [Darknet (AlexeyAB)](https://github.com/AlexeyAB/darknet) for the YOLOv4 implementation.
- [OpenCV](https://opencv.org/) for the robust computer vision and DNN capabilities.
