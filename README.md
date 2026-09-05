# Overview

This repository contains the results of a research project on improving stock prediction performance using various Machine Learning models.


Given the high volatility and complexity of the stock market, predicting stock trends accurately (especially in the long term) is a very difficult task.
A variety of tools (including Machine Learning models) have been applied to the task of stock prediction, with varying levels of success.
However, the short-term volatility and stochastic noise of stocks can limit the usefulness of these tools, especially in long-term prediction. 
For this reason, eliminating this short-term noise from the stock data can improve the effectiveness of Machine Learning models.
Song et al. (2021) proposed a Padding-based Fourier Transform Denoising (P-FTD) method for this purpose. 



In this project, we propose several methods of denoising stock data using the Fourier Transform. 
After applying each proposed denoising method to stock data, we train a Machine Learning model and use it to perform both short- and long-term stock prediction. 
We then compare the performance of each Machine Learning model using our denoised data versus the original (noisy) data and data processed using the P-FTD method.


## Data

For this research project, we use the daily Open, High, Low, Close, and Volume (OHLCV) data for several common stocks and ETFs listed on the New York and Toronto Stock Exchanges, collected from Yahoo Finance. 
These stocks and ETFs represent a variety of financial and economic sectors, including (1) Market Indexes, (2) Technology, (3) Resources, 
(4) Finance, (5) Consumer Defensive, and (6) Commodities. 
The list of stocks and ETFs used in this analysis is below:

* The S&P/TSX Composite Index ETF (^GSPTSE)
* Microsoft Corp. (MSFT)
* Tesla Inc. (TSLA)
* Canadian Natural Resources Ltd. (CNQ.TO)
* BHP Group Ltd. (BHP)
* Bank of Montreal (BMO)
* Visa Inc. (V)
* Loblaw Companies Ltd. (L.TO)
* iShares Silver Trust ETF (SLV)
* United States Oil Fund (USO)

To analyze prediction performance across different market conditions, we took four separate two-year time intervals with 8-month gaps between start dates. 
The 8-month gap between these time intervals was chosen to limit the impact of market seasonality on stock trends. 

* January 2022 - January 2024
* September 2022 - September 2024
* May 2023 - May 2025
* January 2024 - January 2026

The OHLCV data for each of the 10 stocks and ETFs from January 2022 to January 2026 are given in the "Stock_Data" folder. 



## Denoising Methods

We collect and compare the performance of Machine Learning prediction using five different denoising methods: 

* No denoising (Orig)
* Padding-based Fourier Transform Denoising (P-FTD), proposed by Song et al. (2021)
* Linear Drift Denoising (LDD)
* Exponential Linear Drift Denoising (Exp-LDD)
* Exponential Variable Denoising (Exp-VD)

The plots for each of these methods is given in the Python file "Fourier_Denoising_Techniques.ipynb".


## Goodness-of-Fit Measures

We collect four different goodness-of-fit measures: the Root Mean Square Error (RMSE), the Mean Absolute Error (MAE), 
the Mean Absolute Percentage Error (MAPE), and the Standard Deviation of Absolute Percentage Error (SDAPE). 
These goodness-of-fit measures are calculated as follows (Tang et al., 2021): 

$$ RMSE = \sqrt{\frac{1}{N_{test}}\sum_{i=1}^{N_{test}} (y_i - \widehat{y}_i)^2} $$

$$ MAE = \frac{1}{N_{test}}\sum_{i=1}^{N_{test}} |y_i - \widehat{y}_i| $$

$$ MAPE =  \frac{1}{N_{test}}\sum_{i=1}^{N_{test}} \left\lvert \frac{y_i - \widehat{y}_i}{y_i}\right\rvert\ \times 100 $$

$$ SDAPE = \sqrt{\frac{1}{N_{test}}\sum_{i=1}^{N_{test}} \left( \left\lvert \frac{y_i - \widehat{y}_i}{y_i}\right\rvert\ \times 100 - MAPE \right)^2} $$


However, in the performance analysis, we focus on the RMSE, MAE, and MAPE goodness-of-fit measures.



## Machine Learning Models


For this project, we compare the performance of data denoising on four different Machine Learning models. The first two models follow a Recurrent architecture, while the remaining two do not. 
The four models used in this project are: 

* Long Short-Term Memory (LSTM)
* Gated Recurrent Units (GRU)
* Artificial Neural Networks (ANN)
* Transformers

The tabular performance data for each of these four models is given in the "LSTM_Results", "GRU_Results", "ANN_Results", and "Transformer_Results" folders. 


## Performance Analysis

Lastly, we analyze and compare the performance for each denoising method. 
To identify statistical significance of difference in performance between our proposed methods and the benchmarks (no denoising and P-FTD), we perform the Wilcoxon signed-rank test. 
The results of our analysis are given in the "Performance_Analysis" folder. 



## References

Song, D., Baek, A. M. C., & Kim, N. (2021). Forecasting stock market indices using padding-based fourier transform denoising and time series deep learning models. *IEEE Access, 9*, 83786-83796. 
https://doi.org/10.1109/ACCESS.2021.3086537

Tang, Q., Fan, T., Shi, R., Huang, J., & Ma, Y. (2021). Prediction of financial time series using LSTM and data denoising methods. *arXiv preprint*. https://doi.org/10.48550/arXiv.2103.03505

