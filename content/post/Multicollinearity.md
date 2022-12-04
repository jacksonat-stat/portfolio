+++
title= "Multicollinearity"
author= "Andrea Jackson"
date= "2022-12-03"
tags = [
    "Regression",
    "Statistical Analysis",
]
+++

## Multicollinearity
Multicollinearity is a linear association among  regressor variables and exists when two or more regressors have high empirical correlations.

##Mathematical Definition
Muticollinearity exits when there exists a vector,C!=0 such that 

$\sum_{j = 1}^{k} c_{j}x_{j}* = 0$

```
x <- matrix(c(1,2.1,3,6.1),nrow=2,ncol = 2, byrow = TRUE)
x
c <-matrix(c(0,0),nrow=2,ncol=1,byrow=FALSE)
c

showEqn(x, c)
solve(x,c)


```

When this occurs at least one eigenvalue of the x matrix will be close to 0
```
eigen(x)$values
```

What is  it about these small eigenvalues that causes the coefficients to have large variances and poor predictive power?

The coefficients of B = (X*'X)^-1 X'Y can be re-written as

$V\Lambda^{-1}V'X^{*'}Y$

Such that V which is orthogonal ie V' = V^-1

where $\Lamda\$ is a diagonal matrix whose diagonal elements are the eigenvalues of X*'X*

Note that since the inverse of $\Lamda\$  is used in the calcuation of the Beta estimates that means any lamdas close to zero when inverted will be come large and increase the overall coefficients and increase the absolute values of the predicitions
