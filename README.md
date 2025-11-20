# Spectral Clustering & Nonlinear Dimensionality Reduction (Iris Dataset)

 
The Repository focuses on:

- Implementing **spectral clustering from scratch** on the Iris dataset
- Comparing spectral clustering with **K-Means**
- Applying and analyzing **nonlinear dimensionality reduction** methods:
  - Multidimensional Scaling (**MDS**)
  - **Isomap**
  - **Locally Linear Embedding (LLE)**

---

## Files

- `HW8.ipynb` – Main Jupyter notebook with all code, plots and analysis.
- `Data_Iris.csv` – Iris dataset in CSV format (expected in the notebook’s working directory).

> **Note:** Make sure `Data_Iris.csv` is in the same folder as the notebook or update the path in the code:
> ```python
> df = pd.read_csv("Data_Iris.csv")
> ```

---

## Question 1 – Spectral Clustering vs K-Means

In **Q1**, the notebook:

1. Loads and standardizes the Iris features.
2. Builds a **graph with 150 nodes** (one per data point).
3. Constructs an **affinity matrix** using an RBF (Gaussian) kernel.
4. Computes the **degree matrix** and the normalized matrix  
   \( L = D^{-1/2} A D^{-1/2} \).
5. Performs **eigen-decomposition** of \( L \).
6. Uses the top eigenvectors, normalizes them row-wise, and applies **K-Means** in this eigenvector space (spectral clustering).
7. Compares:
   - Spectral clustering predictions vs true species labels
   - Standard **K-Means on the original features** vs spectral clustering  
   using confusion matrices and accuracy scores.

A short comparison/analysis section summarizes which method clusters the Iris species more effectively.

---

## Question 2 – MDS, Isomap, and LLE

In **Q2**, the notebook explores **nonlinear dimensionality reduction** on the same dataset:

- **2(a) MDS (Multidimensional Scaling)**
  - Performs MDS to 2D using Euclidean distances.
  - Visualizes the 2D embedding colored by species.
  - Includes a brief analysis of class separation.

- **2(b) Isomap**
  - Runs Isomap with neighborhood sizes **k = 6, 12, 20**.
  - Plots the 2D embeddings for each value of *k*.
  - Discusses how the choice of *k* affects the global structure and separation of classes.

- **2(c) LLE (Locally Linear Embedding)**
  - Runs LLE with **k = 6, 10, 20, 25**.
  - Plots the embeddings and compares neighborhood sizes.
  - Provides analysis about local neighborhood preservation and class separation.

---

## Requirements

This project uses Python and the following libraries:

- Python 3.x
- [NumPy](https://numpy.org/)
- [Pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/)
- [scikit-learn](https://scikit-learn.org/)  
  (for `StandardScaler`, `KMeans`, `MDS`, `Isomap`, `LocallyLinearEmbedding`, metrics, etc.)
- Jupyter Notebook / JupyterLab

You can install the main dependencies with:

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
# Non-linear-dimensionality-reduction