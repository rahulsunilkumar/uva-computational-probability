1. I solved this using the code below.
```
# p_failure is 1-p_success
p_failure = 0.3
n_students = 29

# using pbinom() as suggested
cumulative_probability = pbinom(3, n_students, p_failure)
print(cumulative_probability)
```
This gave me a probability of 0.0121. 12.1% likelihood that 3 or fewer students do not complete the degree.

2. In this situation the professor can take upto 15 students since more than that would mean she would have to potentially work for more than 20 years (since each student takes five years to complete. I believe this is just `pnbinom(q = 15, size = 10, prob = 0.7)` which yields 0.999.
   
3. This is a similar case where I can use `pnbinom(25, 3, 0.1)` to get 0.541.
