# 02-diagnostics

### A. Probability Table of Genetic Condition
We were given the _sensitivity_, _specificity_, and _prevalence_. 

| Table | $D+$ | $D-$ | Total |
| ----- | -- | -- | ----- |
| $T+$ | $0.00085$ | $0.04995$ | $0.0508$ |
| $T-$ | $0.00015$ | $0.94905$ | $0.9492$ |
| Total | $0.001$ | $0.999$ | $1$

### B. Negative Predictive Value of the Test
$$P(D- \| T-) = \frac{P(T- \cap D-)}{P(T-)} = 0.99984$$
This means that if the test yields a negative result, there is a high probability that the true status is also negative.

### C. Positive Predictive Value as a Function
The positive predictive value with the default prevalence of $P(D+) = 0.001$ is $\frac{0.00085}{0.05080} = 0.0167$. This means there are high chances of false positives. This is not because the test is necessarily a bad one, but because it is such a rare condition that there are more likely to be false positives than true positives.

We can study the behavior of positive predictive value if we make it into a function of an increasing variable $P(D+)$. After reviewing the code done in class, I recreated this plot under this context.

```
# constant for sensitivity and specificity
sensitivity <- 0.85
specificity <- 0.95

# predictive positive value function
ppv <- function(x, sen, spec){ 
  sen*x/(sen*x+(1-spec)*(1-x))
}

# plotting
xxx <- seq(0.001,1,by = 0.01)
yyy <- ppv(xxx, sensitivity, specificity)
plot(xxx,yyy, type = "l", lwd = 5, col = "navy", xlab = "Prevalence", ylab = "Positive Predictive Value")
```

This code yielded this plot: 

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/ff59b5e2-2d7e-4cfe-be6a-005dc22d385f)
