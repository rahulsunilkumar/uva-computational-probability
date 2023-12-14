# 23-bayesian-updating WriteUp

1. My values were $\alpha = 4$ and $\alpha = 2.5$ for the prior probability
<img width="400" alt="Screenshot 2023-12-13 at 6 27 02 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/2c2b6ad8-cfe5-412e-8828-f2d2f26aca71">
The posterior probability moves the curve backwards and shortens the spread.

```
# let's state here as a variable the true probability
p_true <- 0.60

# Bernoulli Sequence can be made using rbinom()
bernoulli_seq <- rbinom(n = 100, size = 1, prob = p_true)

# votes for H
H_votes <- sum(bernoulli_seq)

# votes for T
T_votes <- n - H_votes

cat("votes for candidate H:", H_votes, ", and votes for candidate T:", T_votes)
```

And this code yielded:
```
votes for candidate H: 61 , and votes for candidate T: 39
```

And when put into Desmos, the posterior is:

<img width="1182" alt="Screenshot 2023-12-13 at 6 51 01 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/ffac2510-67c0-4635-8f56-8d247db97fe1">

This guess is incredibly close to the true proportion of $0.6$.

My first thought to express the uncertainity is through a margin-of-error, confidence rating, or confidence intervals. Then I realized that the $$x = \frac{h + \alpha}{h + t + \alpha + \beta}$$ given our parameters, is just really $$f(H) = \frac{H +5}{106}$$

This checks out because $f(61) = 0.623$, just as we had seen in the intersection on Desmos. So to see the spread of the posterior probability subject to the random H votes (in the pursuit of determining uncertainity associated with $p$), I ran the bernoulli sequence 100 times and calculated the posterior probability for each. Then I created a histogram to plot that along with a normal distribution to determine what the spread actually looks like. More analysis in this direction would help really express the uncertainty levels associated with the estimate of $p$, but I think my work below both explains and visualizes it to the scope of the question asked:

```
# array of H Votes
H_votes_array = numeric(0)

# array of posterior probabilities (based of specific H count)
posterior_prob_array = numeric(0)

# find posterior, given N = 100, T = 100 - H, alpha = 5, and beta = 6
# x = (h+alpha)/(h+t+alpha+beta) was turned into f(H) = (H+5)/(106). This plotted the guessed posterior probability subject to change in H.
posterior_prob <- function(H) {
  return((H + 5)/(106))
}

# run bernoulli sequence and find respective posterior probability for that H
for (k in 1:100) {
  H_k = sum(rbinom(n = 100, size = 1, prob = p_true))
  prob_k = posterior_prob(H_k)
  
  # add this iteration to arrays
  H_votes_array[k] <- H_k
  posterior_prob_array[k] = prob_k
}


# plot
curve(dnorm(x, mean = mean(posterior_prob_array), sd = sd(posterior_prob_array)), 
      from = min(posterior_prob_array), 
      to = max(posterior_prob_array), 
      xlab="Posterior Probability", ylab="Amount", 
      main="Normal Distribution of Posterior Probability")

hist(posterior_prob_array, probability=TRUE, add=TRUE, col = rgb(1,1,1,0.2))
```

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/6ecda67a-4c6b-4f38-90ea-02ae4956839d)

I'm not sure if this is the exact way to approach this problem, but I enjoyed messing around with the distributions.
