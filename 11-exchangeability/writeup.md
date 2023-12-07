## Exchangeability Deliverable
1. Exchangeability in probability means that the order of events does not matter for their probability. In layman's terms, it means that we can swap around the order of events without changing the likelihood of those events happening.
2. A non-exchangeable series is the probability of temperature in a city throughout the year, the order of the data matters because you see the progression in temperature. The probability of it being cold is greater later in the year. Conversely, an exchangeable example is flipping a coin. The order of the data does not affect the probability of the flips.
3. 

| | A | a | |
|:---|:---:|:---:|:---:|
| B   | $P(A\cap B) = py$ | $P(a\cap B) = p-py$ | $P(B) = p$ |
| row | $P(A\|B) = \frac{P(A\cap B)}{P(B)} = \frac{py}{p} = y$ | $P(a\|B) = \frac{P(a\cap B)}{P(B)} = \frac{py}{p} = 1-y$ | |
| col | $P(B\|A) = \frac{P(B\cap A)}{P(A)} = \frac{py}{p} = y$ | $P(B\|a) = \frac{P(B\cap a)}{P(a)} = \frac{p-py}{1-p}$ | |
| b   | $p-py$ | $py$ | $P(b) = 1-p$ |
| row | $1-y$ | $\frac{1-2p+py}{1-p}$ | |
| col | $\frac{(1-y)(1-p)}{p}$ | $\frac{1-2p+py}{1-p}$ | |
|     | $P(A) = p$ | $P(a) = 1-p$ | $1$ |

Some work: 
Because, $P(b) = P(a) = 1-p$, we know that $P(a\cap b) = (1-p)-(p-py) = 1-2p+py$
And, it follows: $$P(a|b) = \frac{P(a \cap b)}{P(b)} = \frac{1-2p+py}{1-p}$$
It also follows: $$P(a|b) = \frac{P(b|a) \times P(a)}{P(b)} = \frac{P(a)}{P(b)} \times P(b|a) = 1 \times P(b|a) \therefore P(a|b) = P(b|a)$$
Additionally, $$P(b|A) = \frac{P(A|b) \times P(b)}{P(A)} = \frac{(1-y)(1-p)}{p}$$

4. In order for $A$ to be independent, $$P(A) = P(A|B) = \frac{P(A \cap B)}{P(B)}$$. With the given values $$P(A) = y = \frac{p^2}p = p$$. Thus, $y$ and $p$ must be equivalent.
5. let $y = 0.6$ and $p = 0.5$

| | A | a | |
|:---|:---:|:---:|:---:|
| B   | $0.3$ | $0.2$ | $0.5$ |
| row | $0.6$ | $0.4$ | |
| col | $0.6$ | $0.4$ | |
| b   | $0.2$ | $0.3$ | $0.5$ |
| row | $0.4$ | $0.6$ | |
| col | $0.4$ | $0.6$ | |
|     | $0.5$ | $0.5$ | $1$ |
