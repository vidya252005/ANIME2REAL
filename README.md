# ANIME2REAL
# 🌀 Anime2Real – CycleGAN Image Translation

This project implements **CycleGAN** to translate images between **anime faces** and **real human faces**.  
It’s built using **Python + PyTorch**.

---

## 📖 Overview
**Anime2Real** learns a **two-way mapping** between anime-style faces and realistic human faces using unpaired data.  
The full pipeline includes:
- Dataset download and preprocessing  
- Model architecture (Generators & Discriminators)  
- Training with checkpointing  
- Testing and visualization of results  

CycleGAN enables **unpaired image-to-image translation**, meaning it doesn’t require matched anime ↔ real pairs — only collections of images from each domain.

---

## ⚙️ Requirements
- Python 3  
- PyTorch and torchvision  
- Google Colab (recommended) or a CUDA-enabled Linux machine  
- Kaggle account and API key (`kaggle.json`) for dataset downloads  

---

## 🚀 Setup

### 1️⃣ Clone or Upload Notebook
Use this notebook in **Google Colab** for seamless GPU access.

### 2️⃣ Install Dependencies
!pip install kaggle -q
When prompted, upload your kaggle.json file to authenticate.

3️⃣ Download Datasets

Anime Faces: Anime Face Dataset (Kaggle)

CelebA Faces: CelebA Dataset (Kaggle)

The notebook automatically downloads and unzips them into:



datasets/anime2real/
    trainA/   # Anime face images
    trainB/   # Real face images
    testA/    # Anime face test set
    testB/    # Real face test set



###🧠 Model Architecture
Generator

U-Net / ResNet-inspired

Downsampling → Residual Blocks → Upsampling

Outputs translated images (Anime ↔ Real)

Discriminator

PatchGAN-based classifier

Judges small image patches as real or fake

Provides fine-grained feedback to the generator

Both are implemented in PyTorch and fully customizable.

🧪 References

CycleGAN Paper: Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks — Zhu et al., 2017

Official PyTorch Implementation: junyanz/pytorch-CycleGAN-and-pix2pix

