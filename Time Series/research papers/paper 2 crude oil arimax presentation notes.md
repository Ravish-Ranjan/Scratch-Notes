# Research Paper 2 --- Presentation Notes

## Paper identification

**Title:** *Improving Crude Oil Price Forecasts for India with ARIMAX:
Evidence from the Diebold--Mariano Test*\
**Authors:** Saurabh Mishra and Shubhra Katara\
**Type:** Preprint; explicitly marked as **not peer reviewed** in the
manuscript\
**Running title:** Crude Oil Price Forecasting with ARIMAX in India\
**Study period:** April 2000--March 2025\
**Frequency:** Monthly\
**Observations:** 300\
**Country / context:** India\
**Main idea:** Compare a standard univariate ARIMA model with ARIMAX
that adds the INR/USD exchange rate as an exogenous predictor, and test
whether the difference in forecast accuracy is statistically
significant.

------------------------------------------------------------------------

# 1. What does the research do?

## Research problem

The paper studies **forecasting of Indian crude oil prices**.

The central question is:

> Does adding the INR/USD exchange rate improve crude-oil price
> forecasts compared with using only the historical oil-price series?

The authors compare two models:

1.  **ARIMA**
2.  **ARIMAX**

The difference is important:

### ARIMA

Uses the historical behavior of crude oil prices.

``` text
Past oil prices
      ↓
   ARIMA
      ↓
Future oil price
```

### ARIMAX

Uses historical oil prices **plus an external variable**:

``` text
Past oil prices ──────┐
                      ├──→ ARIMAX ──→ Future oil price
INR/USD exchange rate ┘
```

The paper argues that an Indian oil-price model should account for
exchange-rate dynamics because crude oil is traded internationally in US
dollars and India is highly dependent on imported oil.

------------------------------------------------------------------------

# 2. What data does it use?

## Time period

**April 2000 to March 2025**

That gives:

\[ 25 `\times 12`{=tex} = 300 \]

monthly observations.

------------------------------------------------------------------------

## Target variable

### Indian Basket crude oil price

Measured in:

**USD per barrel**

Source:

**Petroleum Planning and Analysis Cell (PPAC), Ministry of Petroleum and
Natural Gas, Government of India**

------------------------------------------------------------------------

## Exogenous variable

### INR/USD exchange rate

Source:

**Federal Reserve Economic Data (FRED)**

Series:

**EXINUS**

The series represents the INR/USD exchange rate.

------------------------------------------------------------------------

## Data availability

The paper states that the data are openly available through Zenodo.

The paper also states that the data were cleaned and subjected to
outlier correction and consistency checks.

------------------------------------------------------------------------

# 3. Why is the exchange rate relevant?

Suppose international crude oil costs:

\[ \$80/barrel \]

If:

\[ 1\$ = ₹80 \]

then the rupee-denominated equivalent is approximately:

\[ 80 `\times 80`{=tex} = ₹6400 \]

If the rupee depreciates to:

\[ 1\$ = ₹85 \]

the same international price becomes:

\[ 80 `\times 85`{=tex} = ₹6800 \]

Therefore, even if the dollar-denominated oil price does not change,
exchange-rate movements can affect India's domestic oil-cost
environment.

This motivates the inclusion of INR/USD in ARIMAX.

------------------------------------------------------------------------

# 4. Pipeline of the operation

``` text
Monthly Indian Basket crude oil price
                 +
         Monthly INR/USD
                 │
                 ▼
          Data collection
                 │
                 ▼
       Data cleaning / checking
                 │
                 ▼
       Descriptive statistics
                 │
                 ▼
        Exploratory analysis
       ├── Correlation
       └── Rolling statistics
                 │
                 ▼
          ADF stationarity test
                 │
                 ▼
       First differencing
                 │
                 ▼
        ACF / PACF analysis
                 │
                 ▼
         ARIMA specification
             ARIMA(1,1,1)
                 │
          ┌──────┴──────┐
          ▼             ▼
        ARIMA         ARIMAX
          │             │
          │       + INR/USD
          │             │
          └──────┬──────┘
                 ▼
       Forecast generation
                 │
                 ▼
      Residual diagnostics
       ├── Ljung–Box
       └── Jarque–Bera
                 │
                 ▼
     Forecast evaluation
     ├── MAE
     ├── RMSE
     └── MAPE
                 │
                 ▼
        AIC / BIC comparison
                 │
                 ▼
       Diebold–Mariano test
                 │
                 ▼
          Interpretation
```

This is a good slide to reproduce during the presentation.

------------------------------------------------------------------------

# 5. What methods does it choose?

## 5.1 Descriptive statistics

The paper calculates:

-   mean;
-   standard deviation;
-   minimum;
-   maximum;
-   quartiles.

Reported values:

  Variable       Mean   Std. Dev.     Min   Median      Max
  ----------- ------- ----------- ------- -------- --------
  INR/USD       58.35       13.86   39.27    54.34    87.06
  Oil price     65.85       28.07   18.24    64.78   132.47

These show substantial movement in both variables over the 2000--2025
period.

------------------------------------------------------------------------

# 6. Exploratory analysis

## Correlation analysis

The reported correlation between:

-   INR/USD and oil price = **0.18**

The paper interprets the relationship as supportive of including
exchange rates in the forecasting framework.

### Important presentation point

A correlation of 0.18 is not particularly large.

Therefore, do not say:

> "The exchange rate is strongly correlated with oil prices."

A more precise statement is:

> "The paper identifies a positive contemporaneous correlation, although
> the reported correlation is modest; the ARIMAX framework is intended
> to capture dynamic predictive information beyond simple
> contemporaneous correlation."

This is an important distinction.

------------------------------------------------------------------------

## Rolling analysis

The paper uses:

**6-month rolling mean**

and

**6-month rolling standard deviation**

### Purpose

The rolling mean helps visualize the local trend.

The rolling standard deviation provides a view of changing volatility.

The paper highlights volatility spikes around major global shocks,
particularly:

-   2008 global financial crisis;
-   2020 COVID-related disruption.

------------------------------------------------------------------------

# 7. Stationarity testing

The authors use the:

## Augmented Dickey--Fuller (ADF) test

### Null hypothesis

\[ H_0: `\text{Series has a unit root / is non-stationary}`{=tex} \]

### Alternative

\[ H_1: `\text{Series is stationary}`{=tex} \]

------------------------------------------------------------------------

## Reported result

For the crude-oil price:

### Original series

\[ ADF = -2.77 \]

\[ p = 0.063 \]

At the usual 5% significance level, the null is not rejected.

Therefore, the original price series is treated as **non-stationary**.

------------------------------------------------------------------------

## After first differencing

\[ ADF = -11.82 \]

\[ p \< 0.0001 \]

The null is rejected.

Therefore:

\[ d = 1 \]

The series is treated as integrated of order one, (I(1)), for the ARIMA
specification.

------------------------------------------------------------------------

# 8. Why is differencing necessary?

ARIMA requires the integrated component (I(d)).

The original crude-oil price series has a changing level/trend.

First differencing calculates approximately:

\[ `\Delta `{=tex}y_t = y_t-y\_{t-1} \]

This removes much of the non-stationary level behavior.

The result is a series that is more appropriate for modelling temporal
dependence.

------------------------------------------------------------------------

# 9. ACF and PACF

After differencing, the authors examine:

-   ACF --- Autocorrelation Function
-   PACF --- Partial Autocorrelation Function

The plots are used to identify the likely AR and MA orders.

The paper states that the post-differencing ACF/PACF pattern suggests:

\[ ARIMA(1,1,1) \]

------------------------------------------------------------------------

# 10. ARIMA(1,1,1)

The chosen ARIMA model is:

\[ ARIMA(1,1,1) \]

Meaning:

-   (p=1): one autoregressive term;
-   (d=1): first differencing;
-   (q=1): one moving-average term.

------------------------------------------------------------------------

## Estimated coefficients

  Parameter     Coefficient   p-value
  ----------- ------------- ---------
  AR(1)               0.288     0.004
  MA(1)               0.081     0.509
  Sigma²              28.46   \<0.001

The AR(1) coefficient is statistically significant.

The MA(1) coefficient is not statistically significant at the 5% level.

This is worth mentioning if asked about the individual parameter
estimates.

------------------------------------------------------------------------

# 11. Why choose ARIMA?

ARIMA is used as the **baseline univariate model**.

It answers:

> How well can crude oil prices be forecast using their own historical
> behavior?

This is necessary because the researchers need a reference model before
testing whether the exchange-rate variable adds predictive value.

Without the ARIMA baseline, they could not meaningfully quantify the
improvement from ARIMAX.

------------------------------------------------------------------------

# 12. Why choose ARIMAX?

ARIMAX extends ARIMA by adding an external variable.

Conceptually:

\[ `\text{Oil price}`{=tex}\_t = `\text{ARIMA dynamics}`{=tex} +
`\beta`{=tex}(`\text{INR/USD}`{=tex})\_t + `\epsilon`{=tex}\_t \]

The purpose is to capture information that is not contained in the
oil-price history alone.

The authors select INR/USD because:

1.  Crude oil is internationally priced in USD.
2.  India is highly dependent on oil imports.
3.  Exchange-rate fluctuations change the rupee cost associated with
    international oil prices.
4.  Exchange rates can therefore provide predictive information about
    oil-price behavior in the Indian context.

------------------------------------------------------------------------

# 13. Model diagnostics

The authors use residual diagnostics.

## Ljung--Box Q-test

Purpose:

> Check whether residuals still contain autocorrelation.

For ARIMA(1,1,1):

\[ p = 0.97 \]

### Interpretation

There is no evidence of remaining residual autocorrelation.

This is desirable because the model should have captured the predictable
temporal structure.

------------------------------------------------------------------------

## Jarque--Bera test

Purpose:

> Test whether residuals are normally distributed.

Reported:

\[ p = 0.00 \]

The paper therefore observes residual non-normality.

### Important presentation point

Do not hide this result.

You can say:

> "The residuals showed evidence of non-normality, but the Ljung--Box
> result indicated that the residuals did not retain significant
> autocorrelation."

This is more accurate than saying the model is perfect.

------------------------------------------------------------------------

# 14. Forecasting

The paper produces a **12-month forecast** for:

**April 2025--March 2026**

The ARIMA forecast is around:

**USD 70/barrel**

for much of the horizon.

Example reported forecasts:

  Date         Forecast   95% lower CI   95% upper CI
  ---------- ---------- -------------- --------------
  Apr 2025        70.77          60.32          81.23
  Sep 2025        70.09          33.99         106.19
  Mar 2026        70.09          17.02         123.16

------------------------------------------------------------------------

## Important interpretation

The confidence interval becomes much wider as the forecast horizon
increases.

For example:

-   April 2025: relatively narrow interval;
-   March 2026: very wide interval.

This reflects increasing uncertainty as the forecasting horizon grows.

------------------------------------------------------------------------

# 15. How do they evaluate forecasting accuracy?

The paper uses three main error metrics.

## MAE --- Mean Absolute Error

\[ MAE = `\frac{1}{n}`{=tex} `\sum `{=tex}\|y_t-`\hat `{=tex}y_t\| \]

Measures average absolute forecast error.

------------------------------------------------------------------------

## RMSE --- Root Mean Squared Error

\[ RMSE = `\sqrt{
\frac{1}{n}
\sum(y_t-\hat y_t)^2
}`{=tex} \]

Places greater weight on larger errors.

------------------------------------------------------------------------

## MAPE --- Mean Absolute Percentage Error

\[ MAPE = `\frac{100}{n}`{=tex} `\sum`{=tex} `\left`{=tex}\|
`\frac{y_t-\hat y_t}{y_t}`{=tex} `\right`{=tex}\| \]

Expresses average error as a percentage.

------------------------------------------------------------------------

# 16. Why use three metrics?

Because each metric tells something slightly different.

### MAE

Easy to interpret in the original units.

### RMSE

Penalizes large errors more strongly.

### MAPE

Provides a relative percentage measure.

Using several metrics reduces dependence on one particular definition of
forecast error.

------------------------------------------------------------------------

# 17. Model comparison results

The paper reports:

  Metric        ARIMA         ARIMAX
  -------- ---------- --------------
  MAE          7.9537     **6.2081**
  RMSE         9.0226     **7.2944**
  MAPE       10.4929%    **8.1977%**
  AIC        1785.562   **1778.592**
  BIC        1796.541   **1793.230**

The lower values reported for ARIMAX indicate lower forecast error and
lower information criteria in the authors' comparison.

------------------------------------------------------------------------

# 18. What does the improvement mean numerically?

## MAE

From:

\[ 7.9537 \]

to:

\[ 6.2081 \]

Approximate reduction:

\[ `\frac{7.9537-6.2081}{7.9537}`{=tex}`\times100`{=tex}
`\approx21.95`{=tex}% \]

------------------------------------------------------------------------

## RMSE

From:

\[ 9.0226 \]

to:

\[ 7.2944 \]

Approximate reduction:

\[ `\approx19.15`{=tex}% \]

------------------------------------------------------------------------

## MAPE

From:

\[ 10.4929% \]

to:

\[ 8.1977% \]

Approximate reduction:

\[ `\approx21.87`{=tex}% \]

So the reported ARIMAX errors are roughly 19--22% lower depending on the
metric.

------------------------------------------------------------------------

# 19. What is the Diebold--Mariano test?

This is one of the most important parts of the paper.

The error metrics tell us:

> ARIMAX has smaller errors in this experiment.

But there is another question:

> Is the difference in predictive accuracy statistically significant?

The **Diebold--Mariano (DM) test** is used for this.

------------------------------------------------------------------------

## DM test hypothesis

Conceptually:

\[ H_0: `\text{The two forecasts have equal predictive accuracy}`{=tex}
\]

against an alternative that their predictive accuracy differs.

------------------------------------------------------------------------

## Reported result

DM statistic:

\[ 3.432456 \]

p-value:

\[ 0.000598 \]

The p-value is below 0.01.

The authors therefore reject the equal-predictive-accuracy hypothesis.

### Paper's interpretation

The forecast-accuracy difference between ARIMA and ARIMAX is
statistically significant.

------------------------------------------------------------------------

# 20. Why is the DM test useful?

Suppose we only compare:

``` text
ARIMA MAE   = 7.95
ARIMAX MAE  = 6.21
```

We know ARIMAX has lower MAE.

But we do not automatically know whether the observed difference is
statistically meaningful.

The DM test provides a formal statistical comparison of forecast errors.

Therefore the research has two levels of evidence:

``` text
Numerical evidence
       ↓
MAE / RMSE / MAPE
       ↓
ARIMAX has lower errors

Statistical evidence
       ↓
Diebold–Mariano test
       ↓
Difference is statistically significant
```

------------------------------------------------------------------------

# 21. What results are they getting?

The paper reports four major results.

## Result 1 --- Oil prices are non-stationary in levels

The ADF test indicates that the original series is non-stationary.

After first differencing, it becomes stationary.

------------------------------------------------------------------------

## Result 2 --- ARIMA(1,1,1) provides an adequate baseline

The model has:

-   no significant residual autocorrelation according to Ljung--Box;
-   some residual non-normality according to Jarque--Bera.

------------------------------------------------------------------------

## Result 3 --- ARIMAX has lower forecasting errors

ARIMAX reduces:

-   MAE: 7.95 → 6.21
-   RMSE: 9.02 → 7.29
-   MAPE: 10.49% → 8.20%

------------------------------------------------------------------------

## Result 4 --- The improvement is statistically significant

DM test:

\[ DM=3.432456 \]

\[ p=0.000598 \]

Therefore, the paper reports a statistically significant difference in
predictive accuracy.

------------------------------------------------------------------------

# 22. What is their interpretation?

The authors interpret the findings as evidence that **exchange-rate
information contains useful predictive information for Indian crude-oil
price forecasting**.

The main conceptual message is:

> A univariate model based only on past oil prices does not capture all
> relevant information. Adding a macroeconomic variable --- INR/USD ---
> can improve forecasts.

The paper therefore supports a **multivariate forecasting perspective**
for oil prices in an import-dependent economy.

------------------------------------------------------------------------

# 23. Why does ARIMAX potentially improve the forecast?

A univariate ARIMA model essentially asks:

> "What does the past behavior of oil prices tell us about future oil
> prices?"

ARIMAX asks:

> "What does the past behavior of oil prices tell us, and what
> additional information does the exchange rate provide?"

If exchange-rate movements contain information about future oil-price
dynamics, ARIMAX can exploit it.

This is the economic motivation behind the model.

------------------------------------------------------------------------

# 24. Important distinction: prediction vs causal effect

This is very important for presentation.

The paper is primarily a **forecasting study**.

Therefore:

> Better ARIMAX forecasting performance does not automatically prove
> that exchange-rate changes causally determine crude-oil prices.

It establishes that the exchange-rate variable provides useful
predictive information in the specified forecasting framework.

That is a more precise scientific interpretation.

------------------------------------------------------------------------

# 25. Important observation about correlation

The paper reports:

\[ Corr(INR/USD, OilPrice)=0.18 \]

This is a relatively modest contemporaneous correlation.

Yet ARIMAX improves forecast performance substantially.

This illustrates an important time-series concept:

> Predictive usefulness does not have to be the same thing as high
> contemporaneous correlation.

A variable may provide useful information through:

-   lagged effects;
-   temporal dynamics;
-   interactions with the autoregressive structure.

Therefore, the usefulness of INR/USD in ARIMAX should not be judged
solely from the simple correlation coefficient.

------------------------------------------------------------------------

# 26. Important methodological caveat

The paper compares ARIMA and ARIMAX and reports strong improvements.

However, for a rigorous presentation, distinguish:

### What the paper demonstrates

-   lower reported forecasting errors;
-   lower AIC/BIC;
-   significant DM-test result;
-   improved performance within the study's experimental framework.

### What it does not automatically demonstrate

-   universal superiority of ARIMAX for all oil-price forecasting
    problems;
-   causal identification of exchange-rate effects;
-   that INR/USD is the only important external variable;
-   that the same improvement would necessarily hold in another time
    period.

------------------------------------------------------------------------

# 27. Limitations / future work

The paper itself suggests adding additional exogenous variables.

Examples include:

-   global demand shocks;
-   interest-rate differentials;
-   geopolitical risk;
-   other macroeconomic indicators;
-   nonlinear models.

This is important because crude oil prices are affected by many factors
beyond exchange rates.

Potential future models could include:

``` text
ARIMAX
   +
Global demand
   +
Interest rates
   +
Geopolitical risk
   +
Other macro variables
```

------------------------------------------------------------------------

# 28. Preprint status

The manuscript explicitly states:

> **This preprint research paper has not been peer reviewed.**

This should be mentioned in a formal presentation.

It does not mean the analysis is automatically invalid, but it means the
results should be presented as findings of a **preprint**, not as
findings that have already passed journal peer review.

------------------------------------------------------------------------

# 29. AI declaration

The manuscript states that the authors used **Perplexity AI for minor
editorial suggestions such as language refinement and grammar
improvement**.

It states that:

-   research design;
-   modelling;
-   data collection;
-   data cleaning;
-   substantive analysis

were conducted independently by the authors.

This is useful only if your presentation includes a discussion of
research methodology or reproducibility.

------------------------------------------------------------------------

# 30. Presentation-ready 60-second explanation

> "This paper investigates whether the INR/USD exchange rate can improve
> crude-oil price forecasting for India. The authors use monthly Indian
> Basket crude-oil prices and INR/USD exchange rates from April 2000 to
> March 2025, giving 300 observations. They first clean the data,
> examine descriptive and rolling statistics, and use the ADF test to
> establish that the oil-price series is non-stationary in levels but
> stationary after first differencing. ACF and PACF diagnostics lead to
> an ARIMA(1,1,1) baseline model. They then extend this model to ARIMAX
> by adding INR/USD as an exogenous variable. The models are evaluated
> using MAE, RMSE and MAPE, as well as AIC and BIC. ARIMAX reduces MAE
> from 7.95 to 6.21, RMSE from 9.02 to 7.29, and MAPE from 10.49% to
> 8.20%. Finally, the Diebold--Mariano test gives a statistic of about
> 3.43 with a p-value of about 0.0006, so the authors report a
> statistically significant difference in predictive accuracy. Their
> interpretation is that exchange-rate information provides useful
> predictive information beyond the historical oil-price series."

------------------------------------------------------------------------

# 31. Likely presentation questions

### Q1. What is the difference between ARIMA and ARIMAX?

ARIMA uses only the historical target series. ARIMAX additionally
incorporates one or more external explanatory variables.

### Q2. What is the X in ARIMAX?

The X represents **exogenous variables**.

### Q3. Why is INR/USD used?

Because crude oil is internationally traded in US dollars and
exchange-rate changes affect the rupee cost and dynamics associated with
imported oil.

### Q4. Why is differencing performed?

Because the original oil-price series is non-stationary and first
differencing makes it stationary.

### Q5. Why is the model ARIMA(1,1,1)?

The paper uses stationarity results together with ACF/PACF diagnostics
to identify the model structure.

### Q6. What does (p=1) mean?

One autoregressive term.

### Q7. What does (d=1) mean?

The series is differenced once.

### Q8. What does (q=1) mean?

One moving-average term.

### Q9. Why use MAE, RMSE and MAPE together?

They measure forecast error differently: absolute error,
squared-error-sensitive error, and percentage error.

### Q10. Why use the DM test if MAE/RMSE/MAPE are already available?

Because error metrics show the numerical difference, while the DM test
formally tests whether the difference in predictive accuracy is
statistically significant.

### Q11. What does the Ljung--Box test tell us?

Whether residual autocorrelation remains.

### Q12. What does the Jarque--Bera result tell us?

It tests residual normality. The paper finds evidence of non-normal
residuals.

### Q13. Does a significant DM test prove ARIMAX is universally better?

No. It establishes a statistically significant difference for the
forecasts evaluated in this study.

### Q14. Does ARIMAX prove that exchange rates cause oil prices?

No. It demonstrates predictive usefulness, not causal identification.

### Q15. What is the main limitation?

Only one exogenous variable is used, while oil prices are affected by
many global economic and geopolitical factors. The manuscript itself
suggests adding variables such as demand shocks, interest-rate
differentials and geopolitical-risk indicators.

------------------------------------------------------------------------

# 32. One-slide summary

  -----------------------------------------------------------------------
  Component                           Paper
  ----------------------------------- -----------------------------------
  Research question                   Does INR/USD improve Indian
                                      crude-oil price forecasts?

  Country                             India

  Period                              Apr 2000--Mar 2025

  Frequency                           Monthly

  Observations                        300

  Target                              Indian Basket crude oil price

  Exogenous variable                  INR/USD

  Data sources                        PPAC + FRED

  Stationarity                        ADF

  Differencing                        First difference

  Model                               ARIMA(1,1,1)

  Extended model                      ARIMAX

  Diagnostics                         Ljung--Box, Jarque--Bera

  Accuracy metrics                    MAE, RMSE, MAPE

  Information criteria                AIC, BIC

  Statistical forecast comparison     Diebold--Mariano

  ARIMA MAE                           7.9537

  ARIMAX MAE                          6.2081

  ARIMA RMSE                          9.0226

  ARIMAX RMSE                         7.2944

  ARIMA MAPE                          10.4929%

  ARIMAX MAPE                         8.1977%

  DM statistic                        3.432456

  DM p-value                          0.000598

  Main finding                        Exchange-rate information improves
                                      reported forecast accuracy

  Main caveat                         Predictive improvement does not by
                                      itself establish causality or
                                      universal superiority

  Status                              Preprint; not peer reviewed
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 33. The paper in one sentence

> **The study tests whether adding INR/USD exchange-rate information to
> a univariate ARIMA model improves monthly Indian crude-oil price
> forecasts, and reports lower forecast errors plus a statistically
> significant Diebold--Mariano comparison.**
