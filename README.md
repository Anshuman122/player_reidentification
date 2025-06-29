
# YOLOv11 + DeepSORT Realtime Object Tracking

This project implements **real-time person detection and tracking** in video using:

- **YOLOv11** (`yolo11m.pt` model) for object detection
- **DeepSORT Realtime** for tracking across frames
- **OpenCV** for video I/O and visualization

---

## 📂 Project Structure

.
├── models/
│ └── yolo11m.pt # Pretrained YOLOv11 model weights
├── assets/
│ └── 15sec_input_720p.mp4 # Input video file
├── yolo_detector.py # YOLOv11 detection wrapper
├── tracker.py # DeepSORT tracking wrapper
├── yolo_detection_tracking.py # Main script to run detection and tracking
└── README.md # Project documentation

## 🛠️ Requirements

Install dependencies using `pip`:

bash
pip install opencv-python==4.10.0.84
pip install ultralytics==8.3.1
pip install deep-sort-realtime==1.3.2


Note:

ultralytics is required for YOLOv11.

deep-sort-realtime provides the tracking logic.

Python ≥3.8 recommended.



✅ Setup
Clone the repository


git clone <your-repo-url>
cd <your-project-folder>
Download the YOLO model

Place yolo11m.pt inside the models/ directory.

If you don’t have the model file, you can train or download it from the Ultralytics YOLO repository.

Verify input video

Ensure the video file is available at:


assets/15sec_input_720p.mp4
🚀 Running the Code
Run the tracking script:


python yolo_detection_tracking.py
This will:

Open the video

Detect persons in each frame

Assign unique IDs for tracking

Draw bounding boxes and IDs on the video stream

Print the FPS in the console

Press q or Esc to exit.

🎯 Example Output
While running, you will see output similar to:

Current fps: 27.35
Current fps: 28.11
...
And a window displaying the video with tracked bounding boxes:


[ Tracking ID: 1 ]
+------------------------+
|                        |
|      [Person]          |
|                        |
+------------------------+
⚙️ Customization
Adjust confidence threshold
Change confidence=0.2 in main.py when initializing YoloDetector:


detector = YoloDetector(model_path=MODEL_PATH, confidence=0.3)
Use a different video
Update VIDEO_PATH in main.py:


VIDEO_PATH = "assets/your_video.mp4"
🧩 Troubleshooting
Model not found error

Ensure models/yolo11m.pt exists.

Unable to open video file

Check that assets/15sec_input_720p.mp4 is a valid video path.

CUDA errors

This code runs on CPU by default. If you want GPU acceleration, ensure proper CUDA drivers and PyTorch installed.

📄 License
This project is for educational and research purposes only.


