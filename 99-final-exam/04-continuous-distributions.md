# 04-continuous-distribution 

### A. DBP Greater than 104
```
print(1 - pnorm(104, mean = 80, sd = 15))
[1] 0.05479929
```

### B. Male Femur Probability
We are trying to find $P(M \| \text{femur} = 37)$. This can be broken down as the following:

$$P(M \| \text{femur} = 37) = \frac{P(\text{femur} = 37 \| M) \times P(M)}{P(\text{femur} = 37)}$$

And given that, 

$$P(\text{femur} = 37) = P(\text{femur} = 37 \| M)P(M) + P(\text{femur} = 37 \| F)P(F)$$

We can factor out $0.5$ from the denominator and numerator and arrive at, 

$$P(M \| \text{femur} = 37) = \frac{P(\text{femur} = 37 \| M)}{P(\text{femur} = 37 \| M) + P(\text{femur} = 37 \| F)}$$

To mimic this function, I wrote the following code: 
```
# parameters
mean_female <- 36
sd_female <- 3.3
mean_male <- 40
sd_male <- 3.4

femur_length <- 37

# calculate likelihoods
likelihood_female <- dnorm(femur_length, mean = mean_female, sd = sd_female)
likelihood_male <- dnorm(femur_length, mean = mean_male, sd = sd_male)

# final posterior probability
probability_male <- likelihood_male / (likelihood_male + likelihood_female)

print(probability_male)
```
And that produced this probability:
```
0.407765
```
### C. Where Do They Meet?
![Screenshot 2023-12-14 at 5 11 50 AM](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/3a329a37-2a02-4a9f-b370-1ea28a9d9e62)
After graphing in Desmos, we can se tgat tge posterior for male and female intersect at $38.054$. On the graph, we can also see the previous questions `likelihood_male` and `likelihood_female` values.
