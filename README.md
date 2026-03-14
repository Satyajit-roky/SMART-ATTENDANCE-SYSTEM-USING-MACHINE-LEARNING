# SMART ATTENDANCE SYSTEM USING MACHINE LEARNING

A Python-based face recognition attendance system using OpenCV, KNN, and a simple GUI.

This project captures face images, trains a KNN model, and logs attendance into a CSV file every time a recognized person presses **`O`**.

---

## ✅ Features

- Real-time face detection with OpenCV
- Face recognition using K-Nearest Neighbors (KNN)
- Attendance logging to `Attendance/Attendance_<DATE>.csv`
- Optional voice feedback (Windows TTS)
- Streamlit dashboard to view attendance (via `app.py`)

---

## 🧰 Requirements

- Python 3.8+
- Webcam

Install required Python packages:

```bash
pip install -r requirements.txt
```

> If `requirements.txt` is not present, install core dependencies:
>
> ```bash
> pip install opencv-python numpy scikit-learn pywin32 streamlit streamlit-autorefresh pandas
> ```

---

## 📂 Project Structure

```
SMART-ATTENDACE-SYSTEM-USING-MACHINE-LEARNING-main/
├── app.py                  # Streamlit attendance dashboard
├── test.py                 # Run live face recognition + attendance logging
├── background.jpg          # Optional UI background image
├── data/                   # Face data + models + Haarcascade
│   ├── add_faces.py        # Script to capture faces & build training data
│   ├── faces_data.pkl      # Saved face vectors
│   ├── names.pkl           # Labels for each face sample
│   └── haarcascade_frontalface_default.xml
├── Attendance/             # Generated CSV attendance logs
└── README.md
```

---

## ▶️ How to Use

### 1) Add a new user (capture faces)

```bash
python data/add_faces.py
```

Follow the prompt to enter your name and look at the camera until it collects ~100 samples.

### 2) Run the attendance tracker

```bash
python test.py
```

- Press **`O`** to mark attendance for any recognized face
- Press **`Q`** to quit

### 3) View attendance (Streamlit dashboard)

```bash
streamlit run app.py
```

---

## 📝 Notes

- Attendance logs are stored per day in `Attendance/Attendance_<DATE>.csv`.
- If you run into issues with the webcam or model data, delete `data/faces_data.pkl` and `data/names.pkl` and re-run `data/add_faces.py`.

---

## ⭐ License

This project is released under the MIT License.
