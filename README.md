# AQI Analysis of 10 Indian Cities

## 👤 Author

**Name:** Sai Revanth Gudipati\
**Enrollment No.:** 23116037\
**Branch:** ECE

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on Air Quality Index (AQI) data from **10 Indian cities**. The analysis covers **data ingestion, cleaning, feature engineering, AQI computation, and visualization techniques** to understand air quality trends.

## 📂 Dataset

The data has been collected from the **Central Pollution Control Board (CPCB)**'s repository - [CPCB Website](https://cpcb.nic.in/)

The dataset consists of **10 CSV files**, each representing a city, containing the following columns:

- `Timestamp`: Date when data was recorded (DD-MM-YYYY). Ranges from **01-01-2020 to 31-12-2024**.
- `Location`: Locations where data was collected. The cities included are:
  - Bengaluru - Silk Board
  - Chennai - Alandur Bus Depot
  - Delhi - Punjabi Bagh
  - Hyderabad - Central University
  - Kolkata - Rabindra Bharati University
  - Mumbai - Chhatrapati Shivaji Intl. Airport (T2)
  - Gwalior - City Center
  - Jaipur - Police Commissionerate
  - Lucknow - Lalbagh
  - Visakhapatnam - GVM Corporation
- `PM2.5`, `PM10`, `NO2`, `SO2`, `NH3`, `CO`, `O3`: Pollutant concentrations (in **µg/m³**, except **CO** in **mg/m³**).

## 🌍 Pollutant Descriptions

- **PM2.5 & PM10**: Fine particulate matter from combustion, dust, and industrial activities. Major sources include vehicles, industrial emissions, and biomass burning.
- **Nitrogen Dioxide (NO2)**: Reactive gas from vehicle emissions and industrial combustion. Causes respiratory issues and contributes to smog.
- **Ammonia (NH3)**: Emitted from fertilizers, livestock waste, and biomass burning. Affects air quality and contributes to eutrophication in water bodies.
- **Sulfur Dioxide (SO2)**: Emitted from burning coal and oil. Leads to acid rain, haze, and respiratory issues.
- **Carbon Monoxide (CO)**: Produced by incomplete combustion. Causes carbon monoxide poisoning and contributes to smog.
- **Ozone (O3)**: Ground-level ozone is harmful, causing respiratory problems and affecting vegetation.

## 🚀 Project Workflow

### 🔹 1. Data Ingestion

- Loads CSV files for different cities (e.g., **Bengaluru, Chennai, Delhi, etc.**).
- Stores them in a **dictionary** for structured access.

### 🔹 2. Feature Engineering

- Converts `Timestamp` into a **datetime** object.
- Extracts **year, month, day, weekday, and a weekend indicator**.

### 🔹 3. Data Cleaning

- **Outlier Removal**: Uses the **IQR method** to filter extreme values in pollutant columns.
- **Missing Value Imputation**: Fills missing values using the **median** for the corresponding year & month (fallback to overall median).
- **Duplicate Check**: Ensures no duplicate rows exist.

### 🔹 4. Data Consolidation

- Merges all cleaned city datasets into a **single DataFrame**.
- Adds a **'City'** column to differentiate records.

### 🔹 5. AQI Calculation

- Implements **Indian AQI standards** using pollutant breakpoints.
- Computes **sub-indices** for each pollutant.
- Determines **overall AQI** as the **maximum sub-index**.

### 🔹 6. Exploratory Data Analysis (EDA)

#### 📊 **Univariate Analysis**

- Examines **distribution and summary statistics** of AQI using **histograms and box plots**.

#### 📈 **Bivariate Analysis**

- Explores AQI relationships with other variables (**city, weekday/weekend, month**) using **box plots, violin plots, scatter plots**.

#### 🔥 **Multivariate Analysis**

- Uses **pair plots** and a **correlation heatmap** to examine pollutant relationships.

## 🔍 Key Insights

- **Outlier Removal Impact**: The box plots before and after outlier removal showed that the **75th percentile and maximum values** came closer together, indicating successful trimming of extreme values.
- **Data Distribution Across Cities**: The bar plot of record counts revealed **unequal data availability** across cities.
- **AQI Distribution Characteristics**:
  - The histogram and box plot of AQI values highlighted a **right-skewed distribution**, indicating that most AQI readings are low, but a few **severely polluted areas** stretch the upper tail.
  - Descriptive statistics showed that **50% of AQI values are below 100 and 75% are below 150**.
- **Pollutant-AQI Relationships**:
  - Scatter plots of AQI vs. PM2.5, PM10, NO2, CO, and O3 revealed a **distinct lower AQI limit** for given pollutant concentrations, suggesting a **baseline AQI effect** for each pollutant.
  - Linear trends emerged in different pollutant ranges.
- **City and Temporal Patterns**:
  - Heatmap analysis showed that **Chennai, Hyderabad, and Kolkata** typically had AQI values in the **12–61 range**, whereas **Delhi and Lucknow** exhibited **more widespread AQI fluctuations** with **some extreme pollution days**.
  - Box plots comparing **weekday vs. weekend AQI** indicated **minimal differences**, except for **variations in extreme values** (min and max).
  - Monthly box and point plots demonstrated that **AQI tends to be lower mid-year and higher at the beginning and end of the year**, likely due to **increased winter pollution**.

These insights provide a comprehensive understanding of **how air quality varies** by **city, time, and pollutant concentration**, aiding further policy and environmental analysis.

## 🛠️ How to Run the Notebook

1. Install dependencies (if required):
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
2. Open the Jupyter Notebook and **run all cells sequentially**.
3. Visualize results and **interpret insights** from the output cells.

## 📌 Conclusion

This project offers a structured approach to **AQI analysis**, from raw data processing to **insightful EDA**, helping explore air pollution trends in Indian cities.

---

📌 **Author:** *Sai Revanth Gudipati*\
📌 **Enrollment No.:** *23116037*\
📌 **Branch:** *ECE*

