# 102203621_Parameter-Optimization
# Parameter Optimization Assignment - SVM

This repository contains code and results for optimizing Support Vector Machine (SVM) parameters using randomized sampling over multiple data splits. The task was assigned as part of the **Data Science curriculum** and aims to compare classification performance under different configurations.

---

## 📌 Dataset Used

- **Name**: [Letter Recognition Data Set](https://www.openml.org/d/6)
- **Source**: UCI Machine Learning Repository via OpenML
- **Description**: The dataset contains 20,000 samples of capital letters represented by 16 numerical features derived from character images.

---

## ⚙️ Objective

- Use a multi-class dataset with 5,000–30,000 samples
- Generate 10 different random 70-30 train-test splits
- Perform SVM optimization on each using 100 iterations
- Track and save the best accuracy and corresponding parameters for each sample
- Plot a convergence graph for the best-performing sample

---

## 🧪 Implementation

- Language: **Python**
- Libraries: `scikit-learn`, `numpy`, `pandas`, `matplotlib`, `tqdm`
- Parameter tuning using `ParameterSampler` from `scikit-learn`
- Hyperparameters optimized:
  - `kernel`: linear, rbf, poly, sigmoid
  - `C`: sampled from uniform distribution (0.1 to 10)
  - `gamma`: 'scale', 'auto'

---

## 📈 Results

- `svm_optimization_results.csv` contains the best accuracy and SVM parameters for each of the 10 samples.
- A convergence graph is generated (`convergence_graph.png`) showing accuracy over iterations for the best sample.

Example from CSV:
