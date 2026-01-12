## Facial Recognition and Attendance System

### Project Overview

This is a **project** that shows how to use computer vision and facial recognition to build a simple, real-time attendance system.

The app:
- Uses your **webcam** to capture faces in real-time
- Recognizes people from a small folder of **known images**
- Writes their **name and time** into an `Attendance.csv` file

### What is this project?

A small, self-contained Python project that demonstrates:
- Loading and encoding known faces from images
- Capturing frames from a webcam with OpenCV
- Matching live faces against known encodings
- Logging recognized names and timestamps to a CSV file

---

## Tech Stack

- **Language**
  - Python

- **Libraries**
  - `opencv-python` (`cv2`) – webcam access and image processing  
  - `face_recognition` – face detection and encoding  
  - `dlib` – underlying face recognition/ML library  
  - `numpy` – array operations  

- **Other**
  - CSV file for storing attendance (`Attendance.csv`)  
  - Image folders for known faces (`ImagesAttendance`) and tests (`ImagesBasic`)

---

## How it Works (High Level)

1. **Load known faces**  
   The script looks inside the `ImagesAttendance` folder, loads each image, and creates a face encoding for each person.  
   The file name (e.g. `elon musk.webp`) is used as the person’s name (`ELON MUSK`).

2. **Start webcam**  
   The app opens your webcam and reads frames in a loop.

3. **Detect and recognize faces**  
   For each frame, it:
   - Detects any faces
   - Encodes them
   - Compares them with the known encodings
   - Finds the best match (if any)

4. **Draw box and name + mark attendance**  
   - Draws a green rectangle around the recognized face  
   - Puts the person’s name above the box  
   - Writes `NAME,TIME` into `Attendance.csv` (once per person per run)

---
