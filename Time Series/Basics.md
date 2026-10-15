# Basics

1. What is time series? : a set of dependent, ordered data agains timestamp
2. Types
  1. By observations
    1. Discrete-time time series : observations at fixed intervals
    2. Continuous-time time series : continuous observations over a time period
  2. By variable
    1. univariate : one variable over time
    2. multivariate : multiple variable over time
  3. By Duration
    1. cross-sectional : obseration at a instance of time
    2. panel : cross-sectional data over a period of time
  4. By Length
    1. long-time series : with lots of observation
    2. short-time series : few observations
3. Why do TSDA? : study patterns, forcasting, making probability model, develop confidence intervals
4. Steps in TSDA
  1. visualizations
  2. studing the past behaviour
  3. identifing the pattern
  4. forecasting
5. Trend : long-term increase or decrease in data
6. Seasonality : a pattern over a fixed and known period of data where period is related to calendar (can be more than one)
7. cyclicity : a rise and fall pattern with non-fixed time period not necesarrily aligned with calendar and due to some external reason, usally more than 2 year period
8. in general avg length of cycle is longer than season, same with magnitude
9. Seasonal Plot : x-axis seasons, y-axis magnitude
10. ![](asset://localhost/%2Fhome%2Fravish%2FDocuments%2FScratch%20Notes%2Fassets%2FScreenshot%20from%202026-09-13%2021-13-05.png)
11. Seasonal subseries : seprate plot for seach season
12.  
  ![](asset://localhost/%2Fhome%2Fravish%2FDocuments%2FScratch%20Notes%2Fassets%2FScreenshot%20from%202026-09-13%2021-15-29.png)
13.  
  ![](asset://localhost/%2Fhome%2Fravish%2FDocuments%2FScratch%20Notes%2Fassets%2FScreenshot%20from%202026-09-13%2021-15-29.png)
  Scatterplot : done between 2 time-series data to find there relation
14. Correlation plot
15. Lag plot
16. Auto correlation : measures correlation between lagged value os TS, autocorr coefficients makes the ACF
17. Trend is ACF plot : ACF can tell trend if for small lags the ACF value is large and +ve and the value decreases with the lag increase
18. Seasonality in ACF plot : if data has seasonality the ACF plot for seasonal lag gives higher value for multiple of seasonal period than other lags
  1. when data has both a combination of both is seen
19. White noise : TS data which shows no auto correlation, it is uncorrelated across time with E(et) = 0 and Var(Et) = sigma^2 (constant var)
  1. Expected ACF : near 0 (not exact zero cause there might be some noise)
  2. Expect 95% of spikes in ACF to lie within +- (1.96/root(T)) , where T istime series length
  3. if substancial amount of spikes ar outsize the interval that might not be noise

 