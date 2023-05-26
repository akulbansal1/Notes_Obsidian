#ForEx 

- Indicators used:
	- To asses trend: EMA, Ichimoku Clouds, MACD, AROON, Know Sure Thing;
	- To measure momentum: ROC, RSI, Stochastic Oscillator, True Strength Index;
	- To asses volatility characteristics: Bollinger Bands.
- Standardise the reading of each indicator on a scale from -1 to +1 (oversold to overbought)![[Pasted image 20230526203005.png]]
- The model picks the historically best returning trades, and avoids being long/short the same currency, e.g. if model suggests being long USD against EUR, it won't suggest being short EUR against some other currency or being long EUR against some other currency![[Pasted image 20230526203033.png]]
- "In order to minimize tail risk events, stop-loss levels are determined by the first lower quartile of historical performance (e.g. a 1.5% maximum loss)"![[Pasted image 20230526203059.png]]