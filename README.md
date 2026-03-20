# 🏎️ Formula 1 Performance Dashboard (Power BI)

## 📊 Project Overview
This project is an interactive **Formula 1 Performance Dashboard** built using **Power BI**.  
It analyzes driver performance, team performance, race outcomes, and trends across seasons.

The dashboard provides meaningful insights using data visualization and DAX calculations.

---

## 🎯 Objectives
- Analyze **driver performance** based on points and wins  
- Compare **team (constructor) performance**  
- Understand **race trends over time**  
- Study relationship between **grid position and finishing position**  
- Provide an interactive dashboard using slicers  

---

## 📂 Dataset Used
The dataset includes multiple CSV files:

- `results.csv` → Race results  
- `drivers.csv` → Driver details  
- `races.csv` → Race information (date, year, circuit)  
- `constructors.csv` → Team details  

---

## 🧹 Data Cleaning Steps
- Removed unnecessary columns (URL, reference fields, etc.)
- Handled null values and invalid entries
- Converted columns to proper data types
- Created calculated columns:
  - Win
  - Podium
  - Top 10 Finish
- Created **Driver Full Name** column
- Standardized text formatting

---

## 🔗 Data Modeling
Relationships created:

- results → drivers (driverId)
- results → races (raceId)
- results → constructors (constructorId)

---

## 🧠 DAX Measures Used

```DAX
Total Races = DISTINCTCOUNT(results[raceId])

Total Points = SUM(results[points])

Total Wins = CALCULATE(COUNTROWS(results), results[position] = 1)

Podiums = CALCULATE(COUNTROWS(results), results[position] <= 3)

Avg Finish = AVERAGE(results[position])
