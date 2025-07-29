
# 🧠 Plant and Weed Segmentation using U-Net and ResNet50

This repository contains two approaches for performing semantic segmentation on plant and weed datasets:

1. `model_training.py`: A custom U-Net implementation in a standalone Python script.
2. `ResNet50.ipynb`: A Jupyter Notebook using ResNet50 (assumed) as backbone for segmentation.

---

## 📁 Project Structure

project/
├── model_training.py  
├── ResNet50.ipynb  
├── training_images/  
│   ├── image1.jpg  
│   ├── image1.png    <-- Ground truth mask  
│   └── ...  
└── temp/             <-- Created automatically to save models and plots

---
currently the images are not in the repository cause they are very heavy in load to push
## 🧪 1. Running `model_training.py`

### ✅ Step 1: Install Dependencies

```bash
pip install tensorflow tensorflow-addons numpy matplotlib pillow scikit-learn
```

### 📸 Step 2: Prepare Input Images

Place your images and corresponding masks inside the `training_images/` directory.

- Images must be `.jpg` or `.jpeg`
- Corresponding masks must be `.png`
- Both must have the same base filename  
  Example:  
  - `plant1.jpg`  
  - `plant1.png`

### 🚀 Step 3: Run the Script

```bash
python model_training.py
```

This will:
- Train a U-Net model with data augmentation
- Use a weighted cross-entropy loss
- Save the trained model and plots to the `temp/` folder
- Display predicted vs actual segmentation results

---

## 📓 2. Running `ResNet50.ipynb`

### 🧰 Step 1: Install Required Packages

```bash
pip install tensorflow keras numpy matplotlib scikit-learn pillow
```

### 🧾 Step 2: Launch Notebook

Open the notebook using one of the following:
- Jupyter Notebook
- Google Colab
- VSCode Jupyter Extension

### 🧠 What It Does

- Loads the same image-mask dataset
- Uses a ResNet50-based architecture (assumed)
- Trains the model and visualizes outputs

---

## 📝 Additional Notes

- The model assumes **multi-class segmentation** with `n_classes = 4`
- Make sure `.png` masks use proper class indices (0,1,2,...)
- Output files like trained models and accuracy/loss plots will be auto-saved in the `temp/` directory
- Script uses data augmentation techniques such as:
  - Random flipping
  - Hue shifting
  - Image shifting

---
