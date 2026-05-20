# Fire Mapping

## Description   
An interactive map, which uses data of satellite fire detections from NASA FIRMS API of the last 5 days to visualize maps of spatial distribution of fires and its density per country and for the whole globe.

---

## Data Sources  

| Source | Description | Link |
|---|---|---|
| NASA FIRMS API | Near real-time fire detection (VIIRS SNPP, last 1–5 days) | https://firms.modaps.eosdis.nasa.gov/api/ |
| Natural Earth | Country boundaries and geometries | https://naturalearth.s3.amazonaws.com |
 
**API limit (standard key):** 5'000 transactions per 10-minute interval

---

## Setup instructions

### 1. Clone the repository
```bash
git clone https://github.com/LilSheesh7/SDS210_project.git
cd SDS210_project
```

### 2. Get a NASA FIRMS API Key
1. Go to https://firms.modaps.eosdis.nasa.gov/api/map_key/  
2. Register and make a copy of the map key  
Note: The NASA FIRMS API Key is free and limited to 5'000 transactions per 10-minute interval

### 3. Create a ".env" file
Create a file called .env in the root of the project and add your key there
```
FIRMS_API_KEY=your_api_key_here
```
Never commit your .env file. It is listed in the .gitignore 

### 4. Install libraries
If you use Anaconda all packages are available via conda-forge:
```bash
conda install -c conda-forge geopandas folium plotly shapely python-dotenv
```
Alternativly, you can use pip:
```bash
pip install geopandas folium plotly requests python-dotenv shapely numpy pandas
```

### 5. Run the notebook
1. Open notebooks/fire_mapping.ipynb and run from top to bottom  
2. The outputs folder is created automatically on the first run.

---

## Output files

| File | Description |
|---|---|
| `fire_map.html` | Interactive Folium marker map with clustered fire locations |
| `fire_per_country.html` | Choropleth map — total fire count per country |
| `fire_density_per_country_linear.html` | Choropleth map — fires per 100 km² (linear scale) |
| `fire_density_per_country_logarithmic.html` | Choropleth map — fires per 100 km² (log scale) |
| `fire_heatmap.html` | Plotly density heatmap of all raw fire detections |
| `fire_per_country.csv` | Ranked table — countries by total fire count |
| `fire_density_per_country.csv` | Ranked table — countries by fire density |

---

## Author

Simon Rüegg  
Project was made for the course SDS210 at the Depertment of Geography at the University of Zurich