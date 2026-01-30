# Preprocessing-real-world-hazy-images-for-improved-results-of-DehazeFormer

This repository contains the preprocessing pipeline proposed in our paper for
enhancing real-world hazy images prior to applying transformer-based image
dehazing models such as DehazeFormer.

The primary motivation of this work is to reduce the domain gap between
synthetic and real-world haze by performing adaptive, region-aware enhancement
before dehazing.

---

## Overview

The preprocessing pipeline is fully modular and consists of the following
components:

- **Haze Density Estimation (HDE):**  
  A patch-based haze estimator combining Dark Channel Prior (DCP) cues with
  sharpness information to generate a soft haze weight map.

- **CLAHE-based Local Contrast Enhancement:**  
  Improves visibility in low-contrast regions while limiting noise
  amplification.

- **Retinex-inspired Bilateral Filtering:**  
  Enhances fine details and texture in hazy regions without introducing ringing
  artifacts.

- **Adaptive Fusion:**  
  Pixel-wise blending of CLAHE and Retinex outputs guided by the HDE map.

The resulting preprocessed image is intended to be used as input to a
pretrained dehazing model.

---

## Scope of This Repository

⚠️ **Important Note**

- This repository provides a **single-image preprocessing pipeline** intended
  for demonstration and reproducibility of the proposed method.
- The code is **not a full training or batch-processing framework**.
- Quantitative evaluation was performed on a larger image set, as reported in
  the paper.

---

## Sample Results

The `sample_results/` directory contains a **curated subset of representative
image pairs**:

- `original/` – original real-world hazy images  
- `preprocessed/` – corresponding outputs after preprocessing  

Only a small number of representative samples are included for qualitative
visualization. The full set of images used for evaluation is not uploaded due
to size and dataset licensing constraints.

---

## Usage

The preprocessing pipeline operates on a single input image.

Typical steps:
1. Load the hazy image
2. Compute haze density map (HDE)
3. Apply CLAHE-based contrast enhancement
4. Apply Retinex-inspired bilateral filtering
5. Fuse outputs using the HDE map

Refer to the provided notebook/script for implementation details.

---

## Dataset

Experiments were conducted using real-world hazy images from the
**RTTS (Real-World Task-driven Testing Set)** of the RESIDE benchmark.

Due to licensing constraints, the dataset itself is **not included** in this
repository.

---

## Paper

📄 **Paper:** *To be added post-conference*  
The paper describing this method, experimental setup, and quantitative results
will be linked here once publicly available.

---

## License

This repository is released for academic and research use.

