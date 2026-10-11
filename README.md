# Google Play Store Apps - Data Cleaning & Exploratory Data Analysis (EDA)

An end-to-end Exploratory Data Analysis (EDA) and data preprocessing pipeline on the **Google Play Store Apps** dataset. This project cleans raw, messy mobile application data and uncovers key insights regarding app categories, pricing models, user ratings, download installs, and Android version compatibility.

---

## 📋 Table of Contents
- [Project Overview](#project-overview)
- [Dataset Features](#dataset-features)
- [Data Preprocessing & Cleaning Steps](#data-preprocessing--cleaning-steps)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Key Insights](#key-insights)
- [Tech Stack](#tech-stack)
- [Usage / Getting Started](#usage--getting-started)

---

## 🔍 Project Overview
The Google Play Store dataset contains rich information about thousands of Android applications. However, raw real-world data often contains inconsistencies, formatting errors, missing values, and duplicates. This project demonstrates a robust data science workflow:
1. **Data Inspection & Profiling**: Examining data types, missing values, and statistical summaries (`info()`, `describe()`).
2. **Data Cleaning & Transformation**: Handling corrupt rows, converting object types to numeric/datetime formats, and parsing complex string units (e.g., file sizes in MB/KB, install counts with `+` and `,`, and currency prices).
3. **Deduplication**: Removing duplicate records and redundant app entries.
4. **Exploratory Data Analysis**: Analyzing categorical distributions and numerical distributions using visualizations.

---

## 📊 Dataset Features
The raw dataset consists of **10,841 rows** and **13 columns**:
* `App`: Application name
* `Category`: Category the app belongs to (e.g., FAMILY, GAME, TOOLS)
* `Rating`: Overall user rating of the app
* `Reviews`: Total number of user reviews
* `Size`: Size of the app (in MB/KB or varies with device)
* `Installs`: Total number of downloads/installs
* `Type`: Free or Paid
* `Price`: Price of the app (0 for free apps)
* `Content Rating`: Target audience age group (e.g., Everyone, Teen, Mature 17+)
* `Genres`: Sub-genres/genres associated with the app
* `Last Updated`: Date when the app was last updated
* `Current Ver`: Current version of the app
* `Android Ver`: Minimum required Android version

---

## 🛠️ Data Preprocessing & Cleaning Steps

The data cleaning pipeline systematically resolves data quality issues:
* **Duplicate Removal**: Identified and removed **483 exact duplicate rows**. Further deduplicated based on unique app names (`App` column, keeping the first occurrence), reducing the dataset to **9,659 unique apps**.
* **Outlier & Error Correction**: Cleaned erroneous rows containing corrupted column shifts (e.g., invalid category and rating mappings).
* **Feature Engineering & Type Conversions**:
  * **Reviews**: Converted from `object` to integer (`int32`).
  * **Size**: Parsed size strings ending in `'M'` (Megabytes converted to Kilobytes) and `'k'` (Kilobytes), converting them into clean numerical float values.
  * **Installs**: Removed `+` and `,` symbols and converted to integer (`int32`).
  * **Price**: Removed the `$` currency sign and converted to float (`float64`).
  * **Last Updated**: Converted to datetime objects and extracted discrete `day`, `month`, and `year` features for temporal analysis.
  * **Android Ver**: Cleaned string formatting by stripping `" and up"` and `"Varies with device"`.

---

## 📈 Exploratory Data Analysis (EDA)

The EDA phase explores both categorical and numerical variables:
* **Categorical Analysis**: 
  * Analyzed frequency distributions and proportions across `Category`, `Type` (Free vs. Paid), `Content Rating`, and `Genres` using value counts and frequency tables.
  * Highlighted dominant categories such as **FAMILY** (~19%), **GAME** (~9.9%), and **TOOLS** (~8.6%).
* **Numerical Analysis**:
  * Generated five-point statistical summaries and distribution plots (`distplot`, histograms, box plots) for `Rating`, `Reviews`, `Size`, `Installs`, and `Price`.
  * Explored pricing distributions showing that the vast majority of apps (~92.2%) are **Free**, while ~7.8% are **Paid**.

---

## 💡 Key Insights
* **App Distribution**: The Google Play Store is heavily dominated by **Family**, **Game**, and **Tools** applications.
* **Monetization Model**: Free apps vastly outnumber paid apps, indicating that developers rely heavily on in-app purchases and advertisements rather than upfront purchase costs.
* **Ratings**: Average app ratings cluster tightly around a mean of **4.19 / 5.0**, showing a positive skew in user feedback.

---

## ⚙️ Tech Stack
* **Language**: Python
* **Libraries**: 
  * `pandas`, `numpy` for data manipulation, cleaning, and transformation.
  * `matplotlib`, `seaborn` for generating statistical plots and data visualizations.

---

## 🚀 Usage / Getting Started
To run the analysis notebook or script:
```bash

# Install dependencies
pip install pandas numpy matplotlib seaborn

# Run the Jupyter Notebook
jupyter notebook