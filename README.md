# 🚗 Vehicle Energy Dataset (VED) Power BI Dashboard

This repository contains a Power BI dashboard built using the Vehicle Energy Dataset (VED). The dashboard provides insights into vehicle behavior, performance metrics, and energy efficiency, particularly focusing on electric, hybrid, and conventional vehicles.

---

## 📁 Dataset

The dataset used is from the [Vehicle Energy Dataset (VED)](https://github.com/gsoh/VED). It includes detailed data collected from a fleet of vehicles, covering aspects like:

- Vehicle dynamics (speed, load, engine RPM, etc.)
- Trip-level information
- Battery state-of-charge (SOC)
- Vehicle specifications (engine type, class, transmission)

You can download the dataset from the original source:

🔗 **[Download VED Data](https://github.com/gsoh/VED/tree/master/Data)**

---

## 🐍 Data Preprocessing (Python)

The `Dynamics` folder contains multiple CSV files—one for each vehicle. Use the following Python script to merge them into a single CSV before loading into Power BI.

```python
# Set the path to the downloaded 'Dynamics' folder
folder_path = "path/to/Data/Dynamics" 

files = os.listdir(folder_path)
# Create an empty list to store DataFrames
dfs = []

# Loop through all CSV files in the folder
for file in files:
    file_path = os.path.join(folder_path, file)
    
    if os.path.isfile(file_path):  #Only read files, not folders
        df = pd.read_csv(file_path)
        dfs.append(df)
        print(f"Read {file} with {len(df)} rows")

combined_df = pd.concat(dfs, ignore_index=True)
```
After running this script, import combined_df.csv into Power BI and create relationships with V_Type.csv.

## 📊 Dashboard Overview

The Power BI dashboard offers a comprehensive overview of vehicle performance and energy efficiency across different types of vehicles in the dataset. It highlights key metrics and enables quick visual analysis using a mix of card visuals, bar charts, pie charts, and maps.

### ✅ Key Metrics

| Metric | Description |
|--------|-------------|
| **Number of Vehicles** | Total unique vehicles analyzed: **384** |
| **Average Speed (km/h)** | Mean speed across all recorded trips: **40.40 km/h** |
| **Average Trips per Vehicle** | Average number of trips per vehicle: **10.82** |

---

### 📍 Visualizations Explained

- **📌 Trip Map (Top Right)**  
  - Displays all recorded vehicle trips using GPS data.  
  - Useful for understanding travel density and coverage area.

- **🔋 HV Battery SOC (State of Charge)**  
  - Shows the SOC per vehicle as a sorted bar chart.  
  - Helps identify variations in battery levels and usage patterns across the fleet.

- **📈 Average Load %**  
  - Visualizes the average engine load percentage per vehicle.  
  - Highlights which vehicles are operating under more strain.

- **🚗 Vehicle Class Distribution**  
  - Pie chart indicating the proportions of cars, SUVs, and other vehicle classes.  
  - Dominated by “Car” class vehicles in this dataset.

- **⚡ Engine Type Distribution**  
  - Categorizes vehicles into ICE (Internal Combustion Engine), HEV (Hybrid Electric Vehicle), PHEV (Plug-in Hybrid Electric Vehicle), and EV (Electric Vehicle).

- **🔄 Transmission Type**  
  - Shows the frequency of different transmission types (CVT, automatic, etc.), including any missing values.

---

## 🧰 Tools Used

- **Power BI Desktop** – for dashboard creation and data visualization
- **Power Query** – for ETL (Extract, Transform, Load) operations
- **DAX (Data Analysis Expressions)** – to create calculated measures and columns
- **Python** – for preprocessing and merging raw CSV files
- **Bing Maps Integration** – for geospatial trip visualizations

---

## 💡 Skills Demonstrated

- 📌 Data preparation using Python
- 📈 Data transformation using Power Query
- 🧠 DAX calculations for KPIs and time-based measures
- 🎯 Interactive dashboard design with filtering and drill-down
- 🗺️ Geo-mapping and spatial visualizations
- 📊 Clear visual storytelling using structured layout

---
## 📸 Dashboard Preview
![Screenshot 2025-04-14 133112](https://github.com/user-attachments/assets/095f1317-7c59-4ef7-9fe8-7d540b008577)


