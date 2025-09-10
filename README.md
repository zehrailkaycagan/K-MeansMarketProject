# K-Means Market Segmentation Project

This project segments customers into groups based on satisfaction and loyalty scores using the K-Means clustering algorithm. The workflow is implemented in a Jupyter Notebook.

## Contents
- `K-means market segmentasyon.ipynb`: Notebook containing data analysis and modeling steps
- `market_tatmin_sadakat.csv`: Sample dataset with 30 observations (columns: `tatmin` (satisfaction), `sadakat` (loyalty))

## Tech Stack
- Python 3.10+
- NumPy, Pandas
- Matplotlib, Seaborn
- scikit-learn (KMeans, preprocessing)

## Problem Statement
Given a two-dimensional customer dataset (satisfaction, loyalty), group customers into homogeneous segments and visualize them from a marketing/segmentation perspective.

## Approach & Methodology
1. Data Loading & Exploration
   - Read `market_tatmin_sadakat.csv`.
   - Inspect the table and visualize the `tatmin`–`sadakat` scatter plot.

2. Model 1 – K-Means on Raw Data (2 clusters example)
   - Fit `KMeans(n_clusters=2, n_init=10)` on raw data.
   - Append predicted labels to a copy of the data (`clusters['kume_tahmin']`).
   - Visualize colored clusters.

3. Feature Scaling
   - Since K-Means relies on Euclidean distance, standardize features with `preprocessing.scale(x)` to obtain `x_scaled`.

4. Choosing K – Elbow Method
   - For `i = 1..9`, fit KMeans on `x_scaled` and record `inertia_` values (`kikt`).
   - Plot `Number of Clusters vs Within-Cluster Sum of Squares (WCSS)` and identify the “elbow.”

5. Model 2 – K-Means on Scaled Data (Selected K)
   - As an example, train `KMeans(n_clusters=4, n_init=10)` on `x_scaled`.
   - Append predictions to `clusters_new['kume_tahmin']` and visualize colored segments.

## Key Outputs
- Initial scatter plots: Validate data spread.
- Elbow plot: Shows how inertia decreases with K and helps choose a reasonable cluster count.
- Final cluster plot: Colored segment visualization on scaled features with the selected K.

Note: The notebook demonstrates `K=4` as an example. Depending on the business context, testing K in the range 2–5 (or beyond) may yield a more suitable segmentation.

## How to Run
1. Prepare environment
   ```bash
   # (Optional) Virtual environment
   python -m venv .venv
   source .venv/bin/activate   # Windows PowerShell: .venv\Scripts\Activate

   # Dependencies
   pip install -U pip
   pip install numpy pandas matplotlib seaborn scikit-learn jupyter
   ```

2. Open and run the notebook
   ```bash
   jupyter notebook "K-means market segmentasyon.ipynb"
   ```

## Project Structure
```
K-MeansMarketProject/
├─ K-means market segmentasyon.ipynb
├─ market_tatmin_sadakat.csv
└─ README.md
```

## License
This project is an educational example. The dataset and notebook may be reviewed and adapted freely.
