# Decomposition

1. Adjustments
  1. population adjustment
  2. calendar adjustment
  3. inflation adjustment
2. Transformation
  1. Mathematical
    1. power transformation : wt = xt^p , where p = power
    2. log transformation : wt = log(xt)
    3. inverse transform : wt = 1/xt
  2. Box-Cox transformation
    1. wt = log(xt) if lambda  = 0 else (xt^lambda - 1)/lambda
    2. wt = log(xt) if lambda  = 0 else (sgn(xt) * |xt|^lambda - 1)/lambda
      1. lambda = 0 : logarithmic transformation
      2. lambda = 1 : no transformations, only adjustment by 1
      3. lambda = 1/2 : square root + linear transformation
      4. lambda = -1 : inverse + +1

 