# 🌾📊 YieldVision: Agricultural Yield Analysis with Machine Learning 🌾📊

This repository features an in-depth analysis of a large agricultural dataset using advanced machine learning and causal inference techniques. The main goal is to understand the factors influencing crop yield and accurately predict it based on weather conditions, soil properties, and farming practices.

🔗 **[Download the dataset](https://drive.google.com/drive/folders/1FuE-idAFkLtRukpDCAA9N1TZ-fxwo-EX?usp=drive_link)**

## 📑 Table of Contents
- [📜 Introduction](#introduction)
- [⚙️ Installation](#installation)
- [🚀 Usage](#usage)
- [💻 Tech Requirements](#tech-requirements)
- [📊 Dataset Details](#dataset-details)
- [🤝 Contributing](#contributing)
- [📄 License](#license)

## 📜 Introduction
This repository contains a comprehensive analysis of a large agricultural dataset using advanced machine learning and causal inference techniques. The primary goal is to understand the factors influencing crop yield and to accurately predict yield based on various features such as weather conditions, soil properties, and agricultural practices.

## ⚙️ Installation
To install the necessary libraries, run the following command:

```sh
pip install -r requirements.txt
```

## 🚀 Usage
1. **Download the dataset**: [Download the dataset](https://drive.google.com/drive/folders/1FuE-idAFkLtRukpDCAA9N1TZ-fxwo-EX?usp=drive_link) and place it in the `data/` directory.
2. **Run the Jupyter Notebooks**: Open and run the Jupyter Notebooks in the `notebooks/` directory for analysis.

## 💻 Tech Requirements
- 🐍 Python 3.7+
- 📓 Jupyter Notebook
- 📦 Libraries specified in `requirements.txt`

## 📊 Dataset Details
The dataset includes a variety of variables related to meteorological, soil, and crop factors. Below is an overview of these variables:

### APSIM Output Variables in a Nutshell

#### Periodicity of Output:
- **🕒 Rows (Temporal)**: Common periods include daily, weekly, harvest, and annual. Variables may need to be averaged or summed depending on the interval.
- **📊 Columns**: APSIM's modules have variables that reflect their domain.

### Table of Useful Variables:

#### Meteorological 🌤️:
- **🌧️ rain**: (mm/day)
- **🌡️ maxt, mint**: (9 AM min, max temperatures)
- **☀️ radn**: (Mj/m²) solar radiation

#### Soil Related 🌱:
- **🌍 dlayer**: Depth of layer i (array of mm)
- **💧 SW**: Instantaneous water content (mm/mm)
- **🪨 Air_dry, LL15, DUL, SAT**: Static limits of bucket size (array of mm/mm)
- **🌿 XX_dep**: Same as above, but in (array of mm/layer)
- **🌾 ESW**: Extractable soil water (mm) - relative to LL15
- **🌫️ ES**: Soil evaporation (mm/day)
- **💦 EO**: Potential (unlimited) soil evaporation
- **💨 EOS**: Potential (unlimited) soil evaporation limited by cover
- **🌳 cover_surface_runoff**: Total cover from crops & residues, adjusted for height (0-1)
- **🚰 Runoff**: Water that doesn’t infiltrate must run off
- **🌊 Drain**: Water content above DUL drains into layers below. The bottom layer drains to ...
- **🍂 surfaceom_wt**: Surface residue - stubble & harvester remains (kg/ha)
- **🧪 NO3**: Nitrogen - key plant nutrient (kg/ha), from both fertilizer and residue decomposition

#### Crop Related 🌾 (All weights are dry):
- **🌿 biomass_wt**: Total instantaneous weight (g/m²)
- **🥬 biomass_n**: N content (g/m²)
- **🍃 [root, leaf, stem, grain]GreenWt**: Active plant organ weights
- **🌾 XXXGreenN**: N content of organs (g/m²)
- **🌿 cover_green**: Green (photosynthetically active) cover (0-1)
- **🍂 cover_tot**: Green and senesced cover (0-1)
- **🌡️ TT**: Instantaneous Thermal Time (°C/day) - development rate
- **💧 Ep**: Water uptake (mm)
- **🌱 Height**: Height of crop (mm)
- **🍃 LAI**: Leaf Area Index (m²/m²)
- **☀️ FiPAR**: Fraction of intercepted photosynthetically active radiation
- **🍂 SLAI**: Senesced leaf area index (m²/m²)
- **🌱 LL**: Crop-specific lower limit of water extraction (array of mm/mm)
- **🌿 nfact_photo**: Instantaneous stress factor in photosynthesis calculation (0-1)
- **🌱 root_depth**: Depth that roots extend to (mm)
- **💧 swdef_photo**: Soil water deficit factor in photosynthesis calculation (0-1)
- **📅 StageName**: The (instant) phenological stage name
- **🌾 Yield**: Grain yield (kg/ha)

### Useful Summaries 📊:
- **💧 Crop starting & finishing water content**: Used to calculate gross Water Uptake
- **💧 In-crop water uptake**: Key measure of transpiration
- **🌱 PAWC**: Plant Available Water (Capacity/Content) (mm)
- **🌾 Harvest Index (HI)**: Grain yield / total weight - efficiency measure
- **💧 Water Use Efficiency (WUE)**: Grain produced / water used (kg/mm)
- **☀️ PhotoThermalQuotient (PTQ)**: Mean(radiation / mean temperature) over significant crop phases
- **📊 NDVI vs. LAI**: LAI is the green component; NDVI is a reflectance

## 🤝 Contributing
We welcome contributions! Please read `CONTRIBUTING.md` for details on our code of conduct and the process for submitting pull requests.

## 📄 License
This project is licensed under the MIT License. See the `LICENSE` file for details.
