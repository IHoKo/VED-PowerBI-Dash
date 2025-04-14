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
