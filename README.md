# 🪖 Helmet Detection using YOLOv11  

## 📌 Project Overview  
This project demonstrates a real-time helmet detection system using **YOLOv11**, implemented on **Google Colab**.  
The goal is to detect whether bike riders are wearing helmets or not, which can help improve:  
- ✅ Road safety  
- ✅ Traffic surveillance  
- ✅ Law enforcement automation  

The model is trained on a **custom dataset of bike riders** with and without helmets and tested for **real-time inference**.  

---

## 🛠️ Tech Stack  
- **Python**  
- **YOLOv11 (Ultralytics)**  
- **OpenCV**  
- **Google Colab** (for training & testing)  
- **GitHub** (for project storage & version control)  

---

## 📊 Dataset  
The dataset used in this project is publicly available on **Roboflow Universe**.  
🔗 [Helmet Detection Dataset](https://universe.roboflow.com/jayz-workspace/helmet-detector-9rzmg)  

### 📌 Dataset Classes (13 total)  
- Cycling Helmet  
- Half Face  
- Hard Hat  
- Helmet  
- Modular Helmet  
- Motorbike  
- Motorcyclist  
- No Helmet  
- Nutshell  
- Person  
- Plate (Number Plate)  
- Quarter Face Helmet  
- Sports Helmet  

---

## 🚀 Usage

After cloning the repository, open the project in **Google Colab** and run the following commands step by step:

```bash
# Step 1: Clone the repository
git clone https://github.com/Ujjwal007-walle/Helmet-Detection.git
cd Helmet-Detection

# Step 2: Install YOLOv11
pip install ultralytics==8.0.196

# Step 3: Verify installation
yolo --version

# Step 4: Train the model (Helmet Detection Dataset from Roboflow)
yolo detect train data="https://universe.roboflow.com/jayz-workspace/helmet-detector-9rzmg/dataset.yaml" \
    model=yolov11n.pt epochs=50 imgsz=640 batch=16 name=helmet-detection

# Step 5: Validate the model
yolo detect val model=runs/detect/helmet-detection/weights/best.pt data="https://universe.roboflow.com/jayz-workspace/helmet-detector-9rzmg/dataset.yaml"

# Step 6: Run inference on test images
yolo detect predict model=runs/detect/helmet-detection/weights/best.pt source="test_images/"

   

   
