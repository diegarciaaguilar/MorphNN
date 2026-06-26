# Spectral Morphology Classification with Stacking Neural Networks

This repository contains the code and supplementary material associated with the article on galaxy morphological classification using one-dimensional spectra and artificial neural networks. The main goal of the project is to evaluate whether spectral information can support the binary morphological classification of galaxies into early-type and late-type systems, and to report the performance of individual neural-network models and a stacking ensemble.

## Repository contents

```text
.
├── Ensemble.ipynb
├── morphoANN_Outliers/
└── README.md
```

### `Ensemble.ipynb`

This notebook contains the main workflow described in the article, including:

* preprocessing of the spectroscopic data;
* preparation of the training and test samples;
* implementation of the neural-network models used as base learners;
* construction of the stacking ensemble;
* threshold selection and model evaluation;
* computation of the reported metrics, including accuracy, AUC, and threshold-dependent performance measurements.

The notebook is intended to reproduce the main numerical results discussed in the manuscript, particularly the comparison between the individual models and the stacking classifier.

### `morphoANN_Outliers/`

This directory contains the outlier or misclassified galaxy cases discussed in the article. For each object, the material includes:

* the corresponding galaxy image;
* the associated spectrum;
* a brief visual and spectral description;
* a short comment explaining why the model may have failed to classify the object correctly.

These examples are provided as supplementary material to help interpret the limitations of the spectral classifier, especially in ambiguous, transitional, edge-on, or visually complex systems.

## Scientific context

The project explores the connection between spectral information and galaxy morphology. Instead of relying exclusively on image-based visual classification, the models use spectra as input and learn patterns related to stellar populations, emission lines, continuum shape, and other spectral features that may correlate with morphology.

The stacking approach combines the predictions of several neural-network models in order to improve the robustness of the final classification. The results reported in the article show that the ensemble strategy can provide competitive performance and can help reduce the dependence on any single architecture.

## Requirements

The notebook was developed in Python using common scientific and machine-learning libraries. A typical environment should include:

```text
python >= 3.9
numpy
pandas
matplotlib
scikit-learn
tensorflow / keras
keras-tuner
jupyter
```

Additional packages may be required depending on the local configuration used to read the data files or reproduce the exact plots from the article.

## Basic usage

1. Clone the repository:

```bash
git clone https://github.com/<user>/<repository>.git
cd <repository>
```

2. Create and activate a Python environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

On Windows:

```bash
.venv\Scripts\activate
```

3. Install the required packages:

```bash
pip install numpy pandas matplotlib scikit-learn tensorflow keras-tuner jupyter
```

4. Open the notebook:

```bash
jupyter notebook Ensemble.ipynb
```

5. Run the notebook cells in order to reproduce the preprocessing, model training, stacking procedure, and metric calculations.

## Notes on reproducibility

Neural-network training may vary slightly between executions because of random initialization, hardware differences, and backend-level numerical behavior. For this reason, small variations in the reported metrics may occur unless the same random seeds, package versions, and computational environment are used.

The notebook includes the workflow used to obtain the metrics reported in the article, but users should verify local paths, input data availability, and package versions before running the full pipeline.

## Outlier analysis

The `morphoANN_Outliers/` directory is intended to complement the quantitative metrics with a qualitative inspection of difficult cases. These objects are useful for understanding the failure modes of the classifier, including cases where the spectrum and visual morphology may provide partially conflicting information.

## Citation

If you use this repository, please cite the associated article:

```bibtex
@article{GarciaAguilar2026SpectralMorphologyANN,
  author  = {García Aguilar, Diego and collaborators},
  title   = {Spectral galaxy morphology classification with artificial neural networks and stacking ensembles},
  journal = {To be updated},
  year    = {2026},
  note    = {Manuscript in preparation / under review}
}
```

Please update the citation information once the final bibliographic details of the article are available.

## License

Add the license information for this repository here. If the code is intended to be openly reusable, consider adding an open-source license such as MIT, BSD-3-Clause, or GPL-3.0.

## Contact

For questions about the code, data processing, or supplementary outlier material, please contact the repository author or open an issue in this GitHub repository.
