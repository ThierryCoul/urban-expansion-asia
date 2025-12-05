# Urban Expansion in Asia: Ecosystem Service Impact Analysis (1995-2034)

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen)](https://thierrycoul.github.io/urban-expansion-asia/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

> **An interactive web platform showcasing comprehensive ecosystem service valuations across 9 Asian countries, quantifying the environmental cost of rapid urbanization from 1995 to 2034.**

---

## 🌏 [**Explore the Interactive Maps**](https://thierrycoul.github.io/urban-expansion-asia/)

Dive into city-by-city visualizations showing where valuable ecosystems—from coral reefs to mangroves—are being lost to urban sprawl.

---

## 📊 Project Overview

This research initiative provides the first comprehensive, spatially-explicit valuation of ecosystem service losses due to urban expansion across South and Southeast Asia. By combining satellite imagery, machine learning predictions, and ecosystem service economics, we quantify the environmental costs of urbanization in unprecedented detail.

### Key Findings

- 🏙️ **Analysis of 270 cities** across 9 countries (India, Iran, Pakistan, Vietnam, Philippines, Mongolia, Nepal, Laos, and Sri Lanka)
- 🌊 The analysis shows a focus on **coral reefs** ($168,714/ha/year), **coastal wetlands** ($92,669/ha/year) to improve the accounts of natural capital in Asian cities with strong ecosystem values by the oceans  
- 📈 **40-year temporal coverage** combining historical analysis (1995-2024) with ML-based predictions (2024-2034)

---

## 🔬 Methodology Highlights

### 1. Urban Expansion Mapping

**Data Sources:**
- **Global Impervious Surface Area (GISA)** v3: 30m resolution, 93.12% accuracy (1972-2021)
- **ESRI Annual LULC** v3: 10m resolution from Sentinel-2 imagery (2017-2025)
- **Atlas of Urban Expansion** methodology for city boundary delineation

### 2. Machine Learning for Future Predictions

**Neural Netwrork enhanced Cellular Automata Model:**
- **Architecture**: Multi-layer feedforward network (128→64→32 neurons) + convolutional layers (7×7, 3×3, 1×1 kernels)
- **Training**: 200 epochs on 100,000 samples (80/20 train-test split), 93%+ accuracy
- **Input variables**: 15 spatial drivers including:
  - Topography (elevation, slope, aspect)
  - Accessibility (distance to city center, major roads, water bodies)
  - Socioeconomic factors (nighttime lights, population density)
  - Land cover dynamics and protected areas
- **Prediction horizon**: 2024-2034 based on SSP1 population scenarios

### 3. Ecosystem Service Valuation

**Innovative Methodological Contributions:**

#### A. Five-Tier Water Body Differentiation
First study to distinguish water bodies by ecological value:
```
Coral Reefs        → $168,714/ha/year  (Allen Coral Atlas, 30m)
Coastal Wetlands   → $92,669/ha/year   (GMW v3 + ESA class 170)
Coastal Systems    → $13,823/ha/year   (10km coastal buffer)
Inland Wetlands    → $12,277/ha/year   (Freshwater areas)
Rivers & Lakes     → $2,040/ha/year    (Open water bodies)
```

#### B. NDVI-Weighted Vegetation Valuation
Addresses spatial heterogeneity in ecosystem productivity:
```
Weight = (NDVI - NDVIfloor) / (NDVIceiling - NDVIfloor)
```
- Annual Landsat composites (5 TM, 7 ETM+, 8/9 OLI)
- Normalized range: 0.0-0.6 floor-ceiling
- Applied to cropland, forests, woodlands, grasslands

#### C. Country-Specific Agricultural Values
Derived from World Bank agricultural production statistics:
- Philippines: $121,687/ha (1995) → $260,928/ha (2024)
- India: $58,113/ha (1995) → $150,104/ha (2024)
- Captures regional productivity variations

**Biome Valuation Framework** (de Groot et al., 2012):

| Biome Category | Value (USD/ha/year) |
|----------------|---------------------|
| Coral Reefs | $168,714 |
| Coastal Wetlands | $92,669 |
| Coastal Systems | $13,823 |
| Inland Wetlands | $12,277 |
| Tropical Forests | $2,516 |
| Temperate Forests | $1,440 |
| Grasslands | $1,373 |
| Woodlands | $759 |

---

## 🗺️ Interactive Visualizations

Each city features:
- **Multi-period urban extent overlays** (1995, 2024, 2034)
- **Ecosystem value heatmaps** showing spatial distribution of natural capital
- **Expansion area highlighting** with quantified ecosystem losses
- **Detailed statistics** on area growth, loss values, and annual rates
- **Differentiated water body mapping** (coral, mangroves, coastal systems)

### Example: City-Level Analysis

![Ecosystem Loss Visualization](assets/example_map.png)

**Features visible on each map:**
- ✅ Urban extent boundaries by year
- ✅ Ecosystem value gradients (darker green = higher value)
- ✅ Historical loss zones (1995-2024) in red-orange
- ✅ At-risk ecosystems (2024-2034) in green
- ✅ Interactive popups with detailed statistics

---

## 📁 Repository Structure
```
urban-expansion-asia/
├── maps/               # City-level ecosystem analysis HTML files
│   ├── india/
│   ├── iran/
│   ├── pakistan/
│   ├── vietnam/
│   ├── philippines/
│   ├── mongolia/
│   ├── nepal/
│   ├── laos/
│   └── srilanka/
├── assets/             # Logos and images
├── index.html          # Main interactive map interface
└── README.md           # This file
```

---

## 🎯 Key Innovations

1. **First comprehensive ecosystem service valuation** at city-scale across multiple Asian countries
2. **Novel water body differentiation** capturing coastal-marine ecosystem complexity
3. **NDVI-weighted valuation** addressing spatial heterogeneity in ecosystem productivity
4. **Machine learning predictions** based on 15 spatial drivers and 7-year training data
5. **Fully open and reproducible** analysis pipeline with public data sources

---

## 📊 Data Sources

| Dataset | Resolution | Period | Source |
|---------|-----------|--------|--------|
| GISA v3 | 30m | 1972-2021 | Huang et al., 2024 |
| ESRI LULC v3 | 10m | 2017-2025 | Karra et al., 2021 |
| ESA LCCCI | 300m | 1992-2020 | ESA CCI |
| Allen Coral Atlas | 5m | 2018-2020 | Mitchell et al., 2020 |
| Global Mangrove Watch v3 | 10m | 1996-2020 | Bunting et al., 2022 |
| Landsat NDVI | 30m | 1995-2024 | USGS (Collections 5, 7, 8/9) |
| ALOS DEM | 30m | 2006-2011 | JAXA, v4.1 |
| Nighttime Lights | 100m | 2012-2025 | EOG VIIRS |
| Population Density | 100m | 2000-2021 | WorldPop |

---

## 🔗 Related Links

- **[Interactive Map Platform](https://thierrycoul.github.io/urban-expansion-asia/)** - Explore all cities
- **UN-Habitat ROAP** - [https://unhabitat.org/](https://unhabitat.org/)
- **Urban Institute, Kyushu University** - [https://www.urban.kyushu-u.ac.jp/en/](https://urban-institute.kyushu-u.ac.jp/en/)

---

## 👥 Research Team

**Principal Investigator:** Thierry Yerema Coulibaly, Assistan Prof.  
**Affiliation:** Urban Institute, Kyushu University

**Collaborators:**
- Thierry Yerema Coulibaly
- Yohei Takata
- Yuko Kishikami

**Supervisors:**
- Shunsuke Managi
- Bruno Dercon


---

## 📖 Citation

If you use this data or methodology in your research, please cite:
```bibtex
@misc{yourname2024urban,
  title={Urban Expansion in Asia: Ecosystem Service Impact Analysis (1995-2034)},
  author={Thierry Yerema Coulibaly},
  year={2024},
  publisher={GitHub},
  journal={GitHub repository},
  howpublished={https://github.com/ThierryCoul/urban-expansion-asia}
}
```

---

## 📧 Contact

For questions, collaborations, or data requests:
- **Email:** yerema.coul@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/thierrycy/

---

## 📄 License

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).

You are free to:
- **Share** — copy and redistribute the material
- **Adapt** — remix, transform, and build upon the material


---

## 🙏 Acknowledgments

This research was conducted in collaboration with:
- UN-Habitat Regional Office for Asia and the Pacific (ROAP)
- Urban Institute of Kyushu University

We acknowledge the use of data from:
- ESA Climate Change Initiative
- NASA/USGS Landsat Program
- Google Earth Engine Platform
- Allen Coral Atlas
- Global Mangrove Watch

---

## 📈 Project Status

- ✅ Data collection and processing (Complete)
- ✅ ML model training and validation (Complete)
- ✅ Ecosystem service valuation (Complete)
- ✅ Interactive visualization platform (Complete)
- 🔄 Academic paper submission (In progress)
- 📅 Policy brief preparation (Planned)

---

**Last Updated:** December 2025

**Version:** 1.0.0
