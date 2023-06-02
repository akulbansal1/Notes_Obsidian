

Published: 27 May, 2021
Tags: #Portfolio_Construction #Optimisation #Rob_Carver 
[Link](https://qoppac.blogspot.com/2021/05/fit-forecast-weights-by-instrument-by.html)

- "I've generally advocated pooling information across markets when fitting"
	- "preferred method is to pool gross returns, then apply the costs for each individual instruments, so more expensive instruments will end up trading slower, otherwise everything will look pretty similar"

- "when you analyse the different correlation across trading rules for different instruments, you get very similar results"
	- "I advocate using [[Using random data|artificial data]] to estimate the correlations for momentum rules of different speed, since it will give a robust but accurate result"
- Rob's forecast weights for each instrument are still coming out to be different (despite pooling the back-tested performance for all instruments while calculating forecasts weights) because he is "still using specific costs for each instrument - it's only gross returns" that he is pooling.
	- "we could also pool costs, and hence net returns, but to me that doesn't make a lot of sense - I think the costs of an instrument should determine how it is traded"
- "pooling across instruments within the same asset class […] effectively is what was at AHL when [Rob] worked there due to the fact that we ran separate teams for each asset class […], and each team fitted their own models"

- Speed limit
	- "on a per instrument, per trading rule basis it's unlikely (without overfitting) you will get an average SR before costs of more than about 0.40 on average, and you wouldn't want to spend more than a third of that on costs (about 0.13)" `I think expecting average SR of 0.40 per instrument per rule is quite high. To me, expected SR of 0.25 per instrument per rule is a good estimate, therefore I will be using a speed limit of 0.08 SR as my 'speed limit'`.
	- "I optimise on after costs returns, and I am taking SR into account when deciding the correct weights to use. In fact they get penalised twice, since I include a scaling factor of 2.0 on all costs when optimising"
	- "fast rule might not affect turnover on the entire system once added to a bunch of slower rules"
	- "I apply a buffering on the final position [slowing the changes in forecast], which reduced turnover and thus costs anyway, so the marginal effect of allocating to a faster rule might be very small"
	- Even after taking all the aforementioned steps, "this question of whether to apply the speed limit is pretty important. It will results in different individually fitted instrument weights, different asset groupings, and different results"

- Individual: fitting forecast weights individually for each instrument
- Groups: fitting forecast weights after grouping the instrument (using correlation clusters, "clustered things that had similar weights together")
- Everything: pooling the data for all instrument
- Blend: taking an average of the three methods
- Equal weight: weighing all the rules equally (no optimisation); only used as a benchmark

- ![[Screenshot 2023-06-01 at 6.44.32 PM.png]]compares Sharpe ratios across the four different methodologies (ignoring equal weight) and seeing how imposing 'speed limit' impacts SR.
- "first thing we notice is that using all rules is consistently better, after costs, than excluding expensive rules based on my 'speed limit' figure"
	- "we'll still be giving those costly rules a lower weight for the relevant instruments because of their higher costs"
	- "equally weighting only those that pass the speed limit is a great method, and beats everything else"
- "pooling across groups and pooling across everything is better than fitting on an individual instrument"

Summary
- "trying to improve your optimisation technique is a time-sink that will not result in any serious improvement in performance - thought it might result in more robustness"
- "a clearly stupid thing to do is to fit weights for each instrument individually - there just isn't enough meaningful information in a single market. Fitting by grouped instruments will make things more robust and also probably improve performance"
- "Using a blend of weights is cop-out if you can't decide what is best, which has other advantages: any kind of averaging makes things more robust"
- "if you're dealing with a list of trading rules that you know work fairly well across instruments, and you've filtered out those that are too expensive, and the correlation structure is fairly regular: You'd be made not to use equal weights"