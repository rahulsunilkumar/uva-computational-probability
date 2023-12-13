# 20-birth-weight-kde WriteUp
### Gaussian, $s=120$
<img width="400" alt="Screenshot 2023-12-13 at 7 15 27 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/c9ef8a8f-61be-4c39-a7fd-6341033bba97">

### Rectangular, $s=440$
<img width="400" alt="Screenshot 2023-12-13 at 7 16 51 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/8b367e38-b0fa-45a6-b4b8-ee9189e359ec">

### Triangular, $s=800$
<img width="400" alt="Screenshot 2023-12-13 at 7 17 58 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/31630efb-b7e6-4ac3-b01c-4c865406eee2">

### Epanechnikov, $s=500$
<img width="400" alt="Screenshot 2023-12-13 at 7 18 40 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/674e86f6-af0b-4526-a112-7f75e13d35e5">

### Hyperbolic Secant, $s=100$
<img width="882" alt="Screenshot 2023-12-13 at 7 19 18 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/2b6c6665-e2dc-461e-9d99-d9d4c8e04884">

### Cauchy, $s=50$
<img width="880" alt="Screenshot 2023-12-13 at 7 20 00 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/d62cb567-e09b-4e8f-aba4-98910df6db36">

### Reasoning for $s$ values
My reasoning was based off balancing how much can I maximize smoothness versus how much I can maximize accuracy. I often too accuracy over smoothness, but tried to find level ground.

### Smooth Kernel Estimate
![image](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/790a111f-97e1-4bd1-99ae-96863b425f64)

$P(\text{age} \leq 25) = 0.857$

### Comparisons
- Both methods can be used to estimate density.
- Both approaches involve combiniing simpler distributions to model more complex data distributions. For kernel smoothing, the function is centered each data point. In mixture models, the different distributions are combined.
- Both can are, in a way, the sum of functions.
