# 🍃 AI-Based Tea Leaf Disease Detection System

An AI-powered computer vision system to detect and classify tea leaf diseases using the YOLOv8 object detection model. Built to assist farmers in real-time identification and management of crop diseases, improving agricultural productivity and reducing manual diagnosis efforts.

## 📌 Features

- 🔍 Accurate detection and classification of common tea leaf diseases
- 🤖 YOLOv8-based deep learning model for object detection
- 🖼️ Trained on a custom dataset of 6,000+ annotated images (augmented to 26,000+)
- 📊 Performance evaluated using precision, recall, and mAP metrics
- 💡 Real-world application for automated agricultural diagnosis

## 🚀 Tech Stack

- **Deep Learning:** YOLOv8, Ultralytics
- **Languages:** Python
- **Libraries:** OpenCV, NumPy, Pandas, Matplotlib
- **Frameworks:** PyTorch, Ultralytics
- **Tools:** LabelImg (for annotation), Roboflow (for augmentation/export)

## 🧠 Model Architecture

The project uses **YOLOv8n**, the lightweight variant of the YOLOv8 object detection model, ideal for deployment on edge devices or in real-time applications.

Key components:
- Backbone: CSPDarknet
- Neck: PANet
- Head: YOLO Layer
- Anchor-free detection
- Trained for 100+ epochs with custom augmentations

## 📁 Dataset

- Source: Kaggle + custom annotated images
- Classes:
  - Healthy Leaf
  - Algal Leaf Spot
  - Red Rust
  - Tea Mosquito Bug Damage
- Total images: ~26,000 (after augmentation)
- Split: Train (80%), Validation (10%), Test (10%)

## 📊 Results

| Metric      | Value     |
|-------------|-----------|
| mAP@0.5     | 98.4%     |
| Precision   | 97.9%     |
| Recall      | 96.7%     |

Visualization samples and confusion matrices are included in the `results/` folder.

## 📸 Sample Predictions

<p align="center">
  <img src="results/sample1.jpg" width="45%" />
  <img src="results/sample2.jpg" width="45%" />
</p>

## ⚙️ How to Run

1. **Clone the Repository**
   ```bash
   git clone https://github.com/chethancodes-03/AI-Based-Tea-Leaf-Disease-Detection-System-.git
   cd AI-Based-Tea-Leaf-Disease-Detection-System-
2. **Install Dependencies**
   ```bash
    pip install -r requirements.txt
3. **Train the Model**
   ```bash
    yolo task=detect mode=train model=yolov8n.pt data=tea_leaf.yaml epochs=100 imgsz=640
4. **Run Inference**
   ```bash
   yolo task=detect mode=predict model=runs/detect/train/weights/best.pt source=sample_images/

#🧪 Evaluation
**After training, evaluate model performance:**
```bash
yolo task=detect mode=val model=runs/detect/train/weights/best.pt data=tea_leaf.yaml

## 📦 Folder Structure

├── data/ # Training images & annotations
├── runs/ # YOLO training results
├── sample_images/ # Images for testing
├── results/ # Prediction results & plots
├── tea_leaf.yaml # Dataset configuration
├── requirements.txt
└── README.md

## 🔮 Future Improvements

- Integrate a lightweight web dashboard for uploading and scanning images  
- Deploy on edge devices (Jetson Nano / Raspberry Pi)  
- Expand dataset with more disease classes and region-specific data  
