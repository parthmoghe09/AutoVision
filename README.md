# AutoVision
Smart Drive Assistance Mobile App : Real-time driver monitoring and safety enhancement
# AutoVisionAI – Intelligent Driver Assistance & Dashcam System

## Overview

AutoVisionAI is an Android-based intelligent driver assistance and dashcam system designed to enhance road safety through real-time computer vision, sensor-based driving analysis, and audio alerts. The application combines object detection, lane detection, driver behavior analysis, and trip logging into a single mobile platform optimized for real-world driving conditions, particularly Indian roads.

The system functions as a smart dashcam that not only records driving footage but also actively analyzes the driving environment and driver behavior, providing live feedback and post-journey insights.

This project was developed as a final submission for **CS50x**, demonstrating applied computer vision, mobile systems programming, and real-time data processing.

---

## Key Features

### Real-Time Object Detection
- Uses **YOLOv8** (TensorFlow Lite) for on-device object detection
- Detects vehicles, pedestrians, traffic signs, and road obstacles
- Optimized for mobile inference using CPU and NNAPI delegates
- Runs entirely offline after model deployment

### Lane Detection & Road Awareness
- OpenCV-based lane detection pipeline
- Detects lane boundaries and overlays them on the camera preview
- Helps visualize road alignment and vehicle positioning
- Designed to work under variable lighting and traffic conditions

### Driving Behavior Analysis
The application continuously analyzes driving patterns using sensor data:
- Speed monitoring
- Sudden braking detection
- Sharp turn detection
- Acceleration and deceleration trends

These parameters are used to compute a **real-time driving score**, providing feedback on driving safety and smoothness.

### Text-to-Speech Alerts
- Voice alerts for unsafe driving events
- Alerts include:
  - High speed warnings
  - Harsh braking
  - Sharp turns
- Uses Android Text-to-Speech for low-latency audio feedback
- Ensures alerts are non-repetitive and context-aware

### Dashcam with Loop Recording
- Continuous dashcam recording using CameraX
- Implements a **loop-buffer mechanism**
- Automatically overwrites old footage to conserve storage
- Critical events can be preserved for later review

### Trip Logging & Journey History
- Each drive session is logged locally
- Stores:
  - Duration
  - Driving score
  - Event counts
  - Timestamped trip data
- Users can review past journeys through the Journey History interface

### Pre-Drive Safety Checklist
- Ensures camera permissions and system readiness
- Mimics real-world vehicle startup checks
- Prevents accidental driving without active monitoring

---

## System Architecture

The application is modular and event-driven:

- **Camera Layer**  
  - CameraX for video capture and preview  
  - ImageAnalysis pipeline for frame processing  

- **Vision Layer**  
  - YOLOv8 object detector (TensorFlow Lite)  
  - OpenCV-based lane detection  

- **Sensor Layer**  
  - Accelerometer and gyroscope  
  - Speed estimation using location services  

- **Logic Layer**  
  - Driving score computation  
  - Event detection and alert handling  

- **UI Layer**  
  - Live camera overlay  
  - Alert icons  
  - Journey history viewer  

- **Persistence Layer**  
  - Local JSON-based trip storage  

---

## Testing & Evaluation

The system was tested using real-world driving footage collected on urban Indian roads. Testing scenarios included:
- Dense traffic
- Two-wheelers and pedestrians
- Sudden braking events
- Curved roads and intersections

The application maintained stable frame rates and accurate detections during extended driving sessions.

---

## Technologies Used

- **Language:** Kotlin
- **Platform:** Android
- **Computer Vision:** OpenCV
- **Machine Learning:** YOLOv8 (TensorFlow Lite)
- **Camera API:** CameraX
- **Audio:** Android Text-to-Speech
- **Concurrency:** Executors, Coroutines
- **Storage:** Local file system (JSON)

---

## Limitations

- Lane detection accuracy may decrease in poorly marked roads
- Object detection depends on lighting and camera quality
- No cloud sync; all data is stored locally
- Designed for educational and research purposes, not commercial deployment

---

## Future Improvements

- Cloud-based trip analytics
- Emergency event auto-save
- Driver distraction detection
- Improved night-time performance
- GPS-based route visualization

---

## Author

**Parth Moghe**  
CS50x Final Project  
Year: 2025

---

## License

This project is released for educational purposes as part of the CS50 curriculum.
