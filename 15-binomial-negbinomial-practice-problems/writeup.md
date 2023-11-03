1. To calculate the probability that 3 or fewer students do not complete the degree we can use the binomial probability formula. We have $p = 0.7$ and $p^c = 1-p = 0.3$. 
$$P(X = k) = \big( ^n_k \big)\big(p^k(1-p)^{n-k}\big)$$
Where $k$ is the number of students not completing the program (from 0 to 3), $n$ is the total number of students, and $p$ is the probability of completing the program.

We need $P(X\le 3) = P(X=0) + P(X=1) +P(X=2) +P(X=3)$

$$
P(X = 0) = \big( ^{29}_0 \big)\big(0.7^{0}(0.3)^{29}\big) = 0.0000003837
$$

$$
P(X = 1) = \big( ^{29}_1 \big)\big(0.7^{1}(0.3)^{28}\big) = 0.0000044117
$$

$$
P(X = 2) = \big( ^{29}_2 \big)\big(0.7^{2}(0.3)^{27}\big) = 0.0000250223
$$

$$
P(X = 3) = \big( ^{29}_3 \big)\big(0.7^{3}(0.3)^{26}\big) = 0.0000907998
$$

$$\therefore P(X\le 3) = 0.0001206175$$

2. Should be a probability of 1. Given that there is no variation, she should be done with all the students within 20 years.

3. Just like 1, $n$ is the total number of submissions ($25$ in this case).
$k$ is the number of correct solutions (we want all three, so $k = 3$).
$p$ is the probability of a correct solution ($0.1$ in this case).

$$
P(X =3) =\big( ^{25}_3 \big)\big(0.1^{3}(0.9)^{22}\big) = 0.1017)
$$
