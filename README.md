# SSL-MIMeta-CTscan: Self-Supervised Learning for Medical Image Analysis

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

This repository contains the implementation for the study:  
**“Leveraging Self-Supervised Learning for Enhanced Medical Image Analysis: A Comparative Study of Barlow Twins Pre-training and ImageNet Fine-Tuning.”**

---

## 📖 Abstract

Medical image classification often suffers from limited labeled datasets.  
In this project, we employ **Barlow Twins** self-supervised pre-training on **ResNet-18** to generate transferable representations for medical image classification.  
Our approach demonstrates **superior performance** compared to ImageNet pre-trained models across two distinct medical domains:

- **Liver Tumor CT Scans** (4,935 images, 11 organ classes)  
- **Colorectal Cancer Histology** (107,180 images, 9 tissue classes)

Domain-specific Barlow Twins features consistently outperform generic ImageNet features, especially in low-data regimes.

---

## 🚀 Key Features

- **Self-supervised pre-training** using the Barlow Twins framework  
- **Comparative analysis** vs. ImageNet-based transfer learning  
- **Fine-tuning strategies:** surgical (readout only) and full  
- **Multi-domain evaluation:** CT scans and histopathology images  
- **Feature representation analysis** with t-SNE visualization  
- **Strong performance** even with limited labeled data  

---

## 🏥 Medical Applications

### Liver Tumor Domain
- Organ classification from contrast-enhanced CT scans  
- 11 anatomical classes: heart, lungs, liver, spleen, pancreas, kidneys, bladder, femoral heads, etc.  
- Multi-plane inputs: axial, coronal, and sagittal views  

### Colorectal Cancer Domain
- Tissue microenvironment classification  
- 9 tissue types: adipose, background, debris, lymphocytes, mucus, smooth muscle, normal mucosa, cancer-associated stroma, and adenocarcinoma epithelium  

---

## 📊 Key Results

| Domain | Method | Accuracy | Data Regime | Notes |
|---------|---------|-----------|--------------|--------|
| **Liver Tumor CT** | Barlow Twins | ~79% | 100% | vs. 50% (ImageNet, readout only) |
| **Colorectal Cancer** | Barlow Twins | ~97% | 100% | vs. 94% (ImageNet) |

- Barlow Twins features yielded **better separability** in t-SNE visualizations  
- Consistently robust performance under **low-label conditions (0.5%–50%)**

---

## 🛠️ Installation & Usage

```bash
git clone https://github.com/DrMohamedElsherif/SSL-MIMeta-CTscan.git
cd SSL-MIMeta-CTscan
pip install -r requirements.txt
```

### 💡 Example Usage

```python
from models.barlow_twins import BarlowTwins

# Initialize model
model = BarlowTwins(backbone='resnet18')

# Train on MIMeta dataset
# Example: surgical fine-tuning (readout head only)
python train.py --strategy surgical --data_percentage 100

# Full fine-tuning
python train.py --strategy full --data_percentage 100
```

---

## 👩‍🔬 Authors

**Mohamed Elsherif**, **Simon Frank**, **Daniela Kemp**, **Gwent Krause**, and **Tim Rebig**  
Department of Computer Science, Eberhard Karls University of Tübingen

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 📚 Citation

If you use this work, please cite:

```bibtex
@article{elsherif2023ssl,
  title={Leveraging Self-Supervised Learning for Enhanced Medical Image Analysis},
  author={Elsherif, Mohamed and Frank, Simon and Kemp, Daniela and Krause, Gwent and Rebig, Tim},
  journal={University of Tübingen},
  year={2023}
}
```
---

## 📫 Contact

**Mohamed Elsherif**  
📧 [mohamed.elsherif@dkfz-heidelberg.de](mailto:mohamed.elsherif@dkfz-heidelberg.de)  

---

