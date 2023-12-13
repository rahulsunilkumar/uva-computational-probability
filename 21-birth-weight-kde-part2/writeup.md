# 21-birth-weight-kde-part2 WriteUp

### Fit-By-Eye Estimations
Surprisingly and coincidentally, I picked exactly the same values for $m=3000$ and $s=700$ as deliverable 19's values. I chose $\alpha = 16$ and $\beta = 0.0052$ which are also quite close to earlier, but not exactly the same. And lastly, I chose $m_1=3100,s_1=480,m_2=2960,s_2=860,\alpha_1=0.32$ which were again similar to before.

### Gaussian

$s=120$ from previous module:

<img width="400" alt="Screenshot 2023-12-13 at 4 36 26 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/3dc0f725-772d-4ed3-b1da-59019b749ab5">

$s=300$, my adjusting from this module:

<img width="400" alt="Screenshot 2023-12-13 at 4 37 40 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/2ba3e777-accc-45da-9f22-a1f21cbcb032">

I chose to increase the smoothing here because I preferred smoothness over a trimodal fit. While it may fit the data better that bell curve-esque shape works better.

### Rectangular

$s=440$ from previous module:

<img width="400" alt="Screenshot 2023-12-13 at 4 40 24 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/3e6b5232-d5bd-4b10-8b5c-89c69e27823e">

$s=1530$, my adjusting from this module: _And while the CDF was continuous the PDF was not_

<img width="400" alt="Screenshot 2023-12-13 at 4 41 54 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/6ddef8a4-160c-4d21-b166-b35a398d5902">

The fit was erratic when $s$ was lower so I increased it by a lot.

### Triangular

$s=800$ from previous module:

<img width="400" alt="Screenshot 2023-12-13 at 4 42 36 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/60052319-8536-45b8-922c-2de5fb217e60">

For this one, I kept $s=800$ the same. I did not find a better fit:

<img width="400" alt="Screenshot 2023-12-13 at 4 42 36 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/60052319-8536-45b8-922c-2de5fb217e60">

### Epanechnikov 

$s=500$ from previous module:

<img width="400" alt="Screenshot 2023-12-13 at 4 45 52 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/62a8bcc4-1644-4ab5-a325-de1a4cd8ecc5">

$s=1000$, my adjusting from this module:

<img width="400" alt="Screenshot 2023-12-13 at 4 46 42 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/a2176b4c-ae7b-4af6-a8a9-60daba38d401">

The accuracy was only changed slightly despite substantial chances in $s$ so I maxmized that.

### Hyperbolic Secant

$s=100$ from previous module:

<img width="400" alt="Screenshot 2023-12-13 at 4 48 22 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/9e8d9bd8-7913-4827-a36d-a7cd7f5aae77">

$s=400$, my adjusting from this module:

<img width="400" alt="Screenshot 2023-12-13 at 4 49 30 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/82f55ead-747f-4429-8cd4-21388b4afdfe">

### Cauchy

$s=50$ from previous module:

<img width="400" alt="Screenshot 2023-12-13 at 4 50 44 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/093a50fc-6c1b-40f7-9864-c7ae4fdb2ed1">

$s=200$, my adjusting from this module:

<img width="400" alt="Screenshot 2023-12-13 at 4 51 46 PM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/f458e703-b6eb-41cc-90dd-3afc21d4b52b">


### Histogram 

```
# age histogram with curve
age <- d1$age
f <- function(x,s) rowMeans(outer(x,age,function(a,b) dnorm(a,b,s)))
hist(age, freq = FALSE, breaks = 25)
curve(f(x,sd(age)), add=TRUE, lwd = 3, col = "red")

# age histogram with epanechnikov overlay
f <- density(age, adjust = 1, kernel = "epanechnikov")
hist(age, freq = FALSE, breaks = 25)
lines(f, lwd = 3, col = "purple")
```

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/b1b54381-7c47-48b3-8793-3d4be7c36726)
![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/90526006-38cc-4f7f-9762-12f8c7d4cd0a)

The 90th percentile of age is $30.9$. I used the following code to determine this:
```
f <- density(age, adjust = 1, kernel = "epanechnikov")

# finding cdf from density
cdf <- cumsum(f$y) / sum(f$y)

# closest point in cdf to 0.90
index_90th <- which.min(abs(cdf - 0.9))

# Get the corresponding age value
age_90th_percentile <- f$x[index_90th]

# Output the 90th percentile
print(age_90th_percentile)
``` 
