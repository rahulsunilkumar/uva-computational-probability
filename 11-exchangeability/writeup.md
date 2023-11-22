## Exchangeability Deliverable
1. Exchangeability in probability means that the order of events does not matter for their probability. In layman's terms, it means that we can swap around the order of events without changing the likelihood of those events happening.
2. A non-exchangeable series is the probability of temperature in a city throughout the year, the order of the data matters because you see the progression in temperature. The probability of it being cold is greater later in the year. Conversely, an exchangeable example is flipping a coin. The order of the data does not affect the probability of the flips.
3. 

| | A | a | |
|:---|:---:|:---:|:---:|
| B   | $py$ | $p-py$ | $p$ |
| row | $y$ | $1-y$ | |
| col | $y$ | $1-y$ | |
| b   | $p-py$ | $py$ | $p$ |
| row | $1-y$ | $y$ | |
| col | $1-y$ | $y$ | |
|     | $p$ | $p$ | $2p$ |

4. In order for $A$ to be independent, $$P(A) = P(A|B) = \frac{P(A \cap B)}{P(B)}$$. With the given values $$P(A) = y = \frac{p^2}p = p$$. Thus, $y$ and $p$ must be equivalent.
5. let $y = 0.6$ and $p = 0.5$

| | A | a | |
|:---|:---:|:---:|:---:|
| B   | $py = 0.3$ | $p-py = 0.2$ | $p = 0.5$ |
| row | $y = 0.6$ | $1-y = 0.4$ | |
| col | $y = 0.6$ | $1-y = 0.4$ | |
| b   | $p-py = 0.2$ | $py = 0.3$ | $p = 0.5$ |
| row | $1-y = 0.4$ | $y = 0.6$ | |
| col | $1-y = 0.4$ | $y = 0.6$ | |
|     | $p = 0.5$ | $p = 0.5$ | $2p = 1$ |
