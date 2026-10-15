# Non-Stationary Models

## 1. Reasons for Non-Stationarity

1. Seasonality is present.
2. Variance changes over time.
3. Unit roots.
4. Deterministic polynomial trend.

## 2. Lag Operator

The lag operator gives the value of the series at a previous time step.

1. First lag:
  $$
  BY_t=Y_{t-1}
  $$
2. Lag of order d:
  $$
  B^dY_t=Y_{t-d}
  $$

## 3. Difference Operator

The difference operator calculates the difference between the current value and the value at a previous lag.

1. Difference operator of lag k:
  $$
  \nabla_k Y_t=Y_t-Y_{t-k}
  $$
2. Second-order differencing:
  $$
  \begin{aligned}
   \nabla_k^2Y_t
   &=\nabla_k(\nabla_kY_t)\\
   &=\nabla_k(Y_t-Y_{t-k})\\
   &=\nabla_kY_t-\nabla_kY_{t-k}\\
   &=Y_t-2Y_{t-k}+Y_{t-2k}
   \end{aligned}
  $$
3. First-order differencing using the lag operator:
  $$
  \nabla Y_t=(1-B)Y_t
  $$
4. Differencing of order d:
  $$
  \nabla^dY_t=(1-B)^dY_t
  $$

## 4. Differencing a Polynomial Trend

For a polynomial trend of order k, we need to apply the difference operator k times to make it stationary.

## 5. Components of a Time Series

For any time-series data:

$$
Y_t=m_t+s_t+S_t
$$

Where:

- m_t = trend component.
- s_t = seasonal component.
- S_t = additional component as denoted in the original notes.

Seasonal differencing:

$$
\nabla_dY_t=Y_t-Y_{t-d}
$$

Where d is the seasonal period.

For the decomposition above, differencing the individual components gives:

$$
\nabla_dY_t
=(m_t-m_{t-d})
+(s_t-s_{t-d})
+(S_t-S_{t-d})
$$

## 6. ARIMA Model

ARIMA makes a non-stationary series stationary through differencing.

$$
ARIMA(p,d,q)=ARMA(p,q)
\text{ on } \nabla^dY_t
$$

Where d is the order of differencing required to make the series stationary.

1. Differencing with a seasonal lag k can remove seasonality when k is the seasonal period.
2. Differencing of order d removes non-stationarity associated with a trend.

## 7. Unit Root Tests

Unit root tests determine whether a time series has a unit root, which is associated with non-stationarity.

### 7.1 Augmented Dickey–Fuller (ADF) Test

The ADF test checks whether a unit root is present.

- H_0: A unit root is present; the series is non-stationary.
- H_1: No unit root; the series is stationary.

Decision rule at the 5% significance level:

- p>0.05: Fail to reject H_0.
- p\leq0.05: Reject H_0.

### 7.2 KPSS Test

The KPSS test checks whether a time series is stationary around a mean or a deterministic trend, depending on the test specification.

- H_0: The series is stationary.
- H_1: The series is non-stationary.

Decision rule at the 5% significance level:

- p>0.05: Fail to reject H_0; the series is consistent with stationarity.
- p\leq0.05: Reject H_0; evidence of non-stationarity.

### 7.3 Phillips–Perron (PP) Test

The Phillips–Perron test checks for a unit root and uses corrections for serial correlation and heteroscedasticity.

- H_0: The series has a unit root and is non-stationary.
- H_1: The series is stationary.

## 8. Cycle Phases

1. Expansion.
2. Peak.
3. Recession.
4. Depression.
5. Trough.
6. Recovery.

## 9. Types of Seasonality

### 9.1 Deterministic Seasonality

The seasonal pattern remains constant across seasons.

$$
S_t=S_{t+i d}
$$

Where d is the seasonal period and i is an integer.

### 9.2 Seasonality That Evolves as a Stationary Process

The seasonal component evolves over time as a stationary process.

$$
S_t=\operatorname{mean}(S)+v_t
$$

Where:

- E(v_t)=0.
- v_t is stationary.

### 9.3 Seasonality That Evolves as a Non-Stationary Process

The seasonal component evolves over time and includes a random disturbance.

$$
S_t=S_{t-d}+v_t
$$

Where v_t introduces variability.

## 10. SARIMA Model

SARIMA makes a time series stationary by accounting for both trend differencing and seasonal differencing.

### Model equation

$$
\Phi_P(B^S)\phi_p(B)
(1-B^S)^D(1-B)^dY_t
=
\Theta_Q(B^S)\theta_q(B)e_t
$$

Where:

1. S = seasonal period.
2. D = seasonal differencing order.
3. P = seasonal AR order.
4. Q = seasonal MA order.
5. d = trend differencing order.
6. p = trend AR order.
7. q = trend MA order.
8. \phi_p(B) = non-seasonal AR polynomial.
9. \theta_q(B) = non-seasonal MA polynomial.
10. \Phi_P(B^S) = seasonal AR polynomial.
11. \Theta_Q(B^S) = seasonal MA polynomial.

The small \phi and \theta denote the non-seasonal AR and MA components, while the capital \Phi and \Theta denote the seasonal AR and MA components.