<div align="center">

# 🌦️ Weather Forecast Analyzer of Bangladesh 🇧🇩
### *Agricultural & Environmental Weather Record Management and Statistical Analysis System*

![Python](https://img.shields.io/badge/Python-3.12.5-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Statistical_Computing-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Tkinter](https://img.shields.io/badge/Tkinter-GUI_Dashboard-FF6F00?style=for-the-badge&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Project_Status-Active-success?style=for-the-badge)

**Course:** CSC 4162 — Programming in Python (Mid-Term Group Project)  
**Semester:** Fall 2026–27 | **Institution:** American International University-Bangladesh (AIUB)  
**Domain:** 🌾 Agriculture & Local Livelihoods / 🌍 Environment & Sustainability

</div>

---

## 📖 Table of Contents
- [📌 Project Overview](#-project-overview)
- [🎯 Societal Impact & Target Users](#-societal-impact--target-users)
- [🛠️ Tech Stack & Libraries Used](#️-tech-stack--libraries-used)
- [📊 Dataset Information (2016–2026)](#-dataset-information-20162026)
- [✨ Core Features & Functionalities](#-core-features--functionalities)
- [🧱 Program Structure & Python Concepts](#-program-structure--python-concepts)
- [🚀 Installation & Setup Guide](#-installation--setup-guide)
- [👥 Project Group Members](#-project-group-members)

---

## 📌 Project Overview
**Weather Forecast Analyzer of Bangladesh** is a complete Python application designed to clean, manage, and analyze a decade of meteorological records (**2016–2026**) across major cities in Bangladesh (**Dhaka, Chittagong, Sylhet, and Rajshahi**). 

The project transforms **350,880 hourly weather observations** into clean, daily aggregated city records and provides both an interactive **Menu-Driven Console Interface** and a **Tkinter Graphical User Interface (GUI)**. Using **Pandas** and **NumPy**, the system performs statistical computations and automatically categorizes daily weather conditions into actionable advisories (`Normal`, `Heavy Rain`, `Heat Alert`, and `High Wind`) without relying on black-box machine learning models.

---

## 🎯 Societal Impact & Target Users
In Bangladesh, agriculture and local livelihoods depend heavily on seasonal rainfall, air temperature, humidity, and soil temperature.
* **🌾 Small Farmers & Agricultural Workers:** Track regional rainfall totals, heat alerts, and deep soil temperatures (`100 to 255 cm`) to plan irrigation schedules and crop activities.
* **🌍 Environmental Planners & Students:** Analyze multi-year temperature trends, standard deviations, and extreme weather frequencies across divisions.
* **📋 Local Record Keepers:** Easily add, search, update, delete, and permanently store daily weather observations in CSV format.

---

## 🛠️ Tech Stack & Libraries Used

| Category | Technology / Library | Purpose in Project |
| :--- | :--- | :--- |
| **Programming Language** | 🐍 **Python 3.x** | Core programming logic, OOP classes, data structures, file & exception handling |
| **Data Cleaning & File I/O** | 🐼 **Pandas** | Loading raw CSV data, cleaning missing/duplicate rows, datetime conversion, column renaming, daily aggregation, and saving persistent CSV files |
| **Numerical & Statistical Analysis** | 🔢 **NumPy** | Array-based statistical calculations (`mean`, `median`, `max`, `min`, `sum`, `std`) for city-wise weather metrics |
| **Graphical User Interface (GUI)** | 🖥️ **Tkinter** | Interactive desktop dashboard with sidebar navigation, input forms, summary cards, and data tables |
| **Development Environment** | 💻 **VS Code & Jupyter Notebook** | Step-by-step data exploration, backend development, and testing |
| **Version Control** | 🔗 **Git & GitHub** | Collaborative group workflow, branching, and source code management |

---

## 📊 Dataset Information (2016–2026)

* **Raw Dataset File:** `BD_Weather_Data.csv`
* **Cleaned Daily Dataset File:** `BD_Weather_Cleaned.csv`
* **Time Span:** **2016 – 2026** (10+ Years of Historical & Recent Data)
* **Initial Volume:** `350,880` Hourly Records ➔ Aggregated into `14,620` Clean Daily City Records
* **Cities Covered:** `Dhaka`, `Chittagong`, `Sylhet`, `Rajshahi`

<details>
<summary><b>🔍 Click to Expand: Dataset Columns & Weather Parameters</b></summary>
<br>

| Original CSV Column | Cleaned PascalCase Name | Data Type | Description & Unit |
| :--- | :--- | :---: | :--- |
| `time` | `Date` | `String / Date` | Calendar date in `YYYY-MM-DD` format (hours removed) |
| `city` | `City` | `String` | Standardized city name (`Dhaka`, `Chittagong`, `Sylhet`, `Rajshahi`) |
| `temperature_2m` | `Temp` | `Float` | Air temperature at 2 meters above ground (`°C`) |
| `relative_humidity_2m` | `Humidity` | `Float` | Relative air humidity at 2 meters (`0% – 100%`) |
| `rain` | `Rain` | `Float` | Precipitation / rainfall measurement (`mm`) |
| `pressure_msl` | `Pressure` | `Float` | Atmospheric mean sea-level pressure (`hPa`) |
| `cloud_cover` | `CloudCover` | `Float` | Total cloud cover percentage (`0% – 100%`) |
| `wind_speed_100m` | `WindSpeed` | `Float` | Wind speed at 100 meters height (`km/h`) |
| `wind_direction_100m` | `WindDir` | `Float` | Wind direction angle (`0° – 360°`) |
| `soil_temperature_100_to_255cm` | `SoilTemp` | `Float` | Deep soil temperature for agricultural tracking (`°C`) |
| *(Computed Attribute)* | `Status` | `String` | Automated weather advisory (`Normal`, `Heavy Rain`, `Heat Alert`, `High Wind`) |

</details>

---

## ✨ Core Features & Functionalities

1. **🧹 Automated Data Cleaning Pipeline (Pandas):**
   - Inspects dataset with `.head()`, `.tail()`, `.sample()`, `.shape`, `.columns`, `.dtypes`, `.info()`, and `.describe()`.
   - Detects and removes missing values (`.isnull().sum()`, `.dropna()`) and duplicate entries (`.duplicated().sum()`, `.drop_duplicates()`).
   - Standardizes city strings, extracts calendar dates, renames columns to clean `PascalCase`, and aggregates hourly data into daily city averages.

2. **📋 Complete CRUD Operations (Record Management):**
   - **View Records:** Displays formatted tabular weather records.
   - **Add New Record:** Collects validated user input and prevents duplicate `City_Date` entries.
   - **Search Record:** Instant lookup by `Date` (`YYYY-MM-DD`) and `City`.
   - **Update Record:** Modifies existing `Temp`, `Humidity`, and `Rain` values and automatically recalculates the weather alert status.
   - **Delete Record:** Safely removes records from memory and updates storage.

3. **📈 NumPy Statistical Weather Analyzer:**
   - Converts city-specific weather metrics into **NumPy Arrays** (`np.array`).
   - Computes **Mean**, **Median**, **Maximum**, **Minimum**, **Standard Deviation**, and **Total Rainfall** (`np.mean`, `np.median`, `np.max`, `np.min`, `np.std`, `np.sum`).

4. **🚨 Rule-Based Weather Advisory Classification:**
   - 🌧️ **Heavy Rain:** Triggered when `Rain >= 2.0 mm`
   - 🔥 **Heat Alert:** Triggered when `Temp >= 32.0 °C`
   - 💨 **High Wind:** Triggered when `WindSpeed >= 25.0 km/h`
   - ✅ **Normal:** Standard safe agricultural weather conditions

5. **💾 Persistent File Handling & Robust Exception Handling:**
   - Automatically loads from and saves changes to `BD_Weather_Cleaned.csv`.
   - Uses `try-except-else-finally` blocks to handle `FileNotFoundError`, `ValueError` (non-numeric inputs), out-of-range measurements, and invalid date/city inputs without crashing.

---

## 🧱 Program Structure & Python Concepts

<details>
<summary><b>🧩 Click to Expand: Object-Oriented Programming (OOP) & Data Structures Used</b></summary>
<br>

* **Data Model Class (`WeatherRecord`):**
  * Encapsulates a single daily city weather record (`RecordId`, `Date`, `City`, `Temp`, `Humidity`, `Rain`, `Pressure`, `CloudCover`, `WindSpeed`, `WindDir`, `SoilTemp`, `Status`).
  * Includes `GetWeatherStatus()` for conditional alert detection and `ToDict()` to convert objects into Python dictionaries.
* **Manager / Application Class (`WeatherManager`):**
  * Coordinates the master **List** of `WeatherRecord` objects (`self.Records`) and executes all view, add, search, update, delete, NumPy analysis, and CSV save operations.
* **Data Structures Implemented:**
  * **List (`[]`):** Stores and manages all `WeatherRecord` objects dynamically.
  * **Tuple (`()`):** Stores fixed, immutable configuration data (`AllowedCities` and `MenuOptions`).
  * **Dictionary (`{}`):** Converts `WeatherRecord` objects into key-value pairs for Pandas DataFrame export and tabular display.

</details>

---

## 🚀 Installation & Setup Guide

### 1️⃣ Clone the Repository
```bash
git clone
cd Weather-Forecast-Analyzer-Bangladesh
```

### 2️⃣ Install Required Libraries
Make sure you have Python installed, then install `pandas` and `numpy`:
```bash
pip install pandas numpy
```
*(Note: `tkinter` comes pre-installed with standard Python distributions).*

### 3️⃣ Run the Project
* **For Jupyter Notebook / VS Code:** Open `Weather_Forecast_Analysis_BD.ipynb` and click **Run All** (`▶▶`) on the top Jupyter toolbar.
* **For GUI / Python Script:** Run the main application file once the Tkinter dashboard is integrated:
```bash
python main.py
```

---

## 👥 Project Group Members

| Name | Role & Contribution |
| :--- | :--- |
| **Shahadat Hossain (Lead / Backend & Data Analysis)** | Data Cleaning (Pandas), Statistical Analysis (NumPy), OOP Architecture (`WeatherRecord` & `WeatherManager`), Exception & File Handling |
| **Member 2 (GUI & Frontend Integration)** | Tkinter Dashboard Design, Input Forms, Table View, and Event Binding |
| **Member 3 (GUI & Documentation / Testing)** | UI Components, Validation Testing, Project Report |
| **Member 4 (Documentation)** |Project Report |

---

<div align="center">
  <i>Developed for CSC 4162 (Programming in Python) — Fall 2026–27 Semester at AIUB.</i>
</div>
