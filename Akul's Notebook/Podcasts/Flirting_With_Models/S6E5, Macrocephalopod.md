
[Podcast Link](https://podcasts.apple.com/in/podcast/flirting-with-models/id1402620531?i=1000614818563)
Recording Date:  29 May, 2023
Tags: #Crypto #Momentum 

Macrocephalopod is an anonymous user on [FinTwitter](https://twitter.com/macrocephalopod?s=21&t=o6KbAoS5iWVmbjgKh3zr8Q)

- Began career with slow-frequency style premia in a hedge fund. The built a prop desk that trades mid-to-high frequency strategies in crypto.
- Earlier in the 2010s, he was "implementing longer frequency futures strategies, a lot of them in the vein of style-premia". 
	- "Looking back, they were very naïve and [he's] surprised that they worked in the first place"
	- Trading the most liquid futures, rebalancing daily and typically holding the trades for weeks/months and "not doing a whole ton of modelling around the details and the microstructure". "The kind of strategies that I was thinking about: CTA trend following (spent quite a bit of my early career as a quant researcher working on that strategy), carry strategies, strategies which now people like to call macro momentum" ([[Economic Trend]]; [[Research_Papers/Momentum_Trend_Following/A Half Century of Macro Momentum]]).
	- They worked in the first place because over the long-term, they work (at least in the backtest). "I think they work because of two reasons":
		1. Risk premium; there are risks in these strategies that people are not so willing to take.
		2. Historically, these strategies had a big component of inefficiencies in them.
- Big multi-strategy hedge funds "are generally putting more of their capital/risk to work in equity markets than they are to futures markets, implying that there's a greater opportunity there"
	- Because equity trading is a more difficult problem than futures trading, the inefficiencies in quant equity market neutral strategies have sustained (as opposed to futures markets).
	- "There's a much broader range of names to trade in equities"
- Did a whole series on the different errors that can be made while backtesting. [Thread Link](https://twitter.com/macrocephalopod/status/1598823745681903616?s=20)
- "I don't think backtesting as a research tool. [...] For me, the research is what you do before you run the backtest"
	- "You spend a lot of time looking at data and building models and testing hypotheses, trying to understand effects before you even think about simulating"
	- "There are a million ways to mess up doing a linear regression before you even get onto how can you mess things up if you are using some very modern non-linear machine learning tool"
- Use cases of backtesting:
	- final check that the strategy works
	- compare different simulation assumptions:
		- market-impact
		- fill rate
		- borrow availability
		- latency
	- to compare two different variants of the same strategy
	- reconciliation versus live trading

- Importance of factor hedging in a multi-manager equity hedge fund. Macro-factors?
	- "Quant equity manager will have a factor model somewhere, even if that strategy is not entirely built as a factor model"
	- Example: you've got a 100 different managers, each with a Sharpe of 1 and 0.2 correlation with each other
		- if you diversify among these managers, the best you can do is double your Sharpe. If you "reduce the correlation by hedging the factors that are making them correlated, say you can reduce that correlation down to 0.1, then you can triple the sharpe"
	- Hedging away the Macro-factors: economic data releases are very infrequent, so you need to find proxies.

- You moved from operating in hedge fund to operating in a prop fund. Differences?
	- Biggest difference: "in a prop trading firm, you have more freedom in how trading revenues can be used". In a prop fund, providers of capital and the owners are generally the same people so a lot of the arguments around 'how well do we pay our traders or how much of our trading revenue do we re-invest into tech/infrastructure' go away. "You end up with everyone feeling a lot more ownership in what's going on inside the prop firm"

- "started building a crypto desk [from scratch] in first half of 2021"
	- "traditional markets are much more intermediated than crypto markets are". In crypto markets: exchange, clearing house, prime brokers, financing providing etc. will tend to be the same firm.
- adjusting for other factors (such as quality, value, size) when measuring momentum makes the momentum more persistent.
- "You've gone from focusing on longer-term strategies to what you would call mid-frequency strategies. What are the key differentiators between high/mid/low frequency alphas?"
	- "High-frequency is where you care about every tick [...] and low frequency is where you are executing daily or perhaps twice a day and mid-frequency captures everything in between"
	- Mid-frequency: likely using bins data (second bins, minute bins, or hour bins); you are trading continually throughout the day.

- "There's a lot that is in common between mid-frequency and slow styles of trading"
	- "Measure momentum, instead of measuring it over 12 months, we'll look at it intraday or maybe over a few days. We'll look at reversion on the order of minutes rather than on the order of days but a lot of the same ideas can still be applied"
	- "things that you would look at in mid-frequency but you wouldn't look at that much in low-frequency is anything to do with microstructure. Order book, etc."
