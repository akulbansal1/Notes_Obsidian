

Published: 4 Dec, 2020
Tags: #Trend_Following #Rob_Carver 
[Link](https://qoppac.blogspot.com/2020/12/dynamic-trend-following.html)

- Whether or not open or closed equity should matter when trading a position

- Had a chat with Moritz on this [here](https://www.toptradersunplugged.com/115-the-systematic-investor-series-ft-rob-carver-november-22nd-2020/)

- Rob likes to control the positions based on the changes in the instrument's volatility. Moritz, on the other hand, prefers not adjusting his position at all.
- Having a dynamic stop loss, one that increases the stop as your profit on the trade increases in order to let the trade 'breathe' and no volatility adjustments in the middle of a trade is the 'purer' form of trend following
- Dynamic volatility adjustments and dynamic stop losses only make sense in the case of discrete trading systems

- as opposed to continuous systems where you don't have individual trades but a position size that automatically does dynamic vol control by adjusting up/down the desired position size

- Rob uses a moving average crossover rule (16,64) and four variations of it:

|   |   |   |
|---|---|---|
||Dynamic stop loss|No Dynamic stop loss|
|Dynamic Vol Control|1. 'double dynamic'|1. Rob's preference|
|No Dynamic vol control|1. 'purest' form of trend following|1. Simple starter system as presented in Leveraged Trading|

- Stop loss gap = vol * xfactor
- Dynamic vol control: "adjusting open position as vol changes"

- "if vol doubles then the stop loss gap will double (get wider), if it halves then the gap will also half"
- xfactor = 8 because "we use a 0.5x annual standard deviation stop loss to close positions and vol here is daily"

- Dynamically adjusting stop loss for P&L:

- Calculate vol normalized profitability (i.e. "profit or loss in price points divided by the initial vol when the trade was put on")
- "we use an xfactor of 2 when the trade is put on, or if we're losing money. If we make profits the xfactor gradually increased to 8 (which is the default fixed setting) and goes no higher"

Results:

Sharpe (daily returns, annualized)

|   |   |   |
|---|---|---|
||Dynamic stop loss|No Dynamic stop loss|
|Dynamic Vol Control|0.07|0.25|
|No Dynamic vol control|0.05|0.19|

Skew (daily)

|   |   |   |
|---|---|---|
||Dynamic stop loss|No Dynamic stop loss|
|Dynamic Vol Control|-0.02|-0.11|
|No Dynamic vol control|0.4|0|

Skew (weekly)

|   |   |   |
|---|---|---|
||Dynamic stop loss|No Dynamic stop loss|
|Dynamic Vol Control|-0.01|-0.02|
|No Dynamic vol control|0.35|-0.01|

Skew (monthly)

|   |   |   |
|---|---|---|
||Dynamic stop loss|No Dynamic stop loss|
|Dynamic Vol Control|0.05|0.08|
|No Dynamic vol control|0.77|0.05|

Skew (per trade)

|   |   |   |
|---|---|---|
||Dynamic stop loss|No Dynamic stop loss|
|Dynamic Vol Control|4.00|1.87|
|No Dynamic vol control|3.07|1.95|

- Dynamic stop loss adds considerable skew but at great cost to SR.