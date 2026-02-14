# SADBM: Structure-Aware Diffusion Bridge Model for SAR-to-Optical Image Translation (S2OIT)

> **SADBM** is a theoretically grounded diffusion-bridge framework for **SAR-to-Optical Image Translation (S2OIT)**, designed to improve **structural realism** and **fidelity** by explicitly modeling the cross-domain mapping from SAR distributions to optical imagery.

---

## 🔥 News
- **[2026/02]** Initial release of SADBM repository (code, configs, and evaluation scripts).
- **[TBD]** Release of **SEN1-2 Scene** dataset (multi-seasonal, scene-level labels) upon paper publication for downstream classification validation.
- **[TBD]** Full code and pretrained models will be released upon paper acceptance.

---

## 1. Overview

Synthetic Aperture Radar (SAR) can observe the Earth under all-weather and day-night conditions, yet it is difficult for non-experts to interpret. **SAR-to-Optical Image Translation (S2OIT)** aims to generate visually interpretable optical-like imagery from SAR inputs, facilitating cross-modal Earth observation and improving downstream tasks.

However, existing generative approaches (GANs and diffusion models) often struggle with:
- **Weak structural awareness** caused by intrinsic limitations of cross-domain mapping frameworks,
- Lack of **comprehensive structure-aware network design** to preserve geometry, edges, and scene layouts.

To address these challenges, we propose **SADBM (Structure-Aware Diffusion Bridge Model)**.


---
## 2. Key Contributions

### 2.1 Structure-Aware Diffusion Bridge (Doob’s h-transform)
We incorporate **Doob’s h-transform** into the diffusion process to build a **Diffusion Bridge** for explicit **SAR→optical** mapping, treating SAR as a **source distribution** and improving structural consistency.

### 2.2 Edge-information Enhancement (E²)
**E²** enhances SAR structural cues by fusing SAR edge maps with guidance from optical edges, while suppressing speckle-induced artifacts.

### 2.3 Hierarchical Structural Extraction (HSE)
**HSE** extracts **global-to-local** structures and injects **multi-scale** cues into intermediate layers for robust structure representation.

---

## 3. Results

We evaluate SADBM on two representative datasets and demonstrate consistent improvements over state-of-the-art methods in:
- **Structural realism** (shapes, edges, layouts),
- **Structural fidelity** (alignment with SAR-derived geometry),
- Overall translation quality.
> 📌 Actual metrics.
- **PSNR↑**
- **SSIM↑**
- **RMSE↓**
- **LPIPS↓**
- **FSIM↑**

---

## 4. Datasets

### 4.1 SAR2Opt
[[> SAR2Opt.](https://github.com/MarsZhaoYT/SAR2Opt-Heterogeneous-Dataset)]

### 4.2 SEN1-2 Scene
The **SEN1-2 Scene** dataset is derived from the **SEN1-2** benchmark and is tailored for **SAR-optical scene-level classification**.

---

## 5. Installation

```bash
git clone https://github.com/<yourname>/SADBM.git
cd SADBM

# (recommended) create environment
conda create -n sadbm python=3.10 -y
conda activate sadbm

pip install -r requirements.txt


