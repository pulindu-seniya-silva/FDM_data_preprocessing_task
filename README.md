🧹 Loan Data Preprocessing

This repository contains a data preprocessing pipeline applied to a Loan dataset (614 rows × 13 columns).
The project follows the Fundamentals of Data Mining – Data Preprocessing lecture structure.

📂 Dataset

Source: Loan dataset (CSV file).

Attributes: Applicant details (gender, education, income, loan amount, credit history, property area, etc.) and loan approval status.

Issues in raw data:

Missing values (Gender, Dependents, Self_Employed, LoanAmount, Loan_Amount_Term, Credit_History).

Noisy/outlier values in income and loan amounts.

Mixed categorical and numeric features.

🔑 Preprocessing Steps
1. Data Cleaning

Handle missing values:

Categorical → filled with mode (most frequent).

Numeric → filled with median.

Credit_History → filled with mode (since binary categorical numeric).

Outlier treatment:

IQR capping applied to ApplicantIncome, CoapplicantIncome, LoanAmount.

Duplicates: Removed duplicates if any.

String inconsistencies: Trimmed spaces, standardized placeholders (NA, ?, None → NaN).

2. Data Transformation & Discretization

Normalization:

Min–Max scaling [0,1]

Z-score standardization

Decimal scaling

Discretization & smoothing:

Equal-width and equal-depth binning (e.g., ApplicantIncome).

Smoothing by bin mean & bin boundaries (LoanAmount).

Supervised discretization (Decision Tree based) for LoanAmount w.r.t. Loan_Status.

3. Data Reduction

Dimensionality Reduction (PCA):

Projected features into 2 principal components.

PC1 explained ~34.6% variance, PC2 ~21.1%.

4. Data Integration

Not applied here (single file dataset).

Note: Step is relevant when combining multiple data sources.

📊 Outputs

cleaned_basic.csv → Cleaned + transformed dataset (imputed, capped, normalized, discretized).

Notebook (Preprocessing.ipynb) → Step-by-step preprocessing with explanations.

🛠️ Libraries Used

pandas, numpy – data wrangling

matplotlib – visualization

scikit-learn – scaling, PCA, Decision Tree

🚀 How to Run

Open in Google Colab or local Jupyter Notebook.

Upload the raw dataset (Loan.csv).

Run the notebook cells step by step.

Final cleaned dataset will be saved as cleaned_basic.csv.

📖 Learning Outcomes

Understand real-world data quality issues (missing, noisy, inconsistent).

Apply lecture techniques:

Cleaning (missing data, noise, outliers)

Transformation (scaling, smoothing, discretization)

Reduction (PCA)

Produce a ready-to-analyze dataset.
