# 22-maternal-age-mle WriteUp

After reviewing the slides regarding Maximium Likelihood, I set up the eCDF plot and Histogram both overlayed with the estimated _normal_ distribution. This is the code I wrote:
```
# setting parameters
age <- d1$age
mean_age <- mean(age)
sd_age <- sd(age)

# create eCDF with estimated Normal distribution overlay
plot(ecdf(age), main="eCDF with Estimated Normal Distribution", xlab="Age", ylab="ECDF")
curve(pnorm(x, mean=mean_age, sd=sd_age), add=TRUE, col="red")

# create hist with estimated Normal distribution overlay
hist(age, freq=FALSE, main="Histogram with Estimated Normal Distribution", xlab="Age", ylab="Density")
curve(dnorm(x, mean=mean_age, sd=sd_age), add=TRUE, col="red", lwd=2)

```

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/53db3ab2-c628-4011-9961-2283ea2fb010)

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/be7c64e8-f72a-465e-a1fe-151314aa2eb8)
