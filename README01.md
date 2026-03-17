# 📷 Face Recognition Attendance System

An interactive, browser-based facial recognition attendance system built using Python, OpenCV, and the `face_recognition` library. This project is specifically tailored to run seamlessly in **Google Colab** or Jupyter Notebook environments, utilizing JavaScript to access the local webcam directly from the browser.

## ✨ Features
* **Interactive UI**: Clean, button-driven dashboard built with `ipywidgets`.
* **In-Browser Webcam Access**: Uses JavaScript to securely capture photos without requiring local camera setup.
* **New User Registration**: Captures a user's face, extracts facial encodings, and stores them in a local SQLite database.
* **Automated Attendance Marking**: Recognizes registered faces and logs their attendance with a timestamp. Prevents duplicate attendance entries for the same day.
* **Database Logs**: Easily view the attendance history directly within the notebook using Pandas.

## 🛠️ Tech Stack
* **Language**: Python 3
* **Libraries**: `face_recognition`, `OpenCV` (cv2), `numpy`, `pandas`, `sqlite3`, `ipywidgets`
* **Environment**: Google Colab / Jupyter Notebook

## 🚀 How to Run

1. **Open in Google Colab**: Upload the `FacialRecognition.ipynb` file to your Google Drive and open it with Google Colab.
2. **Install Dependencies**: Run the first cell to install the required libraries (`face_recognition` and `ipywidgets`).
3. **Execute Core Logic**: Run the second cell to initialize the database (`attendance_system.db`) and load the core functions.
4. **Launch the UI**: Run the final cell to generate the interactive dashboard.
5. **Usage**:
   * Type a name into the text box and click **Capture & Register**. Allow browser camera permissions when prompted.
   * Click **Mark Attendance** to capture a new photo and verify it against the database.
   * Click **Refresh Logs** to view the current attendance table.

## 🗄️ Database Structure
The system uses a lightweight SQLite database (`attendance_system.db`) with two tables:
* `users`: Stores the user's `name` and their unique facial `encoding` (BLOB).
* `attendance`: Stores an auto-incrementing `id`, the recognized user's `name`, and the `time` (TIMESTAMP) of their attendance.

## ⚠️ Notes
* This notebook relies on `google.colab.output` to execute JavaScript for webcam access. If running locally outside of Colab, the `take_photo()` function will need to be refactored to use standard OpenCV webcam capture (`cv2.VideoCapture(0)`).
