# Machine learning for stock prediction using momentum strategy

**Type:** Master's Thesis 

**Author:** Wing Shan Yeung


**1st Examiner:** Prof. Dr. Stefan Lessmann

**2nd Examiner:** Prof. Dr. Benjamin Fabian


**Model Performance**
![S Paccuracy](https://github.com/sophiayeung/machine-learning-for-stock-prediction-using-momentum-strategy/assets/110398276/22ddd9d2-fe24-41ae-a4b3-94d0945deb4f)
![DAXaccuracy](https://github.com/sophiayeung/machine-learning-for-stock-prediction-using-momentum-strategy/assets/110398276/76cd2779-825a-42d6-8bc0-881375e3c50d)

**Financial Performance**
<img width="839" alt="SP500_return_performance" src="https://github.com/sophiayeung/machine-learning-for-stock-prediction-using-momentum-strategy/assets/110398276/8229e33e-a0ba-4bd9-86d2-8c33d5b8363b">
<img width="829" alt="DAX_return_performance" src="https://github.com/sophiayeung/machine-learning-for-stock-prediction-using-momentum-strategy/assets/110398276/f25937a4-65d4-452c-9884-3226c1dfcd1c">


## Table of Content!
- [Summary](#summary)
- [Working with the repo](#Working-with-the-repo)
    - [Dependencies](#Dependencies)
    - [Setup](#Setup)
- [Reproducing results](#Reproducing-results)
- [Results](#Results)
- [Project structure](-Project-structure)
  

## Summary

Forecasting stock prices are challenging in finance due to the inherent noise in stock price movements and the non-linear relationship between past performance and future stock prices. This paper aims to compare various state-of-the-art neural network models, including Long Short-Term Memory (LSTM), Temporal Convolutional Network (TCN), and transformers, for stock price prediction using the momentum strategy. The momentum strategy involves buying stocks that have recently outperformed their peers and short-selling stocks that have underperformed. Through comparative analysis across two distinct markets (S&P500 for US market and DAX for Germany), this study evaluates the effectiveness of different neural network models in forecasting future stock prices using time series data. 

Our study shows all models achieve similar performance by evaluating model accuracy. Moreover, our study validates the effectiveness of the momentum strategy, particularly 130-30 trading strategy, in achieving significant returns in stock prediction tasks which outperform the market portfolios. 

The GitHub repository contains the experimental part of the thesis.


**Keywords**: neural network, Long Short-Term Memory (LSTM), Temporal Convolutional Network (TCN), transformers, time series stock prediction, momentum strategy (give at least 5 keywords / phrases).

## Working with the repo

### Dependencies

I used Python 3.9 for the study.

### Setup

1. Clone this repository
2. Create an virtual environment (suggest using conda) and activate it
```
conda env create -f thesis.yml
source thesis-env/bin/activate
```
or 

```
python -m venv thesis-env
source thesis-env/bin/activate
```


3. Install requirements
```
pip install --upgrade pip
pip install -r requirements.txt
```


## Reproducing results

* Data Preparation: Due to the large size of dataset, the data for SP500 is not uploaded. Run the 2. Data Collection.ipynb to output the data frin raw_data to \SP500\data. 
* Model Training: The models and data are stored separately in DAX and SP500 folder to avoid mixing up the result. Run the machine learning models with .ipynb file in DAX and SP500 folder directly after data prepation.
* Evaluation: Run the 8.Performance testing.ipybn to produce the analysis. This script analyses the experimental results of five datasets, which corresponds to the section 4 in thesis.


## Results
Section 4 in thesis discusses the main experiment results which are generated from 8.performance_test.ipynb. The ipynb is structured as follow: 

1. Functions: contain functions that are used for further analysis

2. Accuracy Check: import the data and check the accuracy (corresponds to section 4.1.1 Model Accuracy in thesis) 

3. Financial Performance: calcualte the return and risk-retrun characteristics (correponds to section 4.2 Financial Performance in thesis)


## Project structure

```bash
├── README.md
├── paper
  ├── master_thesis_WingShan_Yeung.pdf              -- master Thesis in pdf format
  ├── master_thesis_WingShan_Yeung.tex              -- master Thesis in Latex format
  ├── references_WingShan_Yeung.bib                 -- references in bibtex format
├── thesis.yml                                      -- required libraries in yml format
├── reqirements.txt                                 -- required libraries in txt format
├── raw_data                                        -- unprocessed data from refinitiv
├── 1. data_collection.ipynb                        -- collect data using refinitiv API
├── 2. data_preparation.ipynb                       -- preparing datasets
└── DAX
  ├── 3_RF                                          
      ├── rf_pred                                   -- prediction from random forest
      ├── 3. Random Forest.ipynb                    -- random forest model
  ├── 4_FNN                                         -- feedforward NN model and prediction
  ├── 5_LSTM                                        -- LSTM model and prediction
  ├── 6_Transformer                                 -- transform model and and prediction
  ├── 7_TCN                                         -- TCN model and prediction
  ├── 8_performance
      ├── 8. performance_testing.ipynb              -- anlaysis experiment results          └── SP500                                           -- contain models and result analysis
     

```
