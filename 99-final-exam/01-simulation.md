# 01-simulation

### A. Probability That Both Monte Hall Strategies Give "GOAT"!
To approach this, I experimented with the `game()` function outputs. The simplest way for me to determine the count was to use an if statement that added to a counter when IF `game()` yielded `"goat", "goat"`. I repeated that 1000 times and then divided the counter by 1000 to yield the probability that both strategies simultaneously result in "goat"! Here is the code:

```
require(magrittr)
require(dplyr)

# provided game function
game <- function(N){...}

# setting parameters
num_simulations <- 1000
doors <- 4

# initial count of how many results are have both strategies yield "goat"
both_goats_count <- 0

# loop to run simulation and add onto the both_goats_count counter
for (k in 1:num_simulations) {
  result <- game(doors)
  if(result[1] == "goat" && result[2] == "goat") {
    both_goats_count <- both_goats_count + 1
  }
}

# finding the probability
probability_both_goats <- both_goats_count / num_simulations

# print probability
cat('The probability that both strategies yield "goat" is:', probability_both_goats)
```

And, here is the produced probability:
```
The probability that both strategies yield "goat" is: 0.387
```
### B. A Study of Precision, through Error!
To determine either absolute error or relative error, we need to know $p$, the true probability of getting a `"goat"` under both strategies.

For stategy: STAY—
- $P(G)$, or the probability of picking GOAT first, is $0.75$.
- $P(G \| \text{STAY})$, or the probability of getting GOAT after picking GOAT first and choosing to STAY, is clealry $1$.

This means the probability of getting GOAT in the STAY strategy is $0.75$

For strategy: SWITCH—
- $P(G)$, or the probability of picking GOAT first, is also $0.75$.
- $P(G \| \text{SWITCH})$, or the probability of getting GOAT after picking GOAT first and choosing to SWITCH, is $0.50$.
- $P(C)$, or the probability of picking CAR first, is $0.25$.
- $P(C \| \text{SWITCH}$, or the probability of getting CAR after picking CAR first and choosing to SWITCH is $0$.

This means the probability of getting GOAT in the SWITCH strategy is $(0.75 \times 0.50) + (0.25 \times 1.00)$. Or in other words $P(\text{initally CAR then GOAT})) + P(\text{initially GOAT then GOAT})$. This is $\frac{5}8 = 0.625$

So finally, the true probability of both strategies simultaneously yielding "goat" is $0.75 \times 0.625 = 0.46875$.

I ran my simulation through 50,000 replicates and got $0.3852$. From that we see that there is an absolute error of $$\|\hat{p}-p\| = 0.084$$

And there is a relative error of
$$\frac{\|\hat{p}-p\|}{p} = 0.178$$

This does seem like a high level of error, so either my simulation could be better or my math is flawed.

### C. Contingency Table: Sim v. Math
| Strat 1/Strat 2 $(N = n)$ | Car | Goat |
| - | - | - |
| Car | 0 | $\frac{1}n$ |
| Goar | $\frac{n-1}{n(n-2)}$| $\frac{(n-1)(n-3)}{n(n-2)}$|

| Strat 1/Strat 2 $(N = 4)$ | Car | Goat |
| - | - | - |
| Car | 0 | $\frac{1}4 = 0.25$ |
| Goar | $\frac{4-1}{4(4-2)} = 0.375$| $\frac{(n-1)(n-3)}{n(n-2)} = 0.375$|

To create my simulated version of this contingency table, I wrote the following code:
```
goat_goat_count <- 0
goat_car_count <- 0
car_goat_count <- 0
car_car_count <- 0

for (k in 1:1000) {
  result <- game(doors)
  print(result)
  if(result[1] == "goat" && result[2] == "goat") {
    goat_goat_count <- goat_goat_count + 1
  }
  else if(result[1] == "goat" && result[2] == "car") {
    goat_car_count <- goat_car_count + 1
  }
  else if(result[1] == "car" && result[2] == "goat") {
    car_goat_count <- car_goat_count + 1
  }
  else if(result[1] == "car" && result[2] == "car") {
    car_car_count <- car_car_count + 1
  }
}

cat(goat_goat_count/1000, goat_car_count/1000, car_goat_count/1000, car_car_count/1000)
```

This produced the following contingency table:
| Strat 1/Strat 2 (Sim) | Car | Goat |
| - | - | - |
| Car | 0 | $0.411$ |
| Goar | $0.345$| $0.240$|

Honestly, they do not match that great. But the math checks out and so does the code.










