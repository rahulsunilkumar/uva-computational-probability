# 24-adult-male-weight-mm WriteUp

Following the directions and content on the slides provided, I generated these two plots as per requested:

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/bfef5ff5-631b-4e3d-ad80-363060d7d624)

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/a72fde26-f2e4-4dcb-b938-c160fa9f1ffa)

The slides also asked for $F_{\text{weight}}$ and $f_{\text{weight}}$. I followed the code to make the `NHANES$Weight` version below:

```
# installing NHANES and getting weights
install.packages("NHANES")
w <- NHANES$Weight

xbar <- mean(w, na.rm = TRUE)
s2 <- var(w, na.rm = TRUE)

shape_hat <- xbar^2/s2
scale_hat <- s2/xbar

# F_weight estimate
Fw <- function(x){
  pgamma(x, shape = shape_hat, scale = scale_hat)
}

plot(ecdf(w))
curve(Fw(x), add = TRUE, col = "blue", lwd = 3, main = "Weight")

# f_weight estimate
fw <- function(x){dgamma(x, shape = shape_hat, scale = scale_hat)}
hist(w, freq = FALSE, main = "Weight")
curve(fw(x), add = TRUE, col = "blue", lwd = 3, main = "Weight")
```

These are the plots from the code above:

![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/331c9e4a-ae1b-4626-bd43-baa3060c9b91) ![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/f1e02d73-91fa-49f8-a75d-e34b226a3389)
