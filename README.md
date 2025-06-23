# Rainfall Disaggregation via CNN-CBIR and Cluster Space Logic

This repository presents a novel, modular approach to **temporal rainfall disaggregation** using a blend of clustering, convolutional neural networks (CNN), and a compiler-inspired pipeline. This method transforms daily rainfall totals into realistic hourly sequences, preserving both **statistical fidelity** and **structural rainfall dynamics** across varied climatic regions.

Inspired by logic from content-based image retrieval (CBIR), the model leverages **pattern-based inference** instead of relying solely on stochastic models or function approximation. 

## Overview

- **Clustering**: K-means based structural abstraction of hourly rainfall
- **Cluster Space**: A latent space of all valid sequences grounded in observed data
- **CBIR via CNN**: Retrieves feasible rainfall patterns from history using image-based similarity
- **Redistribution Mechanism**: Autodiff-powered adjustment aligns cluster output with observed totals
- **Result**: High-fidelity disaggregation, with improved dry spell reconstruction and event metrics

## Repo Structure

```
Rainfall-disaggregation/
├── Code/
│   ├── main_model.ipynb
│   ├── Result_analysis.ipynb
│   └── Shaping Excel files.ipynb
│   └── Shaping Excel files.ipynb
│   └── Shaping Excel files.ipynb
│
├── data/
│   ├── .gitkeep
│   └── DATA_SECTION.md
│
├── results/
│   ├── chennai/
│   │   ├── %0 values_chennai.png
│   │   ├── IDF_chennai_compare.png
│   │   ├── IDF_chennai_generated.png
│   │   ├── IDF_chennai_given.png
│   │   ├── event duration stats_chennai.png
│   │   ├── event volume stats_chennai.png
│   │   ├── qq plot of trf_chennai.png
│   │   └── qq plots_chennai.png
│   │
│   ├── delhi/
│   │   ├── %0 values_delhi.png
│   │   ├── IDF_delhi_compare.png
│   │   ├── IDF_delhi_generated.png
│   │   ├── IDF_delhi_given.png
│   │   ├── event duration stats_delhi.png
│   │   ├── event volume stats_delhi.png
│   │   ├── qq plot of trf_delhi.png
│   │   └── qq plots_delhi.png
│   │
│   ├── kolkata/
│   │   ├── %0 values_kolkata.png
│   │   ├── IDF_kolkata_compare.png
│   │   ├── IDF_kolkata_generated.png
│   │   ├── IDF_kolkata_given.png
│   │   ├── event duration stats_kolkata.png
│   │   ├── event volume stats_kolkata.png
│   │   ├── qq plot of trf_kolkata.png
│   │   └── qq plots_kolkata.png
│   │
│   ├── mumbai/
│   │   ├── %0 values_mumbai.png
│   │   ├── IDF_mumbai_compare.png
│   │   ├── IDF_mumbai_generated.png
│   │   ├── IDF_mumbai_given.png
│   │   ├── event duration stats_mumbai.png
│   │   ├── event volume stats_mumbai.png
│   │   ├── qq plot of trf_mumbai.png
│   │   └── qq plots_mumbai.png
│   │
│   ├── %0 values.png
│   ├── event duration.png
│   ├── event volume.png
│   └── idf plots.png
│
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt

```

## Study Scope

- Study Areas: **Delhi, Mumbai, Kolkata, Chennai**
- Data Source: IMD, India (46–52 years of hourly rainfall)
- Benchmarks: NSRP, MMRC, MMRC-K, ANN-K (Bhattacharyya et al., 2023)

## Key Results

- IDF curve error under 10%
- Dry period reconstruction outperforms all compared models
- Structural + statistical consistency
- Robust across arid and monsoon zones

## Data Policy

The dataset used in this work is not included in this repository due to size and distribution constraints. To run the model, place your own `.xlsx` formatted daily rainfall data into the `data/` folder. See `shaping/` for preprocessing.

## Reproduce the Results

1. Clone the repo  
2. Install dependencies:
```bash
pip install -r requirements.txt
```
3. Add your data in `data/`  
4. Run `NOTEBOOK (reworked).ipynb`

## Citation

If you use this work, please cite our preprint:

> Dey, S., Samanta, P., Saha, U. (2024). Disaggregation of Daily Rainfall Using CNN-CBIR and Clusterspace Logic. *Under Review*.

---
