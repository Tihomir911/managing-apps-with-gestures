# managing-apps-with-gestures
AI Camera Studio is a powerful desktop application that uses your webcam to track hands and face, recognize emotions, and let you control applications or websites using finger gestures. Assign actions to 10 different fingers, place them in the red zone, and watch the magic happen!

✨ Features
Real‑time hand & face tracking powered by MediaPipe

Emotion recognition – detects happy, sad, angry, neutral

10 uniquely colored fingertips (left hand 1–5, right hand 6–10) with numbers displayed

Red zone – a transparent rectangle at the top of the video; when a finger enters it, it launches any application or website you have assigned

Multiple‑finger activation – each new finger entering the zone triggers its own action

Customizable assignments – open .exe files, shortcuts, or URLs in your preferred browser

Settings are saved encrypted in settings.pkl

Modern dark UI with tile‑based emotion display

🖼️ Screenshots
(You can add screenshots here)

🚀 How to Use (End User)
Download the latest release archive:
ai_camera_studio.zip – contains the compiled executable.

Extract the archive anywhere on your computer.

Inside the extracted folder you will find:

ai_camera_studio.exe – the main program

emotions/ – folder with emotion images (agli.png, happe.png, natur.png, tired.png)

Double‑click ai_camera_studio.exe to run the application.

Make sure your webcam is connected and working.

Point your fingers at the red zone to test the actions (you can assign them via the ⚙ button).

Important: The emotions folder must always stay in the same directory as the .exe.

🛠️ Building from Source
If you prefer to run from source or modify the code, use the source archive:
camera_manager.zip – contains the Python code.

Prerequisites
Python 3.11 (other versions may cause compatibility issues with MediaPipe)

A webcam

Setup
Extract camera_manager.zip.

Open a terminal in the extracted folder.

Create and activate a virtual environment:

bash
python -m venv venv
.\venv\Scripts\activate   # on Windows
Install dependencies:

bash
pip install opencv-python numpy Pillow mediapipe
Run the application:

bash
python ai_camera_studio.py
Dependencies
Library	Version (tested)
opencv‑python	4.9.0.80
numpy	1.26.4
Pillow	10.1.0
mediapipe	0.10.9
All are listed in requirements.txt.

📁 Project Structure
text
ai_camera_studio/
├── ai_camera_studio.py          # main application
├── emotions/                     # emotion images
│   ├── agli.png
│   ├── happe.png
│   ├── natur.png
│   └── tired.png
├── settings.pkl                  # saved finger actions (created on first use)
└── requirements.txt              # for building from source
📝 How to Assign Actions
Click the ⚙ button in the main window.

For each finger (1–10) you can:

Enter a file path (e.g. C:\Program Files\Steam\steam.exe) or a URL (e.g. https://youtube.com).

Select a browser (if it’s a URL).

Press 💾 Save – the assignment is stored immediately.

Now when that finger enters the red zone, the action will be performed.

🐞 Troubleshooting
Camera not detected? Make sure no other application is using it. Try changing the camera index in the code (cv2.VideoCapture(0) → 1).

Fingers not recognised? Good lighting and a plain background help. Adjust confidence thresholds in HandFaceTracker.__init__ if needed.

Exe shows “The path does not exist”? The mediapipe folder wasn’t included. Use the pre‑built release archive which already contains it, or rebuild with --collect-all mediapipe.
