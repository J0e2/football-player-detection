# ⚽ Football Player Detection & Tracking — YOLOv11

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white) ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)
![Model](https://img.shields.io/badge/Model-YOLOv11-red?style=flat-square)
![Tracking](https://img.shields.io/badge/Tracking-ByteTrack-blue?style=flat-square)
![API](https://img.shields.io/badge/API-FastAPI-009688?style=flat-square)

> Real-time football player detection, multi-object tracking, and team classification — deployed as a **FastAPI REST API**.

---

## 📋 Overview

End-to-end computer vision pipeline for football analytics: detect players with YOLOv11, track them across frames with ByteTrack, and classify teams by jersey color using KMeans clustering.

## 🔧 Pipeline

```
Video Frame
     ↓
YOLOv11 Detection  (custom Roboflow dataset)
     ↓
ByteTrack          (persistent player IDs)
     ↓
KMeans on HSV      (team A / team B classification)
     ↓
FastAPI Response   (bounding boxes + team labels + track IDs)
```

## 📡 API

```bash
POST /detect
# Body: multipart/form-data — image frame (max 10MB)

# Response:
{
  "players": [
    {"id": 7, "bbox": [x,y,w,h], "team": "A", "confidence": 0.94},
    ...
  ]
}
```

## 📊 Metrics

- **MOTA** — Multi-Object Tracking Accuracy
- **MOTP** — Multi-Object Tracking Precision
- **IDF1** — Identity F1 Score

## 🚀 Run

```bash
pip install -r requirements.txt
jupyter notebook football_detection.ipynb
```

---

## 👤 Author

**Yousef Mohamed Yousef**
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/yousef--mohamed--/)
[![Kaggle](https://img.shields.io/badge/Kaggle-Profile-20BEFF?style=flat-square&logo=kaggle)](https://www.kaggle.com/yousefmohamedjoe)
[![GitHub](https://img.shields.io/badge/GitHub-J0e2-181717?style=flat-square&logo=github)](https://github.com/J0e2)

