# Research Paper 1 --- Presentation Notes

## Paper identification

**Title:** *A blend of renewable and non-renewable energy consumption on
economic growth of India: The role of disaggregate energy sources*  
**Authors:** Biswanath Behera, Sanhita Sucharita, Biswajit Patra,
Narayan Sethi  
**Journal:** *Environmental Science and Pollution Research*  
**Year / volume / pages:** 2024, 31, 3902--3916  
**DOI:** 10.1007/s11356-023-31372-0  
**Study period:** 1985--2021  
**Country:** India  
**Observations:** 37 annual observations  
**Main idea:** Instead of treating renewable and non-renewable energy as
single aggregated categories, the paper separates energy consumption
into individual sources and examines how each source is related to
India's economic growth.

---

# 1. What does the research do?

## Research problem

The paper studies the **energy--economic growth relationship in India**.

The key question is:

> Does the type of energy consumed matter for India's economic growth?

Rather than using one total renewable-energy variable and one total
non-renewable-energy variable, the authors disaggregate energy
consumption into individual sources.

### Renewable sources

- Hydro energy
- Nuclear energy

### Non-renewable sources

- Coal
- Oil

The model also controls for:

- Natural resource rent
- Political stability

The authors are interested in both:

1. **Short-run effects** --- what happens to economic growth when
  energy consumption changes in the short term?
2. **Long-run effects** --- what relationship persists over a longer
  period?

They additionally use **Variance Decomposition Analysis (VDA)** to study
how shocks to the different variables contribute to fluctuations in
economic growth over a 10-year forecast horizon.

---

## Main research objectives

1. Determine whether individual renewable and non-renewable energy sources affect India's economic growth.
2. Separate **short-run** and **long-run** effects.
3. Test whether the variables have a long-run equilibrium relationship.
4. Determine how much future variation in economic growth can be attributed to shocks in different energy sources and control  variables.
5. Draw implications for India's energy mix and sustainable economic growth.

---

# 2. What data does it use?

## Time period

**1985--2021**

This gives:

**37 annual observations**

The relatively small sample is mainly because the study requires long,
consistently available annual series for several disaggregated energy
variables.

---

## Dependent variable

### Economic growth

Economic growth is represented using **GDP growth / log-transformed GDP
growth**.

The authors use logarithmic transformation because it:

- helps interpret coefficients in elasticity terms;
- reduces skewness;
- makes the variables more suitable for the econometric framework.

The dependent variable is denoted as:

$$
\ln {=tex}GDPR
$$

---

## Main explanatory variables


| Variable | Meaning                     | Role                 |
| -------- | --------------------------- | -------------------- |
| HEC      | Hydro energy consumption    | Renewable Energy     |
| NEC      | Neuclear energy consumption | Renewable Energy     |
| CC       | Coal consumption            | Non-Renewable Energy |
| Oc       | Oil consumption             | Non-Renewable Energy |


Energy consumption is measured in **terawatt-hours (TWh)**.

---

## Control variables


| Variable | Meaning                                    | Purpose                               |
| -------- | ------------------------------------------ | ------------------------------------- |
| NRR      | Natural resource rent (% of GDP)           | Controls for resource abundance/rent  |
| PS       | Political stability / political risk index | Controls for political conditions     |
| DUM2015  | Structural-break dummy                     | Captures a detected break around 2015 |


---

## Data sources

The paper combines several secondary sources:

- **World Development Indicators (World Bank)** --- GDP and -resource-rent data.
- **British Petroleum Statistical Review of World Energy** --- major consumption series.
- **Our World in Data** --- hydro/nuclear-related energy data.
- **Political Risk Service (PRS) Group / ICRG** --- political/risk information.

The study therefore uses a **multi-source annual time-series dataset for
India**.

---

# 3. What is the pipeline of the operation?

```text
India annual data: 1985–2021
             │
             ▼
      Variable selection
             │
             ├── GDP growth
             ├── Hydro
             ├── Nuclear
             ├── Coal
             ├── Oil
             ├── Natural resource rent
             └── Political stability
             │
             ▼
       Log transformation
             │
             ▼
Descriptive statistics + correlation analysis
             │
             ▼
     Stationarity testing
     ├── ADF test
     ├── Phillips–Perron test
     └── Zivot–Andrews structural-break test
             │
             ▼
       Lag selection
   AIC / SIC / HQC / VAR
             │
             ▼
      ARDL bounds test
       for cointegration
             │
             ▼
     ARDL estimation
     ├── Short-run effects
     └── Long-run effects
             │
             ▼
      Diagnostic testing
     ├── Serial correlation
     ├── Heteroskedasticity
     ├── Jarque–Bera normality
     └── RESET
             │
             ▼
     Structural stability
     ├── CUSUM
     └── CUSUM of Squares
             │
             ▼
 Variance Decomposition Analysis
       (10-year horizon)
             │
             ▼
      Interpretation
      + policy implications
```

This is an important presentation slide because it shows that the paper
does not jump directly to ARDL. It first establishes that the data are
suitable for the model.

---

# 4. What methods does it choose?

## 4.1 Descriptive statistics and correlation analysis

The authors first examine:

- mean;
- standard deviation;
- minimum and maximum;
- skewness;
- kurtosis;
- correlations.

This establishes the basic properties of the variables before
econometric modelling.

---

## 4.2 ADF and Phillips--Perron unit-root tests

### Why?

Time-series regression can produce misleading results when variables are
non-stationary.

The authors therefore determine whether the variables are stationary at:

- level, (I(0));
- first difference, (I(1)).

The paper reports that the variables are suitable for ARDL because they
are stationary at level and/or first difference, with no variable
requiring second differencing.

---

## 4.3 Zivot--Andrews structural-break test

### Why?

A normal unit-root test can be affected by structural breaks.

The authors therefore also test for unit roots while allowing for a
structural break.

This is useful because India's economy and energy system changed
substantially over the 1985--2021 period.

---

## 4.4 VAR-based lag selection

The authors compare lag-selection criteria including:

- AIC;
- SIC;
- HQC.

The criteria identify **one lag** as the optimal lag.

The authors use **HQC** for the subsequent specification.

---

## 4.5 ARDL bounds testing

### ARDL = Autoregressive Distributed Lag

The ARDL model is the central method of the paper.

It is used to estimate:

- short-run relationships;
- long-run relationships;
- adjustment toward long-run equilibrium.

### Why ARDL?

This is one of the most important methodological choices in the paper.

ARDL is appropriate because:

1. The variables are a mixture of (I(0)) and (I(1)) variables.
2. No variable is (I(2)).
3. The sample is relatively small: only 37 annual observations.
4. ARDL can simultaneously estimate short-run and long-run
  relationships.
5. The bounds-testing framework can test for cointegration without
  requiring every variable to have the same integration order.

---

## 4.6 ARDL bounds test for cointegration

The reported F-statistic is:

 F = 9.598 

The statistic exceeds the relevant upper critical bound at the reported
significance levels.

### Interpretation

The authors conclude that the variables are **cointegrated**.

In simple terms:

> Although the variables may move differently in the short run, they
> share a statistically meaningful long-run equilibrium relationship.

---

## 4.7 Error Correction Model (ECM)

The ARDL framework includes an error-correction term.

Reported:

 ECT(-1) = -1.205 

with:

 p  0.001 

### Why?

The ECM tells us how deviations from the long-run equilibrium are
corrected over time.

A negative and significant ECT indicates that short-run deviations tend
to be corrected toward the long-run relationship.

---

## 4.8 Diagnostic tests

The authors check:

- Breusch--Godfrey serial correlation;
- Breusch--Pagan--Godfrey heteroskedasticity;
- Jarque--Bera normality;
- Ramsey RESET.

Reported p-values are above 0.05.

The authors therefore interpret the estimated model as having:

- no problematic serial correlation;
- no significant heteroskedasticity;
- acceptable residual normality;
- no major RESET specification problem.

---

## 4.9 Structural-break analysis

A multiple breakpoint test identifies **2015** as a relevant breakpoint
for economic growth.

The authors introduce:

  

$$
DUM2015 =
\begin{cases}
0, & \text{up to 2014}\\
1, & \text{from 2015 onward}
\end{cases}
$$

### Why?

This prevents an important structural change from being ignored by the
regression.

---

## 4.10 CUSUM and CUSUM of Squares

These tests examine whether the estimated coefficients remain stable
over the sample period.

The paper reports that the test paths remain within the 5% critical
boundaries.

### Interpretation

The authors regard the model as **stable over the sample period**.

---

## 4.11 Variance Decomposition Analysis (VDA)

VDA is used to answer a different question from ARDL.

ARDL asks:

> How is one variable related to another in the short and long run?

VDA asks:

> How much of the future forecast-error variance of a variable is
> associated with shocks to each variable?

The authors use a **10-year forecast horizon**.

---

# 5. Why did the authors choose these methods?

The methodological logic is:

### Problem 1: Time-series data may be non-stationary

→ Use ADF and PP tests.

### Problem 2: Structural breaks may affect stationarity

→ Add Zivot--Andrews testing.

### Problem 3: Variables may have different integration orders

→ ARDL is suitable for a mixture of (I(0)) and (I(1)), provided none is
(I(2)).

### Problem 4: Need both short-run and long-run relationships

→ ARDL + ECM.

### Problem 5: Need to know whether a long-run equilibrium exists

→ ARDL bounds test.

### Problem 6: Need to check model reliability

→ Serial-correlation, heteroskedasticity, normality and RESET tests.

### Problem 7: Need to verify stability

→ CUSUM and CUSUMSQ.

### Problem 8: Need to understand the relative contribution of shocks

→ Variance Decomposition Analysis.

This is the core methodological reasoning you should explain during a
presentation.

---

# 6. What results are they getting?

## 6.1 Stationarity

The unit-root analysis indicates that the variables are stationary at
level and/or first difference, with the main variables suitable for ARDL
and no variable being (I(2)).

This satisfies an important requirement of the ARDL bounds approach.

---

## 6.2 Cointegration

The ARDL bounds-test statistic is:

 F = 9.598 

The statistic exceeds the relevant upper bound.

### Result

The variables have a **long-run cointegrating relationship**.

---

# 7. Main ARDL results

The key ARDL estimates are:

---

  Variable            Short-run Short-run              Long-run Long-run
                    coefficient significance        coefficient significance

---

  Hydro                  -0.358 Not                      -1.312 Not
                                significant                     significant

  Nuclear                 0.369 Not                       0.307 Not
                                significant                     significant

  Coal                    2.049 Significant at            1.700 Significant at
                                10%                             10%

  Oil                     7.993 Significant at           -1.377 Significant at
                                1%                              10%

  Natural                 0.159 Not                       0.132 Not
  resource                      significant                     significant
  rent                                                          

  Political               1.978 Significant at            1.641 Significant at
  stability                     10%                             10%

  2015 dummy             -0.112 Not                      -0.093 Not
                                significant                     significant

---

**Important:** Statistical significance in the paper is indicated using
*, ** and ***; the table reports the conventional significance levels.

---

# 8. Interpretation of the main results

## Hydro energy

The coefficient is negative in both the short and long run, but the
paper reports it as statistically insignificant.

### Interpretation

The study does **not provide statistically strong evidence** that hydro
consumption has a measurable effect on economic growth over this sample.

The authors discuss possible explanations involving environmental and
social costs associated with poorly managed hydropower development.

---

## Nuclear energy

The coefficient is positive in both the short and long run but
statistically insignificant.

### Interpretation

The estimated relationship is positive, but the evidence is insufficient
to conclude that nuclear consumption has a statistically significant
effect on GDP growth in this sample.

---

## Coal

Coal is positive and statistically significant in both the short and
long run.

Long-run coefficient:

 1.700 

The authors interpret this as approximately:

> A 1% increase in coal consumption is associated with a 1.70% increase
> in economic growth in the estimated long-run relationship.

The short-run coefficient is approximately:

 2.049 

### Interpretation

Coal has a substantial role in the estimated Indian energy-growth
relationship, consistent with its large role in electricity generation
and industrial activity.

---

## Oil

Oil has a particularly interesting result.

### Short run

 7.993 

positive and statistically significant.

### Long run

 -1.377 

negative and statistically significant at the reported 10% level.

### Interpretation

The short-run and long-run relationships have **opposite signs**.

This means the relationship between oil consumption and economic growth
changes depending on the time horizon.

A possible interpretation given by the authors is:

- oil consumption can support economic activity in the short term;
- continued dependence on oil can become detrimental to long-run
growth;
- energy conservation and transition toward cleaner energy sources may
alter the long-run relationship.

This is an important point to mention in a presentation because it
demonstrates why separating short-run and long-run effects matters.

---

## Political stability

Political stability has a positive and statistically significant
relationship with economic growth in both short and long run.

The paper interprets this as evidence that a more stable institutional
environment can support economic activity and policy implementation.

---

## Natural resource rent

The coefficient is positive but statistically insignificant.

The paper therefore does not find strong statistical evidence that
natural-resource rent independently determines economic growth in this
specification.

---

# 9. Error-correction result

The error-correction coefficient is:

 ECT(-1) = -1.205 

and is statistically significant.

### Interpretation

The negative sign is consistent with convergence toward the long-run
equilibrium.

The magnitude greater than 1 suggests relatively rapid correction in the
estimated specification.

For presentation, avoid saying simply:

> "120.5% of the disequilibrium is corrected."

A safer statement is:

> "The significant negative error-correction coefficient indicates
> strong adjustment toward the long-run equilibrium after short-run
> deviations."

---

# 10. Variance Decomposition results

For economic growth after 10 years:

  Source of shock           Contribution to variance of GDP growth

---

  Own GDP-growth shock                                     44.384%
  Nuclear energy                                           16.500%
  Political stability                                      14.804%
  Coal                                                     12.403%
  Oil                                                       4.914%
  Natural resource rent                                     2.051%
  Hydro                                                     2.432%
  2015 dummy                                                2.512%

### Main interpretation

At the 10-year horizon, the largest contributor is the **economic-growth
variable's own shock**.

Among the external variables, the paper reports relatively large
contributions from:

- nuclear energy;
- political stability;
- coal consumption.

The VDA therefore complements the ARDL results: a variable can have a
particular regression coefficient while also contributing differently to
forecast-error variance.

---

# 11. What is their overall interpretation?

The paper's central interpretation is:

> India's economic growth during 1985--2021 is closely connected with
> its energy consumption structure, but the effect depends strongly on
> the individual energy source and on the time horizon.

The study finds stronger evidence for **non-renewable energy sources**,
especially coal and oil, than for the renewable sources included in the
model.

However, the authors do **not** interpret this as a reason to
permanently increase dependence on fossil fuels.

Their broader argument is that India's current growth structure remains
energy-intensive and historically dependent on conventional energy,
while the country needs to expand cleaner energy capacity to make growth
more sustainable.

---

# 12. Important distinction: association vs causation

This is worth mentioning during presentation.

The ARDL estimates describe **statistical relationships** between the
variables.

They should not automatically be presented as proof that:

> "Increasing coal consumption causes GDP to increase by exactly 1.70%."

A more accurate presentation statement is:

> "The estimated long-run elasticity between coal consumption and
> economic growth is positive and statistically significant in the
> model."

The paper discusses economic mechanisms and policy implications, but the
econometric coefficients should be interpreted within the model and data
limitations.

---

# 13. Why is the paper interesting?

## 1. It disaggregates energy sources

Instead of:

```text
Renewable energy
vs
Non-renewable energy
```

it uses:

```text
Hydro
Nuclear
Coal
Oil
```

This produces a more detailed picture.

---

## 2. It separates short run and long run

Oil is a good example:

```text
Short run:  positive and significant
Long run:   negative and significant
```

A single aggregated regression would hide this difference.

---

## 3. It considers structural change

The 2015 breakpoint is explicitly incorporated.

---

## 4. It combines multiple econometric tools

The study does not rely on one regression alone.

It combines:

- stationarity tests;
- structural-break testing;
- ARDL;
- ECM;
- diagnostics;
- stability tests;
- VDA.

---

# 14. Limitations and useful points to mention

## 14.1 Small sample

There are only:

**37 annual observations**

This is a major practical limitation because the model contains several
variables.

---

## 14.2 Limited renewable-energy coverage

The authors explicitly state that some renewable sources were excluded
because sufficiently continuous data were not available.

In particular, wind, biomass and solar were not included in the main
empirical analysis because consecutive data availability began later.

This matters because India's renewable-energy landscape is broader than
hydro and nuclear.

---

## 14.3 Annual frequency

The use of annual data means short-term fluctuations are not visible.

Monthly or quarterly data could capture:

- energy shocks;
- economic cycles;
- policy changes;
- short-run adjustments

in greater detail if suitable data were available.

---

## 14.4 Model specification

Economic growth depends on many other factors.

The paper itself suggests future work incorporating:

- technological advancement;
- capital formation;
- additional renewable-energy sources.

---

## 14.5 Interpretation of energy coefficients

Energy consumption and economic growth can influence each other.

Therefore, interpreting the coefficients as simple one-way causality
requires caution.

---

# 15. Presentation-ready 60-second explanation

> "This paper investigates how different sources of renewable and
> non-renewable energy consumption are related to India's economic
> growth from 1985 to 2021. Instead of aggregating energy into broad
> categories, the authors separately examine hydro, nuclear, coal and
> oil consumption, while controlling for natural-resource rent and
> political stability. Because the data are time-series data, the
> authors first perform ADF, Phillips--Perron and Zivot--Andrews
> unit-root tests. They then use ARDL bounds testing because the
> variables are a mixture of I(0) and I(1) and the sample is relatively
> small. The bounds test confirms a long-run relationship, after which
> the ARDL model estimates short-run and long-run effects. The study
> finds that coal has a positive significant relationship with economic
> growth in both horizons, while oil is positive in the short run but
> negative in the long run. Hydro and nuclear effects are statistically
> insignificant. The authors then use variance decomposition to examine
> how shocks contribute to economic-growth fluctuations over ten years.
> Overall, the paper argues that India's growth remains strongly
> connected to conventional energy, while a gradual transition toward
> renewable energy is important for sustainable growth."

---

# 16. Likely presentation questions

### Q1. Why did they use ARDL instead of ordinary regression?

Because the data are time-series data, variables have different
integration orders, and the authors want to estimate both short-run and
long-run relationships.

### Q2. What does I(0) mean?

A variable is stationary in its original level.

### Q3. What does I(1) mean?

The original series is non-stationary, but its first difference is
stationary.

### Q4. Why can't ARDL be used if a variable is I(2)?

The standard ARDL bounds-testing framework assumes variables are at most
I(1).

### Q5. What is cointegration?

Cointegration means non-stationary variables share a stable long-run
equilibrium relationship.

### Q6. Why is an error-correction term needed?

It captures how deviations from the long-run equilibrium are corrected
over time.

### Q7. Why use VDA after ARDL?

VDA answers a different question: it quantifies the contribution of
shocks from different variables to future forecast-error variance.

### Q8. Why was a 2015 dummy introduced?

A structural-break test identified 2015 as a relevant breakpoint in
economic growth.

### Q9. What is the most interesting empirical result?

Oil has opposite short-run and long-run signs:

- short run: positive and significant;
- long run: negative and significant.

### Q10. Does the study prove that coal causes economic growth?

No. It establishes statistically significant relationships within the
specified dynamic model; causal interpretation requires additional
identification assumptions and evidence.

---

# 17. One-slide summary

---

  Component                           Paper

---

  Research question                   How do individual energy sources
                                      relate to India's economic growth?

  Country                             India

  Period                              1985--2021

  Frequency                           Annual

  Observations                        37

  Dependent variable                  Log GDP growth

  Renewable variables                 Hydro, nuclear

  Non-renewable variables             Coal, oil

  Controls                            Natural-resource rent, political
                                      stability

  Stationarity                        ADF, PP, Zivot--Andrews

  Main model                          ARDL

  Long-run test                       ARDL bounds test

  Short/long-run adjustment           ECM

  Stability                           CUSUM, CUSUMSQ

  Shock analysis                      VDA

  Cointegration                       Confirmed

  Strong positive relationship        Coal

  Oil result                          Positive short run, negative long
                                      run

  Hydro/nuclear                       Not statistically significant

  Main conclusion                     India's growth remains closely
                                      linked to conventional energy;
                                      expanding cleaner energy is
                                      important for sustainable growth

---

 