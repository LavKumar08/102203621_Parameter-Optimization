# NuSVC Optimization on Dry Bean Dataset

This project performs hyperparameter tuning for the `NuSVC` model using a random search strategy on the [Dry Bean Dataset](https://archive.ics.uci.edu/ml/datasets/Dry+Bean+Dataset) from the UCI Machine Learning Repository.

---

## 📂 Dataset

**Name:** Dry Bean Dataset  
**Source:** UCI Machine Learning Repository  
**Download Link:** [https://archive.ics.uci.edu/ml/machine-learning-databases/00602/DryBeanDataset.zip](https://archive.ics.uci.edu/ml/machine-learning-databases/00602/DryBeanDataset.zip)  
**Description:**  
The dataset contains physical and morphological features of 7 types of dry beans (e.g., Barbunya, Seker, Horoz, etc.).

---

## ⚙️ Project Workflow

1. **Download and unzip** the Dry Bean dataset from UCI.
2. **Read and preprocess** the Excel file:
   - Encode the categorical class label.
   - Scale the numerical features using `StandardScaler`.
3. **Model Training:**
   - Use `NuSVC` from `sklearn.svm`.
   - Hyperparameters tuned:
     - `kernel`: `linear`, `rbf`, `poly`, `sigmoid`
     - `nu`: Randomly sampled from a uniform range between 0.01 and 0.3
   - Perform 30 random iterations per split.
4. **Evaluation:**
   - Repeat across 10 different train-test splits (stratified).
   - Track the best accuracy and corresponding parameters per split.
5. **Save Results:**
   - Store results in `NuSVC_Optimization_Results.xlsx`
   - Plot and save convergence of accuracy vs. iteration for the best run.

---

## 📊 Files Generated

- `NuSVC_Optimization_Results.xlsx`: Accuracy and hyperparameters for each split.
- `NuSVC_Convergence_BestRun.png`: Plot showing accuracy evolution across iterations for the best run.
- Python script (or notebook): Executes all steps from download to result visualization.

---

## 🧠 Libraries Used

- `pandas`
- `numpy`
- `matplotlib`
- `sklearn` (`NuSVC`, `LabelEncoder`, `StandardScaler`, `train_test_split`, `accuracy_score`)
- `zipfile`, `os`, `wget` (for downloading/extracting data)

---

## 🔍 Example Output

| Split   | Top Accuracy (%) | Top Parameters     |
|---------|------------------|--------------------|
| Run_1   | 94.56             | rbf, nu=0.12       |
| Run_2   | 94.31             | linear, nu=0.09    |
| ...     | ...              | ...                |

---

## 📌 Notes

- Invalid `nu` values (leading to `ValueError`) are skipped.
- Accuracy is computed using the `accuracy_score` from scikit-learn.
- You can increase the number of iterations for more exhaustive tuning.

---

