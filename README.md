# FBI Time Series Forecasting

## 📌 Project Overview
This project focuses on forecasting **monthly crime trends** using a historical dataset of crime incidents provided by the FBI. The dataset includes attributes such as crime type, location (neighborhood, coordinates), and temporal data (year, month, day, hour, minute).

The goal is to **predict future monthly crime occurrences by crime type** using time series modeling (SARIMA). The final model achieves **81.57% accuracy** with low MAE and RMSE, making it suitable for real-world crime trend forecasting and public safety planning.

---

## 🚨 Problem Statement
The objective is to forecast monthly crime trends using historical FBI crime incident data. Challenges include:

- Handling missing values and duplicate records.
- Addressing geographical inconsistencies.
- Capturing both **long-term trends** and **short-term variations** in crime patterns.

**Goals:**

- Analyze seasonal and long-term patterns in crime data.
- Train a robust time series model (SARIMA).
- Generate actionable insights for law enforcement agencies.

---

## 📂 Dataset

**Filename:** `Train.xlsx`

**Features:**

| Column           | Description                           |
|------------------|----------------------------------------|
| TYPE             | Type of crime (e.g., Other Theft)     |
| HUNDRED_BLOCK    | Street block of crime                 |
| NEIGHBOURHOOD    | Neighborhood name                     |
| X, Y             | Spatial coordinates                   |
| Latitude, Longitude | Geographic coordinates              |
| HOUR, MINUTE     | Time of the crime                     |
| YEAR, MONTH, DAY | Date of the crime                     |
| Date             | Combined datetime field               |

**Key Stats:**

- Rows: `474,565`
- Columns: `13`
- Missing Values:
  - `NEIGHBOURHOOD`: 51,491
  - `HOUR`, `MINUTE`: 49,365
  - `HUNDRED_BLOCK`: 13
- Duplicate Rows: `44,618`

---

## 🛠 Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/fbi-time-series-forecasting.git
   cd fbi-time-series-forecasting
