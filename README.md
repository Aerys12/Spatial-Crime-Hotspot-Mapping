# Spatial-Crime-Hotspot-Mapping
## Hamilton Theft Spatial Analysis
This Jupyter notebook performs a geospatial and statistical analysis of theft incidents across Hamilton, New Zealand’s SA2 areas, integrating multiple data sources:

- **Territorial & SA2 boundaries** (Stats NZ shapefiles)  
- **Convenience‐store locations** (GeoJSON)  
- **Police station locations** (GeoJSON)  
- **Theft counts** (ANZSOC/Ta data, 2021–2024)  
- **Census data** (2023 SA2 population and demographic CSV)  
- **Employment/unemployment** (2018 SA2 Excel dataset)

## Key Steps

1. **Data Ingestion & Cleaning**  
   - Read shapefiles (TA & SA2), GeoJSON, CSV/TSV, and Excel.  
   - Standardize and spatially join convenience‐store and police‐station counts by SA2.  
   - Clean and aggregate theft records by `AreaUnit` → SA2.  
   - Merge in Census population, compute population density, and calculate unemployment rates.

2. **Exploratory Analysis**  
   - Pearson correlations between theft rate, store density, unemployment rate, and pop. density.  
   - Scatterplots with regression fits for each predictor.

3. **Regression Modeling**  
   - Univariate OLS for each predictor (store count, unemployment rate, population density).  
   - Multivariate OLS combining predictors; compare R², AIC, coefficient significance.

4. **Spatial Autocorrelation**  
   - Compute **Moran’s I** on raw theft counts.  
   - Compute **Moran’s I** on OLS residuals to assess leftover spatial clustering.

5. **Interactive Mapping** (optional)  
   - Folium choropleth layers toggled by year, with a shared legend and custom title.

## Usage

1. **Clone** this repo:  
   ```bash
   git clone https://github.com/Aerys12/Spatial-Crime-Hotspot-Mapping.git
2. Install dependencies:
   ```bash
   pip install geopandas pandas folium statsmodels pysal branca openpyxl seaborn
3. Run the notebook
   ```bash
   jupyter lab Hamilton_Theft_Analysis.ipynb

