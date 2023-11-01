## Exchangeability Deliverable
1. Exchangeability in probability means that the order of events does not matter for their probability. In layman's terms, it means that we can swap around the order of events without changing the likelihood of those events happening.
2. A non-exchangeable series is the probability of temperature in a city throughout the year, the order of the data matters because you see the progression in temperature. The probability of it being cold is greater later in the year. Conversely, an exchangeable example is flipping a coin. The order of the data does not affect the probability of the flips.
3. 
| | A | a | |
|:---|:---:|:---:|:---:|
| B   | $p^2$ | $p-p^2$ | $p$ |
| row | $y$ | $1-p$ | |
| col | $y$ | $\frac{p-p^2}{1+p}$ | |
| b   | $p-p^2$ | $1+p^2$ | $1+p$ |
| row | $\frac{p-p^2}{1+p}$ | $\frac{1+p^2}{1+p}$ | |
| col | $1-p$ | $\frac{1+p^2}{1+p}$ | |
|     | $p$ | $1+p$ | $4p+2$ |

4. In order for $A$ to be independent, $$P(A) = P(A|B) = \frac{P(A \cap B)}{P(B)}$$. With the given values $$P(A) = y = \frac{p^2}p = p$$. Thus, $y$ and $p$ must be equivalent.
5. let $y = 0.2$ and $p = 0.4$
   
| | A | a | |
|:---|:---:|:---:|:---:|
| B   | $p^2 = 0.16$ | $p-p^2 = 0.24$ | $p = 0.4$ |
| row | $y = 0.2$ | $1-p = 0.6$ | |
| col | $y = 0.2$ | $\frac{p-p^2}{1+p} = 0.17$ | |
| b   | $p-p^2 = 0.24$ | $1+p^2 =1.16$ | $1+p = 1.4 $ |
| row | $\frac{p-p^2}{1+p} = 0.17$ | $\frac{1+p^2}{1+p} = 0.83$ | |
| col | $1-p = 0.6$ | $\frac{1+p^2}{1+p} = 0.83$ | |
|     | $p = 0.4$ | $1+p = 1.4$ | $4p+2 = 3.6$ |
