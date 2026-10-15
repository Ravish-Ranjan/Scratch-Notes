# Evaluation

1. MSE
2. RMSE
3. MAE
4. MAPE
5. sMAPE
6. R2 score = 1 - (sum of square error / sum of square deviation)
7. Adjusted R2 score based on degree of freedom

$$
R_adj = 1- (1-R^2)\frac{T-1}{T-1-k}
$$

8. the lower the better

$$
AIC = Tlog (MSE) + 2(k+2)
$$



$$
AIC_C = AIC + \frac{2*(k+2)*(k+3)}{T-k-3}
$$

10. the lower the better

$$
BIC = Tlog(MSE) + (k+2) logT
$$

 