## Diagnostic Odds Deliverable

1. Let _Cancer_ be $C$, _Not Cancer_ be $N$, _Test Positive_ be $+$, and _Test Negative_ be $-$.
$$P(C) = p$$ 
$$P(+|C) = \frac{P(+|C)}{P(C)} \therefore P(+|C) = P(C)P(+|C) = (p)(tp) = tp^2 $$
$$P(-|N) = \frac{P(-|N)}{P(N)} \therefore P(-|N) = P(N)P(-|N) = (1-p)(tn) $$

|REVISED Table| Cancer | Not Cancer | Margins|
|:---|:---:|:---:|:---:|
|Test Positive|$tp^2$|$(1-p)(1-tn)$|$(tp^2)+(1-p)(1-tn)$| |
|Cond. Col|$tp$|$1-tn$||
|Cond. Row|$\frac{tp^2}{(tp^2)+(1-p)(1-tn)}$|$\frac{(1-p)(1-tn)}{(tp^2)+(1-p)(1-tn)}$||
|Test Negative|$p-tp^2$|$(1-p)(tn)$|$p-tp^2+(1-p)(tn)$| |
|Cond. Col|$1-tp$|$tn$||
|Cond. Row|$\frac{p-tp^2}{(p-tp^2)+(1-p)(tn)}$|$\frac{(1-p)(1-tn)}{(p-tp^2)+(1-p)(tn)}$||
|Margins|$p$|$1-p$|1|

2. $$P(C|+) = \frac{P(C \cap +)}{P(+)} = \frac{tp^2}{tp^2+(1-p)(1-tn)} = \frac{(0.01)(0.90)}{(0.01)(0.90)+(0.99)(0.2)} = 0.0435 (\text{REVISED})$$
3. To visualize this figure, I plotted the positive predictive value as a function of cancer incidence $f(p)$ using the code below.
```
p = seq(0,1,0.05)
y = (0.9*p)/((0.9*p)+((1-p)*(1-0.95)))
plot(p,y)
lines(p,y, type = "l", col = "red")
```

<img width="716" alt="fig1" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/ff565fa8-96d2-45ef-8883-be7752a14212">

4. The probability of UVA being better than JMU is not contingent on the condition that JMU wins a head-to-head match-up. This means that the probability of UVA football being better than JMU football is independent.
REVISED: Additionally, $$P(\text{JMU wins} | \text{UVA better}) = \frac{P(\text{UVA better} | \text{JMU wins})P(\text{JMU wins})}{P(\text{UVA better})}$$
And we know that $P(\text{UVA better} | \text{JMU wins} = P(\text{UVA better})$, therefore:
$$P(\text{JMU wins} | \text{UVA better}) = \frac{P(\text{UVA better})P(\text{JMU wins})}{P(\text{UVA wins})} = P(\text{JMU wins})$$
This shows the relationship between $P(\text{JMU wins})$ and $P(\text{JMU wins} | \text{UVA better})$ is that they are equivalent and the probability of JMU winning does not change whether UVA is better or not.
