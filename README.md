# YOLOv10 Object Detection on a youtube footage

This repository contains a Python script that automates the setup and execution of object detection using the YOLOv10 model. The script downloads the necessary weight files, performs object detection on both images and videos, and compresses the output video.

link to the actual youtube video : https://youtu.be/CftLBPI1Ga4?si=1n2yP3NUSxlmZj04


![Object Detection in Action](https://github.com/Torajabu/YOLOv10-Object-cars-persons-and-bikes-Detection---Python/raw/main/result_compressed-ezgif.com-video-to-gif-converter.gif)

## Prerequisites

Before running the script, ensure you have the following installed:

- Python 3.x
- `pip` (Python package installer)
- `git` (for cloning the YOLOv10 repository)
- `ffmpeg` (for video compression)

You can install `ffmpeg` using the following commands:

- **Ubuntu/Debian:**
  ```bash
  sudo apt-get update
  sudo apt-get install ffmpeg

    macOS:
    

    brew install ffmpeg

    Windows:
    Download and install from the official FFmpeg website.

Installation

    Clone this repository:
   

    git clone https://github.com/your-username/yolov10-object-detection.git
    cd yolov10-object-detection

    Run the script:
   

    python yolov10_detection.py

Script Overview

The script performs the following tasks:

    Directory Setup:

        Creates necessary directories for outputs and weights.

    Clone YOLOv10 Repository:

        Clones the YOLOv10 repository if it doesn't already exist.

    Install Dependencies:

        Installs the required dependencies for YOLOv10.

    Download Weight Files:

        Downloads the YOLOv10 weight files if they are not already present.

    Object Detection:

        Performs object detection on an image and a video using the YOLOv10 model.

    Video Compression:

        Compresses the output video using ffmpeg.

Customization

You can customize the script by modifying the following variables:

    base_dir: The base directory where all files will be stored.

    image_source: The path to the image for object detection.

    video_source: The path to the video for object detection.

Example
python
Copy

# Define paths
base_dir = "/home/rajab/Downloads"
output_dir = os.path.join(base_dir, "yolov10_outputs")
weights_dir = os.path.join(base_dir, "yolov10_weights")

# URLs of the weight files
urls = [
    "https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10n.pt",
    "https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10s.pt",
    "https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10m.pt",
    "https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10b.pt",
    "https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10l.pt",
    "https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10x.pt"
]

Output

    The output images and videos will be saved in the yolov10_outputs directory.

    The compressed video will be saved as result_compressed.mp4 in the video_results directory.

Troubleshooting

    Image/Video Not Found: Ensure the paths to the image and video are correct.

    Compression Failed: Ensure ffmpeg is installed correctly and the output directory exists.

Acknowledgments

    YOLOv10 by THU-MIG for the object detection model.

    FFmpeg for video compression.

    Royalty free videos youtube channel for the footage used

