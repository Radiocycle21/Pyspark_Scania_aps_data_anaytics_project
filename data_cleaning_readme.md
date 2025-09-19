# 🧹 Data Cleaning – APS Failure Dataset

This document summarizes the data cleaning process performed on the Scania APS Failure Dataset before Exploratory Data Analysis (EDA).

---

## 📌 Steps Performed

1. **Handled missing values**
   - Original dataset contained `"na"` strings for missing values.
   - Replaced `"na"` with proper `NULL` values.

2. **Type conversion**
   - All sensor columns (except `class`) were originally stored as `STRING`.
   - Converted to `FLOAT`, rounded, and finally cast to `BIGINT` for consistency.
   - Ensures numerical operations and statistics can be performed.

3. **Target variable cleanup**
   - The `class` column was categorical (`pos`, `neg`).
   - Converted into a binary integer:
     - `pos` → `1` (failure)
     - `neg` → `0` (normal)

4. **Table versions created (Python / PySpark)**
   - `df_clean_long` → numeric conversion.
   - `df_clean_final` → final dataset with binary target.

5. **Table versions created (SQL / Databricks tables)**
   - `aps_all` → combined training & test dataset.
   - `aps_all_clean` → NA → null cleaning.
   - `aps_all_clean_long` → numeric conversion.
   - `aps_clean_final` → final cleaned dataset with binary target.

---

## ✅ Current Status
- Dataset is fully cleaned and standardized.  
- Ready for **Exploratory Data Analysis (EDA)** phase.  

---

## 📂 Repo Structure (relevant parts)

