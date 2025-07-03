# 🧠 Multimodal AI for Liver Cancer Detection  
*A Repository for Liver Cancer Diagnosis Using Multimodal Medical Data*  

[![License](https://img.shields.io/badge/License-MIT-blue.svg )](https://opensource.org/licenses/MIT )  
[![Python](https://img.shields.io/badge/Python-3.8+-brightgreen.svg )](https://www.python.org/ )  
[![PyTorch](https://img.shields.io/badge/PyTorch-1.13+-orange.svg )](https://pytorch.org/ )  

This repository implements a **multimodal AI framework** for liver cancer (hepatocellular carcinoma, HCC) detection by integrating **medical imaging (CT/MRI), histopathology, clinical data (EHR), and genomic features**. It addresses challenges like missing modalities, domain adaptation, and explainability, leveraging recent advances in self-supervised learning (SSL) and transformer-based fusion.

---

## 🔍 Key Features  
1. **Dynamic Fusion Transformer**:  
   - Uses cross-attention to weight contributions of imaging, clinical data, and histopathology dynamically.  
   - Inspired by CLIP (Radford et al., 2021) for aligning heterogeneous modalities.  

2. **Robust Missing Modality Handling**:  
   - Implements MISA (Saha et al., 2024) and learnable embeddings for incomplete data.  

3. **Self-Supervised Pretraining**:  
   - Adapts **Models Genesis** (Zhou et al., 2021) for medical imaging SSL.  

4. **Explainability**:  
   - Integrates Grad-CAM and latent shift analysis (Guarrasi et al., 2024) for interpretable predictions.  

5. **Lightweight Deployment**:  
   - Uses GhostNet (Han et al., 2023) for single-GPU inference.  

---

## 📦 Datasets  
| Dataset          | Modalities          | Features                                      | Source                                                                 |
|------------------|---------------------|-----------------------------------------------|------------------------------------------------------------------------|
| **LiTS17**       | CT                  | Liver/tumor masks, diverse lesion sizes       | [LiTS Challenge](https://competitions.codalab.org/competitions/17094 )  |
| **CirrMRI600+**  | MRI (T1W, T2W)      | Cirrhotic liver segmentations, multimodal     | [Git](https://github.com/NUBagciLab/CirrMRI600Plus)                       |
| **HCC-TACE-SEG** | CT/MRI + Clinical   | Expert annotations, treatment outcomes        | [Git](https://github.com/openmedlab/Awesome-Medical-Dataset/blob/main/resources/HCC-TACE-Seg.md)                        |
| **TCGA-LIHC**    | Genomic + Imaging   | Survival data, radiomics                      | [TCGA-LIHC](https://portal.gdc.cancer.gov/projects/TCGA-LIHC) |

---

## 🗓️ Detailed Plan (6-Month Timeline)  

### **Month 1: Data Curation & Preprocessing**  
- **Tasks**:  
  - Acquire LiTS17, CirrMRI600+, HCC-TACE-SEG, and TCGA-LIHC datasets.  
  - Standardize preprocessing: stain normalization for histopathology (Macenko et al., 2009), MICE imputation for clinical data (Azur et al., 2011).  

### **Month 2: Exploratory Data Analysis & Baseline Models**  
- **Tasks**:  
  - Analyze modality-specific features (e.g., tumor texture in MRI vs. CT).  
  - Train unimodal baselines (ResNet50 for imaging, XGBoost for EHR).  

### **Month 3: Model Development**  
- **Tasks**:  
  - Implement CrossModalTransformer with attention fusion.  
  - Pretrain Models Genesis on unlabeled CT/MRI data.  

### **Month 4: Advanced Analysis**  
- **Tasks**:  
  - Integrate Grad-CAM for tumor localization.  
  - Test domain adaptation with CycleGAN (Zhu et al., 2017).  

### **Month 5: Validation & Ablation**  
- **Tasks**:  
  - Compare fusion methods (early vs. late) on Dice score.  
  - Validate on external datasets (LiTS17, BraTS21).  

### **Month 6: Manuscript Preparation**  
- **Tasks**:  
  - Draft paper using Overleaf template.  
  - Publish curated datasets (CC-BY license).  

---
## 📚 References  
1. **Radford, A., et al. (2021)**. *Learning Transferable Visual Models From Natural Language Supervision*. [arXiv](https://arxiv.org/abs/2103.00020). 
2. **van der Gijp, A., et al. (2025)**. *Navigating the landscape of multimodal AI in medicine: A scoping review on technical challenges and clinical applications*. Medical Image Analysis. [DOI](https://doi.org/10.1016/j.media.2025.102123 )
3. **Mi, Z., et al. (2025)**. *Multi-instance curriculum learning for histopathology image classification with bias reduction*. Medical Image Analysis. [DOI](https://doi.org/10.1016/j.media.2025.102157 ) 
4. **Sekuboyina, A. K., et al. (2019)**. *The Liver Tumor Segmentation Benchmark (LiTS)*. [arXiv](https://arxiv.org/abs/1901.04056 ).
5. **Chen, L., et al. (2024)**. *Vision Models Are Becoming Better Image Feature Extractors Than Manual Annotations*. [arXiv](https://arxiv.org/abs/2404.00578 )
6. **Waqas, A., Tripathi, A., and Rasool, G. (2024)**. *Embedding-based Multimodal Learning on Pan-Squamous Cell Carcinomas for Improved Survival Outcomes*. [DOI](https://doi.org/10.3389/frai.2024.1430984 )
---

## 📄 License  
This project is licensed under the MIT License. See `LICENSE` for details.  

## 📬 Contact  
For questions or collaboration, email a.kornaev@ronc.ru.  
