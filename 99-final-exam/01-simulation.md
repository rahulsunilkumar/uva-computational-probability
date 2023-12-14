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

Because we're only looking for BOTH strategies to yield `"goat"`, we are only interested in the probabilities AFTER the first choice was made as `"goat"`. Anything else and the first strategy will automatically yield `"car"`.

1. _Always stay with the first door selected_: When you incorporate this strategy you initially pick goat and do not move and the probability that you chose a goat is $3/4$.
2. _Always switch to the unopened door_: When you incorporate this strategy you initially pick goat and always move and the probability that you chose a goat is $1/2$.

So the probability for `"goat", "goat"` is $\frac{3}4 \times \frac{1}2 = \frac{3}8 = 0.375$

I ran my simulation through 50,000 replicates and got $0.3852$. From that we see that there is an absolute error of $$\|\hat{p}-p\| = 0.001$$

And there is a relative error of
$$\frac{\|\hat{p}-p\|}{p} = 0.03$$

This follows logically, and shows that our simulation has good precision.

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
sim_count = 10000

for (k in 1:sim_count) {
  result <- game(doors)
  if(result[1] == "goat") {
    if(result[2] == "goat") {
      goat_goat_count <- goat_goat_count + 1
    }
    else {
      goat_car_count <- goat_car_count + 1
    }
  }
  else {
    if(result[2] == "goat") {
      car_goat_count <- car_goat_count + 1
    }
    else {
      car_car_count <- car_car_count + 1
    }
  }
}
cat(car_car_count, car_goat_count, goat_car_count, goat_goat_count)
cat(car_car_count/sim_count, car_goat_count/sim_count, goat_car_count/sim_count, goat_goat_count/sim_count)
```

This produced the following contingency table:
| Strat 1/Strat 2 (Sim) | Car | Goat |
| - | - | - |
| Car | 0 | $0.2591$ |
| Goar | $0.3751$| $0.3658$|

This is a great fit! The simulation matches the classmate's proposed solution relatively well, in fact each cell has a relative error less than $0.05$ $(0, 0.04, 0.0003, 0.02)$. 









