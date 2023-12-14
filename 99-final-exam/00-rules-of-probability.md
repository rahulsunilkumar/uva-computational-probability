# 00-rules-of-probability

### A. Let's take a look at the table with conditional, marginal, and cell probabilities.
First, I populated the table with the general form. The general form is based on the assumptions:
1. $P_C$ represents the probability of a **planned caesarean delivery**.
2. $P_V$ represents the probability of a **planned vaginal delivery**.
3. $P_D$ represents the probability of **postnatal depression**.
4. $1-P_D$ represents the probability of **no postnatal depression**.

| Table | Depression | No Depression | All | 
| -------- | -------------- | ----------------- | --- | 
| Planned Vaginal | $P(P_D \cap P_V)$ | $P(1-P_D \cap P_V)$  | $P(P_V)$ |
| row | $P(P_D \| P_V)$ | $P(1-P_D \| P_V)$ | 1 |
| col | $P(P_V \| P_D)$ | $P(P_V \| 1-P_D)$ |  |
| Planned Caesarean | $P(P_D \cap P_C)$ | $P(1-P_D \cap P_C)$ | $P(P_C)$ |
| row | $P(P_D \| P_C)$ | $P(1-P_D \| P_C)$ | 1 |
| col | $P(P_C \| P_D)$ | $P(P_C \| 1-P_D)$ |  |
| All | $P(P_D)$ | $1-P_D$ | 1 |

With the information we are given, that $P_D = 0.10$, $P_C = 0.04$, and subsequently $P_V = 0.96$, we can fill out the table. Important to note, the risk of postnatal depression and deliverty method are independent of each other. That's why $P(P_D \| P_V) + P(1-P_D \| P_V)$ is $1$, that's why $P(P_V \| P_D) = P(P_V)$, and others.

| TABLE | Depression | No Depression | All | 
| -------- | -------------- | ----------------- | --- | 
| Planned Vaginal | 0.096 | 0.864 | 0.96 |
| row | 0.10 | 0.90 | 1 |
| col | 0.96 | 0.96 |  |
| Planned Caesarean | 0.004 | 0.036 | 0.04 |
| row | 0.10 | 0.90 | 1 |
| col | 0.04 | 0.04 |  |
| All | 0.10 | 0.90 | 1 |

### B. What if the probability of planned caesarean increased to 0.30?
Simply change the value, $P_C = 0.30$ and $P_V = 0.70$. The table is as follows:

| TABLE | Depression | No Depression | All | 
| -------- | -------------- | ----------------- | --- | 
| Planned Vaginal | 0.07 | 0.63 | 0.70 |
| row | 0.10 | 0.90 | 1 |
| col | 0.70 | 0.70 |  |
| Planned Caesarean | 0.03 | 0.27 | 0.30 |
| row | 0.10 | 0.90 | 1 |
| col | 0.30 | 0.30 |  |
| All | 0.10 | 0.90 | 1 |

### C. What if the probability of postnatal depression increased to 0.15 too?
Simply change the value, $P_C = 0.30$ and $P_V = 0.70$. And now, $P_D = 0.15$ and $1-P_D = 0.85$. The table is as follows:

| TABLE | Depression | No Depression | All | 
| -------- | -------------- | ----------------- | --- | 
| Planned Vaginal | 0.105 | 0.595 | 0.70 |
| row | 0.15 | 0.85 | 1 |
| col | 0.70 | 0.70 |  |
| Planned Caesarian | 0.045 | 0.255 | 0.30 |
| row | 0.15 | 0.85 | 1 |
| col | 0.30 | 0.30 |  |
| All | 0.15 | 0.85 | 1 |

### D. Causation between Caesarean Section and Postnatal Depression?
In the scenario given, the probabilities are calculated under the assumption of **independence** between delivery method and postnatal depression. This means the occurrence of postnatal depression is not influenced by the method of delivery. Observational data is useful for correlatins but not for establishing a causal relationship. Even if the rates of depression were higher in one group over another, it does not imply the conclusion stated in D. There could be many other influential confounding variables. If the situation is going to declare independence between the variables at the start, then clearly you cannot revert back to a dependent relationship!
