## Bayes Rules Deliverable

1. We are looking for $$P(3|y) = \frac{P(3 \cap y)}{P(y)}$$ And to do this I thought it would be best to create a frequency tables with $10,000$ repititions and take probabilities from there. To accomplish this I did
```
arr <- array(mystery(10000)
table(arr)
```
which resulted in

<img width="269" alt="Screenshot 2023-09-22 at 12 20 02 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/8bafdc1f-ea9a-4f22-a07d-36ec28e688ff">

and allowed me to derive $$P(3|y) = \frac{\frac{8}{10000}}{\frac{5+80+8}{10000}} = 0.086$$

2. Similarly, from the frequency table, I can tell that $a$ is most likely to start a word with probability of $\frac{1045}{10000} = 0.105$.

3. We are looking for which vowel is most likely to have the first vowel in the word at the fourth position. From the data collected, this must be $e$.

4. There is no N/A column to look at, so I took the sum of the existing positions to find that there are $269$ words in this set of $10000$, which is $0.027$

5. $P(1) + P(3) + P(5) = 0.438$ and $P(2) + P(4) + P(6) = 0.438$. I used the work from table below. **Even is more likely**.
<img width="916" alt="Screenshot 2023-09-22 at 12 50 29 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/70de9284-d20b-4403-a507-464fab708f84">
