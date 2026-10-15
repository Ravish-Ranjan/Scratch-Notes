# Models

1. Autoregressive Process AR(p)
  1. p = order of model $$ y_t = c + e_t + \sum_{i=1}^p \phi_i y_{t-i} $$
  2. it tells that current value is dependent on past values
  3. if p = 1
    1. Yt is stationary if
    2. -1 < phi_1 < 1
  4. if p = 2
    1. Yt is stationay if
    2. -1 < phi_2 1, phi_1 + phi2 < 1, phi2 - phi1 < 1
  5. E(AR(p)) = c / (1 - summation(phi_i)) assuming constant mean
  6. Var(AR(p)) = sigma_e^2 / (1 - summation(phi^2)) assuming mean = 0 and constant varience
  7. cov = 0 for lag l where l > p

$$
AR(1)  Cov(Y_t,Y_{t-l}) = \begin{cases} \frac{\phi_1 \sigma_e^2}{1- \sum{\phi_i^2}}, l = 1  0, l>1 \end{cases}
$$

$$
ACF_k = \frac{Cov(Y_t, Y_{t-k})}{Var(Yt)} = \frac{\gamma_k }{\gamma_0}
$$

2. Moving Average at q MA(p)
  1. new value dependent on past q errors

$$
y_t = c + e_t + \sum_{i = 1}^q \Theta_ie_{t-i}
$$

2. Expected mean assuming constant 1. E(Yt) = c 
3. Varience assming mean 0 
1. 
  $$
  Var(y_t) = \sigma_e^2 +\sigma_e^2 \sum_{i=1}^q \Theta_i^2
  $$
4. Covarience 
1. 
  $$
  Cov(Y_t,Y_{t-1}) = \Theta_1 E(e_{t-1}^2)  = \Theta_1\sigma_e^2
  $$
5. Correlation 
1. 
  $$
  ACF_k = \rho_k = \frac{\gamma_k}{\gamma_0} = Corr(Y_t,Y_{t-k}) = \begin{cases} \frac{\Theta_1}{1 + \sum_{i=1}^q \Theta_i^2}, k = 1  0 , k> 1 \end{cases}
  $$
6. ARMA why not both 
7. combination of AR(p) and MA(q) 


$$
ARMA(p,q) = y_t = \sum_{i=1}^p \phi_i y_{t-i} - e_t - \sum_{j=1}^q \Theta_j e_{t-j}
$$

4. ACF plot

$$
ACF_k = \rho_k = \frac{Cov(y_t,y_{t-k})}{\sigma_t \sigma_{t-k}}
$$

2. for stationary 
1. 
  $$
  \rho_k =\frac{ \gamma_k}{\gamma_0}
  $$
3. Properties 
1. 
  $$
  \rho_k = \rho_{-k}
  $$
  ```
  2. 
  ```
  $$
  |\rho_k| \le 1
  $$
  ```
  3. non-uniqueness : ACF for 2 or more stationary normal process can be same,it wil b unique by unique ACF, mean and varience 
  ```
4. White Noise 
5. constant mean and varience 
6. Gaussian white noise when et follows normal distribution 
1. ACF = 1 if k = 0 else 0 
7. Random Walk 
8. just dependent on previous value and current error 


$$
y_t = \mu + e_t + y_{t-1}
$$

3. can be expressed as 
1. 
  $$
  y_t = t\mu + \sum_{i=1}^t ei
  $$
  ```
  2. 
  ```
  $$
  Mean = t\mu  Varience = t\sigma_e^2  cov_k = (t-k)\sigma_e^2  corr_k = \sqrt{1 - \frac{k}{t}}
  $$
4. PACF : due to transitive relation between elements between yt and yt-k maybe new data is just reflecting old data 
5. PACF_k = corr(yt,yt-k | yt-1,yt-2,yt-3 . . . . . . . yt-k+1) 
6. it can be estimated as phi_p in AR(p) model 
7. yale walker equation for ACF 
8. get yt = et + sum of phi_i*yt-i 
9. multiply yt with yt-k = yt-k et + sumof yt-k*phi_i* yt-i 
10. take expectaion on both side and divide by varience = pk = sum phi_i * pk-1 
11. for k 1 its phi

 