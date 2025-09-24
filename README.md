# Heart Attack Prediction Enhancement through Data Augmentation and Preprocessing

This project proposes a novel approach to enhance the performance of heart attack prediction models. Our methodology focuses on advanced data handling, meticulous cleaning, and augmenting the data volume of the original dataset to achieve a significant boost in model accuracy and reliability.

## 📖 Abstract

Cardiovascular diseases are a leading cause of death globally, making accurate prediction of heart attacks a critical area of research in healthcare. While many machine learning models have been developed for this purpose, their performance is often limited by the quality and volume of the available data. This project addresses these limitations by introducing a systematic pipeline for data preprocessing, cleaning, and augmentation. By enriching the dataset and refining the features, we demonstrate a substantial improvement in the predictive power of various machine learning models.

## 📂 Dataset

The primary dataset for this study is sourced from Kaggle, which is a common benchmark for heart disease prediction. Our work involves several stages of data transformation, resulting in multiple versions of the dataset:

- **Original Data:** Located in `data/kaggle/`.
- **Cleaned & Merged Data:** Intermediate datasets after cleaning and merging are available in the `data/` directory (e.g., `phase1_post_clean.csv`, `phase2_post_clean.csv`).
- **PCA-transformed Data:** Datasets after applying Principal Component Analysis (PCA) are also in the `data/` directory (e.g., `phase3_post_pca.csv`).

## ⚙️ Methodology

Our workflow is divided into several phases, each documented in a series of Jupyter notebooks:

### Phase 1 & 2: Data Preprocessing and Initial Analysis

- **Exploratory Data Analysis (EDA):** We begin with a thorough EDA to understand the initial dataset's characteristics, distributions, and potential issues. (`src/phase1/phase1.1_EDA.ipynb`)
- **Feature Correlation and Duplication Analysis:** We analyze the correlation between features and identify any duplicate entries to ensure data quality. (`src/phase1/phase1.5_feature-correlation.ipynb`, `src/phase1/phase1.6_duplication-analysis.ipynb`)
- **Data Cleaning:** This central step involves handling missing values, correcting inconsistencies, and preparing the data for modeling. (`src/phase1-2_data_preprocessing.ipynb`)

### Phase 3 & 4: Feature Engineering and Data Augmentation

- **Data Merging:** We augment the dataset by merging it with other relevant data sources. (`src/phase3-4/merging_data.ipynb`)
- **Principal Component Analysis (PCA):** To reduce dimensionality and capture the most important information, we apply PCA to the dataset. (`src/phase3-4/phase3_pca.ipynb`, `src/phase3-4/phase4_pca.ipynb`)

## 🤖 Modeling

We trained and evaluated several state-of-the-art machine learning models to predict the likelihood of a heart attack. The notebooks for training each model can be found in the `models/` directory:

- **CatBoost:** `models/catboost.ipynb`
- **Extra Trees:** `models/extraTree.ipynb`
- **Random Forest:** `models/random forest.ipynb`
- **XGBoost:** `models/train_xgboost.ipynb`

## 📊 Results

The results of our experiments show a consistent performance improvement across all models after applying our data enhancement pipeline. For detailed visualizations of the model performance and comparisons, please refer to the `utils/res-visualization.ipynb` notebook.

## 🚀 How to Run

To reproduce the results of this project, please follow the notebooks in the following order:

1.  **Data Preprocessing:** Start with the notebooks in `src/phase1/`, followed by `src/phase1-2_data_preprocessing.ipynb`.
2.  **Feature Engineering:** Run the notebooks in `src/phase3-4/`.
3.  **Modeling:** Train the models using the notebooks in the `models/` directory.
4.  **Result Visualization:** Finally, visualize the results with `utils/res-visualization.ipynb`.

## 📁 Workspace Structure

```
├── README.md
├── data/
│   ├── base.csv
│   ├── phase1_post_clean.csv
│   ├── phase1_pre_merge.csv
│   ├── phase2_post_clean.csv
│   ├── phase3_post_pca.csv
│   ├── phase4_post_pca_ca-thal-included.csv
│   └── kaggle/
│       ├── kaggle_heart_attack_healthcare_base.csv
│       ├── kaggle_heart_attack_remap.csv
│       └── kaggle_heart_disease_remap.csv
├── models/
│   ├── catboost.ipynb
│   ├── extraTree.ipynb
│   ├── random forest.ipynb
│   └── train_xgboost.ipynb
├── src/
│   ├── phase1-2_data_preprocessing.ipynb
│   ├── phase1/
│   │   ├── phase1.1_EDA.ipynb
│   │   ├── phase1.5_feature-correlation.ipynb
│   │   └── phase1.6_duplication-analysis.ipynb
│   └── phase3-4/
│       ├── merging_data.ipynb
│       ├── phase3_pca.ipynb
│       └── phase4_pca.ipynb
└── utils/
    └── res-visualization.ipynb
```
