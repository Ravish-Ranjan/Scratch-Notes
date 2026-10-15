# Stationality Expected

1. Mean :

$$
\mu = E(X) = \sum_{i = 1}^{N} xi * p(X=xi)
$$

2. Varience :

$$
\sigma^2 = Var(X) = \sum_{i=1}^{N} (xi - \mu)^2 * p(X = xi) = E(X^2) - E(X)^2
$$

3. Standard deviation :

$$
\sigma = \sqrt(\sigma^2)
$$

4. Covarience :

$$
Cov(X,Y) = \sum_{i=1}^{N} (x - \mu)(y-\mu)p(X=x,Y=y) = E(X,Y) - E(X)E(Y)
$$

5. Correlation :

$$
Corr(X,Y) = \frac{Cov(X,Y)}{\sigma_x\sigma_y}
$$

6. Stationary : series whoes properties doesnt depents on the time at which the series is observed
  1. First-order stationary : identicaly if takesn snapshot of series at any point
  2. E(Xt) = constant
7. Type of stationary
  1. weak : constant mean and varience, cov and corr being function of time-diff only
    1. $$ \gamma_k = Y_{t,t+k} $$
  2. strict/strong : prob dist doesnt change over t, it has same joint dist. prob. rg. : iid white noise
  3. if Xr is gaussian TS
8. mean,variance is constant and cov,corr independent of t for any lag k
9. Zero-mean models
  1. IID noise
  2. binary process
  3. random walk :
    $$
    S_t = \sum_{i = 1}^{t} X_i 
    \newline
    S_0 = 0
    $$
  4. simple symetric random walk : when in random walk Xt is binary

 