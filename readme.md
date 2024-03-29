# ONNX XiNet-pose Pose Detection for Embedded Devices
This repository contains code that is developed to run ONNX models of XiNet pose detection on embedded devices, such as Raspberry Pi and Nvidia Jetson, with minimal dependencies and without requiring the installation of PyTorch.

## Overview
The code in this repository provides a lightweight solution for running XiNet pose detection models in ONNX format on embedded devices. The code is designed to be efficient and easy to use, with minimal dependencies and no need to install PyTorch.

The repository contains a Python script that can be used to load an ONNX model file and run inference on input images or video streams. The script uses the OpenCV library to handle image input/output and drawing of detected poses.


## Dependencies
Python 3.x

numpy
python-opencv 
onnxruntime
matplotlib

## Usage
Clone the repository: git clone https://github.com/AlbertoAncilotto/YoloV8_pose_onnx

Install the required dependencies: pip install numpy opencv-python onnxruntime matplotlib

The code is setup for using the default cv2 camera for inference. For use with an NVidia Jetson, switch commenting on these two lines
```
#cap = jetson_camera.VideoCapture(out_width=IMG_SZ[0], out_height=IMG_SZ[1])
cap = cv2.VideoCapture(0)
```
Code is setup for multi target pose detection. Switching to single target allows instead for the ability to use lowpass filtering on the output pose. Switch commenting on these two lines to enable
```
# frame = post_process_single(frame, output[0], score_threshold=0.2)
frame = post_process_multi(frame, output[0], score_threshold=0.2)
```


## License
The code in this repository is licensed under the MIT License. Feel free to use and modify the code as needed.