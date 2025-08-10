# Depth-Inference-for-Unstructured-Multi-view-Stereo

**Authors:**  
- Dheeraj Chilukuri  
- Meenakshisundram Ganapathi Subramanian  
- Soorya Boopal  
_MS in Robotics and Autonomous Systems_  
Arizona State University

---

## 📖 Overview
This repository contains the implementation and benchmark results for **MVSNet** and a **GRU-enhanced R-MVSNet** for dense depth estimation from unstructured multi-view images.  

- **MVSNet (Baseline):** Uses differentiable homography warping and 3D CNN cost-volume regularization.  
- **GRU-based R-MVSNet:** Replaces memory-heavy 3D CNN with convolutional GRU sequential regularization — reducing complexity from **O(H×W×D)** to **O(H×W+D)**. This enables **high-resolution reconstructions** with improved scalability.

Our experiments on the **DTU dataset** show that the GRU-based approach enhances both quality (accuracy, completeness, F-score) and inference speed.

---

## 📂 Repository Structure

```
.
├── cnn_wrapper/       # CNN-based cost volume and training utilities
├── doc/               # Documentation, references, and design notes
├── mvsnet/            # Core implementation of MVSNet & R-MVSNet architectures
├── results/           # Output reconstructions, metrics, plots
├── tools/             # Dataset preprocessing, evaluation scripts
├── LICENSE            # License file (MIT/Apache2/GPLv3)
├── README.md          # This file
└── requirements.txt   # Python dependencies
```

---

## ✨ Features
- End-to-end training for depth inference from multi-view images.
- Baseline MVSNet with 3D CNN regularization.
- Memory-efficient R-MVSNet with sequential GRU.
- Adaptive depth range sampling for refined reconstructions.
- Evaluation scripts for DTU benchmark.
- Ready-to-use training & testing pipelines.

---

## 🛠 Installation

```
git clone https://github.com//MVSNet-RMVSNet-Depth.git
cd MVSNet-RMVSNet-Depth
pip install -r requirements.txt
```

---

## 📊 Usage

### **Train a model**
```
python mvsnet/train.py --config configs/train_config.yaml
```

### **Test / Evaluate**
```
python mvsnet/test.py --config configs/test_config.yaml
```

Results (depth maps, point clouds) will be saved in `results/`.

---

## 📈 Results Summary

| Model       | Accuracy ↓ | Completeness ↓ | F-Score ↑ | Inference Time ↓ |
|-------------|------------|----------------|-----------|------------------|
| MVSNet      | Baseline   | Baseline       | Baseline  | Moderate         |
| R-MVSNet    | Improved   | Improved       | Higher    | Faster           |

Qualitative and quantitative results are in the `results/` folder.  
Figures and detailed analysis are provided in the **final_report.pdf** (to be uploaded).

---

## 🔧 Enhancements Implemented
- **GRU-based regularization** (Inspired by NRR-MVSNet)
- **Adaptive depth hypothesis sampling**
- **High-resolution scalability** without tiling/downsampling

---

## 📚 References
- Y. Yao et al., *MVSNet: Depth Inference for Unstructured Multi-view Stereo*, ECCV 2018  
- Q. Xu et al., *NRR-MVSNet: Non-local Recurrent Regularization Networks for Multi-view Stereo*, arXiv 2021  

Full reference list and experiment details in `Final_report.pdf`.

---



