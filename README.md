# YOLOv10 Object Detection on a youtube footage

This repository contains a Python script that automates the setup and execution of object detection using the YOLOv10 model. The script downloads the necessary weight files, performs object detection on both images and videos, and compresses the output video.

<svg viewBox="0 0 1200 800" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="inputGradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#4F46E5;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#7C3AED;stop-opacity:1" />
    </linearGradient>
    <linearGradient id="processGradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#059669;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#10B981;stop-opacity:1" />
    </linearGradient>
    <linearGradient id="outputGradient" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#DC2626;stop-opacity:1" />
      <stop offset="100%" style="stop-color:#EF4444;stop-opacity:1" />
    </linearGradient>
    <filter id="shadow" x="-20%" y="-20%" width="140%" height="140%">
      <feDropShadow dx="3" dy="3" stdDeviation="3" flood-color="#000000" flood-opacity="0.3"/>
    </filter>
  </defs>
  
  <!-- Background -->
  <rect width="1200" height="800" fill="#F8FAFC"/>
  
  <!-- Title -->
  <text x="600" y="40" text-anchor="middle" font-family="Arial, sans-serif" font-size="28" font-weight="bold" fill="#1E293B">
    YOLOv10 Object Detection Architecture
  </text>
  <text x="600" y="65" text-anchor="middle" font-family="Arial, sans-serif" font-size="16" fill="#64748B">
    Cars, Persons, and Bikes Detection System
  </text>
  
  <!-- Input Section -->
  <g>
    <!-- Input Box -->
    <rect x="50" y="120" width="200" height="120" rx="10" fill="url(#inputGradient)" filter="url(#shadow)"/>
    <text x="150" y="145" text-anchor="middle" font-family="Arial, sans-serif" font-size="16" font-weight="bold" fill="white">
      Input Sources
    </text>
    
    <!-- Video Icon -->
    <rect x="80" y="160" width="40" height="30" rx="3" fill="white" opacity="0.9"/>
    <circle cx="90" cy="170" r="3" fill="#4F46E5"/>
    <text x="130" y="175" font-family="Arial, sans-serif" font-size="12" fill="white">YouTube Video</text>
    
    <!-- Camera Icon -->
    <rect x="80" y="195" width="35" height="25" rx="3" fill="white" opacity="0.9"/>
    <circle cx="97" cy="207" r="5" fill="#4F46E5"/>
    <text x="130" y="210" font-family="Arial, sans-serif" font-size="12" fill="white">Live Feed</text>
  </g>
  
  <!-- Arrow 1 -->
  <path d="M 270 180 L 320 180" stroke="#64748B" stroke-width="3" fill="none" marker-end="url(#arrowhead)"/>
  
  <!-- Pre-processing Section -->
  <g>
    <rect x="340" y="120" width="180" height="120" rx="10" fill="url(#processGradient)" filter="url(#shadow)"/>
    <text x="430" y="145" text-anchor="middle" font-family="Arial, sans-serif" font-size="16" font-weight="bold" fill="white">
      Pre-processing
    </text>
    
    <text x="430" y="170" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">
      • Frame Extraction
    </text>
    <text x="430" y="190" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">
      • Resize and Normalize
    </text>
    <text x="430" y="210" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">
      • OpenCV Processing
    </text>
  </g>
  
  <!-- Arrow 2 -->
  <path d="M 540 180 L 590 180" stroke="#64748B" stroke-width="3" fill="none" marker-end="url(#arrowhead)"/>
  
  <!-- YOLOv10 Model Section -->
  <g>
    <rect x="610" y="100" width="220" height="160" rx="10" fill="#1E293B" filter="url(#shadow)"/>
    <text x="720" y="125" text-anchor="middle" font-family="Arial, sans-serif" font-size="18" font-weight="bold" fill="white">
      YOLOv10 Model
    </text>
    
    <!-- Backbone -->
    <rect x="630" y="140" width="180" height="30" rx="5" fill="#3B82F6"/>
    <text x="720" y="160" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">
      Backbone (Feature Extraction)
    </text>
    
    <!-- Neck -->
    <rect x="630" y="180" width="180" height="30" rx="5" fill="#8B5CF6"/>
    <text x="720" y="200" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">
      Neck (Feature Fusion)
    </text>
    
    <!-- Head -->
    <rect x="630" y="220" width="180" height="30" rx="5" fill="#F59E0B"/>
    <text x="720" y="240" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">
      Detection Head (Predictions)
    </text>
  </g>
  
  <!-- Arrow 3 -->
  <path d="M 850 180 L 900 180" stroke="#64748B" stroke-width="3" fill="none" marker-end="url(#arrowhead)"/>
  
  <!-- Post-processing Section -->
  <g>
    <rect x="920" y="120" width="180" height="120" rx="10" fill="url(#processGradient)" filter="url(#shadow)"/>
    <text x="1010" y="145" text-anchor="middle" font-family="Arial, sans-serif" font-size="16" font-weight="bold" fill="white">
      Post-processing
    </text>
    
    <text x="1010" y="170" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">
      • NMS Filtering
    </text>
    <text x="1010" y="190" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">
      • Confidence Threshold
    </text>
    <text x="1010" y="210" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">
      • Bounding Box Refine
    </text>
  </g>
  
  <!-- Arrow down -->
  <path d="M 1010 260 L 1010 310" stroke="#64748B" stroke-width="3" fill="none" marker-end="url(#arrowhead)"/>
  
  <!-- Detection Results Section -->
  <g>
    <rect x="920" y="330" width="180" height="140" rx="10" fill="url(#outputGradient)" filter="url(#shadow)"/>
    <text x="1010" y="355" text-anchor="middle" font-family="Arial, sans-serif" font-size="16" font-weight="bold" fill="white">
      Detection Results
    </text>
    
    <!-- Car icon -->
    <rect x="940" y="375" width="25" height="15" rx="2" fill="white"/>
    <circle cx="945" cy="395" r="3" fill="white"/>
    <circle cx="960" cy="395" r="3" fill="white"/>
    <text x="975" y="385" font-family="Arial, sans-serif" font-size="12" fill="white">Cars</text>
    
    <!-- Person icon -->
    <circle cx="950" cy="410" r="5" fill="white"/>
    <rect x="947" y="415" width="6" height="15" rx="1" fill="white"/>
    <text x="975" y="420" font-family="Arial, sans-serif" font-size="12" fill="white">Persons</text>
    
    <!-- Bike icon -->
    <circle cx="945" cy="445" r="3" fill="white"/>
    <circle cx="960" cy="445" r="3" fill="white"/>
    <rect x="947" y="440" width="15" height="3" fill="white"/>
    <text x="975" y="450" font-family="Arial, sans-serif" font-size="12" fill="white">Bikes</text>
  </g>
  
  <!-- Technology Stack -->
  <g>
    <rect x="50" y="500" width="800" height="120" rx="10" fill="#F1F5F9" stroke="#E2E8F0" stroke-width="2"/>
    <text x="450" y="525" text-anchor="middle" font-family="Arial, sans-serif" font-size="18" font-weight="bold" fill="#1E293B">
      Technology Stack
    </text>
    
    <!-- Tech items -->
    <g>
      <!-- Python -->
      <rect x="80" y="545" width="80" height="30" rx="5" fill="#3776AB"/>
      <text x="120" y="565" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">Python</text>
      
      <!-- PyTorch -->
      <rect x="180" y="545" width="80" height="30" rx="5" fill="#EE4C2C"/>
      <text x="220" y="565" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">PyTorch</text>
      
      <!-- OpenCV -->
      <rect x="280" y="545" width="80" height="30" rx="5" fill="#5C3EE8"/>
      <text x="320" y="565" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">OpenCV</text>
      
      <!-- Ultralytics -->
      <rect x="380" y="545" width="80" height="30" rx="5" fill="#00D4FF"/>
      <text x="420" y="565" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">Ultralytics</text>
      
      <!-- NumPy -->
      <rect x="480" y="545" width="80" height="30" rx="5" fill="#013243"/>
      <text x="520" y="565" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">NumPy</text>
      
      <!-- YOLOv10 -->
      <rect x="580" y="545" width="80" height="30" rx="5" fill="#FF6B35"/>
      <text x="620" y="565" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" fill="white">YOLOv10</text>
    </g>
    
    <!-- Performance Metrics -->
    <text x="450" y="600" text-anchor="middle" font-family="Arial, sans-serif" font-size="14" font-weight="bold" fill="#374151">
      Key Features: Real-time Detection • Multi-class Classification • High Accuracy • Video Processing
    </text>
  </g>
  
  <!-- Data Flow Indicators -->
  <g>
    <text x="150" y="110" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" font-weight="bold" fill="#4F46E5">
      INPUT
    </text>
    <text x="430" y="110" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" font-weight="bold" fill="#059669">
      PROCESS
    </text>
    <text x="720" y="90" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" font-weight="bold" fill="#1E293B">
      AI MODEL
    </text>
    <text x="1010" y="110" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" font-weight="bold" fill="#059669">
      PROCESS
    </text>
    <text x="1010" y="320" text-anchor="middle" font-family="Arial, sans-serif" font-size="12" font-weight="bold" fill="#DC2626">
      OUTPUT
    </text>
  </g>
  
  <!-- Arrow marker definition -->
  <defs>
    <marker id="arrowhead" markerWidth="10" markerHeight="7" refX="9" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="#64748B"/>
    </marker>
  </defs>
  
  <!-- Feedback loop arrow -->
  <path d="M 150 470 Q 50 400 150 330 Q 250 400 350 330" stroke="#9CA3AF" stroke-width="2" fill="none" stroke-dasharray="5,5"/>
  <text x="200" y="395" text-anchor="middle" font-family="Arial, sans-serif" font-size="10" fill="#6B7280">
    Continuous Processing Loop
  </text>
</svg>

link to the actual youtube video : https://youtu.be/CftLBPI1Ga4?si=1n2yP3NUSxlmZj04

## RESULTS
### Video Result  
![Object Detection in Action](https://github.com/Torajabu/YOLOv10-Object-cars-persons-and-bikes-Detection---Python/blob/main/result_compressed.gif)  

### Image Result  
![YOLOv10 Detection Result](https://github.com/Torajabu/YOLOv10-Object-cars-persons-and-bikes-Detection---Python/blob/main/image%20%20object%20dection%20result.jpg)


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
   

    git clone https://github.com/Torajabu/YOLOv10-Object-cars-persons-and-bikes-Detection---Python.git

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

