# 🎭 Emotion-Based Style Transfer with CNNs 🎨

## 📌 Overview  
This project integrates **emotion recognition** with **neural style transfer** to dynamically apply artistic styles based on the emotional context of images. It uses a **21-layer CNN** for emotion classification and a neural style transfer model to generate **emotionally enriched** stylized images.

## 🚀 Features  
✅ **Emotion Classification:** A deep **21-layer CNN** trained on the **ExpW dataset** to classify emotions into seven categories.  
✅ **Neural Style Transfer:** A deep residual CNN that applies artistic styles based on detected emotions.  
✅ **Emotion-Driven Styling:** Each detected emotion maps to a specific artistic style, dynamically transforming images.  
✅ **PyTorch & TensorFlow Integration:** Built with **PyTorch** for style transfer and **TensorFlow** for emotion recognition.  

## 🖼️ System Architecture  
1. **Emotion Recognition Model:**  
   - Inputs an image and predicts one of **7 emotions** (`happy`, `sad`, `fear`, `neutral`, `surprise`, `disgust`, `angry`).  
   - Uses **CNN-based classification** with dropout, batch normalization, and fully connected layers.  
2. **Style Transfer Model:**  
   - Applies **Neural Style Transfer (NST)** based on the detected emotion.  
   - Uses **VGG16-based perceptual loss** for enhanced stylization.  

## 📊 Dataset  
- **Expression in-the-Wild (ExpW) dataset** with **91,793 labeled facial images**.  
- Emotion classes: `angry`, `disgust`, `fear`, `happy`, `sad`, `surprise`, `neutral`.  
- **Data Augmentation** applied to balance class distribution.  

## 🔧 Installation & Setup  

### **1️⃣ Install Dependencies**  
```bash
pip install torch torchvision tensorflow numpy matplotlib opencv-python
```

### **2️⃣ Clone the Repository
```bash
git clone https://github.com/yourusername/emotion-style-transfer.git
cd emotion-style-transfer
```

### **3️⃣ Run Emotion Classification
```bash
python emotion_classifier.py --image path/to/image.jpg
```

### **4️⃣ Run Style Transfer
```bash
python style_transfer.py --content path/to/image.jpg --emotion happy
```

## 📝 Results  
### 🎭 Emotion Classification Accuracy  
- **Training:** 96.53%  
- **Validation:** 79.34%  
- **Test:** 77.51%  

### 🎨 Style Transfer Performance  
- Uses **VGG16 perceptual loss** (`relu2_2`) for the most visually stable results.  
- Styles trained for each emotion on artistic images inspired by **Van Gogh, Munch, and DALL·E-generated styles**.  

---

## 🖥️ Implementation Details  
- **Emotion Classifier:** 21-layer CNN with **convolutional, pooling, batch normalization, and dropout layers**.  
- **Style Transfer:** Deep residual CNN with **instance normalization** and **perceptual loss** (content + style loss).  
- **Training:**  
  - **Emotion classifier:** 50 epochs, Adam optimizer, learning rate **0.001**.  
  - **Style transfer:** 5 epochs per style due to computational limits (**ideal: 50-100 epochs**).  
- **Hardware Used:** **NVIDIA Tesla P100 GPU** for training.  

---

## 🎯 Future Work  
🔹 Expand to **multi-style transfer** instead of one style per emotion.  
🔹 Improve **emotion classification accuracy** by incorporating **attention mechanisms**.  
🔹 Optimize **style selection** for better **texture transfer**, beyond color matching.  

---

## 👨‍💻 Authors  
- **Rahul Saxena** *(University of Massachusetts Amherst)*  
- **Dishant Padalia** *(University of Massachusetts Amherst)*  
