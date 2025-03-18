# Cross-Border Electricity Price Forecasting with Deep Learning  

This repository contains the implementation for **“Cross-Border Electricity Price Forecasting with 
Deep Learning”**, a Bachelor’s thesis conducted at Karlsruhe Institute of Technology (KIT). 
The study systematically evaluates multiple deep learning models for day-ahead electricity price 
forecasting (DAEPF) in the Germany-Luxembourg (DE-LU) bidding zone, leveraging data from 15 
European bidding zones.  

## Thesis Overview  

This study compares various deep learning architectures for forecasting electricity prices 
and evaluates their generalization capabilities across multiple bidding zones. The key aspects of 
this work include:  

- **Benchmarking deep learning models**: NHITS, NBEATSx, TFT, VT, LSTM, and Mamba.  
- **Learning strategies**: Zero-shot, one-shot (correct and incorrect configuration), and few-shot (4 weeks & 30 days).  
- **Feature stages**: Calendar features, gas prices, load data, synthetic price estimates, CO₂ emissions, load, renewable and non-renewable generation, and cross-border trading data.  
- **Hyperparameter optimization**: Automated tuning to select the best-performing models.  
- **Reproducibility**: Storing optimized configurations for later use in transfer learning.  

This implementation systematically trains, optimizes, and evaluates multiple deep learning models to identify the most effective forecasting approach.  

> **Note**: To improve scrollability, the outputs of test cells and some training cells have been removed as they were very long and hindered readability.


## Repository Structure

### Data Folder Structure

The `data/` folder is organized as follows:

- **Germany_time_zone/**: Contains datasets for day-ahead electricity price forecasting in the Germany-Luxembourg zone. This directory includes datasets for each exogenous feature stage.

- **Transfer Learning/**: Includes all the necessary web crawlers required for Transfer Learning. Due to storage limitations, the Transfer Learning datasets are not included in this repository. However, the crawlers can be used to fetch the data by running them in the correct **ascending numerical order**.

- **Plots/**: Contains Jupyter notebooks for visualizing the training and testing datasets.

- **Forecast_Missing_Values/**: Includes the logic and methods used to forecast missing exogenous features, as described in the thesis.

### Model Folder Structure

The `Models/` folder is organized as follows:

- **Baseline Forecasting Models/**: Contains Jupyter notebooks for baseline forecasting models, evaluated on the 2024 test set.

- **[Model_Name]/** (e.g., LSTM, Transformer, NHITS, etc.): Each model has its own dedicated folder, structured as follows:
  - **Evaluation/**: Contains notebooks for evaluating the model across different exogenous feature stages.
  - **Hyperparameter Optimization/** (except Mamba): Holds the logic and individual notebooks for optimizing hyperparameters on multiple exogenous feature stages.
  - **best/**: Stores the best-optimized configurations of the model, tuned for the corresponding exogenous feature stage.

- **Transfer Learning/**: Includes subfolders for models that undergo transfer learning (`NBEATSx`, `NHITS`, `TFT`, `VT`). Each of these models is evaluated on different learning strategies.

This structured organization ensures clear separation of baseline models, hyperparameter tuning, and transfer learning experiments, making it easier to navigate and reproduce results.



