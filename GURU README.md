📊 Startup Acquisitions Data Analysis

📌 Project Overview

This project analyzes a dataset of startup acquisitions using Python. The goal is to explore patterns in acquisition data, understand relationships between variables, and perform basic data cleaning and visualization.

The analysis is performed in a Jupyter Notebook (Google Colab compatible), leveraging popular data science libraries.

---

📂 Dataset

The dataset used:

- File name: "acquisitions (1).csv"
- Total records: 9,562
- Total columns: 12

Key Columns:

- "id" – Unique identifier
- "acquisition_id" – Acquisition reference ID
- "acquiring_object_id" – Company acquiring another company
- "acquired_object_id" – Company being acquired
- "term_code" – Type of acquisition deal
- "price_amount" – Acquisition value
- "price_currency_code" – Currency of transaction
- "acquired_at" – Date of acquisition
- "source_url" – Reference link
- "source_description" – Description of source
- "created_at", "updated_at" – Record timestamps

---

⚙️ Technologies Used

- Python 3
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Google Colab

---

🔍 Analysis Steps

1. Import Libraries

Basic data science libraries are imported:

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

---

2. Load Dataset

df = pd.read_csv("/content/acquisitions (1).csv")

---

3. Data Exploration

- Checked dataset structure using:

df.info()
df.shape

---

4. Missing Values Analysis

df.isnull().sum()

Key Findings:

- "term_code" has a large number of missing values (~7656)
- "source_url" and "source_description" also contain missing data
- Minor missing values in "acquired_object_id", "price_currency_code", and "acquired_at"

---

5. Correlation Analysis

A heatmap was used to visualize relationships between numerical variables:

plt.figure(figsize=(10,6))
sns.heatmap(df.corr(numeric_only=True), annot=True, cmap="coolwarm")
plt.title("Correlation Heatmap")
plt.show()

---

📈 Key Insights

- The dataset is largely complete for numeric fields like "price_amount"
- Significant missing data exists in categorical and descriptive fields
- Correlation analysis is limited due to few numeric columns
- Most insights will likely come from:
  - Time-based analysis ("acquired_at")
  - Currency normalization
  - Acquisition trends

---

🚀 Possible Improvements

- Handle missing values (imputation or removal)
- Convert "acquired_at" to datetime format
- Normalize currency values for better comparison
- Perform:
  - Time series analysis
  - Top acquiring companies analysis
  - Acquisition value distribution

---

▶️ How to Run

1. Open the notebook in Google Colab
2. Upload the dataset file
3. Run all cells sequentially

---

📌 Future Scope

- Build predictive models for acquisition pricing
- Visualize acquisition trends over time
- Create dashboards using tools like Power BI or Streamlit

---

👨‍💻 Author

Guru_DS

---

📎 Note

Make sure the dataset path is correctly updated when running outside Google Colab.

---
