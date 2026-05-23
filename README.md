# ECG Time Series Reconstruction with Variational Autoencoder (VAE)

Official implementation for the paper:

**Reconstructing 12-Lead ECG from 3-Lead ECG using Variational Autoencoder to Improve Cardiac Disease Detection of Wearable ECG Devices**

Published in PLOS Digital Health, 2025.

---

## Overview

This repository implements a Variational Autoencoder (VAE) framework for reconstructing 12-lead ECG signals from reduced-lead ECG recordings.

The project aims to improve cardiac disease detection capability for wearable ECG devices by recovering clinically informative multi-lead ECG representations from limited input signals.

Our framework provides:

- Efficient ECG signal reconstruction
- Compact latent representation learning
- Fast training and inference
- Improved downstream diagnostic utility

---

## Paper

📄 PLOS Digital Health Publication:

[https://journals.plos.org/digitalhealth/article?id=10.1371/journal.pdig.0001335](https://journals.plos.org/digitalhealth/article?id=10.1371/journal.pdig.0001335)

📄 arXiv Version:

[https://arxiv.org/abs/2510.11442](https://arxiv.org/abs/2510.11442)
---

## Installation

```bash
pip install -r requirements.txt
```

---

## Dataset Preparation

### Preprocess MIMIC ECG Dataset

```bash
python data/datasets_preprocess/MIMIC/make_dataset.py
```

### Build DataLoader

```bash
python -m reconstruction.data.build_dataloader
```

---

## Training

Train the VAE model:

```bash
python models/vae/vae_train_100.py \
    --config config/MIMIC/mimic_cond.yaml \
    --save_dir ./results/vae_100/
```

---

## Testing

Evaluate the trained model:

```bash
python models/vae/vae_test_100.py \
    --config config/MIMIC/mimic_cond.yaml \
    --save_dir ./results/vae_100/
```

---

## Visualization

Visualize reconstructed ECG signals:

```bash
python evaluation/plot2.py
```

---

## Evaluation Metrics

Compute reconstruction metrics:

```bash
python evaluation/compute_metric.py
```

---

## Project Structure

```text
├── models/
│   └── vae/
│       ├── vae_model_100.py      # VAE architecture
│       ├── vae_train_100.py      # Training script
│       └── vae_test_100.py       # Evaluation script
├── config/                       # Configuration files
├── data/                         # Dataset preprocessing and loading
├── evaluation/                   # Evaluation and visualization
└── utils/                        # Utility functions
```

---

## Main Results

Our VAE-based ECG reconstruction framework demonstrates:

- High-quality 12-lead ECG reconstruction
- Robust latent representation learning
- Efficient inference for wearable-device scenarios
- Improved support for downstream cardiac disease detection

---

## Citation

If you find this repository useful, please cite:

```bibtex
@article{guan2025reconstructing,
  title={Reconstructing 12-Lead ECG from 3-Lead ECG using Variational Autoencoder to Improve Cardiac Disease Detection of Wearable ECG Devices},
  author={Guan, Xinyan and Lai, Yongfan and Jin, Jiarui and Li, Jun and Wang, Haoyu and Zhao, Qinghao and Zhang, Deyun and Geng, Shijia and Hong, Shenda},
  journal={PLOS Digital Health},
  volume={4},
  number={5},
  pages={e0001335},
  year={2025},
  publisher={Public Library of Science}
}
```

---

## Authors

- Xinyan Guan
- Yongfan Lai
- Jiarui Jin
- Jun Li
- Haoyu Wang
- Qinghao Zhao
- Deyun Zhang
- Shijia Geng
- Shenda Hong

For questions or collaboration, please contact:

📧 xinyan.guan.25@ucl.ac.uk

---

## Acknowledgements

We thank the following open-source projects for their valuable contributions:

- :contentReference[oaicite:2]{index=2}
- :contentReference[oaicite:3]{index=3}
