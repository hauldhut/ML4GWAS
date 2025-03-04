# Guideline for Running Code

## 1. Data

The following datasets are used in this analysis:

- `Xcont.csv`: GWAS data of *Oryza sativa*.
- `cont_LMM_grain.weight_p0.05_sort.tsv`: Grain weight data after filtering based on biological characteristics.
- `cont_LMM_time.flowering_p0.05_sort.tsv`: Time to flowering data after filtering based on biological characteristics.
- `Ycont.txt`: Output data including phenotypes for time to flowering and grain weight.
- `indep_1000_10_0.3.prune-43k.in`: Input data for the advanced regressor after filtering based on biological characteristics.

These files can be downloaded at Prepared_data: [Prepared_data](https://drive.google.com/drive/folders/1IZvDN6Wy_S8X2wP3CgPFmw4lkHA8cJaF?usp=sharing)

---

## 2. Filtering Data

**Python script:** `BI_Rice_SNPs_Pvl_Filtering.py`

- **Requirements:** Python `3.7.1`, `pandas` package.
- **Input:** Data from `Prepared_data`.
- **Process:** The script filters the data based on p-values and prepares it for model training.
- **Output:** Filtered data saved in **`Filtered_data`**.
These files can be downloaded at Filtered_data: [Filtered_data](https://drive.google.com/drive/folders/1IZvDN6Wy_S8X2wP3CgPFmw4lkHA8cJaF?usp=sharing)
---

## 3. Training Model

**Python script:** `BI_Rice_SNPs.py`

- **Requirements:** Python `3.7.1`, `pandas` package, `scikit-learn` package.
- **Input:** Data from `Filtered_data`.
- **Process:** The script trains models using multiple regression techniques.

### 3.1 Grid Search with Cross-Validation
Utilizes [`GridSearchCV`](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html) from `sklearn.model_selection` for hyperparameter tuning.
- Applied to **Random Forest Regression** and **Support Vector Regression**.

### 3.2 Random Forest Regression
[`RandomForestRegressor`](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html) from `sklearn.ensemble`.

### 3.3 Support Vector Regression
[`SVR`](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVR.html) from `sklearn.svm`.

### 3.4 Lasso Regression with Cross-Validation
[`LassoCV`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LassoCV.html) from `sklearn.linear_model`.

### 3.5 Multi-Task Lasso Regression with Cross-Validation
[`MultiTaskLassoCV`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.MultiTaskLassoCV.html) from `sklearn.linear_model`.

### 3.6 Elastic Net Regression with Cross-Validation
[`ElasticNetCV`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.ElasticNetCV.html) from `sklearn.linear_model`.

### 3.7 Multi-Task Elastic Net Regression with Cross-Validation
[`MultiTaskElasticNetCV`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.MultiTaskElasticNetCV.html) from `sklearn.linear_model`.

**Results:** The trained model outputs can be downloaded at Results: [Results](https://drive.google.com/drive/folders/1IZvDN6Wy_S8X2wP3CgPFmw4lkHA8cJaF?usp=sharing)

---

For any issues or questions, please contact the project team.
