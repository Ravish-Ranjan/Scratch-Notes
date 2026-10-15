# Decomposition

1. Adjustments
  1. population adjustment
  2. calendar adjustment
  3. inflation adjustment
2. Transformation
  1. Mathematical
    1. power transformation : 
      1.  
        $$
        w_t = y_t^p
        \newline
        p = power
        $$
         
    2. log transformation :
      1.  
        $$
        w_t = log(y_t)
        $$
    3. inverse transform : 
      1.  
        $$
        w_t = \frac{1}{y_t}
        $$
  2. Box-Cox transformation
    1. Easrly box-cox
      1.  
        $$
        w_t = \begin{cases}  
        log(y_t), \lambda = 0  \\
        \frac{y_1^\lambda - 1}{\lambda}, \lambda \ne 0 \\
        \end{cases}
        $$
         
    2. Modified Box-Cox
      1.  
        $$
        w_t = \begin{cases} 
        log(y_t) , \lambda = 0 \\ 
        \frac{sign(y_t) |y_t|^\lambda -1}{\lambda} \\ \end{cases}
        $$
      2. cases
        1. lambda = 0 : logarithmic transformation
        2. lambda = 1 : no transformations, only adjustment by 1
        3. lambda = 1/2 : square root + linear transformation
        4. lambda = -1 : inverse + +1
  3. Decomposition
    1.  
      $$
      Y_t = f(T_t,S_t,C_t,R_t)
      $$

```
Yt : time series
Tt : trend
St : seasonality
Ct : cyclicity
Rt : residual
```

1. Additive Decomposition : when seasonal fluctuation doesn't vary with time series length 
  1.  
    $$
    Y_t = T_t + S_t + C_t + R_t
    $$
2. Multiplication Decomposition : when seasonal pattern varies with time
  1.  
    $$
    Y_t = T_t * S_t * C_t * R_t
    $$
3. Seasonal adjusted
  1. additive
    $$
    Y_t - S_t
    $$
  2. multiplicative
    $$
    \frac{Y_t}{S_t}
    $$
4. Finding trend
  1. we can use moving avg m-MA : order m moving aveg. where m is window size
    1. odd window size : no worry m-MA
    2. even window size : which size to choose more??
      1. do both and take avg 2-m-MA
      2. here end ones are 1/2m weighted and other middle ones are 1/m giving total m/m = 1 weight 
    3. end k points gets missing where m = 2k + 1 for odd
    4. if m is size of season or cycle it removes that respecivly
    5. weighted moving avg : a weight is assigned to terms in window while [avg.ing](http://avg.ing)
      1. weights are symetric around window and sum to 1
5. decomposition additive
  1. use m-MA to find trend 1-m-MA if m is even
    1. detrend by removing it from Yt
  2. for season 
    1. take avg of a season point for all repeasting seasons  
    2. now you have a vector of avgs of size m : mean center them (0 for additive , 1 for multiplicative)
    3. remove from trend adjusted Yt to get residual or cycle + residual
  3.  

 