# Geospatial Data Cleaning Pipeline

Python pipeline to clean and validate GPS/survey data before mapping in QGIS/ArcGIS.

## Problem
Raw GNSS/Total Station data has outliers, datum shifts, duplicate points that break maps.

## Solution
Automated pipeline using Pandas & NumPy that:
- Detects coordinate outliers using Z-score & IQR
- Flags datum errors (WGS84 vs Minna datum)
- Removes duplicate points within 0.5m tolerance
- Exports clean CSV + error report

## Tech Stack
Python, Pandas, NumPy, QGIS

## Results
- 98% bad points flagged automatically
- Reduced manual cleaning from 8 hours to 45 minutes per project
- Used on 50k+ rows of real survey data

## Usage
```python
python clean_gps.py --input raw_data.csv --output clean.csv --report errors.csv
