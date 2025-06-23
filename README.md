# Re_identification_in_a_Single_Feed\

# ⚽ Player Re-Identification in a Single Video Feed

This project performs **player re-identification** in a football match video using a single camera feed. Each player is assigned a unique ID that remains consistent even when the player leaves and re-enters the frame.

---

## 📌 Objective

To detect and track players in a 15-second video using:

- YOLOv11 (custom trained model)
- Deep SORT tracker

---

## 🎯 Approach and Methodology

1. **Detection**:
   - Used a fine-tuned YOLOv11 model (`best.pt`) to detect players, referees, and the ball.

2. **Tracking**:
   - Used the Deep SORT algorithm to track each player across frames.
   - Maintained the same ID for players who temporarily leave and reappear in the video.

---

## 🗂️ Project Structure

| File                  | Description                                 |
|-----------------------|---------------------------------------------|
| `main.py`             | Main Python script to run the tracking      |
| `15sec_input_720p.mp4`| Input video clip                            |
| `best.pt`             | YOLOv11 model for detection *(not in repo)* |
| `README.md`           | Project overview and instructions           |
| `requirements.txt`    | Python dependencies                         |
| `player_reid_report.pdf` | Brief project report                    |

---

## 🚀 How to Run

### 1. 🔧 Install Requirements

```bash
pip install -r requirements.txt
````

### 2. 💾 Download YOLOv11 Model

Since `best.pt` exceeds GitHub's upload size, download it from Google Drive:

👉 [Download best.pt](https://drive.google.com/file/d/1-5fOSHOSB9UXyP_enOoZNAMScrePVcMD/view)

> After downloading, place it in the same folder as `main.py`.

### 3. ▶️ Run the Tracker

```bash
python main.py
```

* A video window will open showing players with bounding boxes and consistent IDs.
* Press `Q` to exit.

---

## 📽️ Example Output

Each player will have a green bounding box with a label like:

```
ID: 1
ID: 2
```

These IDs stay the same even if a player disappears and comes back.

---

## 📦 Dependencies

Installed via `requirements.txt`:

* ultralytics
* opencv-python
* deep\_sort\_realtime
* numpy
* torch

---

## ✅ Status

* [x] Player detection using YOLOv11
* [x] Re-identification using Deep SORT
* [x] Tracks consistent player IDs
* [x] OpenCV visualization working

---
