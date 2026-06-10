# 🚗 Real-Time Driver Behavior Detection System using YOLOv10

This repository contains the source code and configuration for a Real-Time Driver Behavior Detection System. Built on the state-of-the-art **YOLOv10** architecture, this system monitors and detects driver anomalies such as driver fatigue and unauthorized mobile phone use to ensure road safety.

---

## 📁 Repository Structure
* `yolov10/` - Core YOLOv10 architecture and source files.
* `Driver Behavior.ipynb` - Core Jupyter Notebook used for model training, evaluation, and inference.
* `dataset.yaml` - Configuration file defining dataset paths and classes (`Drowsiness`, `Natural`, `Yawn`, `PhoneUse`).
* `requirements.txt` - Python dependencies required to run the project.

---

## 📊 Dataset & Trained Model Weights

Due to GitHub's file size limits (100MB), the large dataset (~9GB) and the final trained weights are safely hosted externally on Hugging Face:

* **📦 Download Dataset:** [Hugging Face Dataset Link](https://huggingface.co/datasets/Manuka0329/driver-behavior-dataset/tree/main)
* **🧠 Download Trained Weights (runs):** [Hugging Face Model Link](https://huggingface.co/Manuka0329/driver-behavior-yolov10/tree/main)

---

## 🚀 Getting Started & Installation

Follow these steps to set up and run the project locally on your machine:

### 1. Clone the Repository
```bash
git clone https://github.com/ManukaAbeysekara2004/Driver_Behavior_Detection_AI.git
```

### 2. Setup the Virtual Environment
* It is highly recommended to use Python **3.10** or **3.11** for this project to avoid package version conflicts.
* Create a virtual environment to isolate the project dependencies:
```bash
# Go inside the Driver_Behavior_Detection_AI folder 
cd Driver_Behavior_Detection_AI

# On Windows (If you have multiple Python versions installed):
.py -3.10 -m venv venv

# On Mac/Linux (Or alternative Windows setup):
python3.10 -m venv venv

# Activate the virtual environment
# On Windows (PowerShell):
.\venv\Scripts\Activate.ps1

# On Windows (CMD):
.\venv\Scripts\activate.bat

# On macOS/Linux:
source venv/bin/activate
```

### 3. Setup the Environment & Dependencies
* Once your virtual environment is ***activated***, install all the required libraries using the requirements.txt file:

``` Bash
pip install -r requirements.txt
```

### 3. Place Dataset and Weights
* Download Dataset: [Link](https://huggingface.co/datasets/Manuka0329/driver-behavior-dataset/tree/main)
   - Download the dataset from Hugging Face.
   - Extract it and place it in the root directory under the folder name `dataset/`.

*  Download Trained Weights (runs): [Link](https://huggingface.co/Manuka0329/driver-behavior-yolov10/tree/main)
   - Download the trained weights (runs) from Hugging Face.
   - Extract it and place it in the root directory under the folder name `runs/`.

### 4. Run the Driver Detection System
* Open the Driver Behavior.ipynb notebook using Jupyter Lab/Notebook or VS Code, and run the cells to start the training or real-time camera inference.

---

## 🧠 Jupyter Notebook Workflow & Execution Guide

If you open the `Driver Behavior.ipynb` notebook, you will see the development pipeline structured in the following order:

1. **Install yolov10 and Import Dependencies** - Setting up the environment.
2. **Load Model** - Loading the base pre-trained YOLOv10 model.
3. **YOLOv10 Model Testing on Sample Image** - Verifying the base model installation.
4. **Real Time Detections** - Preliminary real-time camera testing.
5. **Draw bounding using labelImg** - Dataset labeling and preprocessing.
6. **Train model** - Training the custom driver behavior model on the dataset.
7. **Load Trained Model** - Loading the final trained weights (`best.pt`).
8. **Evaluate** - Performance evaluation metrics (Confusion Matrix, Loss graphs, etc.).
9. **Test trained model using pictures** - Testing the final model on static evaluation images.
10. **Test trained model using camera** - Running the final real-time driver detection system.

> 💡 **Quick Run Note for Users:** If you have already downloaded our pre-trained model weights (`runs`) from Hugging Face and placed them in the root directory, you do not need to retrain the model from scratch. You can **skip steps 1 to 6 and start executing directly from Step 7 (Load Trained Model)** to see the live driver detection system in action!

---

## 🧠 Model Features & Detection Classes

The model has been optimized to detect specific driver behaviors in real-time, focusing heavily on:

* Drowsiness
* Phone use
* Ywan
* Natural
