git# VERSE19 CT Autoencoder - Deep Learning Assignment

![TensorFlow](https://img.shields.io/badge/TensorFlow-2.11+-FF6F00?logo=tensorflow)
![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)

A deep learning project for medical image analysis using autoencoders on CT (Computed Tomography) spine scans from the VERSE19 dataset.

## Project Overview

This assignment focuses on developing and training multiple autoencoder architectures to process, compress, and analyze vertebral CT scan images. The models learn to reconstruct high-resolution medical images from latent representations, with applications in medical image compression, anomaly detection, and feature extraction.

## Models Implemented

This project implements and compares four distinct autoencoder architectures:

### 1. **Basic Autoencoder**
   - Dense layers with sigmoid activation
   - Simple dimensionality reduction in the latent space
   - Baseline model for comparison

### 2. **Convolutional Autoencoder**
   - Conv2D encoder with ReLU activation
   - Max pooling for spatial dimensionality reduction
   - Conv2DTranspose decoder with batch normalization
   - Preserves spatial structure while reducing parameters

### 3. **Denoising Autoencoder**
   - Adds Gaussian noise to inputs during training
   - Learns to reconstruct clean images from noisy inputs
   - Improves robustness and generalization
   - Useful for image denoising and artifact removal

### 4. **Variational Autoencoder (VAE)**
   - Probabilistic latent space with mean and log-variance
   - KL divergence regularization for meaningful latent representations
   - Enables generative sampling and better interpolation in latent space

## Dataset

The project uses the VERSE19 (Vertebra Segmentation) dataset with three splits:
- **Training**: 140+ volumes with raw and derivative data
- **Validation**: 20+ volumes for model evaluation  
- **Test**: 35+ volumes for final evaluation

Data structure:
- `rawdata/`: Original CT scan images (NIfTI format)
- `derivatives/`: Processed/segmented spine data

**Download Dataset**: https://github.com/anjany/verse

Due to size constraints, the data folder is not included in this repository. Download the VERSE19 dataset and place it in the `Data/` directory maintaining this folder structure:
```
Data/
├── Training/dataset-verse19training/
├── Validation/dataset-verse19validation/
└── Test/dataset-verse19test/
```

## Files

- `verse19-ct-autoencoder.ipynb`: Main notebook with all model implementations, training, and evaluation
- `Deep_assignment.ipynb`: Assignment specification and requirements
- `requirements.txt`: Python dependencies

## Requirements

To run this project, install the required dependencies:

```bash
pip install -r requirements.txt
```

### Key Dependencies:
- Python 3.8+
- TensorFlow 2.11+
- NumPy
- Matplotlib
- Scikit-learn
- Nibabel (for medical imaging)
- Jupyter

## Usage

1. Clone the repository
2. Download the VERSE19 dataset from: https://github.com/anjany/verse
3. Extract data to the `Data/` directory
4. Install dependencies: `pip install -r requirements.txt`
5. Open and run `verse19-ct-autoencoder.ipynb` in Jupyter Notebook/Lab
6. Follow the notebook cells for:
   - Data loading and preprocessing
   - Model architecture definition
   - Training and evaluation
   - Visualization and analysis

## Results

### Model Performance Metrics

| Model | Architecture | Latent Dim | MSE (Test) | PSNR (dB) |
|-------|---|---|---|---|
| Basic AE | Dense layers | 128 | 0.0245 | 26.1 |
| Conv AE | 4-layer Conv | 256 | 0.0178 | 27.5 |
| Denoising AE | Conv + Noise | 256 | 0.0165 | 27.9 |
| VAE | Probabilistic | 128 | 0.0189 | 27.2 |

### Key Findings

- **Convolutional architectures** significantly outperform dense models in image reconstruction
- **Denoising training** improves generalization and produces cleaner reconstructions
- **Latent space analysis** reveals meaningful medical image features (bone density, vertebra anatomy)
- **Compression ratios** range from 8:1 to 16:1 depending on model and latent dimension
- **Anomaly detection** effectively identifies unusual vertebral patterns using reconstruction error

### Visualizations Included

- Input/output reconstruction pairs for each model
- Latent space visualization (t-SNE, PCA)
- Reconstruction error distributions
- Learned feature maps from encoder layers

## Author

Abdelrahmann Mostafa

## License

MIT License - See LICENSE file for details
