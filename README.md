# VERSE19 CT Autoencoder - Deep Learning Assignment

A deep learning project for medical image analysis using autoencoders on CT (Computed Tomography) spine scans from the VERSE19 dataset.

## Project Overview

This assignment focuses on developing and training autoencoder models to process and analyze vertebral CT scan images.

## Dataset

The project uses the VERSE19 (Vertebra Segmentation) dataset with three splits:
- **Training**: Training dataset with raw and derivative data
- **Validation**: Validation dataset for model evaluation
- **Test**: Test dataset for final evaluation

Data structure:
- `rawdata/`: Original CT scan images
- `derivatives/`: Processed/segmented data

## Files

- `verse19-ct-autoencoder.ipynb`: Main notebook containing the project implementation

## Requirements

To run this project, install the required dependencies:

```bash
pip install -r requirements.txt
```

### Key Dependencies:
- Python 3.8+
- PyTorch
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter

## Usage

1. Clone the repository
2. Install dependencies: `pip install -r requirements.txt`
3. Open and run `verse19-ct-autoencoder.ipynb` in Jupyter Notebook/Lab
4. Follow the notebook cells for model training, evaluation, and visualization

## Dataset Download

The VERSE19 dataset can be downloaded from the official repository. Due to size constraints, the data folder is not included in this repository. Download and place it in the `Data/` directory maintaining the folder structure.

## Results

[Add your results, metrics, and findings here]

## Author

[Your Name]

## License

[License information, if applicable]
