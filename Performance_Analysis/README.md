# Overview
In this folder, we have collected the statistical performance results for stock prediction. 
The code used for analyzing the performance data is given in the “Stock_Prediction_Performance_Analysis.ipynb” Python file. 

Each of the four Machine Learning methods (LSTM, GRU, ANN, and Transformers) have their own subfolders for the analysis results on short- and long-term stock prediction. 
In each subfolder, we have collected:
* Counts for how many times each method yielded the lowest error measures for each of the 40 stock and time interval combinations (recorded in the “Performance_Counts” CSV files)
* The median performance ratios versus no denoising (Orig) and P-FTD (recorded in the “Orig_Comparison_Ratio” and “Padding_Comparison_Ratio” CSV files, respectively)
* Wilcoxon signed-rank test statistics with significance for the performance ratios (recorded in the “Orig_Wilcoxon_Stat_Results” CSV files)
* Wilcoxon signed-rank test *p*-value (recorded in the “Orig_Wilcoxon_p_value_Results” CSV files)

Please note that median performance ratios less than 1 indicate that our proposed method outperforms the benchmarks (no denoising and/or P-FTD). 
