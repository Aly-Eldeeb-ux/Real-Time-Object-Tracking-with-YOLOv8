# Real-Time-Object-Tracking-with-YOLOv8
This repository provides a real-time object tracking system powered by YOLOv8 and ByteTrack/BotSort, with a simple Streamlit interface for interaction
 Features

 Live Camera Tracking – track objects directly from your webcam.

 YOLOv8 Integration – accurate and efficient object detection.

 Multi-Object Tracking – powered by ByteTrack or BoT-SORT.

 Configurable Parameters:

Detection confidence threshold

Image resolution

Custom object classes (default: person)

Streamlit Web UI for easy use.

 Project Structure
├── app.py            # Streamlit app (UI for choosing mode and starting tracker)
├── tracker.py        # YOLOv8 detection + ByteTrack/BotSort tracking logic
├── requirements.txt  # Dependencies list
└── README.md         # Documentation

 Installation
 Clone the repository
git clone https://github.com/your-username/real-time-detection.git
cd real-time-detection

 Create a virtual environment
python -m venv venv


Activate it:

Windows (cmd.exe)

venv\Scripts\activate.bat


Windows (PowerShell) (if execution policy allows)

venv\Scripts\Activate.ps1


 If you see an “execution policy” error, fix it with:

Set-ExecutionPolicy RemoteSigned -Scope CurrentUser


Linux/MacOS

source venv/bin/activate

 Install dependencies
pip install -r requirements.txt

 Usage

Run the Streamlit app:

streamlit run app.py

Live Camera Tracking

In the Streamlit page, choose Live Camera.

Click Start Live Camera Tracking.

An OpenCV window will appear showing detected and tracked objects.

Press q to exit.

⚙️ Configuration

You can customize detection/tracking in tracker.py:

WEIGHTS = "yolov8s.pt"        # Model weights (e.g. yolov8s.pt, yolov8n.pt)
CONF_THRES = 0.5              # Confidence threshold
IMG_SIZE = 640                # Input image size
TRACKER_CFG = "bytetrack.yaml"  # Options: "bytetrack.yaml", "botsort.yaml"
FILTER_CLASSES = [0]          # Filter classes (0=person, 2=car, None=all)


Classes: YOLO class IDs (0 = person, 2 = car, etc.)

To track all objects, set FILTER_CLASSES = None.

 Requirements

See requirements.txt
. Key libraries include:

opencv-contrib-python – OpenCV with extra features

ultralytics – YOLOv8 framework

torch, torchvision – PyTorch deep learning library

streamlit – Web interface

matplotlib, numpy, pandas

 Notes

Ensure your webcam is properly connected.

For GPU acceleration, install PyTorch with CUDA support:
 PyTorch Installation Guide

To switch trackers, edit TRACKER_CFG in tracker.py.

For video file tracking, you can extend the commented run_tracker_video() function in tracker.py.

 Example
Streamlit UI:
Real-Time Object Tracker
Choose mode: [Upload a Video | Live Camera]

Tracking Output:

Green bounding boxes with object ID and confidence score.

(You can add screenshots or GIFs here to make your repo stand out)

 License

This project is licensed under the MIT License.
