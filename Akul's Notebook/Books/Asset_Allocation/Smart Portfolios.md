
[Book Link](<file:///Users/akul/Desktop/Work Work Work/books/Asset Allocation/Carver, Robert - Smart Portfolios_ A practical guide to building and maintaining intelligent investment portfolios-Harriman House (2017).pdf>)
Author(s): Rob Carver
Publish Year: 2017
Tags: #Asset_Allocation #Macro_TA #Portfolio_Construction #Rob_Carver

# Part One: Theory of Smart Portfolios

## <u>Chapter 1: What is the Best Portfolio?</u>
- Definition of the 'best portfolio': "The highest expected real after costs total geometric absolute return, for a given level of risk and time horizon, in a particular investment currency"
- "the benefits of diversification are greater when average returns are measured with geometric means"
- "Accumulating funds do not pay dividends; […] Distributing funds pay out all the income that their underlying assets earn"
	- "Do not compare accumulating and distributing fund based purely on how their prices have changed"
- "Personally, I'm extremely sceptical about the need for currency hedging"
	- "hedging doesn't improve pre-cost returns"
	- "reduces the diversification benefit of having a portfolio of assets spread over multiple currencies, by making them more correlated with each other"
	- Higher management fees, and other costs e.g., carry and roll.
	- "hedging is an expensive alternative without any clear advantages"
	- "steer clear of currency hedged products"


## <u>Chapter 2: Uncertainty and Investment</u>
- "There are many ways of doing this [measuring risk of different outcomes] but I prefer to use standard deviation"
- "Throughout the rest of the book I don't distinguish between the two different types [geometric and arithmetic], instead I just refer to a generic standard deviation". Author uses geometric mean and standard deviation.


## <u>Chapter 3: Trying to Find the Best Portfolio</u>
- "use geometric returns for the Sharpe Ratios"
- "if inflation rises then returns will probably be dragged down by a reverse repricing which will cause PE ratios to fall (and so reduce stock prices), and bond yields to rise (causing bond prices to plummet)"
- Author created a sample portfolio of U.S. Bonds and S&P 500. He equalised the Sharpe Ratio of the two assets. Volatility of each asset remained the same. He also reduced the returns of both the assets, given his view of both bonds and equities valuation being too high. He says valuation of equities have been significantly helped by downward trending inflation for the past few decades.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_4_Historic_Annualised_Average_and_Standard_Deviation_Of_Real_Returns_For_US_Assets.png">


## <u>Chapter 4: Simple, Smart, and Safe Methods to find the Best Portfolio</u>
- Using the portfolio created, the author creates a distribution of geometric returns using Bootstrapping to see the likely returns over an x-length period.
	- "randomly choose a series of years from the data set, and find the returns for bonds and stocks in each of those years. So, for example, if I selected 1987 then I'd use the adjusted stocks return (-1.1%), and bond return (-8.9%) for that year"
	- "Each time I choose a year I replace it, so it can be chosen again"
- "Even investors who are terrified of risk should have some exposure to equities"
- Splitting your portfolio between cash and maximum Sharpe Ratio is a good way of investing for conservative investors.
- "nobody should invest entirely in equities". If you want the highest returns possible, a small allocation (10%) to bonds is good for the portfolio.
- "low-risk, low-return, assets should be avoided by Sharpe Ratio maximising investors who can't use leverage. This is because you have limited cash: investing in safer assets that have lower returns is a poor use of that cash"
- "avoid leveraged ETFs as they aren't suitable for long-term investments, only for taking short-term tactical bets"
- "The risk weighting is the weighting in the portfolio normalised by the amount of risk each asset has"
	- Calculate the volatility factor by dividing the target volatility by the asset's estimated volatility.
	- Multiply volatility factor by risk weight to get the cash weight.
	- Sum of all cash weights won't necessarily add up to 100%. Calculate the multiplying factor and multiply the cash weights by this factor to get final weights.
- "I made a number of mistakes [while creating my own portfolio prior to leaving the financial industry] but the biggest was building my portfolio from the bottom up"
	- "My exposure to asset classes and to different countries wasn't the result of deliberate decisions, but a consequence of what I'd already decided to buy"
- Advantages of handcrafted method
	- Produces max SR portfolio
		- "equal weight portfolio will be optimal if the geometric means, standard deviations and correlations within a group are equal"
	- No data is harmed
		- "isn't unduly bothered by the uncertainty of the past"
	- Not easily shocked
		- "Correlations rising in a crisis is only a serious issue if you've leveraged up your portfolio on the assumption of low correlations"
- To maximise geometric mean using the handcrafting method:
	1. Group low-risk assets together:
		1. Max geometric mean portfolio: "Give the low-risk group a 10% [risk] allocation"
		2. Compromise portfolio (in the middle of max geometric mean and max SR): "Give the low-risk group a 30% allocation in risk-weighted terms"
		3. Max Sharpe Ratio portfolio: "give each group a 50% allocation in risk-weighted terms"
	2. Continue to allocate portfolio weighs within the two groups, as usual.
- Ideally, an asset allocating portfolio should take into account the changes in asset volatility and correlations.
- Scenarios where equal weights (within a group) don't make sense:
	- Large mismatch between group sizes
		- "can improve on equal weights in an unbalanced portfolio by increasing the weight on the larger group of assets"
	- Equal weights deviate too far from the market capitalisation weighted consensus
	- Some assets are going to be more expensive to trade or hold
		- "Some types of asset just cost more to buy or own, and there isn't much we can do about that. […] This justifies a lower allocation than the equal weighting they'd have with the same costs"
	- You have assets in your portfolio with risky risk
		- "Some assets have less predictable risk". Standard deviation does not explain all risk.
		- "They have high negative skew, and a high kurtosis"


## <u>Chapter 5: Smart Thinking About Costs</u>
- "Passive ETFs are usually the cheapest way to get market exposure"
- Visible costs:
	- Brokerage
	- Taxes
	- Annual management fees
	- Other fund management fees (administration, custody fees and marketing costs of collective funds)
- Invisible costs:
	- Execution
	- Trading costs inside funds (higher for actively managed funds
- Three types of costs:
	1. Initial costs:
		- "Payable on all types of investments. Examples: commissions, initial charges, taxes, and execution
	2. Holding costs:
		- "have to be paid regularly whilst you hold your position […]. Examples: annual management fees and trading costs inside ETFs"
	3.  Rebalancing costs
		- "incurred from any buying and selling you do in your portfolio after it's been set up. Examples: commissions, fund switching charges, taxes, and execution"
- "Large investors should worry about market impact; for small investors minimum commissions are more important"
- "execution costs are rarely, if ever, revealed; some managers are unaware they exist for and many other don't bother to estimate them even for internal reporting purposes"
- Variable percentage costs:
	- Initial costs to set up portfolio: Minimum brokerage commissions; fixed taxes (e.g., UKT PTM Levy)
- Fixed percentage costs:
	- Initial costs: percentage or per share brokerage; percentage based taxes (e.g. stamp duty); Bid-ask spread; market impact
	- Holding costs: annual management fees; trading costs inside collective funds
- The Rule of 20:
	- Used to compare costs that occur only once (initial cost) and other that are ongoing (holding costs and possibly trading costs)
	- "assign a current value to this ongoing annual charge using a technique called discounted cash flow valuation"
	- "For example a $100 annual fee over five years with interest rates at 4% will have an upfront present value of $445, but $100 a year for ten years with the same interest rate is worth almost twice as much: $811"
	- "A $100 annual holding charge discounted at 3% over 30 years has an upfront present day value of just under $2000, so to convert annual costs into a single currency value you can multiply by 20"
	- "Investors who have a shorter investment horizon can use a different multiplier: for 20 years use a multiplier of 15, for ten years use 8.5, and for five years use 4.5"
- Table 23 shows an "example of cost calculation table"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_23_Example_Of_Cost_Calculation_Table_FTSE_100_ETF.png">
	- First three columns show holding costs. "These are all fixed percentage costs"
		- Annual management fee; and invisible trading costs inside a fund
	- Next four columns show specific initial costs
		- Tax (fixed); brokerage commissions (variable cost); bid-ask spread (fixed); and "market impact (zero for retail but with a fixed value for institutional investors)"
	- "To make this [total initial cost] an annual cost and comparable with the holding costs I use the rule of 20, and divide the initial cost by 20"
- When comparing different funds, "you need to use the total return including any dividend payments and after deducting any costs that don't appear in published performance figures"
- "A lot of this material in this chapter is less relevant for the largest institutions. Institutional investors can probably afford to invest directly in shares, although they need not bother if they can find a cheap enough ETF"
- "Tactics for reducing the execution costs of trading at larger sizes"
	- "These can also be used by experienced retail traders, especially those buying less liquid stocks such as those of smaller firms"
	1. <u>Get paid the spread</u>
		- If you put a limit order at the top bid, and get filled, you'll have a negative execution cost (because mid-price of bid-ask is assumed as the trading price).
		- If you don't get filled and are forced to chase the market, increasing your limit order, your execution cost is much higher. "Does this mean limit orders are a waste of time?"
		- "To save face and limit the damage you can determine the highest price you'd pay". Like placing a stop-loss 'if the price moves x points, I will put a market order, before that I will keep increasing my limit order'.
		- "If you can stomach the risk I'd strongly advocate a strategy of placing limit orders into the market"
		- The author has "assumed that you are paying the spread in the calculations [he has] used in the rest of the book"
	2. Trade more slowly
		- "The solution is to break up your order into smaller chunks and execute it more gradually. The slower you execute, and the smaller the size of each order, the lower the market impact of each trade. This is known as order smoothing or order splitting"
		- "in my experience even relatively sophisticated institutional investors often give themselves quite short periods of time to complete trades, relative to their average holding period". Read [[Trading Costs of Asset Pricing Anomalies]] on trading costs by AQR.


## <u>Chapter 6: The Unkown Benefits and Known Costs of Diversification</u>
- "diversification isn't entirely free. It will probably cost more in brokerage commissions if you have a modest portfolio"
- "risk-adjusted returns are extremely hard to forecast"
- "If all assets have the same risk-adjusted return (Sharpe Ratio), and the same risk, then they must have the same geometric mean of returns"
- "both geometric mean and Sharpe Ratio increase with diversification"
- "Picking stocks is a waste of time, because a highly concentrated group of 'high conviction' bets will do worse than a larger diversified portfolio"
- "In my opinion there are probably only three truly distinct asset classes: bonds, equities, and alternatives"
- Costs assumed (for individual shares):
	- Brokerage fees: 6 GBP per trade
	- Bid-ask spread: 0.05%
- To calculate the cost of buying individual shares, the author added up all the initial costs (i.e., brokerage, stamp duty, slippage) and "divide the initial cost by 20 to get an annual cost"
- To evaluate whether diversifying is worth the extra cost, the author first calculated the cost of diversifying (i.e., buying additional assets) and then used the average correlation among the assets to calculate the benefit in geometric return.
	- If the increase in geometric return is higher than the increase in costs, it is worth diversifying.
- "a more expensive trading system needed to earn twice as much more in pre-cost returns than the extra costs it attracted"
	- "the basic idea that uncertain benefits have less value than certain costs is still valid"
- Author calculated the minimum average correlation required for diversification to still be beneficial. Since correlation is uncertain, he made a distribution of correlations. Then, he compared how confident can we be that diversification will still be beneficial. Figure 31 shows this exercise.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Figure_31_Uncertainty_In_Correlation_Estimate_Means_We_Can't_Be_Sure_About_Diversification_Benefits.png">
	- "the breakeven correlation [where diversification does not add any value] is very extreme [..] we can be extremely confident that diversifying was the right thing to do" in this example.
- "the main difference between Sharpe Ratio maximiser and geometric mean investors will be their asset allocation. The former will have more safe bonds, and the latter a large proportion of riskier equities"
	- All decisions following this broad asset allocation will be the same for both investors, those who want to maximise Sharpe and those who want to maximise geometric return.
- "The bid-ask spread on liquid ETFs covering developed market indices like the S&P 500 is similar to the underlying shares or even tighter; I assume 0.05%"
- "large investors can work with ETF market markets to create new ETF units"
- Types of collective investment funds:
	- Open ended:
		- Hand the money "to the manager, who went and bought the underlying shares to put inside the fund"
		- "The fund itself couldn't be traded on a stock market. This made the pricing and fee structure more opaque"
	- Closed ended:
		- Go "to the stock market and bought the fund off someone who already owned it"
		- "This did mean that closed end funds often traded at a premium or a discount to the value of the investments inside them"
	- ETF:
		- "a hybrid of open and closed ended funds"
		- "Normally they behave like closed ended funds"
		- "However let's suppose you wanted to do a huge purchase of an ETF. […] you would go to the ETF market maker and new shares would be purchased to put inside the ETF. This creates new units in the ETF"
- "It's crazy to think that an investor can replicate what an ETF manager does more cheaply if they're trying to do exactly what they are doing"

- Handcrafting, Equal Weighting, or Market Cap Weighting?
	- "a market cap portfolio assumes that investments in larger firms are expected to return more than those in smaller companies"
	- "Smaller indices like the DAX 30 are more vulnerable to excessive concentration than those with 100 or 500 shares, like the FTSE and S&P 500"
		- "Emerging markets, and other countries with undiversified economies, will also be more concentrated"
		- "The Australian and Canada resource-heavy indices have around 50% of the index in the top ten stocks"
	- "The management fee of the market cap weighted ETF for Canada is a relatively expensive 0.4% a year, and the equal weighted ETF is even more expensive at 0.5%. I assume that trading within the fund costs around 0.1% for the market cap ETF, and 0.4% for the equal weighted variation"
	- "Table 34 sum [author's] findings once I include the effect of difference costs levels; it shows the ranking of each option at different portfolio values"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_34_What's_The_Best_Way_To_Allocate_Across_The_Canadian_TSX_Equity_Index.png">
		- "the breakeven point at which direct investment makes sense is around $15,000"
	- "As the vast majority of equal weighted funds have a higher management fee, the smartest option is to steer clear of equal weighted funds"
	- "a number of ETFs have been launched using capped indices: '25/50' and '10/40' are common variants"
		- "the weight of any single company is capped at 25% of the index. The weight of 5% of the companies in the index […] is capped at 50%"

- Buy the whole index, or just a part of it?
	- Tables 35 and 36 compare different variations of the handcrafting method, i.e. whether you should restrict yourself to a number of stocks per industry or take the entire universe into consideration.
		<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_35_What_Is_The_Expected_Performance_Of_Different_Portfolio_Weighting,_For_Direct_Investment_In_The_S&P500.png"><img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_36_What's_The_Optimal_Number_Of_Shares_To_Buy_In_Each_Sector.png">
		- For institutional investors, it makes much more sense to include all the stocks into the portfolio using handcrafting method due to lower fixed costs and greater diversification benefits.
		- "don't buy less than $2,000 of each share when considering whether to buy more than on share per sector"

- The smartest way to invest in a given country
	- "two possible routes for investing in a given country":
		1. "Below a certain threshold of total investment size, investors should stick to <u>buying a market cap weighted ETF</u>". Table 37 shows the minimum investment to make direct share buying worthwhile for US investors.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_37_What's_The_Minimum_Investment_To_Make_Direct_Share_Buying_Worthwhile_For_US_Investors.png">
		2. "If you have enough money it is feasible to <u>buy selected individual stocks</u> to get exposure to a given country"

- Does diversifying by buying multiple funds make sense?
	- "after diversifying you will probably end up with higher management fees, trading costs within the fund will be higher, and both bid-ask spreads and market impact can increase"
	- "Table 40 shows the lowest viable investment per fund for a given minimum commission level"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_40_What's_The_Lowest_Viable_Investment_Per_Fund_To_Avoid_Paying_Excessive_Costs_Given_The_Minimum_Brogerage_Fee.png">


# Part Two: Creating Smart Portfolios
- "You should not expect to read this part in one sitting unless you are looking for a cure for insomnia, and there are some parts of it you may never need to read"
- "Everyone should read the first two chapters"
- "these chapters [9 and onwards] are options depending on the amounts you have to invest"
- "chapter thirteen brings everything together and shows several examples of top-down portfolio for different investors. This chapter is compulsory reading for everyone"
- "Throughout part two I assume that nobody can or should try to predict risk-adjusted returns. Part three explains what changes you should make to your portfolio construction process if that statement is untrue"

## <u>Chapter 7: A Top-Down Approach to Building Smart Portfolios</u>

- Why is top-down smart?
	- Advantages to using a top-down approach:
		- "Forces diversification: reduces home and asset class bias"
		- Breaks down the daunting process "into a series of simpler decisions about smaller groups of assets"
		- "ensures as much diversification as possible when the inevstor can only afford to buy a handful of funds"
		- "diversification will still be maintained and potentially dangerous stock picking limited to a small part of the portfolio"

- The top-down portfolio
	- "The first step is to form the assets you have into groups which contain similar securities".<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_10_A_Simple_Top-Down_Example_Step_One_Asset_Classes.png">
	- "risk weightings assume that all assets have the same volatility of returns, and cash weightings which translate these into real money weights that account for different levels of risk"
	- Portfolio 11 shows the next step in the process, drilling down into the second level of the portfolio, i.e. allocation to different countries.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_11_A_Simple_Top-Down_Example_Step_Two_Countries.png">
		- "The final row, below the double lines, show the final weight in each individual country and asset combination"
	- To look at risk weights allocated to different countries within an ETF, the author takes the cash weights that have been allocated to different countries within the ETF and then calculates the risk weight.
		- Once he has the risk weights, he then adjusts the risk weight allocated to that ETF accordingly. For example: if he wants Emerging Markets to get a risk weight of 6% and an aggregate ETF (which has exposure to all global markets) gives EM a risk weight of 12%, he will want to give this particular ETF a risk weight of 50%.
		- In Portfolio 14, the author wanted to allocate 75% risk weight to developed markets (of which 30% should be in the U.S.) and 25% risk weight to emerging markets. The IAGG ETF had a cash allocation of 8% to emerging market; accounting for different volatility, this translates into a risk weight of 12%. "Risk weighting for IAGG is Y and for the pure emerging market fund EMAG it is Z. So the total risk weight for emerging markets will be (Y * 12%)+Z, and this should equal 25%. […] Y+Z=70%, since I've allocated 30% to the US fund AGG. […] I now have the risk weights for all three ETFs: 30% in the U.S. fund AGG, 51% in IAGG and 19% in the pure emerging market fund EMAG. I then translated these into cash weights using the usual method I introduced in chapter four"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_14_Example_Showing_Extra_Exposure_Row.png">

- The road map
	<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Smart_Portfolios_Portfolio_Building_Journey.png">
	- Core and satellite
		- Versions of this fashionable idea:
			1. "core is a developed equity portfolio, with the satellite reflecting exotica like bonds, emerging markets, and hedge funds. [...] will probably result in a relatively overweight exposure to developed market equities"
			2. "core contains long-term strategic holdings and the satellite consists of short-horizon tactical bets. [...] assumes an ability to forecast the performance of different fund management styles [...] (which I'm also extremely skeptical of)"
			3. "core consists of low-cost index funds, while the satellite is stuffed full of active managers. [...] a passive core and active satellite, is a more promising idea"

- Issues to consider
	- How to split up the portfolio
		- "best way to split an equity allocation [...] is by industry"
		- In the case of bong weightings, "should you first split you pool of assets into corporate and government bonds, or by bond maturity?"
	- Which assets should be included?
	- How should assets we weighted?
		- "you might want to constrain a particular part of your portfolio a lower allocation than equal weights would suggest"
	- Does the portfolio need to be split further?
		- "Because the process is top-down, at each stage you can decide if you need to continue dividing your portfolio into smaller parts"
		- "Often some parts of the portfolio will be more granular than others"


## <u>Chapter 8: Asset Classes</u>

- What division of asset classes?
	- "Traditionally investment managers have used a three asset class approach - equities, bonds and alternatives - as shown in portfolio 15"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_15_Traditional_View_Of_Asset_Classes_Alternatives_As_A_Seperate_Bucket.png">
		- "as you might recall from chapter four, most investors should have no cash except for those in the Ultra Cautious category"
	- The grouping shown in portfolio 16 "better reflects the risks inherent in the various different types of alternatives"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_16_New_View_Of_Asset_Classes_Most_Alternatives_Included_In_Relevant_Asset_Class.png">
		- This grouping essentially uses covariance with equities and bonds to classify alternatives into equities-like, bond-like, and genuine alternatives.

- The smart way to weight asset classes
	- "I assume that bond-like alternatives have bond-like volatility, and equity-like alternatives about as risky as traditional equities"
	- "The correlation between equities and bonds varies over time, but has average around zero"
		- "If you're using risk weighting then with identical correlations [equity-bond, bond-alternatives, and equity-alternatives] and equal risk-adjusted returns all the assumptions of equal weighting hold, and in theory you should invest in portfolio 18"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_18_Best_Asset_Class_Allocation_For_Maximum_Sharpe_Ratio_With_No_Constraints_On_Alternatives.png">
		- Portfolio 18 gives 66% risk weighting to alternatives. Alternatives should get a lowe weight because they "don't have well behaved risk, and have a nasty habit of becoming much riskier very quickly"
			- "ETFs for alternative assets usually cost a lot more, and direct investment via hedge funds and other exotic legal entities is an equally epensive business"
			- "Smaller market cap, lower post-cost returns and unpleasantly un-forecastable risk; putting these together justifies a lower weight to alternatives [...] I've chosen 10% but in my opinion any initial allocation between 0% and 25% is reasonable. I wouldn't go higher than 25%"
	- #idea_strategic_asset_allocation Portfolio 19 (for low-risk, maximum Sharpe Ratio investors) and 20 (for higher, maximum geometric returns investors) show the risk (and cash) weights after limiting risk allocatino to alternatives at 10%.
		<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_19_Best_Asset_Class_Allocatino_For_Sharpe_Ratio_Maximum_Portfolio_With_10_In_Alternatives.png"><img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_20_Best_Asset_Class_Allocation_For_Maximum_Geometric_Mean_Portfolio_Investor_With_10_In_Alternatives.png">
		- Compromise portfolio "lies somewhere between the two, with risk weighting of 30% in bonds and 70% in equities"
		- Table 41 summarises "the cash weightings of the various different permutations"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_41_Cash_Weightings_Of_Nine_Different_Asset_Allocation_Portfolios.png">


## <u>Chapter 9: Alternatives</u>

- Different groups of alternatives
	1. "<u>Equity-like alternatives will do badly when there is poor economic news</u>, or when investors get scared. Certain hedge fund strategies also rely on risk remaining low, and lose monery when it increases"
	2. "<u>Bond-like alternatives are sensitive to higher interest rates and spikes in inflation</u>"
	3. "<u>Genuine alternatives have relatively little to do with either of the main asset classes.</u> Some of them even have a negative average return"

- Genuine alternatives
	- Two subcategories:
		1. Insurance-like alternatives:
			- "negatively correlated with bonds and stocks"
			- "negative expected returns"
			- Gold and precious metals
			- Long volatility
			- Tail protection hedge funds
			- Insurance currencies (safe haven currencies)
		2. Standalone alternatives:
			- "uncorrelated assets"
			- "expect to have positive returns"
			- Managed futures
			- Global macro hedge funds
	- "With the exception of tail protect I managed to find ETFs for each of the strategies in this bucket, although their performance was disappointing and their fees relatively high"
	- "Portfolio 21 shows a suggested breakdown for genuine alternatives, for an institutional investors who can access all the different categories"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_21_Suggested_Allocation_For_Genuine_Alternatives_Sub-Portfolio.png">

- Equity-like alternatives
	- "assets I think should be categorised as equity-like alternatives"
		- Private equity and venture capital: "equity in unlisted firms"
		- Real estate: "exposed to the same economic cycle as stocks [...] Also rents, like equity earnings, tend to rise with inflation"
		- Commodities (excluding precious metals): "Like equities, commodity prices are closely linked to inflation"
		- Most hedge fund strategies: "are correlated with equities and they tend to suffer when general deleveraging events occur"
			- Equity neutral ("use signficant leverage to boost returns which leaves them highly vulnerable to things going wrong")
			- Fixed income relative value ("negatively correlated to bond returns, [...] but does make them more like equities. Again they use significant leverage")
			- FX Carry ("depreciations [of currency you are buying] tend to occur when people are selling equities and other risky assets. Again, considerable leverage is employed by FX Carry managers")
			- Volatility Selling ("profitable in the long run but will occasionally result in very large losses, often when equity markets collapse")
	- Portfolio 22 shows "a weighting scheme for an investor who is willing and able to have an extensive portfolio of alternatives"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_22_Suggested_Weighting_For_Equity-Like_Alternatives.png">

- Bond-like alternatives
	- Assets in this category:
		- Private debt: "very similar to, if a little riskier than, public debt"
		- Peer-to-peer lending: "like buying an extremely risky bond"
		- Infrastructure, real assets, and asset-backed securities: "gives you acces to stream of future revenue"
		- Hedge funds with long bias in bonds: "they usually bet on the overall bon market going up; this makes them more correlated to the underlying asset class"

- Alternative assets for ETF investors
	- Genuine alternatives
		- Portfolio 24 shows how a large US retail investor can use ETFs to get exposure to genuine alternatives.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_24_Suggested_Weighting_For_Genuine_Alternatives_Sub-Portfolio_(Large_US_ETF_Investor).png">
		- UK investors have access to a much narrower range of ETFs for alternatives. Portfolio 27 shows the sample alternative portfolio for a large UK ETF investor.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_27_Suggested_Weighting_For_Genuine_Alternatives_Sub-Portfolio_(Large_UK_ETF_Investor).png">
	- Equity-like alternatives
		- Portfolio 28 shows how a large US retail investor can use ETFs to get exposure to equity-like alternatives.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_28.png">
		- Portfolio 30 shows how a large UK retail investor can use ETFs to get exposure to equity-like alternatives. Now many short volatility funds are available for UK investors so that has been removed.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_30.png">
	- Bond-like alternatives
		- Portfolio 32 shows how a large US retail investor can use ETFs to get exposure to bond-like alternatives.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_32_Suggested_Weighting_For_Bond-Like_Alternatives_(US_ETF_Investor).png">
		- Portfolio 33 shows how a large UK retail investor can use ETFs to get exposure to bond-like alternatives.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_33.png">


## <u>Chapter 10: Equities Across Countries</u>

## <u>Chapter 11: Equities Within Countries</u>

## <u>Chapter 12: Bonds</u>

## <u>Chapter 13: Putting It All Together</u>


# Part Three: Predicting Returns
- "I think that the first thing is you should have a strategic asset allocation mic that assumes that you don't know what the future is going to hold" - Ray Dalio

## <u>Chapter 14: Predicting Returns and Selecting Assets</u>

- "prediction is hard. No matter how low (or high) things can go, they can always go even lower or much higher"
	- "it's not enough to predict the future, you have to predict it better than anyone else can"
- Figure 32 shows the distribution of Sharpe Ratio estimates condition on the previous 12 months momentum, for US equities.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Figure_32_Distribution_Of_Sharpe_Ratio_Estimates_Is_Quite_Different_For_High_Versus_Low_Momentum.png">
	- "The plot for bonds is equally striking"
	- "If I run the analysis on relative performance of equities versus bonds, conditioned on relative momentum, I get similar results"
- "adjustments to your portfolio weights to reflect the output of the momentum model should improve your returns"
- Two risk factors used: momentum and the dividend yield risk factors

- How can use smart forecasting models to construct portfolios?
	- "Firstly you can adjust your portfolio weights. Secondly you can use it to select certain assets, and drop others"

- Introducing two smart forecasting models
	- #idea_tactical_asset_allocation Momentum model:
		- Start with portfoloi weights. Get the returns from the last 12 months. Calculate the trailing Sharpe Ratios. Use Table 46 to adjust portfolio weights according to the Sharpe Ratio.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_46_How_Much_To_Adjust_Handcrafted_Weights_Given_Trailing_Returns.png">
		- Normalise the weights so the weights add up to 100%.
			- "decide whether you want to use an absolue or a relative momentum model"
			- "With a relative model you are always fully invested"
			- "With an absolute momentum model you will not be fully invested if there are any assets in the portfolio that are falling in price"
			- In absolute momentum, normalisation is only required if the weights add up to more than 100%.
	- #idea_value_investing #idea_tactical_asset_allocation Yield model:
		- "stocks that pay higher dividends outperform others. It turns out that this works pretty well in bonds as well, and across different asset classes"
		- "within equities you could use earnings yield (the inverse of price-to-earnings ratio), and for all assets you use carry (the yield, less an appropriate short term interest rate like LIBOR or the Fed funds rate)"
		- Start with portfolio weights. Get the yield for each asset. "Ideally you need the dividend yield (equities or equity funds) or yield to maturity (bonds funds). With the ETFs you should use the underlying yield of the assets within it, but you can also use the ETF's own dividend yield". Divide the yield by the standard deviation of the returns of each asset class. "Work out the median Sharpe Ratio, and each asset's relative difference to the median". Use Table 47 to adjust portfolio weights according to the Sharpe Ratio calculated in the previous step.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_47_How_Much_To_Adjust_Handcrafted_Weights_Given_The_Difference_In_Yield_Sharpe_Ratios.png">
	- Refer to Appendix C if "you want to use your own favourite forecasting mode, or create a new model from scratch"

- Using forecasting models in a top-down handcrafted portfolio
	- Different properties of momentum and dividend yield models
		- #idea_tactical_asset_allocation "when assets are very similar, value type models like dividend yield tend to do better"
		- "risk-adjusted yields on different asset classes can be wildly different for long periods of time"
	- "the Sharpe Ratio is also much lower [than fixed weight portfolio]. The yield model is not a great success at predicting risk-adjusted returns for different asset classes"
	- "My recommendaitno for asset allocation is to use a relative momentum model"
	- #idea_tactical_asset_allocation To combine forecasts of multiple models:
		- Start with the fixed portfolio weights. Get the portfolio weight adjustment factors for each model. Multiply the adjustment factors from each model, then the take the *n*th root (geometric mean). Multiply the portfolio weigths with the adjustment factors. Normalise the weights such that they add up to 100%.
	- Forecasting models wiith multiple levels
		- Author uses relative momentum on the broad asset class leve; and combines relative momentum and yield models within asset class.
		- Portfolio 85, for example. "relative momentum only in equities and bonds. Then we'll use momentum and yield within equities [...]. Finally we'll use the same two models within bonds"djust portfolio weights according to the Sharpe Ratio calculated in the previous step.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Portfolio_85_Simple_Example_To_Demonstrate_Models_With_Multiple_Levels.png">
		- To work out the combined Sharpe Ratios, e.g. the trailing Sharpe Ratios of equities (to be used in the momentum model), "we need to take a weighted average of the trailing SR" of the constituents. The risk weightings uesd should be the weights "after you've already applied the forecasting model multiplier within a group"
	- Weighting and selecting individual stocks with a model of returns
		- "I don't recommend using forecasting models for both weighting and selection. [...] If you want to use a model to select your equities, then just hold them in fixed weights"
		- "Selection works best when (a) there are plenty of assets to choose from, and (b) they are fairly similar"
		- "I would propose using dividend yield to select one or more equities in each sector, and then hold those in equal weights"
			- "avoid firms with very high dividend yield. There is strong evidence that these have lower risk-adjusted returns"
			- "you can use forecasted dividends"
			- "set a minimum level of dividend cover. The dividend cover ratio is the earnings per share divided by the divided per share. [...] At a minimum dividend cover should be 1"
			- "minimum and maximum thresholds for other accounting ratios:"
				- Dividend yield < 10%
				- P/E ratio < 1.5
				- Forecast dividend cover > 1.2
				- Gearing (debt divided by shareholder equity) < 0.5
		- Buy the highest yielding large cap, mid cap, and small cap stock in the proportion 60%-20%-20%, respectively.
			- "The appropriate portfolio for different number of stocks in each sector are shown in Table 52"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_52_How_To_Squeeze_Small_And_Mid_Cap_Stocks_Into_Your_Sector_Sub-Portfolio.png">
	- "Ideally you should use the yield to maturity measure as a substitute for dividend yield" when picking bond ETFs.
	- Adjustment factors are calculated at each level of the top-down portfolio, which are then multiplied with the risk weights to get the allocation adjustment according to the model.

- Adjusting portfolio weights when you don't have a model
	1. Forecasting Sharpe Ratios
		- "you need to determine the expected Sharpe Ratio of each asset over some time horizon"
		- "Work out the median Sharpe Ratio, and each asset's relative difference to the average"
		- Use the first and third column of Table 60 to "find the portfolio weight adjustment factors"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_60_How_Much_Should_We_Adjust_Handcrafted_Weights_By_If_We_Have_A_Prediction_For_Asset_Sharpe_Ratios_Which_Is_Not_Based_On_A_Model.png">
	2. Scoring system
		- "Assign a score to asset; higher score mean higher returns. Use a range for scores between -20 and +20"
		- "Work out the median Sharpe Ratio, and each asset's relative difference to the average"
		- Use the first and third column of Table 60 to "find the portfolio weight adjustment factors"


## <u>Chapter 15: Active Fund Managers</u>

- Active fund managers
	- "To find out [if your favorite fund manager is truly different, superior] you should first find an alternative option: a passive fund which closely matches the mandate of the active fund manager you are considering"
		- "Make sure you are using returns with all costs deducted; both visible and invisible"
		- "Measure the historic standard deviation of returns for both funds to make sure they are similiar [...] Normalise the returns of both funds"
		- "Measure the outperformance of the active fund"
		- "Finally measure the correlation"
	- "Table 61 shows the difference in arithmetric returns required to be 90% sure that one fund is better than another, depending on the length of the track record and the correlation between the active and passive fund"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_61_How_Much_Improvement_In_Average_Post-Cost_Return_Do_We_Need_To_Be_90_Sure_That_An_Active_Fund_Is_Probably_Better_Than_A_Passive_Alternative.png">
	- "when choosing active fund managers I wouldn't rely that heavily on statistical analysis of a fund manager's track. [...] However I am more interested in how a manager makes investment decisions and manages risk, rather than focusing purely on the track record that results from that decision making"

- Smart beta
	- Fully optimised
		- "weights optimised for maximum expected risk-adjusted returns"
		- No ETFs can be found "offering fully optimised weights"
		- Does not perform well
	- Equal weighting
		- "assumes correlations, risk, and risk-adjusted returns are identical"
		- "most common smart beta ETF weighting"
	- Volatility parity
		- "All assets get weighted inversely to their risk"
		- "assumes correlations and risk-adjusted returns are identical"
		- "uses historic risk"
	- Risk parity
		- "All assets get weighted inversely based on their contributino to portfolio risk"
		- "assumes risk-adjusted returns are identical"
		- "uses hitoric risk and correlations"
	- Maximum diversification
		- "Weights optimised for maximum portfolio diversification"
		- "assumes risk-adjusted returns are identical"
		- "uses historic correlationa dna risk"
	- Minimum variance
		- "weights optimised for minimum portfolio risk"
		- "assumes risk-adjusted returns are identical"
		- "uses historic correlations and risk"
	- Handcrafted
		- "assets are grouped and then equally weighted within, and across, groups"
		- "assumes correlations are equal beterrn assets in the same group"
		- "uses historic correlaitons" and historic risk
	- Market cap weighted
		- "weight assets by market capitalisation"
	- "Volatility weighting makes the most sense across asset classes, where volatility can be quite different"
	- "I'm fairly skeptical of more complicated smart beta weighting approaches"
	- Table 63 summarises the results of an academic paper, which cover the returns of PB and momentum risk factors for global equities.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_63_Annual_Geometric_Mean_Of_Excess_Returns_For_Global_Equities_Of_Different_Sizes_And_Exposure_To_Price-Book(PB)_And_Momentu_Risk_Factors.png">
		- "Value only starts working once we look beyond the larges, most efficiently prices, firms"
		- "Momentum - buying stocks that have gone up the most in the last 12 months - is a clear winner for all firm sizes"
		- "a combination of risk factors does better than a single factor"
	- Table 65 shows "the maximum viable management fee premium that should be paid for a given product"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_65_Maximum_Annual_Extra_Management_Fee_You_Should_Pay_For_A_Smart_Beta_Factor_Fund.png">
	- "Generally, however, most smart beta funds are likely to be far too expensive to bother purchasing, relative to boring but cheap market cap weighted alternatives"

- Robo advisors
	- "there are several reasons why I am not keen on robo advisors:"
		- "they aren't cheap"
		- "some of these robots do some pretty stupid things"
		- "I am not convinced these robots are robotic enough"
		- "robo advising is relatively inflexible. You can't usually decide to own individual shares, have different allocations, invest in alternatives"


# Part Four: Smart Rebalancing
- "Chapter sixteen explains the theory and principles you need to understand to do rebalancing properly"
- "In chapter seventeen I show you how to use these principles when running smart portfolios"
- Chapter eighteen discusses "some careful portfolio repair. This is more extreme form of rebalancing"

## <u>Chapter 16: The Theory of Rebalancing</u>

- Why do you need to rebalance?
	- "you need to rebalance for two reasons:"
		1. "when you Target Weights (the portfolio cash weights you'd like to have) are unchanged, but the cash weights implied by the value of the underlying assets - your Current Weights - no longer properly reflect them. I call this portfolio drift"
			- "retail investors should be cautioned against investing money they could conceivably need in the next five years"
			- "If possible you should avoid ETFs which don't manage very much money: anything less than $500 million in the US or 100 million GBP in the lest developed UK market. There are more likely to be de-listed than larger funds"
		2. "if you changed your Target Weights. This is an allocation change"
			- Changes to volatility: if you're planning to use rule of thumb volatility estimates like Rob, "these won't ever change"
			- Changes to risk weights: correlations: In top-down handcrafted method, "large changes [in correlations] mean you should consider changing the grouping, and thus the Target Weights"
			- Changes to risk weights: expected risk-adjusted returns: using predictive models to change risk weights
			- Changes to risk weights: selection of a subset of assets: for example, if you are picking stocks using the yield model and the ranking changes
			- Changes to risk weights: change to index membership: "there is no reason why stocks will underperform just because they are no longer members of an index. So personally I'd avoid changing your selectino of stocks based on index criteria"
			- Changes to risk weights: new, and better, funds appearing: "The constant innovation in the ETFs market is usually a good thing for investors, but it can also casue some decision making headaches"

- Is it worth reweighting and by how much?
	- "having slightly different portfolio weights doesn't make much difference. However if weights get seriously out of line because you're not rebalancing at all then the cumulative effect will be significant"
	- "Tables 71 and 72 show the all-in trading costs for US and US investors; including commissions, bid-ask spread cost, and UK stamp duty"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_71_Cost_Per_Trade_For_US_Equity_Investors_In_Large_Cap_Shares_Or_ETFs.png"><img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_72_Cost_Per_Trade_For_UK_Equity_Investors_In_Large_Cap_Shares_Or_ETFs.png">
	- Figure 37 shows the turnover of sample portfolios using the respective models (on x-axis).
		- "a simple three asset model containing US and UK equities, and US bonds; where I check prices and trade every month"
	- "Naively rebalancing your portfolio on every twist and turn of the market will badly hurt performance"
	- "With a <u>No-Trade-Zone</u> you ignore small reweighting trades; if your Current Weights are only slightly out of line you don't bother adjusting them"
		- If, for example, your No-Trade-Zone shifts up or down because of a change in Target Weight, you trade just enough to put on the edge of the No-Trade-Zone, as opposed to trading to get the Current Weight exactly equal to the Target Weight.
	- With a <u>Minimum-Trade-Size</u> you ignore the small trades that will stack up costs; this is especially relevant for smaller portfolios, but not so much for larger portfolios as even small trades on larger portfolio will probably surpass the Minimum-Trade-Size threshold.
		- "Suppose, for example, that the minimum for a UK investors was 250 GBP. With a 50,000 GBP portfolio this corresponds to 0.5%. […] with a Current Weight of 0.75% and a No-Trade-Zone of 1% to 3% the required trade of 0.25% would be too small"
	- "How wide a No-Trade-Zone? What Minimum-Trade-Size? […] depends on two factors: (a) the number of assets in your portfolio, and (b) the level of costs that you are paying"
		- "the correct Minimum-Trade-Size is invariant to portfolio size, but should be related to minimum brokerage fees"
		- "the optimum levels of No-Trade-Zone will be different depending on the number of assets owned, and the value of your portfolio"
		- "the best No-Trade-Zone width to use is one half of the average portfolio weight, which is also equal to 100% divided by the number of assets you own"
			- "See 'Optimal trading under proportional transaction costs' by Richard Martin, Risk magazine, 2014"
		- "I calculated an optimal Minimum-Trade-Size of 250 GBP in the UK, and $150 in the cheaper US market"
		- "Investors with larger account should use a higher Minimum-Trade-Size […] I'd recommend using the lower of 250 GBP ($150), and 0.1% of your portfolio value"
		- Using the recommended no trade zone and minimum trade size reduce costs drastically.
	-   "If you have the resources to do it then large institutional portfolios should be rebalanced daily. […] Monthly or quarterly rebalancing is also acceptable"

- When to substitute and when not to
	- If, when using the yield model for example, "you've bought a firm that subsequently drops to second place in the yield rankings […] Should you buy the share that now outranks it and cur the old stock out of your portfolio?"
		- "you first need to calculate the cost of doing the substitution"
		- "To start with [while calculating what benefit you get from switching] you should calculate the expected improvement in yield"
			- Using 'The 20 Rule', you can multiply an annual cost by 20 to find its present value. Since you are less certain about the future benefits than you are about the future costs, you use a factor of 5.
			- "an increase in dividends from 4% to 5%, which is a 1% improvement, would improve expected future returns by 1% / 5 =0.2% a year. This has a present value of 0.2% x 20 =4%"
		- "I'd recommend checking yields and doing substitutions relatively infrequently: every six months or annually"
	- If one of the companies you hold get taken over or acquired, and you get paid by shares in some other company in the same sector, you don't need to make any changes (unless you're using the yield model to pick stocks). If, on the other hand, you get paid by shares in a company in a different sector, you need to make changes to the stocks you hold.
		- As a rule of thumb, expecting an improvement of "0.05% per proportion of the portfolio that is reallocated from the overweight back to the newly underweight sector" is a conservative estimate.
		- Compare the cost of reallocation and the benefit of reallocation to decide whether it is worth reallocating or not.
	- "appearance of new and better ETFs:"
		- A "new fund [replacing] part of old fund allocation" is a reweighting and so "you can use the No-Trade-Zone method"
		- "For a complete substitution you need to work out how much improvement in diversification you are likely to get adjusted for uncertainty, measure this using the expected increase in annual geometric mean of returns, and then apply the rule of 20 to see if it covers your initial costs"
		- Table 73 shows "breakeven costs when substituting for more diversified assets"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_73_Breakeven_Costs_When_Substituting_For_More_Diversified_Assets.png">
			- "each row shows a particular type of diversifying substitution trade that you can do"
			- The last "column shows […] the breakeven level - if initial costs [of substitution trade] are higher than this value than it isn't worth doing the substituting trades"
			- MC & HC refer to "Market Capitalisation weighted" and "Hand Crafted weighted", respectively
			- "add up the benefits from different rows if you're doing multiple degrees of diversification simultaneously. Suppose, for example, you own a global equity ETF with market cap weightings, and you plan to buy country ETFs with handcrafted weights"; this replacement will involve rows 6, 8, and 10, adding up the annual benefit to 0.35% and the breakeven cost to 7%.
	-   When switching between funds, management fees and other costs also need to be taken into consideration. Calculate the difference between the fees of the funds you are switching from and the funds you are switching into, and multiply this by 20 to get the total benefit (or loss) from lower (or higher) fees. Adding the benefit (loss) of fees to the diversification benefit gives the true benefit of making the switch. Often times, this will be a negative number because the costs are usually higher for funds that are more diversifying.

- Tax considerations
	- "Many institutions hold their funds inside tax exempt trusts"
	- "take tax into account when considering substitution"
		- Benefit = (up front diversification benefit) + 20 x (cost old fund - cost new fund)
		- Substitute the fund if: benefit > initial trading cost + tax due on switch
	- "Warning: never let the tax tail wag the investment dog. Only consider trades that already make sense because they provide more diversification and/or a futures saving in annual costs. Don't do trade purely for tax purposed that wouldn't otherwise provide any benefit"
	- "I recommend that you should never do any reweighting trades that will generate a capital gains tax liability"



## <u>Chapter 17: Portfolio Maintenance</u>
- "extremely important. Assets that are overweight need to be sold and underweight assets should be topped up"

- Annual review
	- Check for more diversifying collective funds
	- Check for cheaper funds
	- Monitor active funds; "you need to make sure you're still happy with them, Rerun the statistical tests in Chapter Fifteen to see if their performance still justifies their inclusion"
	- Check for changes in stock selection

- Reacting to external events
	- Stock takeovers: "Use the method on page 410 to deicide if you should hang on to the shares you'll end up with, or substitute them for something else"
	- Cash takeovers, bankruptcies, fund delisting: "consider how to replace the missing stock or fund"
	- "In all cases you should consider bringing forward a periodic reweighting of your portfolio"

Periodic portfolio reweighting
- "Larger investors with full-time portfolio managers may also want to rebalance monthly, weekly, or even daily"
	- "For institutional investors, doing many small trades inherently throughout the month is a much better strategy than doing fewer large trafes at the beginning of each month, especially when other funds will be trying to do the same"
- "You should normally trade to the edge of the [No-Trade-]zone. However, if you are doing more than selling then it makes sense to trade closer to the middle of the zone rather than be left with un-inveted cash"
- "any reweighting must be greater than the Minimum-Trade-Size"

Tax implications of portfolio maintenance
- Once you have a list of potential substitution trades (matched sell and buys) and a list of potential reweighting trades (sales and purchases that do not need to be matched); these trades pass the cost-benefit analysis without considering tax; follow the process in this section to do the trades "in the most tax-efficient way"
- Do loss making sales or those without tax implications
	- "Do all selling trades that generate a tax loss first, or which are inside tax-free accounts"
	- "You'd normally sell down to the closest upper edge of the zone but if this generates a tax loss then it's better to trade to the lower edge"
- The best substitution sales that generate a profit, up to your tax free allowance
	- "Do all the trades with the largest net benefit first. [...] only do as many substitution trades as you can without generating net profits above your tax free allowance"
- Remaining substitution sales, considering tax costs
	- "recalculating their [each selling trade's] net benefit but this include the tax charges that would arise on each one"
- If possible, any reweighting sales up to your tax free allowance
	- "You should only do sales for the purposes of reweighting if you have some of your tax free allowance remaining"
- Set aside target cash for withdrawals and fund tax efficient accounts
	- "Before you being buying you should ensure there is enough cash on hand to meet your cash target for any withdrawals that you have to make"
- Buying within tax free accounts
	- "In a tax-free account you will ideally be buying higher volatility, higher yielding assets like equities or riskier bonds"
	- First do transfer trades (selling position in a taxable account to buy the same position in a tax-free account). "Next do any buying which matches substitution sales that you have completed, again largest first. Finally, do purchases of reweighting purposes"
- Buying within taxable accounts
	- "buying low volatility, lower yielding, assets - like bonds"
	- "first on large substitution buy trade where you've already done the matching sale, [...] before moving to reweighting trades"

Rebalancing example
- Author shows how will an investor, using the author's process of portfolio maintenance, go about doing the trades on annual basis.


## <u>Chapter 18: Portfolio Repair</u>



## <u>Appendix C: Technical Stuff</u>
- Formal method for dealing with different group sizes
	- Handcrafting assumes that groups are of similar sizes, or have similar degrees of internal diversification.
	- "Calculate the diversification multiplier within each group"
		- *N* assets within group, correlation matrix *p* and risk weights *w* (summing to 1). [1 / (sqrt(*w'pw*))]
		- "You'll get a higher diversification multiplier for larger groups, those with closer to equal weighting and those with lower correlations"
		- "Multiply each group weight by its diversification multiplier"
		- "Renormalise the weights"

- Creating your own forecasting model
	- "Good [forecasting] variable to choose are those that use risk-adjusted returns. This means that you can pool data across different instruments when testing"
	- "calculate the average [median] absolute value of your forecasting variable [...] Let's call this value [...] the magic number"
	- Limit your "forecasting to a range: between minus two, and plus two, magic numbers"
	- Table 104 shows adjustment factor according to 'multiples of magic number' forecast<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_104_How_Much_Should_You_Adjust_Handcrafted_Weights_Given_A_Forecast.png">
	- "I choose these multipliers (0.6 and 1.48) carefully to reflect the typical lower power of forecasting models. [...] they are derived from examining the difference in portfolios with weights bootstrapped based on returns distributions conditional on relatively high or low forecasts"