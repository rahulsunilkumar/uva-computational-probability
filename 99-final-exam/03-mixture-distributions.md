# 03-mixture-distribution

### A. 90th Percentile of Yearly Hospital Charges

I wrote this code to simulate the data for this scenario. It seemed to be a better approach especially given the provided `rhc` function. 

```
# Function to generate hospital charges
rhc <- function(n) {
  rgamma(n, shape = 2, scale = 2) * rbinom(n, 1, .4)
}

# Generate a large number of samples, e.g., 100,000
samples <- rhc(100000)

# Find the 90th percentile
percentile_90th <- quantile(samples, 0.9)

print(percentile_90th)
```
This gave me an answer of:
```
5.195713
```
### B. Histograms of Class Average yearly Hospital Charge
The code I wrote for that is as follows: 
```
# function to generate hospital charges
rhc <- function(n) {
  rgamma(n, shape = 2, scale = 2) * rbinom(n, 1, .4)
}

# set number of students and simulations
num_students <- 30
num_classes <- 1000

# simulate the class averages
class_averages <- replicate(num_classes, mean(rhc(num_students)))

# plotting histogram
hist(class_averages, breaks = 30, 
     main = "Histogram of Class Average Yearly Hospital Charges",
     xlab = "Average Hospital Charges (in thousands of dollars)",
     ylab = "Frequency")
```
This yielded the following plot: 
![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/328e3cf6-4ad6-4e50-8841-01f1b758d2e6)

### C. Probability that 10 Won't Pay!
This would be easily calculated by:
```
pnbinom(9, 30, 0.6) = 0.02048509
```


