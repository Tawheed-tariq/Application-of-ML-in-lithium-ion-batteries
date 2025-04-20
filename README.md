# Application of ML in lithium-io-batteries

This repository presents a study focused on predicting the electrochemical performance of doped lithium nickel-cobalt-manganese (NCM) oxide cathodes used in lithium-ion batteries (LIBs). The project explores the use of machine learning (ML) models in combination with advanced feature engineering techniques to accurately predict initial discharge capacity (IC) and 50th cycle end discharge capacity (EC).

## 📌 Overview

With the ever-growing demand for high-performance LIBs, the optimization of NCM cathodes through doping has gained significant attention. However, the vast combinatorial space of potential dopants and their concentrations makes experimental exploration challenging. In this study:

- We use ML to model and predict IC and EC.
- Feature engineering techniques such as SOAP, MBTR, and n-gram are employed for representing the atomic structure.
- ML models including LightGBM, XGBoost, and Random Forest are trained and evaluated.

## 📂 Dataset

- The dataset contains 168 doped NCM compositions with 20 dopant variations.
- Each data point includes:
  - Material composition
  - Lattice constants
  - Crystal volume
  - Operating voltage
  - Dopant properties
  - Atomic and molar masses

### Target Variables
- **IC**: Initial discharge capacity (mAh/g)
- **EC**: End capacity after 50 cycles (mAh/g)

## 🔧 Feature Engineering Techniques

### 1. Smooth Overlap of Atomic Positions (SOAP)
Encodes local atomic environments using Gaussian smearing and spherical harmonics.
Reference: [Bartók et al., 2013](https://doi.org/10.1103/PhysRevB.87.184115)

### 2. Many-Body Tensor Representation (MBTR)
Represents structural information including distances and angles between atoms.
Reference: [Huo & Rupp, 2022](https://doi.org/10.1038/s41524-021-00678-7)

### 3. n-Gram Representation
Uses graph-based analysis of atomic connections to create histograms of atomic sequences.
Reference: [Ward et al., 2016](https://doi.org/10.1038/npjcompumats.2016.28)

## 🤖 Machine Learning Models

- **XGBoost**
- **LightGBM**
- **Random Forest**

### Training Details:
- 80/20 Train-Test Split
- 5-Fold Cross-Validation
- GridSearchCV for Hyperparameter Tuning

## 🧪 Evaluation Metrics

- Root Mean Squared Error (RMSE)
- R² Score

## 📝 Results

- Achieved RMSE as low as **12.48 mAh/g** (IC) and **11.75 mAh/g** (EC)
- Best results obtained with XGBoost using MBTR descriptors

## 📚 References

- Ko et al., 2023 – [doi:10.1016/j.jallcom.2023.172840](https://doi.org/10.1016/j.jallcom.2023.172840)
- Sutton et al., 2020 – [doi:10.1038/s41524-020-00362-y](https://doi.org/10.1038/s41524-020-00362-y)
- Bartók et al., 2013 – [doi:10.1103/PhysRevB.87.184115](https://doi.org/10.1103/PhysRevB.87.184115)
- Huo & Rupp, 2022 – [doi:10.1038/s41524-021-00678-7](https://doi.org/10.1038/s41524-021-00678-7)
- Ward et al., 2016 – [doi:10.1038/npjcompumats.2016.28](https://doi.org/10.1038/npjcompumats.2016.28)
- Kim et al., 2021 – [doi:10.1021/acscentsci.1c00611](https://doi.org/10.1021/acscentsci.1c00611)

## 📈 Future Work

- Incorporating deep learning models for end-to-end learning
- Exploring transfer learning between similar battery chemistries
- Extending the model to predict additional battery performance metrics

