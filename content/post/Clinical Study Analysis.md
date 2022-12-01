+++
title= "Weekly Clinical Data Review"
author= "Andrea Jackson"
date= "11/30/2022"
tags = [
    "T-test",
    "Statistical Analysis",
]
+++




## Statistical Analysis Used Lacanemab in Early Alzeimers Disease 
Two Sample T-test to determine the initial sample sizes for the placebo group and the treatment group.
Alpha is set at .05 and Power is .90. The sigma from a previous study is 2.031 and the estimated delta is .373. The Cohens D is .1836 rounded to .2. The Sample size at these levels is 624.


```
delta <-.373
sigma<-2.031
d<-delta/sigma
d
library(pwr)
pwr.t.test(d=.d,sig.level=.05,power=.90,type = 'two.sample',alternative = "two.sided")

```

## Final Sample Size for study

After accounting for a 20% drop out rate. The New sample size is 783.


