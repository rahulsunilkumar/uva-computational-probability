# Roulette Simulation Writeup

### Welcome to my blog post! For this project, I used a computer simulation to understand the deceptive assurance of the Martingale strategy in Roulette.

To accomplish this, Prof. Stewart provided us code and a helpful 30 minute explanation video on how both the strategy works and the code to simulate the strategy works. To start, I looped the `one_series` 1000 times and added the profit each time to a `total_profit` value. This value at the end was divided by 1000 (which I will reveal later!)

Now, the vizualization was a little more difficult but I plotted the array of row 1 and 5 which was `game_index` and `ending_budget`. I ran a loop where I set a seed, which Prof. Stewart once showed us how to do, and plotted that to get **five** different vizualizations of the simulation. Here are the graphs:

![sim1](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/0b0a1b75-24a9-4ef6-b74e-f2cdf524d4d2)
![sim2](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/340610ba-2c71-4c2f-b00f-2fd798fde797)
![sim3](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/13b47619-b97e-425e-a172-773f844587fb)
![sim4](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/b3b3935e-8f74-4b1e-b10e-9aafd0bbeed3)
![sim5](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/603c7f17-2ebf-419b-92a7-4fdfb53e9e64)

So, after 1000 simuations, the $$\frac{\text{total profit}}{1000} = -42.2\text{ dollars}$$
This shows that ultimately, while the strategy seems okay when you break it down into subsequences, it'll likely get you losing money.

### Here's what happens when you change the parameters
1. When I increased the `starting_budget` from $200$ to $300$ and increased the `winning_threshold` from $300$ to $400$ the average earnings went down to $-73.15$. I also tried increasing the `winning_threshold` to $400$ without altering `starting_budget` which yielded similarly at $-73.03$. This seems to me that the `winning_threshold` is a more determining factor in your loss than your starting budget. This makes more sense— if you are out to make more money that means you will play for longer and lose more.
2. After resetting to default, I increased `max_wager` to $150$ which gave me $-44.30$. There seems to be minimal difference but again, the more you bet, the more you have to lose.

### In regards to the stopping rule, we also wanted to determine, on average, how many plays are made before players stop. 

To do this, I implemented a looped `total_playcount` just like `total_profit` and divided it by $1000$ simulations. This particular run of the simulation gave me $-37.10$ average earnings and $180.64$ average playcount.

### It's important to note that while this simulation was great, it has its flaws.
It firstly simplifies roulette, because I think that you can bet on more than just red, black, green. Instead, a number, row, or a corner. There are more terms and details to the game and while this simplification works for our purposes it would be lacking when attempinting to accurately model real-life.






