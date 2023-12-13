# 18-world-series Writeup

Hey! Welcome to the blog, HR manager! Let's talk about the rules of probabily and discrete probability functions in regards to the World Series.
1. In probability, a random variable is a value subject to chance, likes heads or tails (1 or 0). The outcome to a "first to $k$" process is a **bivariate** random variable because we need two pieces of information: (1) the wins of the Diamondbacks and (2) the wins of the Rangers. While they are independent, they are connected since the series ends once one team reaches $k$ wins. Either the Diamondbacks win or the Rangers win (1 or 0).
2. For a $P_d$ v. $P_r$ cross-table there are many binomial probabilities needed to be calculated.
   
| D/R | 0 win | 1 win | 2 win | 3 win | 4 win |
| --- | ----- | ----- | ----- | ----- | ----- | 
| 0 win | n/a | $(^0_0)P_d^0P_r^1 = P_r$ | $(^1_0)P_d^0P_r^2 =P_r^2$ | $(^2_0)P_d^0P_r^3 = P_r^3$ | $(^3_0)P_d^0P_r^4 =P_r^4$ |
| 1 win | $(^0_0)P_d^1P_r^0 = P_d$ | $(^1_0)P_d^1P_r^1$ | $(^2_0)P_d^1P_r^2$ | $(^3_0)P_d^1P_r^3$ | $(^4_0)P_d^1P_r^4$ |
| 2 win | $(^1_1)P_d^2P_r^0 = P_d^2$ | $(^2_1)P_d^2P_r^1$ | $(^3_1)P_d^2P_r^2$ | $(^4_1)P_d^2P_r^3$ | $(^5_1)P_d^2P_r^4$ |
| 3 win | $(^2_2)P_d^3P_r^0 = P_d^3$ | $(^3_2)P_d^3P_r^1$ | $(^4_2)P_d^3P_r^2$ | $(^5_2)P_d^3P_r^3$ | $(^6_2)P_d^3P_r^4$ |
| 4 win | $(^3_3)P_d^4P_r^0 = P_d^4$ | $(^4_3)P_d^4P_r^1$ | $(^5_3)P_d^4P_r^2$ | $(^6_3)P_d^4P_r^3$ | 0 |

3. The probability that the Diamondbacks wins is the probability of scenarios 4-0, 4-1, 4-2, and 4-3, which is the bottom row of our cross-table! That means the probability of the Diamondbacks winning should be: $$P_d^4 + (^4_3)P_d^4P_r^1 + (^5_3)P_d^4P_r^2 + (^6_3)P_d^4P_r^3$$
When $P_d = 0.55$ this equates to: $$(0.55)^4 + (^4_3)(0.55)^4(0.45)^1 + (^5_3)(0.55)^4(0.45)^2 + (^6_3)(0.55)^4(0.45)^3 = 0.608$$
So, there's an $0.608$ probability that the Diamondbacks win the world series when $P_d = 0.55$. I calculated this using Desmos's $\text{nCr}()$ function as shown below.

<img width="300" alt="Screenshot 2023-12-13 at 4 25 33 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/3d7ed7eb-3c7c-4ff2-8fd8-33c647d0210c">

4. When $P_d = x$ in my Desmos session, the graph is the following. As you can see, the previous $P_d = 0.55$ is also denoted and its respective probability of $0.608$ is shown.

<img width="400" alt="Screenshot 2023-12-13 at 4 26 57 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/14544e20-1acb-44dc-a40b-2dc8acf158e9">

5. Figuring this out was a lot more difficult for me and took some time. I started with trying to represent $P(\text{Diamondbacks Win})$ as a summation subject to $k$. After trial and error and a lot of googling, I represented it as such: 
$$P(\text{Diamondbacks Win Series}) = \Sigma_{n=k}^{2k-1}\left((^{n-1}_{k-1})P_d^kP_r^{n-k}\right)$$
When putting that in Desmos and setting $k=4$, our initial parameter, I got the same curve as before, as shown below:

<img width="1557" alt="Screenshot 2023-12-13 at 4 33 13 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/563a9dba-fed3-451a-ada6-c97c809bbf3a">

Now, frankly, I do not know how to to find what $k$ value is needed for a $P(\text{Diamondbacks Win Series}) \geq 0.80$. However, after setting $P_d = 0.55$ again I can manually raise $k$ to determine what value is needed to satisfy our condition. This point is $k=36$, take a look at how I did it below.
<img width="600" alt="Screenshot 2023-12-13 at 4 42 34 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/0926a4f6-a208-4877-9457-dba556ec8bd7">

6. Here is the plot for the $P(\text{Diamondbacks Win Series} | P_d = x) \geq 0.8$
![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/1f61491c-ec97-4a17-86a2-581bd18770fd)

7. We are looking for, $$\frac{P(\text{Diamondbacks Win Series in 7} | P_d = 0.55) \times P(P_d = 0.55)}{P(\text{Diamondbacks Win Series in 7})}$$
From our table we know that $P(\text{Diamondbacks Win Series in 7} | P_d = 0.55) = (^6_3)P_d^4P_r^3$. And I am interpreting the sentence "...either $P_d = 0.55$ or $P_d = 0.45$." as a 50/50 chance of either. Lastly, we need to employ total probability to figure out $P(\text{Diamondbacks Win Series in 7})$ assuming that probability of either probability (0.55 or 0.45) is 0.5. 

Thus, computing it all gives us, ironically, $0.55$ as the answer.

8. I'm assuming for this, we are looking at just this world series where maximums are $k=4$, $n=7$, and the default $P_d = 0.55$.

```
draw_random_series_outcome <- function(P_d) {
  P_r <- 1 - P_d
  
  # randomly pick game count
  n <- sample(0:7, 1)
  
  # randomly pick win count within 4
  k <- sample(0:min(n, 4), 1)
  
  # randomly pick loss count within 3
  l <- sample(0:min(n, 4), 1)
  
  # calculating probability
  probability <- choose(n-1, k-1) * (P_d^k) * (P_r^(l))
  
  return(list("outcome" = paste(k, "-", l, " win", sep=""), "probability" = probability))
}

# default probability from problem
P_d_default <- 0.55 
random_outcome <- draw_random_series_outcome(P_d_default)
print(random_outcome)
```

Here's an example of the output: 

<img width="100" alt="Screenshot 2023-12-13 at 6 17 24 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/0777f741-75b9-4435-be61-0fffd3d4949a">

The inputs are again: $k$, the successes in a series up to 4 represented as `k`. $n$, the sum of wins and losses represented as `n`. $l$, the losses in a series up to 4 represented as `l` (normally $n-k$). 
The output is the outcome scenario formatted "wins"-"losses" and the probability.

Random outcome generators like these can help with sport-analysis and data generation.

9. We would have to change the probabilities to account for this. We would need a $P_{d,AZ}$ v. a $P_{d,TX}$ and a $P_{r,AZ}$ v. a $P_{r,TX}$, respectively. This would become a lot more complicated, the overall probability of a particular series outcome is the product of the probabilities of each game's outcome, following the series' schedule. Perhaps something like a Monte Carlo simulation would help addressing the complexity.


