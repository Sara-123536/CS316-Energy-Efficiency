Predicting Building Energy Efficiency

CS316 — Introduction to AI and Data Science Prince Sultan University

This project uses machine learning to predict the heating load and cooling load of residential buildings from their design features. The goal is to help design more energy-efficient buildings, which supports sustainability by reducing energy use and carbon emissions (UN SDGs 7, 11, and 13).

Team
Sarah AlSahhaf
Nourah AlMuhanna

Instructor: Dr. Heyfa Ammar

Dataset

Energy Efficiency dataset from the UCI Machine Learning Repository. Link: https://archive.ics.uci.edu/dataset/242/energy+efficiency

768 samples (building shapes simulated in Ecotect)
8 input features: relative compactness, surface area, wall area, roof area, overall height, orientation, glazing area, and glazing area distribution
2 targets: heating load and cooling load (kWh/m²)

The notebook loads the dataset automatically from UCI, so there is no file to download.

What the project does
Loads and cleans the data (checks missing values and duplicates)
Optimizes memory usage by downcasting data types
Checks outliers with boxplots and the IQR rule
Explores the data (distributions, correlation heatmap, scatter plots)
Splits and scales the data (scaler fit on training data only, to avoid leakage)
Applies PCA to handle the correlated shape features
Trains four regression models for each target: Linear Regression, Ridge, Lasso, and Polynomial (degree 2)
Evaluates the models with R², MAE, and RMSE, and confirms reliability with 5-fold cross-validation
Finds the most important features and tests which relationships are statistically significant
How to run

The easiest way is Google Colab:

Open Google Colab
Upload CS316 Energy Efficiency.ipynb (File → Upload notebook)
Run all cells (Runtime → Run all)

The first cell installs one small package (ucimlrepo); everything else uses libraries that Colab already has.

To run it locally instead, install the requirements and open the notebook in Jupyter:

pip install numpy pandas matplotlib seaborn scikit-learn scipy ucimlrepo
jupyter notebook
Results

The regression models predict both energy loads with high accuracy. The Polynomial (degree 2) model performed best, reaching an R² above 0.90 on the test set for both targets. The most influential design features were the building's overall height and relative compactness, while orientation had little effect.

(Exact numbers are shown in the notebook output.)

Files
CS316 Energy Efficiency.ipynb — the full project notebook (data prep, EDA, modeling, evaluation)
README.md — this file

Tools
Python, pandas, NumPy, scikit-learn, matplotlib, seaborn, SciPy — run in Google Colab.
