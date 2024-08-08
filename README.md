# 🌾📊 Agricultural Yield Analysis with Machine Learning 🌾📊

This repository features an in-depth analysis of a large agricultural dataset using advanced machine learning and causal inference techniques. The main goal is to understand the factors influencing crop yield and accurately predict it based on weather conditions, soil properties, and farming practices.

🔗 **[Download the dataset](https://drive.google.com/drive/folders/1FuE-idAFkLtRukpDCAA9N1TZ-fxwo-EX?usp=drive_link)**

## 📑 Table of Contents
- [📜 Introduction](#introduction)
- [⚙️ Installation](#installation)
- [🚀 Usage](#usage)
- [💻 Tech Requirements](#tech-requirements)
- [📊 Dataset Details](#dataset-details)
- [📈 Analysis and Methods](#analysis-and-methods)
- [🤝 Contributing](#contributing)
- [📄 License](#license)

## 📜 Introduction
This notebook presents a comprehensive analysis of a large dataset using various machine learning and causal inference techniques. The primary goal of this project is to understand the factors influencing crop yield and to accurately predict yield based on available features.

### Objectives
1. **Data Preprocessing**: Handle missing values, standardize features, and prepare the data for modeling.
2. **Exploratory Data Analysis (EDA)**: Perform visual and statistical analyses to uncover patterns and relationships in the data.
3. **Feature Selection**: Identify the most relevant features for predictive modeling using techniques like Stepwise Forward Selection and Backward Elimination.
4. **Modeling**: Apply multiple regression models, including Linear Regression, Lasso Regression, Ridge Regression, and Random Forest, to predict crop yield.
5. **Model Evaluation**: Evaluate model performance using metrics such as Mean Squared Error (MSE) and R-squared (R²).
6. **Causal Inference**: Utilize methods like DoWhy and Causal Forests to estimate the causal effect of selected features on crop yield.
7. **Comparison of Models**: Compare the performance of different models and methods to identify the most effective approach for predicting crop yield.

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
The dataset contains various features that potentially impact crop yield, including weather conditions, soil properties, and agricultural practices. Key features include:
- **soilCapacity**: Soil water holding capacity
- **yield**: Crop yield
- **EpSum, EpAfterFlowering, CGRAroundFlowering, EpSum_1**: Weather and growth-related metrics

### APSIM Output Variables
APSIM’s text, space-separated output files can be flexibly configured. The time dimension is represented by rows, and the state dimension is represented by columns. Multiple independent output components can be configured in a simulation.

#### Periodicity of Output:
- **🕒 Rows (Temporal)**: Common periods include daily, weekly, harvest, and annual (calendar). Each period is characterized by an event that marks its termination. Depending on this interval, variables may need to be averaged, summed, etc.
- **📊 Columns**: APSIM’s modules have variables that can be reported.

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
- **🌊 Drain**: Water content above DUL drains into layers below. The bottom layer drains to...
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

## 📈 Analysis and Methods
### Data Preprocessing
Ensuring the dataset is clean and ready for analysis by handling missing values and scaling features appropriately.

### Exploratory Data Analysis (EDA)
Generating visualizations like pair plots, correlation heatmaps, and feature importance plots to understand the relationships between features and crop yield.

### Feature Selection
Using statistical techniques to identify the most important features for predictive modeling.

### Model Training and Evaluation
Applying different machine learning models to the dataset and evaluating their performance using various metrics.

### Causal Inference
Employing causal inference techniques to estimate the causal effects of key features on crop yield.

### Visualizations
- **Pair Plot**: Visualize relationships between several key continuous variables simultaneously.
- **Correlation Heatmap**: Visualize the correlation coefficients between variables to identify features highly correlated with the target variable.
- **Feature Importance Plot**: Identify which variables have the most influence on the target variable.
- **Yield Over Years**: Scatter plot showing the distribution of yield values over the years.
- **2D PCA**: Visualize the data in two dimensions using the first two principal components.

## 🤝 Contributing
We welcome contributions! Please read `CONTRIBUTING.md` for details on our code of conduct and the process for submitting pull requests.

## 📄 License
This project is licensed under the MIT License. See the `LICENSE` file for details.
