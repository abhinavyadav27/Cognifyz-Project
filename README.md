# 🍽️ Restaurant Data Analysis | Cognifyz Technologies

A Python data analysis project on a restaurant dataset of **9,551 restaurants** and **21 columns**, completed as part of the **Cognifyz Technologies** data analytics tasks (Level 1 and Level 2). It covers data preprocessing, descriptive statistics, geospatial analysis, service-feature analysis (table booking and online delivery), price range analysis and feature engineering.

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Tools & Libraries](#-tools--libraries)
- [Dataset](#-dataset)
- [Tasks Completed](#-tasks-completed)
- [Key Findings](#-key-findings)
- [Notes & Limitations](#-notes--limitations)
- [Repository Structure](#-repository-structure)
- [How to Run](#-how-to-run)
- [Future Scope](#-future-scope)
- [Author](#-author)

---

## 📖 Project Overview

The objective is to explore restaurant data to understand how ratings, price ranges, locations and services such as table booking and online delivery relate to each other. The analysis is done end to end in a single Jupyter/Colab notebook, from loading and cleaning the data to visualization and a final correlation analysis.

---

## 🧰 Tools & Libraries

| Tool | Purpose |
|---|---|
| **Python** | Core language |
| **Pandas** | Data loading, cleaning, grouping and aggregation |
| **NumPy** | Numerical operations |
| **Matplotlib** | Charts and scatter plots |
| **Seaborn** | Histograms and heatmaps |
| **Google Colab / Jupyter** | Notebook environment |

---

## 🗂 Dataset

**File:** `Cognifyz_Restaurant_Dataset.csv` | **Size:** 9,551 rows × 21 columns

| Group | Columns |
|---|---|
| Identification | Restaurant ID, Restaurant Name |
| Location | Country Code, City, Address, Locality, Locality Verbose, Longitude, Latitude |
| Food & Cost | Cuisines, Average Cost for two, Currency, Price range |
| Services | Has Table booking, Has Online delivery, Is delivering now, Switch to order menu |
| Ratings | Aggregate rating, Rating color, Rating text, Votes |

---

## ✅ Tasks Completed

### Level 1

**Task 1: Data Exploration and Preprocessing**
- Checked shape, column names and data types
- Checked missing values (only `Cuisines` had missing values: 9 rows) and filled them with `"Unknown"`
- Checked duplicates (none found)
- Analyzed the distribution of Aggregate rating and grouped it into classes (0–2, 2–3, 3–4, 4–5)

**Task 2: Descriptive Analysis**
- Mean, median and standard deviation of numeric columns
- Restaurants by country code, top 10 cities and top 10 cuisine combinations

**Task 3: Geospatial Analysis**
- Latitude/longitude summary statistics
- Scatter plot of restaurant locations, and a version colored by Aggregate rating
- Average rating by city and restaurant distribution by country

### Level 2

**Task 4: Table Booking and Online Delivery**
- Percentage of restaurants offering table booking and online delivery
- Average rating with and without table booking
- Online delivery availability across price ranges

**Task 5: Price Range Analysis**
- Distribution of restaurants across price ranges (1–4)
- Average rating by price range

**Task 6: Feature Engineering**
- Created `Restaurant Name Length` and `Address Length`
- Encoded `Table Booking Binary` and `Online Delivery Binary` (Yes = 1, No = 0)

### Final Analysis
- Correlation of all numeric features with Aggregate rating, plus a full correlation heatmap
- Exported the cleaned dataset with 25 columns as `Cognifyz_Cleaned_Restaurant_Data.csv`

---

## 🔑 Key Findings

**Ratings**
- Mean rating is **2.67** and median is **3.2** on a 0–5 scale; the highest rating in the data is 4.9.
- Rating classes: 0–2 → 2,158 · 2–3 → 1,891 · **3–4 → 4,388 (largest)** · 4–5 → 1,114.

**Location & cuisine**
- Country code `1` accounts for **8,652** of the 9,551 restaurants.
- Top cities: **New Delhi (5,473)**, Gurgaon (1,118), Noida (1,080), Faridabad (251) and Ghaziabad (25).
- Most common cuisines: North Indian (936), North Indian + Chinese (511), Fast Food (354), Chinese (354) and North Indian + Mughlai (334).

**Table booking & online delivery**
- Only **12.1%** of restaurants offer table booking and **25.7%** offer online delivery.
- Restaurants **with table booking average 3.44** versus **2.56 without**.
- Online delivery is most common in **price range 2 (41.3%)** and least common in price range 4 (9.0%).

**Price range**
- Most restaurants are in **price range 1 (4,444)**, then range 2 (3,113), range 3 (1,408) and range 4 (586).
- Average rating rises with price range: **2.00 → 2.94 → 3.68 → 3.82**, so price range 4 has the highest average rating.

**Correlation with Aggregate rating**

| Feature | Correlation |
|---|---:|
| Price range | 0.44 |
| Votes | 0.31 |
| Online Delivery Binary | 0.23 |
| Table Booking Binary | 0.19 |
| Average Cost for two | 0.05 |

Price range and votes show the strongest positive relationship with rating. Correlation does not imply causation.

---

## ⚠️ Notes & Limitations

- **Unrated restaurants:** 2,148 restaurants have an Aggregate rating of `0.0`, which most likely means "not rated" rather than a true zero. This pulls the mean rating and the 0–2 class down. Excluding them would give a clearer picture.
- **Geographic concentration:** the data is heavily concentrated in the New Delhi region, so findings mainly reflect that area.
- **Small samples in city rankings:** cities at the top of the average-rating list (for example Inner City at 4.9) may have very few restaurants, so those averages are not reliable on their own.
- **Currency:** `Average Cost for two` is recorded in different currencies, so it is not directly comparable across countries; the `Price range` field is the better cross-country measure.
- Columns such as Restaurant ID, Latitude and Longitude are identifiers or coordinates, so their correlation values have little business meaning.

---

## 📁 Repository Structure

```
├── Cognifyz Project.ipynb                 # Full analysis notebook
├── Cognifyz_Restaurant_Dataset.csv        # Input dataset (add this file)
├── Cognifyz_Cleaned_Restaurant_Data.csv   # Output of the notebook (optional)
└── README.md
```

---

## ▶️ How to Run

1. Open `Cognifyz Project.ipynb` in [Google Colab](https://colab.research.google.com/) or Jupyter Notebook.
2. Upload `Cognifyz_Restaurant_Dataset.csv`. In Colab it is read from `/content/Cognifyz_Restaurant_Dataset.csv`; change the path if you run it locally.
3. Run all cells from top to bottom.

```bash
pip install pandas numpy matplotlib seaborn
```

---

## 🚀 Future Scope

- Treat rating `0.0` as missing and re-run the rating analysis
- Interactive map (Folium or Plotly) for the geospatial analysis
- Split multi-value cuisines into individual cuisines for a cleaner cuisine ranking
- Regression or classification model to predict restaurant rating
- Build a Power BI or Tableau dashboard on the cleaned dataset

---

## 👤 Author

**Abhinav Yadav**

Skills demonstrated: Python · Pandas · Data Cleaning · EDA · Geospatial Analysis · Feature Engineering · Data Visualization

⭐ If you found this project useful, consider giving the repository a star!
