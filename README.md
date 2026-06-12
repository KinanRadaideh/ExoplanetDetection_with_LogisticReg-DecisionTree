# Exoplanet Detection using Machine Learning

This project applies machine learning techniques to classify Kepler Objects of Interest (KOIs) as either confirmed exoplanets or false positives using NASA Kepler data.

The project compares a Decision Tree classifier with Logistic Regression after removing leakage-prone features such as NASA pipeline disposition flags and confidence scores. The goal is to force the models to learn from physical and astronomical parameters rather than from pre-existing classification hints.

## Project Files

* `ExoplanetDetectionProject_Code.ipynb`
  Main Jupyter notebook containing preprocessing, exploratory data analysis, model training, tuning, and evaluation.

* `Exoplanet_Detection_using_Machine_Learning_Techniques.pdf`
  Final project report.

* `Project Proposal.pdf`
  Original project proposal.

* `Dataset Fields Explanation.pdf`
  Explanation of the dataset columns in simpler terms.

* `original_dataset.csv`
  Original Kepler dataset used in the project.

* `df_fully_preprocessed.csv`
  Cleaned and preprocessed dataset used for modeling.

## Dataset

The dataset is based on Kepler Objects of Interest (KOIs), where each instance represents a possible exoplanet candidate detected by the Kepler Space Telescope.

The original target variable is `koi_disposition`, which includes these categories:

* `CONFIRMED`
* `FALSE POSITIVE`
* `CANDIDATE`

For this project, candidate instances were removed to create a binary classification task between confirmed exoplanets and false positives.

## Methods Used

* Data cleaning and preprocessing
* Data leakage removal
* Exploratory Data Analysis
* Feature selection
* Decision Tree classification
* Logistic Regression
* Grid Search
* Stratified Cross-Validation
* Confusion Matrix
* ROC Curve and AUC evaluation

## Results

The Decision Tree model performed better than Logistic Regression after leakage-prone features were removed.

| Model               | Accuracy | Precision | Recall | F1-Score |
| ------------------- | -------: | --------: | -----: | -------: |
| Decision Tree       |     0.90 |      0.86 |   0.82 |     0.84 |
| Logistic Regression |     0.84 |      0.74 |   0.78 |     0.76 |

The final Decision Tree model achieved an AUC of approximately 0.942.

## How to Run

1. Clone or download this repository.
2. Open `ExoplanetDetectionProject_Code.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
3. Make sure all files remain in the same folder as the notebook.
4. Run the notebook cells in order.

## Requirements

This project uses:

* Python
* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn

## Notes

Because all files are stored in the same folder, the notebook should read the CSV files using relative paths such as:

```python
original_df = pd.read_csv("original_dataset.csv")
df = pd.read_csv("df_fully_preprocessed.csv")
```

## Authors

* Kinan Radaideh
* Mohamad Almasri
