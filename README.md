Here’s an updated **README.md** for your Sign Language Detection project. It walks through the purpose, setup, code structure, and how to build and run the system step-by-step:

---

```markdown
# 🤟 Sign Language Detection using MediaPipe, OpenCV & LSTM

This project aims to detect and interpret hand gestures (alphabets and digits) from live webcam input using MediaPipe for hand tracking and an LSTM neural network for classification. It translates sign language into readable text in real-time.

## 🚀 Features
- Real-time hand gesture recognition via webcam
- Uses **MediaPipe** for precise hand landmark detection
- LSTM-based model trained on custom gesture data
- Supports alphabets (A–Z) and numbers (0–9)
- Translates gestures into text with confidence score

---

## 🛠️ Tech Stack

| Purpose                | Tool/Library            |
|------------------------|-------------------------|
| Hand Tracking          | [MediaPipe](https://mediapipe.dev) |
| Image Processing       | OpenCV                  |
| Deep Learning Model    | Keras (LSTM)            |
| Data Handling          | NumPy                   |
| Visualization          | TensorBoard (optional)  |

---

## 📂 Project Structure

```

.
├── MP\_Data/                  # Stores .npy extracted features
├── Image/                   # Collected images for each gesture
├── function.py              # Utility functions (hand detection, landmarks, etc.)
├── collect\_images.py        # Script to collect training data
├── extract\_keypoints.py     # Extracts hand landmarks into .npy
├── train\_model.py           # LSTM model training script
├── real\_time\_detection.py   # Real-time gesture recognition
├── model.json / model.h5    # Trained model structure and weights
└── README.md                # You're here!

````

---

## 📦 Installation

```bash
git clone https://github.com/NabhyaIoT2026/Sign-Language-2.git
cd Sign-Language-2
pip install -r requirements.txt
````

**Required Libraries:**

```bash
pip install opencv-python mediapipe tensorflow numpy
```

---

## 📸 Step 1: Collect Gesture Images

Capture images for each gesture using your webcam:

```bash
python collect_images.py
```

📌 *Press keys like `a`, `b`, `1`, `2` etc. to save gestures for each label. Images will be saved under `Image/` directory.*

---

## 📌 Step 2: Extract Keypoints

Use MediaPipe to extract 21 hand landmark keypoints from collected frames and save them as `.npy` files:

```bash
python extract_keypoints.py
```

---

## 🧠 Step 3: Train the LSTM Model

Train an LSTM model using saved `.npy` keypoints data:

```bash
python train_model.py
```

✅ This will:

* Load data from `MP_Data/`
* Train a 3-layer LSTM model
* Save `model.json` and `model.h5` after training

Use TensorBoard (optional):

```bash
tensorboard --logdir=Logs
```

---

## 🎯 Step 4: Run Real-Time Detection

Use your webcam for real-time sign detection:

```bash
python real_time_detection.py
```

💬 The predicted sign and its confidence will appear on top of the screen.

---

## 🧪 Dataset Info

| Class Type | Count                                            |
| ---------- | ------------------------------------------------ |
| Alphabets  | A-Z (custom)                                     |
| Numbers    | 0–9 (custom)                                     |
| Sequences  | 30 per class                                     |
| Frames     | 30 per sequence                                  |
| Shape      | `(30, 63)` (30 frames × 21 landmarks × 3 coords) |

---

## 📝 To Add New Gestures

1. Update `actions = np.array([...])` with new gestures.
2. Re-run `collect_images.py`, `extract_keypoints.py`, and `train_model.py`.

---

## 🙋‍♂️ Author

**Nabhya Sharma**
[GitHub](https://github.com/NabhyaIoT2026)

---

## 📃 License

MIT License – feel free to use and modify!

---

## 🔗 Project Link

👉 [GitHub Repository](https://github.com/NabhyaIoT2026/Sign-Language-2)

```

---

Would you like this auto-converted into a `README.md` file and ready to upload to your repo?
```

