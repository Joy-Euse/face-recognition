AI Without ML — Face Recognition Using MediaPipe & LBPH

This project implements a complete face-recognition pipeline without using machine learning training on deep neural networks.
Instead, it combines:

MediaPipe Face Detection → for locating face bounding boxes

LBPH (Local Binary Patterns Histograms) → for classical feature-based face recognition

This approach follows traditional AI techniques and demonstrates how detection + recognition can work without modern ML training.

📌 Project Features

✔ Real-time face detection using MediaPipe
✔ Classical LBPH face recognition
✔ Training on multiple users
✔ Predicts identity live using webcam
✔ Simple and lightweight — no GPU required

📂 Project Structure
project/
│
├── dataset/
│   ├── Person1/
│   ├── Person2/
│   ...
│
├── models/
│   ├── lbph_face_model.xml
│   ├── label_map.json
│
├── capture.py        # Capture images for training
├── train.py          # Train LBPH model
├── predict.py        # Real-time recognition
└── README.md

🔧 1. Installation
Requirements

Install required packages:

pip install opencv-python
pip install opencv-contrib-python
pip install mediapipe


Note:
opencv-contrib-python is required for LBPH face recognizer.

🎥 2. Step 1 — Capture Images

Run:

python capture.py


Then:

Enter the person's name (e.g., Joyeuse)

Look into the webcam

Images will be automatically saved under dataset/<person_name>/

Press Q to stop capturing

Capture images for at least two different people.

🧠 3. Step 2 — Train the LBPH Model

Run:

python train.py


This script:

Loads all images in dataset/

Assigns numeric labels to each person

Trains an LBPH face recognizer

Saves:

models/lbph_face_model.xml

models/label_map.json

You should see:

Training completed! Model saved.

👁️ 4. Step 3 — Real-Time Recognition

Run:

python predict.py


The script will:

Detect faces using MediaPipe

Crop the detected face

Predict identity using LBPH

Display name + confidence score on screen

Press Q to exit.

🎬 5. Video Demonstration Requirement

Your submission should include a 20–40 second video showing:

Two different people

MediaPipe detecting faces

LBPH recognizing each person correctly

🔗 6. Explanation of the Pipeline
🔍 Face Detection (MediaPipe)

MediaPipe performs lightweight face detection in real time.
It outputs:

Bounding box

Face landmarks

Confidence score

We use the bounding box to crop a clean face region.

🧠 Face Recognition (LBPH)

LBPH (Local Binary Pattern Histograms):

Converts the face into grayscale

Extracts texture patterns

Builds a histogram representation

Compares it to known faces

Outputs:

label (person ID)

confidence score

It works well with small datasets and is fast.

🎯 7. Tips for Best Accuracy

Capture 40–100 images per person

Ensure good lighting

Keep background as plain as possible

Capture different angles (left/right/center)

Avoid blurry images

👤 8. Author

Name: Joyeuse
Project: AI Without ML – Week 13
Institution: Rwanda Coding Academy