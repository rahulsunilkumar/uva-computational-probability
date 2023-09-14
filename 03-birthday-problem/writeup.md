## Birthday Problem

2. `set.seed` basically allows for the coder to make a random generation to be reproducible. You are essentially setting a random "roll" of sorts.
3. `R` represents repetitions.
4. For a class of $28$, the probability of a shared birthday rises from $0.14$ to $0.65$. I Changed `S = 11` to `S = 28` and `v = 11` to `v = 28`

```
## Code from class
set.seed(1)

one_roster <- function(S = 28){
  birthdays <- sample(x = 365, size = S, replace = TRUE)
  any(duplicated(birthdays))
}

R <- 100000
out1 <- rep(NA, R)
for(i in 1:R){
  out1[i] <- one_roster()
}
mean(out1)

out2 <- replicate(R, one_roster())
mean(out2)

## Additional Code

first_duplicate <- function(){
  birthdays <- sample(x = 365, size = 366, replace = TRUE)
  min(which(duplicated(birthdays)))
}

out3 <- replicate(R, first_duplicate())
hist(out3, freq = FALSE)

plot(ecdf(out3), xlab = "Roster size", ylab = "Proability of shared birthday", main = "Proability of shared birthday by class size")
abline(h=mean(out2), v = 28)
```
5.

<img width="526" alt="Screenshot 2023-09-14 at 2 33 02 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/16e18570-a0ca-4463-ae25-e091f1a8b050">

6. Well `which`, in this situation, returns the `TRUE` parts of an array. Additionally, `min` returns the minimum value of its paramaters. So what this function does is finds the duplicates and yields the first time in which there is a duplicate birthday.
