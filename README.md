Raspberry Pi 5 Face Recognition Setup Guide:

This document outlines the full workflow for setting up a virtual environment, installing dependencies, capturing images, training encodings, and running real‑time face recognition using Camera Module 3 on a Raspberry Pi 5.
Create a Python Virtual Environment

Use a virtual environment so all Python packages stay isolated and avoid conflicts with system packages.

python3 -m venv ~/face_rec --system-site-packages

The --system-site-packages flag allows the environment to use system-installed libraries like NumPy.

Activate the Virtual Environment
source ~/face_rec/bin/activate
Once activated, all Python commands will use the venv.

Install Required Python Packages:
Install the face recognition library and helper utilities.
pip install face_recognition imutils
If OpenCV is needed and not available, install:
sudo apt install python3-opencv

Download the source code and run below commands.
Capture Training Images
Use the provided script to capture face images.
python image_capture.py
Images should be stored in your dataset folder.

Train Face Encodings
Run the training script to generate encodings.pickle inside the virtual environment.
python model_training.py
This creates the encoding file compatible with the venv.

Run Real-Time Facial Recognition
Start the recognition script.
python facial_recognition.py
The script will:
Initialize the Raspberry Pi Camera Module 3
Detect faces
Compare them with trained encodings
Display results with bounding boxes and names
