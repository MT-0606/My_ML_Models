# Machine Learning Engineer Capstone: Moisture Content

## Description

### Why did you build this project?
I built this project to apply machine learning to a building science problem: moisture accumulation in wood-based wall sheathing, which can contribute to structural deterioration and costly repairs. My building science coursework motivated me to investigate how temperature, relative humidity, and historical moisture measurements could help anticipate moisture conditions.

### What problem(s) does it solve?
The project aims to predict moisture content in middle-height cellulose-insulated wall sheathing 24 hours ahead, using hourly monitoring data from the Building Science Corporation’s study of double-stud walls in the Northeastern United States. A forecast could help building envelope consultants and maintenance staff identify potential moisture concerns earlier and review indoor humidity conditions before problems worsen.

### What have you learned?
Through this work, I learned that a physically plausible relationship does not automatically produce an effective predictive model. Temperature and relative humidity alone were weaker predictors than I expected in the models tested. The results highlighted the importance of considering moisture history alongside environmental conditions, comparing models with a simple baseline, and interpreting prediction errors carefully.

## Features
* **Exploratory data analysis:** Examines seasonal moisture patterns, missing measurements, and anomalies in hourly wall and environmental data.
* **24-hour moisture forecasting:** Predicts moisture content in middle-height cellulose-insulated wall sheathing.
* **Historical and environmental predictors:** Uses previous measurements, temperature, and relative humidity to investigate predictive performance.
* **Baseline comparison:** Compares linear regression with a persistence baseline that assumes moisture content remains unchanged.
* **Model evaluation:** Measures prediction accuracy using mean absolute error (MAE) and mean squared error (MSE).
* **Time-aware validation:** Preserves chronological order and fits preprocessing on training data to prevent information leakage.
  
## How to Use
### 1. Download the project
Clone the repository and enter the project folder:
```bash
git clone https://github.com/MT-0606/My_ML_Models.git
cd My_ML_Models/new_capstone
```
### 2. Install the required packages
The project requires Python and Jupyter Notebook, along with the libraries imported in the notebook. Install the required packages:
```bash
python -m pip install notebook pandas numpy matplotlib seaborn scikit-learn
```
### 3. Check the dataset
Ensure that `0000 Devens Logger Data.csv` is in the project folder. (The original XLSM workbook is excluded from the repository as it is too big.) Check that the notebook's data-loading cell points to the CSV file. If it contains an absolute path from the author's computer, change it to the filename or your own local path.
### 4. Run the notebook
Start Jupyter Notebook:
```bash
jupyter notebook
```
Open `moisture_factors.ipynb`, then choose **Restart Kernel and Run All Cells** (or the equivalent option in your Jupyter interface).
### 5. Review the results
Follow the notebook's analysis and model evaluation. Review the prediction errors and compare the forecasting model with the persistence baseline.

## Technologies
* **Language:** Python
* **Libraries:** `pandas`, `scikit-learn`, `numpy`
* **Environment:** Jupyter Notebook

## Collaborators
This was a solo project, meaning no outside help was given.
