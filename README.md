
# Jess Protein Quantification Analysis

This Python script processes output from a **Jess Simple Western Assay**, fits a **quadratic standard curve**, and back-calculates protein concentrations for experimental samples. It also produces a summary bar plot with standard deviations.

---

## 📂 Overview

The script performs the following key steps:

1. **Imports raw data** from a CSV file (`jesstestdata.csv`)
2. **Filters sample and standard data**
3. **Fits a quadratic curve** to the standard curve data
4. **Calculates R²** to assess the fit quality
5. **Back-calculates sample concentrations** from measured area values
6. **Accounts for dilution and sample volume**
7. **Generates a summary table** of mean, standard deviation, and coefficient of variation (CV) for each sample
8. **Plots a bar graph** of original protein concentrations with error bars

---

## 📋 Requirements

This script uses the following Python packages:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`

Install all dependencies using:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## 📁 File Structure

```bash
project-folder/
├── data_example/
│   └── jesstestdata.csv          # Raw input file from Jess instrument
├── jess_analysis_script.py       # This analysis script
└── README.md                     # This file
```

---

## 🧪 Data Input

- The input CSV file (`jesstestdata.csv`) should contain `Sample` and `Area` columns.
- Standards must be labeled with "Standard" or "STD" and listed in descending order of concentration.

---

## ⚙️ Key Parameters

- **Standard concentrations (ug/mL)**:  
  Defined as `(1.75, 1.5, 1.25, 1.0, 0.75, 0.5)`

- **Sample volumes (µL)**:  
  Set in `samp_vols` — used for back-calculating original concentrations

- **Quadratic model**:  
  Fitted using `np.polyfit(degree=2)` on standards data

---

## 📊 Output

- The script prints:
  - The **quadratic equation** used for the standard curve
  - The **R² value** of the fit
- A bar plot is generated showing:
  - **Mean original concentration per sample**
  - **Standard deviation as error bars**
- A summary dataframe is created showing:
  - **Mean**, **standard deviation**, and **CV (%)** per sample

---

## ✅ Notes

- If you change the number of samples or volumes, update the `num_samp` and `samp_vols` variables.
- Ensure the sample naming is consistent so the regex filtering works properly.

---

## 📞 Contact

If you encounter any issues with this script or have questions about how to adapt it to a new dataset, please reach out to the script author.
