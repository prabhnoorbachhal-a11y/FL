# FL
# https://github.com/prabhnoor-bachhal/federated-maize-disease
# Federated Learning for Maize Leaf Disease Classification

**Author:** Dr. Prabhnoor Bachhal  
**Institution:** Chitkara University, Punjab, India  
**Contact:** prabhnoor.bachhal@chitkara.edu.in  

---

##  About

This repository accompanies the research paper:

> **"Optimizing Federated Learning for Maize Leaf Disease Classification using Internet of Agricultural Things"**  
> *Prabhnoor Bachhal et al., 2025.*

The study presents a **Federated Learning (FL)** framework integrated with **Transfer Learning** for the detection of maize leaf diseases within **IoAT (Internet of Agricultural Things)** environments.  
The approach ensures **data privacy** while achieving accuracy comparable to centralized learning models.

---

##  Implementation Reference

This repository provides **experimental documentation and result details**.  
The implementation was adapted and conceptually based on the open-source project:

🔗 [AI-LabX/federated-learning-pytorch](https://github.com/AI-LabX/federated-learning-pytorch)

All experiments in this paper were customized for maize leaf disease classification using **DenseNet-121** within a **federated setup**.

---

## Dataset

The dataset used in this study is a maize subset of the **PlantVillage dataset**, publicly available at:  
 [https://www.kaggle.com/datasets/emmarex/plantdisease](https://www.kaggle.com/datasets/emmarex/plantdisease)

- **Total images:** 4,585  
- **Classes:** 5 (Healthy, Blight, Rust, Gray Leaf Spot, and others)  
- **Preprocessing applied:** resizing, normalization, and augmentation (rotation, flip, zoom, brightness adjustment).

---

##  Methodology Summary

| Step | Description |
|------|--------------|
| 1️⃣ | Data preprocessing and augmentation using image transformation techniques. |
| 2️⃣ | Federated Learning framework setup with multiple clients (non-IID distribution). |
| 3️⃣ | Feature extraction using transfer learning (DenseNet-121 backbone). |
| 4️⃣ | Model aggregation using Federated Averaging (FedAvg) algorithm. |
| 5️⃣ | Evaluation on centralized and federated setups with identical test sets. |

---

##  Results Summary

| Model | Setup | Accuracy | Precision | Recall | AUC |
|--------|--------|-----------|------------|---------|------|
| **DenseNet-121 (FL + TL)** | Federated | **99.89%** | **99.76%** | **99.68%** | **99.5%** |
| ResNet152V2 | Federated | 96.5% | 96.1% | 95.9% | 97.3% |
| VGG16 | Federated | 93.9% | 94.2% | 93.8% | 94.1% |
| MobileNetV2 | Federated | 91.8% | 91.3% | 91.5% | 92.0% |

✅ The proposed DenseNet-121-based federated model outperformed other architectures in all metrics.

---

##  Hardware Configuration

| Component | Specification |
|------------|----------------|
| CPU | Intel® Core™ i7-9700K @ 3.60GHz |
| GPU | NVIDIA GeForce GTX 1080 Ti (11GB) |
| RAM | 32 GB |
| OS | Ubuntu 20.04 LTS |
| Framework | PyTorch 2.0.0 + Python 3.10 |
| Communication Rounds | 50 |
| Local Epochs | 5 per round |

---

##  How to Use (Optional for Readers)

Although the current repository provides only documentation and configuration details, users can replicate similar experiments using the open-source baseline:

```bash
git clone https://github.com/AI-LabX/federated-learning-pytorch
cd federated-learning-pytorch
# Adapt the dataset path to the PlantVillage maize subset
# Modify the model file to use DenseNet-121
# Run training
python main.py
