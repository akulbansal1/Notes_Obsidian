

Published: 20210304
Tags: #Regime #Rob_Carver 
[Link](https://qoppac.blogspot.com/2021/03/does-it-make-sense-to-change-your.html)

- It does make sense to change the speed of your trading rules based on the volatility.
- It does make sense to change the allocation to momentum and carry rules as vol increase. Increase the signal strength as vol decreases.
	- Low vol: normalised vol in the bottom 25% quintile
	- Medium: between 25% and 75%
	- High: between 75% and 100%
- Vary the raw forecasts based on the volatility regime we are in. This does improve Sharpe slightly.
	- Rob has implemented this change

- `It does not make sense that Rob would implement this overlay of scaling the position based on the volatility quintil because the rules and the instrument position sizing are already normalizing volaitlity by targeting a constant level of volatility. This looks like overfitting to me.`