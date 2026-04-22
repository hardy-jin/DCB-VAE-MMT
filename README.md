# 🚗 DCB-VAE + Multimodal Transformer for Imbalanced Traffic Crash Prediction

## 📌 Overview

This repository provides the official implementation of our paper:

**“Dynamic Conditional Balanced VAE with Multimodal Transformer for Imbalanced Traffic Crash Prediction”**

Traffic crash prediction suffers from **extreme class imbalance** and **heterogeneous multimodal data**.
To address these challenges, we propose a two-stage framework:

* **DCB-VAE**: A latent-space representation learning model for adaptive negative sampling
* **Multimodal Transformer (MMT)**: A transformer-based architecture that models cross-modal interactions using semantic tokens

---

## 🧠 Key Contributions

* ✅ Representation-driven negative sampling via latent space learning
* ✅ KNN-based hard negative mining (near-collision scenarios)
* ✅ Multimodal transformer with semantic token design
* ✅ Improved performance on highly imbalanced crash datasets

---

## 🏗️ Framework

```
Raw Data → Feature Engineering → DCB-VAE (Sampling) → Multimodal Transformer → Prediction
```

---

## 📂 Repository Structure

```
├── data/                  # Processed dataset (or instructions to generate)
├── models/
│   ├── dcb_vae.py         # DCB-VAE implementation
│   ├── transformer.py     # Multimodal Transformer
├── training/
│   ├── train_vae.py
│   ├── train_transformer.py
├── utils/
│   ├── preprocessing.py
│   ├── metrics.py
├── configs/
│   ├── config.yaml        # Hyperparameters
├── main.py
└── README.md
```

---

## ⚙️ Installation

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

pip install -r requirements.txt
```

---

## 🧪 Environment

* Python 3.9+
* PyTorch
* Scikit-learn
* CatBoost
* NumPy / Pandas

GPU recommended:

* NVIDIA GPU (e.g., RTX 3090)

---

## 🚀 Training

### Step 1: Train DCB-VAE

```bash
python training/train_vae.py
```

### Step 2: Generate Balanced Samples

```bash
python utils/generate_samples.py
```

### Step 3: Train Multimodal Transformer

```bash
python training/train_transformer.py
```

---

## 📊 Hyperparameters

Key parameters used in the paper:

| Parameter              | Value |
| ---------------------- | ----- |
| k (KNN)                | 13    |
| Latent dimension       | 8     |
| γ (contrastive weight) | 0.3   |
| α (attraction weight)  | 0.1   |
| KL warmup T            | 20    |

All parameters were tuned using **grid search on validation set**.

---

## 📈 Evaluation Metrics

* Precision
* Recall
* F1-score
* ROC-AUC

---

## 🔁 Reproducibility

* Random seed fixed: `42`
* All experiments use the same train/validation/test split
* Hyperparameters are reported in the paper (Table 4)

---

## 📎 Code Availability Statement

This repository is provided to ensure **reproducibility and transparency** of the results reported in the paper.

---

## 📖 Citation

If you find this work useful, please cite:

```bibtex
@article{han2026dcbvae,
  title={Dynamic Conditional Balanced VAE with Multimodal Transformer for Imbalanced Traffic Crash Prediction},
  author={Han, Jintong and others},
  journal={Engineering Applications of Artificial Intelligence},
  year={2026}
}
```

---

## 🤝 Acknowledgements

This work is supported by research in transportation safety and intelligent systems.

---

## 📬 Contact

Jintong Han
University of Georgia
Email: [your_email@uga.edu](mailto:your_email@uga.edu)
