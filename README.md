# CIFAR-10 Image Classification Hackathon

## Overview  
This project was developed as part of a one-day hackathon. The goal was to leverage **transfer learning** to classify images from a subset of the **CIFAR-10 dataset**.  
We used the **VGG16 pre-trained model** (on ImageNet) and fine-tuned it to classify 5 selected classes from CIFAR-10:  

- ✈️ Airplane  
- 🚗 Automobile  
- 🐦 Bird  
- 🐱 Cat  
- 🐶 Dog  

---

## Dataset 
- **CIFAR-10**: 60,000 32×32 color images in 10 classes.  
- **Subset Used**: 30,000 images from 5 classes.  
- **Train/Test Split**: 50,000 training images, 10,000 testing images.  
- **Preprocessing Steps**:  
  - Normalization (scaled pixels to [0,1])  
  - Label remapping for 5 classes  
  - Data augmentation (rotation, flips, shifts)  

---

## Model Architecture
- **Base Model**: VGG16 (pre-trained on ImageNet, with frozen layers).  
- **Custom Layers**:  
  - Global Average Pooling  
  - Dense (256 neurons, ReLU)  
  - Dropout (50% for regularization)  
  - Dense (5 neurons, Softmax for classification)  

- **Compilation**:  
  - Optimizer: Adam  
  - Loss: Categorical Crossentropy  
  - Metric: Accuracy  

---

## Training
- **Batch Size**: 64  
- **Epochs**: 5  
- **Validation Set**: Used for monitoring overfitting  
- **Data Augmentation**: Improved generalization with limited dataset  

---

## Results
- Achieved **high validation accuracy** (~80–85%).  
- Confusion matrix and classification report showed strong performance across most classes.  
- Some misclassifications observed between visually similar classes (e.g., Cat vs Dog).  

---

## Key Learnings 
- Transfer learning greatly reduced training time and improved performance.  
- Data augmentation was critical in preventing overfitting.  
- VGG16 performed well, but future improvements could include **ResNet** or **EfficientNet** for better accuracy.  


