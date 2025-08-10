"# Riceleaf" 
# Rice Leaf Disease Detection using CNN

## 1. Introduction
Rice is one of the most important staple foods in the world, but it is highly susceptible to various leaf diseases such as:
- **Bacterial Leaf Blight**
- **Brown Spot**
- **Leaf Smut**

These diseases significantly affect crop yield and quality. Early detection is critical for timely intervention. This project uses **Convolutional Neural Networks (CNN)** and **Transfer Learning (InceptionV3)** to classify rice leaf diseases from images.

---

## 2. Objectives
- Develop a CNN-based image classification model for detecting rice leaf diseases.
- Apply **Transfer Learning** for improved accuracy with limited data.
- Evaluate model performance using accuracy and loss metrics.
- Prepare a deployable model for mobile or web applications.

---

## 3. Dataset Description
-- Source: Provided dataset (120 JPG images, 40 images per class)
- Classes:
  - Leaf Smut
  - Brown Spot
  - Bacterial Leaf Blight
- Image Format: .jpg
- Structure: Images grouped into folders by class
- Train/Validation Split: 80% training, 20% validation

**Folder Structure**:
Data/
├── train/
│ ├── BacterialLeafBlight/
│ ├── BrownSpot/
│ └── LeafSmut/
└── test/
├── BacterialLeafBlight/
├── BrownSpot/
└── LeafSmut/

---

## 4. Methodology

### 4.1 Data Preprocessing
- Rescaling (1./255)
- Data augmentation (rotation, zoom, horizontal flip)
- Train/validation split

### 4.2 Model Architecture
- **Base Model:** InceptionV3 (TensorFlow Hub, pretrained on ImageNet)
- **Custom Layers:**
  - Flatten
  - Dense (512 units, ReLU)
  - Dropout (0.2)
  - Dense output layer (3 units, Softmax)

### 4.3 Compilation
- Loss: `categorical_crossentropy`
- Optimizer: `Adam` (learning rate = 0.001)
- Metrics: `accuracy`

### 4.4 Training
- Epochs: 30
- Batch Size: 16
- Environment: Google Colab / Local Machine

---

## 5. Results

**Final Metrics:**
- **Training Accuracy:** ~100%
- **Validation Accuracy:** ~75%
- **Training Loss:** Decreased steadily
- **Validation Loss:** Slight fluctuations

**Observations:**
- Accuracy improved rapidly in early epochs
- Slight overfitting after ~15 epochs

---

## 6. Challenges Faced
- Small dataset → risk of overfitting
- Class imbalance in some samples
- Limited validation images
- Hardware limitations

---

## 7. Solutions Implemented
- Applied **data augmentation**
- Used **Transfer Learning**
- Added **Dropout** & L2 regularization
- Reduced learning rate

---

## 8. Future Improvements
- Collect larger dataset
- Use advanced augmentation techniques
- Deploy as Android app or Web API
- Test lightweight models like MobileNetV2

---

## 9. Conclusion
Successfully built a CNN model with Transfer Learning (InceptionV3) to classify rice leaf diseases into three categories. Achieved **75% validation accuracy** despite small dataset, showing strong potential for agricultural applications.

---

## 10. References
- TensorFlow Hub: [https://tfhub.dev](https://tfhub.dev)
- Dataset sources: Kaggle & custom images
- IRRI Research Papers

---
