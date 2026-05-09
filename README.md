# Global-War-Data-Preprocessing
# Global War Conflicts Dataset — Complete Data Preprocessing

## What Is This?

A dataset of 3,000 real-world military conflicts — countries, 
casualties, economic losses, refugees, terrain, climate, weapons, 
outcomes — 30 columns of raw, imperfect, real-world data.

Real-world data is never clean. This notebook proves it.

---

## What Was Done — Step by Step

### Step 1 — Understanding the Data
Before touching anything, the dataset was fully explored —
data types checked, missing values counted, statistical 
summaries reviewed. Know your data before you change it.

### Step 2 — Missing Values
Three columns had missing data — Alliance_A, Alliance_B, 
and Resource_Dispute. Each was handled with logic, not 
just deletion. Missing alliances? Filled as "Unknown". 
Missing resource dispute info? Filled as "Not Reported".

### Step 3 — Encoding Categorical Columns
Machines don't understand "Desert" or "Civil War" — 
they understand numbers. Three encoding strategies used:

  • Label Encoding     → for binary columns (Yes/No)
  • Ordinal Encoding   → for ranked categories  
  • One-Hot Encoding   → for unordered categories like 
                         Conflict_Type, Terrain, Climate_Zone

### Step 4 — Outlier Detection & Removal (The Hard Part)
Every single numerical feature — all 17 of them — got its 
own individual boxplot. Not combined. Not rushed. One by one.

Outliers removed using the IQR method:
  Lower Bound = Q1 - 1.5 × IQR
  Upper Bound = Q3 + 1.5 × IQR

Anything beyond these bounds? Removed. Data integrity first.

### Step 5 — Distribution Visualization
After outlier removal, distribution plots (displot) created 
for numerical features to confirm clean, reasonable spread.

### Step 6 — Scaling (Two Methods, Side by Side)
All features scaled using subplot comparisons:

  • Standard Scaler   → mean=0, std=1 (for ML algorithms 
                         sensitive to variance)
  • MinMax Scaler     → range 0 to 1 (for neural networks 
                         and distance-based models)

---

## End Result

Started with: 30 messy columns, missing values, 
              text categories, wild outliers

Ended with: 100% numeric, clean, scaled, ML-ready data

Every transformation documented. Every decision explained.
This is what professional data preprocessing looks like.

---

## Tools Used
Python | Pandas | NumPy | Matplotlib | Seaborn 
Scikit-learn (LabelEncoder, OneHotEncoder, StandardScaler, MinMaxScaler)
Python | Pandas | NumPy | Matplotlib | Seaborn 
Scikit-learn (LabelEncoder, OneHotEncoder, 
              StandardScaler, MinMaxScaler)
