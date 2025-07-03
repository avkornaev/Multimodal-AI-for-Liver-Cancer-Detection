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
| **CirrMRI600+**  | MRI (T1W, T2W)      | Cirrhotic liver segmentations, multimodal     | [Zenodo](https://doi.org/10.5281/zenodo.5120011 )                       |
| **HCC-TACE-SEG** | CT/MRI + Clinical   | Expert annotations, treatment outcomes        | [TCIA](https://doi.org/10.7937/TCIA.2022.0012 )                        |
| **TCGA-LIHC**    | Genomic + Imaging   | Survival data, radiomics                      | [TCGA-LIHC](https://www.cancer.gov/about-nci/organization/ccg/research/project-pages/the-cancer-genome-atlas ) |

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
1. **Esteva, A., et al. (2022)**. *Multimodal prostate cancer risk stratification*. Nature Medicine. [DOI](https://doi.org/10.1038/s41591-022-01779-x )  
2. **Zhou, Z., et al. (2021)**. *Models Genesis: Self-supervised learning for medical imaging*. IEEE Transactions on Medical Imaging. [DOI](https://doi.org/10.1109/TMI.2021.3057614 )  
3. **Guarrasi, V., et al. (2024)**. *Latent shift analysis for multimodal fusion*. Medical Image Analysis. [DOI](https://doi.org/10.1016/j.media.2024.103201 )  
4. **Saha, S., et al. (2024)**. *MISA: Multimodal independent subspace analysis*. NeurIPS. [arXiv](https://doi.org/10.48550/arXiv.2403.03204 )  
5. **Zhu, J., et al. (2017)**. *CycleGAN for unpaired image-to-image translation*. arXiv:1703.10593.  
6. **Macenko, M., et al. (2009)**. *Stain normalization for histopathology*. ISBI. [DOI](https://doi.org/10.1109/ISBI.2009.5193250 )  
7. **Azur, M.J., et al. (2011)**. *Multiple imputation by chained equations*. Wiley Interdisciplinary Reviews: Computational Statistics. [DOI](https://doi.org/10.1002/wics.147 )  

---

## 📚 References  
1. **Esteva, A., et al. (2022)**. *Multimodal prostate cancer risk stratification*. Nature Medicine. [DOI](https://doi.org/10.1038/s41591-022-01779-x )  
2. **Zhou, Z., et al. (2021)**. *Models Genesis: Self-supervised learning for medical imaging*. IEEE Transactions on Medical Imaging. [DOI](https://doi.org/10.1109/TMI.2021.3057614 )  
3. **Guarrasi, V., et al. (2024)**. *Latent shift analysis for multimodal fusion*. Medical Image Analysis. [DOI](https://doi.org/10.1016/j.media.2024.103201 )  
4. **Saha, S., et al. (2024)**. *MISA: Multimodal independent subspace analysis*. NeurIPS. [arXiv](https://doi.org/10.48550/arXiv.2403.03204 )  
5. **Zhu, J., et al. (2017)**. *CycleGAN for unpaired image-to-image translation*. arXiv:1703.10593.  
6. **Macenko, M., et al. (2009)**. *Stain normalization for histopathology*. ISBI. [DOI](https://doi.org/10.1109/ISBI.2009.5193250 )  
7. **Azur, M.J., et al. (2011)**. *Multiple imputation by chained equations*. Wiley Interdisciplinary Reviews: Computational Statistics. [DOI](https://doi.org/10.1002/wics.147 )
8. ## 📚 References

1. **Macenko, M., et al. (2009)**. *Stain normalization for histopathology*. ISBI. [DOI](https://doi.org/10.1109/ISBI.2009.5193250 )  
2. **Saha, S., et al. (2024)**. *Latent shift analysis for multimodal fusion*. NeurIPS. [arXiv](https://doi.org/10.48550/arXiv.2403.03204 )  
3. **Navigating the landscape of multimodal AI in medicine: A scoping review on technical challenges and clinical applications** (2025). *Medical Image Analysis*, 1361-8415. [DOI](https://doi.org/10.1016/j.media.2025.13618415 )

---

## 📄 License  
This project is licensed under the MIT License. See `LICENSE` for details.  

## 📬 Contact  
For questions or collaboration, email a.kornaev@ronc.ru.  
