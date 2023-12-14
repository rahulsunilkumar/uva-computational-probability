# 05-empirical-cdf

### A. CDF Plot
```
# provided data generation
rhc <- function(n) {
  rgamma(n, shape = 2, scale = 2) * rbinom(n, 1, .4)
}

# plotting ecdf
plot(ecdf(rhc(1000)), main = "Empirical CDF of Yearly Hospital Charges for UVA Students", xlab = "Hospital Charges (Thousands of Dollars)", ylab = "Cumulative Probability", xlim = c(0, max(hospital_charges)))

```
![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/79641bf4-87ee-4a26-be76-a0e94dd34eb4)

### B. Cap the Charges
Here's how I implemented the $1,500 ceiling:
```
# modified rch() to accomodate for cap
rhc_with_cap <- function(n) {
  
  # generate hospital charges
  charges <- rgamma(n, shape = 2, scale = 2) * rbinom(n, 1, .4)
  
  # cap the charges at 1.5
  charges[charges > 1.5] <- 1.5
  return(charges)
}

# plotting capped ecdf
plot(ecdf(rhc_with_cap(1000)), main = "CDF of Hospital Charges with $1,500 Cap", xlab = "Hospital Charges (Thousands of Dollars)", ylab = "Cumulative Probability")

```
And here's what it looks like:

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/b33cdd53-36ef-4c9b-9efb-572f5ecdc73c)

### C. Median, Under New Policy? 
The median is 0, which makes sense because that's the charge for 60% of the students.
```
print(median(rhc_with_cap(1000)))
[1] 0
```
