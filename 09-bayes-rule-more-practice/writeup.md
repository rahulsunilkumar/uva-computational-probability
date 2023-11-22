1. $0.44 + 0.35 - 0.20 = 0.59$
2. <img width="952" alt="Screenshot 2023-09-22 at 1 23 00 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/78d85bd3-bdf7-4def-9a4d-5e3051fd86b5">
3. REVISED: They are NOT independent, since $P(\text{Apple} | \text{Laptop}) > P(\text{Apple} \cap \text{Laptop})$
4. $\big(\frac{1}{3}\big)\big(\frac{1}{10}\big) + \big(\frac{1}{3}\big)\big(\frac{1}{100}\big) + \big(\frac{1}{3}\big)\big(\frac{1}{1000}\big) = 0.037$ 
5. $\big(\frac{4}{7}\big)\big(\frac{1}{10}\big) + \big(\frac{2}{7}\big)\big(\frac{1}{100}\big) + \big(\frac{1}{7}\big)\big(\frac{1}{1000}\big) = 0.060$
6. $\frac{\big(\frac{4}{7}\big)\big(\frac{1}{10}\big)}{0.060} = 0.95$

REVISED 7a. 
$$P(\text{Fair} | \text{TTT}) = \frac{P(\text{TTT} | \text{Fair})P(\text{Fair})}{P(\text{TTT})} = \frac{P(\text{TTT} | \text{Fair})P(\text{Fair})}{P(\text{TTT} | \text{Fair}) +P(\text{TTT} | \text{Unfair})}$$
$$\frac{(0.50)^3 \times 0.80}{((0.25)^3 \times 0.20) + ((0.50)^3 \times 0.80)} = 0.97$$

REVISED 7B. 
Using binomial probability, 
$$P(\text{k successes in n trials}) = (\text{n choose k}) \times p^k \times (1-p)^{(n-k)}$$
In our context,
$$P(\text{2 heads in 3 flips} | \text{unfair}) = (3 \text{ choose }2) \times (0.75)^2 \times (0.25)^1 = 0.42$$

