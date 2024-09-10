[Link](https://www.youtube.com/watch?v=Ets0xGCjQ14&t=286s&ab_channel=QuantProgram)
[Documentation for reference](https://www.quantconnect.com/docs/v2/)
## Initialise, OnData and other Built in Functions
- `initialize` function will get the start and end dates, portfolio starting cash, and the tickers of which instruments are to be used in testing
- `on_data` function will punch the orders

## Debug, Avg price, Logs
- To retrieve the information about a particular ticker in the portfolio:
	```python
	# in the initilize class:
	self.ticker = self.add_equity("SPY", Resolution.DAILY)
	
	# in the on_data class:
	self.portfolio[self.ticker.symbol].quantity
	self.portfolio[self.ticker.symbol].average_price
	```
- Print statement in the "Log" section of backtests by using `.debug`
	```python
	self.debug("Number of shares" + str(self.portfolio[self.ticker.symbol].quantity) +\
	"@Price" + str(self.portfolio[self.ticker.symbol].average_price))
	```

## Challenge 1
- <u>Create a portfolio of SPY, QQQ, and TLT and allocate 33% to each. Log the quantity and average price these tickers were filled at.</u>
- Solution:
```python
# region imports
from AlgorithmImports import *
# endregion

class EmotionalOrangeJaguar(QCAlgorithm):

	def initialize(self):
	
		self.set_start_date(2010, 1, 1)
		self.set_end_date(2023, 6, 6)
		self.set_cash(100000)
		
		self.snp = self.add_equity("SPY", Resolution.DAILY)
		self.tech = self.add_equity("QQQ", Resolution.DAILY)
		self.bond = self.add_equity("TLT", Resolution.DAILY)

  

	def on_data(self, data: Slice):
	
		if not self.portfolio.invested:
			for instr in self.Portfolio.Keys:	
				self.set_holdings(instr,0.33)
		
		for instr in self.Portfolio.Keys:
		
			self.debug("bought " + str(self.portfolio[instr].quantity) + " quantity of " +\
			str(instr) + " @ " + str(self.portfolio[instr].average_price))
```

## Adding indicators
- Adding simple moving averages and plotting them alongside the price of the ticker
	- `self.SetWarmup(100)`  : this will load at least 100 days of data before the moving averages to make sure there is enough data for calculations of the moving average in the initial period.
	- `IsWarmingUp`  : to make sure `on_data` function only runs after the warming up is completed
	```python
	class EmotionalOrangeJaguar(QCAlgorithm):  
	
		def initialize(self):
			self.set_start_date(2020, 1, 1)
			self.set_end_date(2023, 6, 6)
			self.set_cash(100000)
			
			self.ticker = self.add_equity("SPY", Resolution.DAILY)
			
			self.fast_ma = self.SMA(self.ticker.symbol, 20)
			self.slow_ma = self.SMA(self.ticker.symbol, 50)
			
			self.SetWarmup(100)
		
		def on_data(self, data: Slice):
			
			if self.IsWarmingUp:
				return
			
			if not self.portfolio.invested:
				self.MarketOrder(self.ticker.symbol, 10)		  
			
			self.Plot("SPY","MA20", self.fast_ma.Current.Value)
			self.Plot("SPY","MA50", self.slow_ma.Current.Value)
			self.Plot("SPY","SPY", self.ticker.Price)
	```

## Entry and Exit Conditions
- Adding trade rules based on moving averages
	```python
	class EmotionalOrangeJaguar(QCAlgorithm):  
	
		def initialize(self):
			self.set_start_date(2020, 1, 1)
			self.set_end_date(2023, 6, 6)
			self.set_cash(100000)
			
			self.ticker = self.add_equity("SPY", Resolution.DAILY)
			
			self.fast_ma = self.SMA(self.ticker.symbol, 20)
			self.slow_ma = self.SMA(self.ticker.symbol, 50)
			
			self.SetWarmup(100)
		
		def on_data(self, data: Slice):
			
			if self.IsWarmingUp:
				return
			
			if not self.portfolio.invested:
				# ENTRY condition
				if self.ticker.Price > self.fast_ma.Current.Value:
					self.set_holdings("SPY", 1)
			
			if self.portfolio.invested:
				# EXIT condition
				if self.ticker.Price < self.fast_ma.Current.Value:
					self.liquidate()
			
			self.Plot("SPY","MA20", self.fast_ma.Current.Value)
			self.Plot("SPY","MA50", self.slow_ma.Current.Value)
			self.Plot("SPY","SPY", self.ticker.Price)
	```

## OnOrderEvent, OrderID, OrderFree
- `on_order_event` function is called whenever there is a trade. It has information like filled price etc.
	```python
		def on_order_event(self, order_event):
			my_order = self.transactions.get_order_by_id(order_event.order_id)
			self.log("{0}: {1}: {2}:".format(self.time, my_order.type, order_event))
	```

## Stop Loss and Take Profit
1. `self.stop_market_order` in the `on_data` function where the order to enter the trade is added
	```python
	my_stock = self.ticker.symbol
	if not self.portfolio.invested: # when entering a trade
		if self.ticker.Price > self.fast_ma.Current.Value:
			self.market_order(my_stock, 150)
			self.stop_market_order(my_stock, -150, self.securities[my_stock].close * 0.95)
			# 5% stop loss market order
	```
2. Another method by explicitly putting a liquidation order. Same method can be used for Take Profit
	```python
	my_stock = self.ticker.symbol
	if self.portfolio.invested: # when already in a trade
		if self.ticker.Price < (self.portfolio[my_stock].average_price * 0.95):
			# IF current price is less than 95% of the price we got filled at
			self.liquidate()
	```

### Trader consolidator, custom bar
- Useful for if you want to create bars of custom lengths, like 25 minutes bars, etc.

## Dynamic Universe and Portfolio Backtesting
- *refer to the code in QC platform*

# Documentations
- 