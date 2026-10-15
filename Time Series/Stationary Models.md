# Stationary Models

## 1. Autoregressive Process AR(p)

1. p = order of the model.
  $$
  Y_t = c + e_t + \sum_{i=1}^{p}\phi_i Y_{t-i}
  $$
2. It tells that the current value is dependent on past values.
3. If p=1:
  1. Y_t is stationary if:
  2. -1 < \phi_1 < 1.
4. If p=2:
  1. Y_t is stationary if:
  2. -1 < \phi_2,\quad \phi_1+\phi_2 < 1,\quad \phi_2-\phi_1 < 1.
5. Expected value of AR(p):
  $$
  E(AR(p))=\frac{c}{1-\sum \phi_i}
  $$
    Assuming constant mean.
6. Variance of AR(p):
  $$
  \operatorname{Var}(AR(p))
    =\frac{\sigma_e^2}{1-\sum \phi_i^2}
  $$
    Assuming mean =0 and constant variance.
7. Covariance =0 for lag l, where l>p.
  $$
  \operatorname{Cov}(Y_t,Y_{t-l})=
    \begin{cases}
    \dfrac{\phi_1\sigma_e^2}{1-\sum \phi_i^2}, & l=1,\\[6pt]
    0, & l>1.
    \end{cases}
  $$
8. ACF:
  $$
  ACF_k=\frac{\operatorname{Cov}(Y_t,Y_{t-k})}
    {\operatorname{Var}(Y_t)}
    =\frac{\gamma_k}{\gamma_0}
  $$

## 2. Moving Average Process MA(q)

1. The new value depends on past q errors.
  $$
  Y_t=c+e_t+\sum_{i=1}^{q}\Theta_i e_{t-i}
  $$
2. Expected mean, assuming a constant:
  $$
  E(Y_t)=c
  $$
3. Variance, assuming mean-zero errors:
  $$
  \operatorname{Var}(Y_t)
    =\sigma_e^2+\sigma_e^2\sum_{i=1}^{q}\Theta_i^2
  $$
4. Covariance:
  $$
  \operatorname{Cov}(Y_t,Y_{t-1})
    =\Theta_1 E(e_{t-1}^2)
    =\Theta_1\sigma_e^2
  $$
5. Correlation:
  $$
  ACF_k=\rho_k
    =\frac{\gamma_k}{\gamma_0}
    =\operatorname{Corr}(Y_t,Y_{t-k})
  $$
    
  $$
  \rho_k=
    \begin{cases}
    \dfrac{\Theta_1}{1+\sum_{i=1}^{q}\Theta_i^2}, & k=1,\\[6pt]
    0, & k>1.
    \end{cases}
  $$

## 3. ARMA(p, q)

1. ARMA combines AR(p) and MA(q).
2. It is a combination of autoregressive and moving average processes.
  $$
  ARMA(p,q):
  $$
    
  $$
  Y_t=\sum_{i=1}^{p}\phi_iY_{t-i}
    -e_t-\sum_{j=1}^{q}\Theta_j e_{t-j}
  $$

## 4. ACF Plot

1. General ACF formula:
  $$
  ACF_k=\rho_k
    =\frac{\operatorname{Cov}(Y_t,Y_{t-k})}
    {\sigma_t\sigma_{t-k}}
  $$
2. For a stationary process:
  $$
  \rho_k=\frac{\gamma_k}{\gamma_0}
  $$
3. Properties:
  1. Symmetry:
    $$
    \rho_k=\rho_{-k}
    $$
  2. Bounded values:
    $$
    |\rho_k|\leq 1
    $$
  3. Non-uniqueness: The ACF of two or more stationary normal processes can be the same. It will

 