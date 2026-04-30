# MEXE-Electives-2-Final-Assessment-Machine-Learning-Model-Development
Final Assessment — Machine Learning Model

# Final Assessment — Machine Learning Model

## 1. Pair Information

* **Pair Name:** World pop
* **Members:**
1. Queian Kim Jambalos
2. Lelanie Lorraine Hernandez


* **Topic:** World Population Classification of Continents
* **Chosen Model:** Logistic Regression

**Why this model?**
We chose **Logistic Regression** as our baseline model because our objective was to determine if there is a linear relationship between demographic statistics (like population size and density) and geographical location. By using a standard classification algorithm, we aimed to test the hypothesis that population trends are distinct per continent.

## 2. Dataset Overview

* **Dataset Source:** `world_population.csv` https://www.kaggle.com/datasets/iamsouravbanerjee/world-population-dataset
* **Description:** The dataset contains population statistics for 234 countries/territories. The goal is to predict the continent of a country based solely on its demographic figures.
* **Target Variable:** `Continent` (Categorical: Asia, Europe, Africa, Oceania, North America, South America)
* **Features Used:**
* `Area (km²)`
* `Density (per km²)`
* `Growth Rate`
* `World Population Percentage`
* `2022 Population`
* `2020 Population`
* `2015 Population`
* `2010 Population`
* `2000 Population`
* `1990 Population`
* `1980 Population`
* `1970 Population`


## 3. Preprocessing Summary

* **Cleaning steps:** Checked for missing values and filled any potential nulls with `0` to prevent runtime errors.
* **Encoding:** No categorical encoding was required for the features as the input variables selected were all numerical.
* **Scaling:** Applied `StandardScaler`. This converted values into Z-scores to ensure that large numbers (like Population in the millions) did not overpower small decimals (like Growth Rate).
* **Train–test split:** 80% Training / 20% Testing. We used `stratify=y` to ensure that the Test set included a representative sample of countries from every continent.

## 4. Model & Results

* **Model used:** Logistic Regression (`multi_class='multinomial'`, `max_iter=5000`)
* **Metrics:**
* **Accuracy:** ~40%
* **Confusion Matrix:** Shows high confusion between developing nations in different continents.


* **Visualizations:**
* Class Distribution Bar Chart
  <img width="841" height="538" alt="image" src="https://github.com/user-attachments/assets/11b9dc20-a3e4-4b56-b96a-5cb59ae13431" />

* Confusion Matrix Heatmap
  <img width="851" height="547" alt="image" src="https://github.com/user-attachments/assets/673409c2-6a09-4d98-a43a-3b0abb550dd8" />

* ROC Curve
  <img width="1012" height="701" alt="image" src="https://github.com/user-attachments/assets/5bf912ab-7145-4bb8-8594-60718870c02a" />



* **Insights:**
1. **Demographics ≠ Geography:** The modest accuracy proves that population statistics are **global traits**, not continental ones. A small, developing country in Asia looks mathematically identical to one in Africa.
2. **Growth Rate is the Strongest Predictor:** The model successfully learned to distinguish **Africa** (consistently high growth > 2%) from **Europe** (low or negative growth).
3. **Density as a Separator:** High population density helped separate Asian countries from North American ones, though significant overlap remains.
4. **Limitation:** To achieve near-perfect accuracy, **Geospatial Data (Latitude/Longitude)** would be required, as demographics alone are insufficient for precise location prediction.



## 5. How to Run

1. **Install VS Code + Python + Jupyter Extension**
2. **Install dependencies:**
Run the following command in your terminal:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn

```


3. **Open the Notebook:**
Open `World-Population_FinalModel_Jambalos_Hernandez.ipynb` in VS Code.
4. **Run all cells:**
Click "Run All" to load the data, train the model, and see the evaluation results.
*Note: You can use the Live Prediction Tool (Section 3.4) to manually test specific countries.*
