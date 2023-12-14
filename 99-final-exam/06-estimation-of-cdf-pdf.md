# 06-estimation-of-cdf-pdf

### A. Estimated Density Function (Norm, MLE, Adult Males' Heights)
Here's the code and following it is my plot:
```
# get data
Hmisc::getHdata(nhgh)
d1 <- nhgh[1:500,]

# filter out adult males
adult_males <- d1[d1$age > 18 & d1$sex == "male", ]

# set density
density_values <- dnorm(x, mean = mean(adult_males$ht), sd = sd(adult_males$ht))

# plot density
plot(x, density_values, type = "l", main = "Estimated Density of Adult Male Height", xlab = "Height (cm)", ylab = "Density")
```
![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/37acad2c-50e5-4eda-a55a-03334bdff415)

### B. Estimated Density Function (Gamma, Method of Moment, Adult Females' BMI)
Here's the code and following it is my plot: 
```
# get data
Hmisc::getHdata(nhgh)
d1 <- nhgh[1:500,]

# filter for adult females (age > 18 and female)
adult_females <- d1[d1$age > 18 & d1$sex == "female", ]

# sample mean and variancce like from the class slides
mean_bmi <- mean(adult_females$bmi, na.rm = TRUE)
var_bmi <- var(adult_females$bmi, na.rm = TRUE)

# method of moments estimates for gamma dist
shape_hat <- mean_bmi^2 / var_bmi
scale_hat <- var_bmi / mean_bmi

# setting density
x <- seq(0, max(adult_females$bmi, na.rm = TRUE))
density_values <- dgamma(x, shape = shape_hat, scale = scale_hat)

plot(x, density_values, type = "l", main = "Estimated Density of Adult Female BMI", xlab = "BMI", ylab = "Density")
```
![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/8b7281ec-0d5d-4b20-aa74-b33dc8fbc6cc)

### C. Estimated Density Function (Gaussian, Kernel, Adults SCr)
Here's the code and following it is my plot:
```
adults <- d1[d1$age > 18, ] # filter adults

# kernel density estimation on SCr
sc_kde <- density(adults$SCr, na.rm = TRUE)

# plotting the estimated density function
plot(sc_kde, main = "Estimated Kernel Density of Adult SCr Levels", xlab = "SCr (Creatinine Levels)", ylab = "Density", col = "blue")
```

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/da69a4e7-28d9-4a6c-b604-4112ba989d0c)

### D. Prevalence of Diabetes
For this, I started with getting my "Heads" and "Tails" by finding the "successess" and "fails" of diabetes.
```
success_count <- sum(d1$dx == 1, na.rm = TRUE)
fail_count <- sum(d1$dx == 0, na.rm = TRUE)

cat(success_count, fail_count)
```
For which I got:
```
79 421
```
This question isn't informed so I kept $\beta$ at $1$ and kept $\alpha$ at $1$. Here is what that looked like:

![Screenshot 2023-12-14 at 7 00 10 AM](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/4c4f2318-a636-489d-a88d-e738ed61d56c)


### E. Informative Prior
While our initial prior was generally informed, we can make a more informed prior by looking at the data. There are 79 yes cases for 421 no's. This is roughly 1:5. I made $\alpha$ and $\beta$ that accordingly.

![Screenshot 2023-12-14 at 6 54 52 AM](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/1ee8b14c-d295-43fe-b52a-daa74b5cbda2)

