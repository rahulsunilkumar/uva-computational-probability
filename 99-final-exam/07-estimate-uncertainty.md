# 07-estimate-uncertainty

### A. $1/20$ Support Interval
This interval is called the likelihood interval and represents a range of values for $\mu$ where the likelihood function is really high. This function tells us how likely the parameters are given the data as opposed to the usual opposite of how likely the data is given the parameters. The interval for this is $0.05$ which is a twentieth of the peak.

### B. Interval From the Posterior
```
posterior_mean <- 3100  # mean of the posterior distribution
posterior_sd <- sqrt(10)  # standard deviation of the posterior distribution

# calculate the 0.025 and 0.975 quantiles of the posterior distribution
# these quantiles define the 95% credible interval
lower_bound <- qnorm(0.025, mean = posterior_mean, sd = posterior_sd)
upper_bound <- qnorm(0.975, mean = posterior_mean, sd = posterior_sd)

print(c(lower_bound, upper_bound)) # print it!
```
From which you get the interval:
```
[1] 3093.802 3106.198
```
These are the lower and upper boudns of 95% credible interval for the posterior distribution of the mean birth weight. This means there's a 95% probability of the true mean birth weight between this interval.
