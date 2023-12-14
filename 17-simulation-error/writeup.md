# 17-simulation-error WriteUp

### Welcome!
Hey, HR manager! Welcome to my blog post that will dissect the concepts of absolute error versus relative error and simulation probabilities. This subject is important because when it comes to making decisions BASED off of simulated data, understanding the error and nature of that error is crucial, whether it be election outcomes, system failures, or market trends. Therefore, error is important to keep track of, specifically absolute and relative errors.
1. Absolute Error— This is the difference between the estimated probability value from the simulation ad the true probability value. $$|\hat{p}-p)|$$
2. Relative Error— This error is a normalized version of Absolute Error that provides context to how severe the error really is. This is useful when comparing errors with different scales of probabilities. $$\frac{|\hat{p}-p|}{p}$$

### Simulation Program

In this post, I demonstrate the concepts of error through R. Experiments/simulations were conducted to understand how the number of replicates in a Monte Carlo simulation affects the accuracy of estimating a probability (or error). The replicates varied from $2^2$ to $2^{15}$ and the "true" probabilities from $0.01$ to $0.50$. Below is the simulation code:

```
replicates <- 2^(2:15)
probabilities <- c(0.01, 0.05, 0.10, 0.25, 0.50)

absolute_errors <- matrix(NA, nrow = length(replicates), ncol = length(probabilities))
relative_errors <- matrix(NA, nrow = length(replicates), ncol = length(probabilities))

for (k in 1:length(replicates)) {
  for (n in 1:length(probabilities)) {
    p <- probabilities[n]
    r <- replicates[k]
    p_hat <- rbinom(5000, r, p)/r
    absolute_errors[k, n] <- mean(abs(p_hat - p))
    relative_errors[k, n] <- mean(abs(p_hat - p)/p)
  }
}

plot(log2(replicates), log(absolute_errors[,1]), ylim = range(log(absolute_errors)), xaxt = "n", type = "l", xlab = "Number of Replicates", ylab = "Absolute Errors")
for(k in 1:length(probabilities)) lines(log2(replicates), log(absolute_errors[,k]), col = k)

axis(1, at = log2(replicates), labels = replicates)
legend(2, -4.5, legend = c("p = 0.01", "p = 0.05", "p = 0.10", "p = 0.25", "p = 0.50"), fill = c("black", "red", "lightgreen", "blue", "turquoise"), cex = 0.5)

plot(log2(replicates), log(relative_errors[,1]), ylim = range(log(relative_errors)), xaxt = "n", type = "l", xlab = "Number of Replicates", ylab = "Relative Errors")
for(k in 1:length(probabilities)) lines(log2(replicates), log(relative_errors[,k]), col = k)

axis(1, at = log2(replicates), labels = replicates)
legend(2, -4, legend = c("p = 0.01", "p = 0.05", "p = 0.10", "p = 0.25", "p = 0.50"), fill = c("turquoise", "blue", "lightgreen", "red",  "black"), cex = 0.6)
```

### Produced Plots
And, here is the relationship plotted in a $\log_{10}$ scale:

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/aa73735c-af6f-4325-bbe1-f70da1fcf5e1)

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/d6395b57-0b76-4ba1-84d8-3dbedfc8e2ea)

### Interpretation of Plots
We see, for larger probabilities (like $p = 0.50$), the absolute error quickly flattens out, suggesting that we can achieve a reasonable estimate with a moderate number of replicates.
For smaller probabilities (like $p = 0.01$), while the absolute error may be small, the relative error can be quite significant, implying that the proportional inaccuracy of our estimate can be high, even if the absolute error looks minimal.
The choice of the number of replicates in a simulation should consider the true probability being estimated and the acceptable level of error, whether absolute or relative.


