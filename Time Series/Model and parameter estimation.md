# Model and parameter estimation

1. models selection
  1. plot ACF and PACF : based on its behaviour determine the models and its order
2. Parameter selection 
  1. how to determine the parameter of the which are the unknown coefficients
  2. Methods
    1. method of moments
    2. maximum likelyhood estimation
    3. ordinary least squares
  3. Method of moments (mean varience autocovarience)
    1. sample satistics estimated population statistics
    2. example : theoretical autocorrelation = rho, sample autocorrelation = r
    3. compare rho with r and find the coefficients 
  4. Maximum likelihood estimation
    1. we choose parameters which when used in model makes the obsereved data most probable under assumes probability model and conditions
    2. L(params) = P(observed data | params)
    3. example log-licklyhood is used
  5. Ordinary least squares model
    1. pick any params and find error
    2. tune params to get error least (SSE)
3. yule-walker estimation (MoM)
  1. good for AR with large sample size
  2. find sample mean and varience
  3. compare it with actual statistics formula and find coefficients

```
AR(1) = yt = phi yt-1 + et
ACF_1 = rho_0 = phi = statistical formula 
carience = sigma e^2 / (1 - phi^2) = gamma_0
sigmae^2 = (1-phi^2) * gamma_0
estimated phi2 given = 0.8
therefore sigma^2 = (1-0.8^2) (25) = 0
```

4. conditinal least squares
  1. yt = phi yt-1 + et
  2. et= yt - phi yt-1
  3. SSE = sum of (yt - phi yt -1)^2
  4. diff with unknown
  5. = -2 sum (yt-1)(yt - phiyt-1) = 0 for minimum
  6. = sum (yt-1 x *yt) = phi2 sum (ty-1x*  yt-1) 

 