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

## Mathematical Definition
Muticollinearity occurs when there exists a vector,C!=0 such that 




![multicollinearity](https://latex.codecogs.com/svg.latex?\Large&space;\sum_{j&space;=&space;1}^{k}&space;c_{j}x_{j}*&space;=&space;0)



```
x <- matrix(c(1,2.1,3,6.1),nrow=2,ncol = 2, byrow = TRUE)
#      [,1] [,2]
# [1,]    1  2.1
# [2,]    3  6.1
c <-matrix(c(0,0),nrow=2,ncol=1,byrow=FALSE)
#      [,1]
# [1,]    0
# [2,]    0
showEqn(x, c)
# 1*x1 + 2.1*x2  =  0 
# 3*x1 + 6.1*x2  =  0 



```

When this occurs at least one eigenvalue of the x matrix will be close to 0
```
eigen(x)$values
#[1]  7.12805813 -0.02805813
```

What is  it about these small eigenvalues that causes the coefficients to have large variances and poor predictive power?

 



The Coefficients of ![coefficients](https://latex.codecogs.com/svg.latex?\Large&space;B\&space;=(X^{*'}X)^{-1}&space;X'Y&space;&space;) can be re-written as ![coefficients](https://latex.codecogs.com/svg.latex?\Large&space;V\Lambda^{-1}V'X^{*'}Y&space;&space;)



Such that V is orthogonal ie ![v matrix](https://latex.codecogs.com/svg.latex?\Large&space;V'\&space;=&space;V^{-1}&space;&space;) and ![lambda](https://latex.codecogs.com/svg.latex?\Large&space;\Lambda\&space;&space;) is a diagonal matrix whose diagonal matrix whose diagonal elements are the eigenvalues of ![lambda](https://latex.codecogs.com/svg.latex?\Large&space;X^{*'}X&space;&space;)





Note that since the inverse of ![lambda](https://latex.codecogs.com/svg.latex?\Large&space;\Lambda\&space;&space;) is used in the calculation of the Beta estimates that means any lambdas close to zero when inverted will become large and increase the overall coefficients and increase the absolute values of the predictions