# Overview

In this folder, we have collected the performance data for the ANN model using each of the five denoising techniques. 
The CSV files beginning with “Short_” denote the performance on short-term stock prediction, while the CSV files beginning with “Long_” denote the performance on long-term stock prediction. 
The Python file “Stock_ANN_MultiStocks.ipynb” contains the ANN model, denoising techniques, and method to collect performance data. 



## Denoising Method Designations:
We applied five denoising techniques (including no denoising) for the data. These five techniques are: 

* No Denoising (‘Orig’)
* Padding-based Fourier Transform Denoising (P-FTD)
* Linear Drift Denoising (LDD)
* Exponential Linear Drift Denoising (Exp-LDD)
* Exponential Variable Denoising (Exp-VD)

Each CSV file contains the performance data collected for either short- or long-term prediction using each of these denoising techniques.
For example, the CSV titled “Short_ANN_Exp_LDD_Results.csv” contains the tabular performance data for short-term prediction using Exp-LDD denoising. 


## CSV Column Labels

The CSV columns are as follows: 
* “Stock” – denotes the stock symbol (^GSPTSE, SLV, etc.)
* “Type” – denotes the Machine Learning model used (LSTM, GRU, ANN, and Transformer)
* “Start Date” – denotes the starting date of the time interval used
* “End Date” – denotes the ending date of the time interval used
* “Seed” – denotes the random seed value used for model training
* “Open (RMSE)”, “High (RMSE)”, “Low (RMSE)”, “Close (RMSE)”, “Volume (RMSE)” – denote the Root Mean Square Error (RMSE) goodness-of-fit measures for the Machine Learning prediction. 
* “Open (MAE)”, “High (MAE)”, “Low (MAE)”, “Close (MAE)”, “Volume (MAE)” – denote the Mean Absolute Error (MAE) goodness-of-fit measures for the Machine Learning prediction. 
* “Open (MAPE)”, “High (MAPE)”, “Low (MAPE)”, “Close (MAPE)”, “Volume (MAPE)” – denote the Mean Absolute Percentage Error (MAPE) goodness-of-fit measures for the Machine Learning prediction. 
* “Open (SDAPE)”, “High (SDAPE)”, “Low (SDAPE)”, “Close (SDAPE)”, “Volume (SDAPE)” – denote the Standard Deviation of Absolute Percentage Error (SDAPE) goodness-of-fit measures for the Machine Learning prediction. 
