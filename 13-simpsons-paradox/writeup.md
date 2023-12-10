## Simpson's Paradox Deliverable
1. To do this, use the proportions given in the book: Males 0.6, 0.7 and Females: 0.2, 0.3, but with equal 20 for $T$ and $T^c$
 <img width="538" alt="Screenshot 2023-11-03 at 5 28 05 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/ae09cf4f-4537-47b8-96a1-f0f9f8deea71">

CORRECTIONS: 

**Males**:

$P(R | T) = \frac{P(R \cap T)}{P(T)} = \frac{12/40}{20/40} = 0.60$

$P(R | T^c) = \frac{P(R \cap T^c)}{P(T^c)} = \frac{14/40}{20/40} = 0.52$

**Females**: 

$P(R | T) = \frac{P(R \cap T)}{P(T)} = \frac{4/40}{20/40} = 0.20$

$P(R | T^c) = \frac{P(R \cap T^c)}{P(T^c)} = \frac{6/40}{20/40} = 0.30$

**Total**: 

$P(R | T) = \frac{P(R \cap T)}{P(T)} = \frac{16/80}{40/80} = 0.40$

$P(R | T^c) = \frac{P(R \cap T^c)}{P(T^c)} = \frac{20/80}{40/80} = 0.50$


We see, as in accordance with the textbook, an equal treatment allocation leads to a 10% reduction in recovery rate.

2. Let's say there are now 60 participants, 20 are men and 40 are women, thus having a 2:1 ratio. The $T$ and $T^c$ are balanced just like in 1.
<img width="534" alt="Screenshot 2023-11-03 at 5 56 42 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/7778b515-6197-4bcf-a266-6f55c567a030">

It shows the same pattern.

CORRECTIONS: 

Using the same correction model as earlier the $(P(R|T),\;P(R|T^c))$ pairs are as follows:
Males: (0.6, 0.7), Females: (0.2, 0.3), Total: (0.33, 0.43).

3. $$\text{Absolute: }\Delta = P(R|T)-(R|T^c) \quad \text{Relative: }\rho = \frac{P(R|T)}{P(R|T^c)}$$
4. In Table 1, the absolute effect is $\Delta = P(R|T)-(R|T^c) = 0.1 \text{ percent}$ and the relative effect is $\rho = \frac{P(R|T)}{P(R|T^c)} = 0.80 \text{ percent}$. In Table 1, the absolute effect is $\Delta = P(R|T)-(R|T^c) = 0.1 \text{ percent}$ and the relative effect is $\rho = \frac{P(R|T)}{P(R|T^c)} = 0.77 \text{ percent}$. 
The absolute effect is the same, but the relative measure increases. 
