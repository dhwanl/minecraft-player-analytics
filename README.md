# Polyglot Data Analysis: An Interactive Minecraft Player Dashboard

## Project Overview

This project is an interactive dashboard for analyzing a dataset of Minecraft players, built using a modern, two-language ("polyglot") workflow. It demonstrates using **R for data wrangling/statistics** and **Python for interactive dashboards and machine learning.**

The project transforms raw player demographic data (`players.csv`) and session logs (`sessions.csv`) into a clean, unified dataset. This clean data is then used to power an interactive dashboard built *directly inside a Jupyter Lab notebook* using Python's `ipywidgets`.

### Dashboard Features
* **Part 1: Data Preparation (R)**
    * Raw data is loaded, cleaned, and merged using R's `tidyverse` and `lubridate`.
    * A K-Means clustering analysis is performed in R to segment players into four distinct "personas."
    * The final, clean dataset (`minecraft_dashboard_data.csv`) is saved to disk.

* **Part 2: Interactive Dashboard (Python)**
    * **Interactive Plots:** The dashboard provides `plotly` charts with `ipywidgets` controls to filter the player data by age and experience level in real-time.
    * **Player Personas:** A plot visualizes the four player personas (e.g., "Casual Players," "Power Users") discovered by the R script.
    * **Subscription Predictor:** A machine learning model (Logistic Regression) is trained in Python using `scikit-learn` to predict subscription likelihood. The dashboard provides an interactive tool to get predictions for new, hypothetical players.

## Tech Stack

* **Environment:** Jupyter Lab
* **Data Preparation (R Kernel)**
    * **Language:** R
    * **Key Packages:** `tidyverse`, `lubridate`, `recipes` (for scaling), `kmeans` (for clustering)
* **Dashboard & Modeling (Python Kernel)**
    * **Language:** Python
    * **Key Packages:** `pandas`, `scikit-learn` (for ML), `plotly` (for plots), `ipywidgets` (for interactivity)

## How to Run This Project

This project requires two separate Jupyter notebooks running in the same directory.

### Prerequisites
* Jupyter Lab
* An R kernel installed for Jupyter
* A Python 3 kernel installed for Jupyter
* The raw data files: `players.csv` and `sessions.csv`

### Step 1: Data Preparation (R Notebook)
1.  Create a new notebook named `01_Data_Prep.ipynb` (or similar) using an **R kernel**.
2.  Run the package installer cell to get `tidyverse`, `lubridate`, and `recipes`.
3.  Run the main data preparation cell. This will:
    * Load `players.csv` and `sessions.csv`.
    * Clean, merge, and cluster the data.
    * Save a new file: `minecraft_dashboard_data.csv`.
4.  You can close this notebook once the CSV is created.

### Step 2: The Interactive Dashboard (Python Notebook)
1.  Create a second notebook named `02_Dashboard.ipynb` (or similar) using a **Python 3 kernel**.
2.  Run the package installer cell to get `pandas`, `scikit-learn`, `plotly`, and `ipywidgets`.
3.  Run the "Load Data & Train Model" cell. This loads `minecraft_dashboard_data.csv` and trains the `scikit-learn` model.
4.  Run the remaining cells one by one. Each cell will display a part of the dashboard (the interactive plot, the persona plot, and the prediction tool) in its output.

## Project Context & Acknowledgements

This project was developed to apply the complete data science workflow (data wrangling, exploration, clustering, modeling, and interactive communication) as taught in the **DSCI 100: Introduction to Data Science** course. The R-for-wrangling and Python-for-dashboarding workflow is a practical application of the concepts covered.

## Project File Structure