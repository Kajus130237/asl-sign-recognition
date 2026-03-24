# ASL Sign Language Recognition

Real-time American Sign Language (ASL) alphabet recognition using computer vision and machine learning.  
Built during **Erasmus exchange studies** at the University of Aveiro, Portugal.

---

## 📌 Project Overview

This project recognizes **28 ASL hand signs** (A–Z + `space` + `del`) in real time using a webcam.  
Two models were trained and compared:

| Model | Approach | Input |
|-------|----------|-------|
| **Model 1 — SVM** | Support Vector Machine via scikit-learn Pipeline | MediaPipe 63 keypoint features |
| **Model 2 — RNN** | Recurrent Neural Network | Sequential hand landmark data |

A real-time inference script uses the trained SVM model with **prediction smoothing** (majority vote over a sliding window) to reduce flickering.

---

## Technologies

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0097A7?style=flat&logo=google&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)

- **MediaPipe Hands** — hand landmark detection (21 keypoints → 63 features)
- **scikit-learn** — SVM classifier with Pipeline
- **OpenCV** — webcam capture and real-time display
- **TensorFlow / Keras** — RNN model training
- **joblib** — model serialization

---

## How to Run

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/asl-sign-recognition.git
cd asl-sign-recognition
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run real-time recognition
Open `Project2_model1_real_time.ipynb` in Jupyter and run all cells.  
Make sure your webcam is connected. Press **`q`** to quit.

---

## How It Works

1. Webcam captures each frame in real time
2. **MediaPipe Hands** detects 21 hand landmarks (x, y, z) → 63 features
3. Features are passed to the trained **SVM Pipeline**
4. Prediction is smoothed using a **majority vote** over the last 7 frames
5. The predicted letter is displayed on screen with confidence margin

---

## 👤 Author

**Kajus Misevičius, Rusnė Andrulevičiūtė**  
VILNIUS TECH — Artificial Intelligence Systems (BSc, Year 3)  
Erasmus @ University of Aveiro, Portugal (2025–2026)  
