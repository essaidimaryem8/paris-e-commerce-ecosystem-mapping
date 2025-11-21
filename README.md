# Paris E-Commerce Ecosystem Mapping

**Data Science Study**  
**Author:** Maryem Essaidi  
**Date:** November 2025

---

## Project Overview

This project identifies the most attractive Paris arrondissements for e-commerce brands seeking physical expansion (flagship stores, pop-ups, dark stores, omnichannel hubs). 

Using open municipal data, I built a **Commercial Activity Index (0–100)** combining foot traffic proxies and city-backed commercial revitalization signals.

---

## Research Question

Can terrace density and city-backed commercial revitalization efforts reliably predict the best arrondissements for e-commerce physical expansion in 2025–2027?

---

## Key Findings

| Rank | Arrondissement | Score |
|------|----------------|-------|
| 1 | 6e Luxembourg | 72.9 |
| 2 | 3e Temple | 70.9 |
| 3 | 10e Entrepôt | 69.6 |
| 4 | 11e Popincourt | 57.1 |
| 5 | 5e Panthéon | 52.9 |

- **6e arrondissement** ranked #1 — ideal for premium flagship stores
- **3e and 10e** emerged as high-growth zones with strong city investment
- Methodology enables **60–80% cost reduction** vs traditional real estate consulting

---

## Data Sources

| Dataset | Records | Source |
|---------|---------|--------|
| Terrace Authorizations | 23,911 | [Paris Open Data](https://opendata.paris.fr/explore/dataset/commerces-semaest/information/) |
| SEMAEST Vitalized Shops | 311 | [Paris Open Data](https://opendata.paris.fr/explore/dataset/terrasses-autorisations/information/?disjunctive.arrondissement&disjunctive.typologie) |
| Arrondissement Boundaries | 20 polygons | [Paris Open Data](https://opendata.paris.fr/explore/dataset/arrondissements/information/?disjunctive.l_ar&disjunctive.c_arinsee&disjunctive.c_ar) |

---

## Methodology

1. **Data Processing** — Cleaned and geolocated 24,222 commercial activity points using pandas and GeoPandas
2. **Spatial Mapping** — Performed spatial joins to assign each point to its arrondissement
3. **Index Calculation** — Built a normalized Commercial Activity Index combining terrace density and SEMAEST density
4. **Visualization** — Created interactive maps (Folium) and executive charts (Plotly)

### Commercial Activity Index Formula

```
Terrace Density = Number of Terraces / Area (km²)
SEMAEST Density = Number of SEMAEST Shops / Area (km²)

Commercial Score = (Terrace_normalized + SEMAEST_normalized) × 50
```

---

## Repository Structure

```
├── notebook/
│   └── paris_ecommerce_analysis.ipynb
│
├── data/
│   ├── terrasses_autorisations.csv
│   ├── commerces_semaest.csv
│   └── arrondissements.geojson
│
├── report/
│   └── Paris_ECommerce_Ecosystem_Report.pdf
│
├── visualizations/
│   ├── Top_5_Arrondissements_Commercial_DNA_Comparison.png
│   ├── Top_10_Arrondissements_by_City_Retail_Investment.png
│   └── Top_10_Highest_Foot_Traffic.png
│
├── maps/
│   ├── Final_Commercial_Score_Map.html
│   ├── SEMAEST_Shops_Map.html
│   └── Terrace_Density_Map.html
│
└── README.md
```

---

## How to Run

1. Clone the repository
```bash
git clone https://github.com/essaidimaryem8/paris-e-commerce-ecosystem-mapping.git
```

2. Install dependencies
```bash
pip install pandas geopandas folium plotly scikit-learn
```

3. Open the notebook
```bash
jupyter notebook notebook/paris_ecommerce_analysis.ipynb
```

---

## Interactive Maps

The `/maps` folder contains three interactive HTML maps. Download and open in any browser:

- **Final_Commercial_Score_Map.html** — Commercial Activity Index choropleth
- **SEMAEST_Shops_Map.html** — City investment distribution
- **Terrace_Density_Map.html** — Foot traffic heatmap

---

## Tools & Technologies

- Python (pandas, GeoPandas, scikit-learn)
- Folium (interactive mapping)
- Plotly (visualizations)
- LaTeX (report formatting)

---

## Contact

**Maryem Essaidi**  
[LinkedIn](https://www.linkedin.com/in/maryem-essaidi-274009254/) | Email: maryemessaidi8@gmail.com