
[Paper Link](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3330134)
Author(s): Rattray, Granger, Harvey and Hemert
Publish Year: 2019
Tags: #WifeyAlpha #ManAHL #Asset_Allocation 

## <u>Abstract</u>
- "the negative convexity induced by rebalancing can be substantially mitigated […by] an allocation to a trend-following strategy"
- "*strategic rebalancing*, which uses smart rebalancing timing based on trend-following signals"

## <u>Introduction</u>
- "rebalancing means selling (relative) winners, and if winners continue to outperform, that detracts from performance"
- Figure 2. "The maximum drawdown of the monthly-rebalanced portfolio is 1.2 times (or 5 percentage points) worse than that of the buy-and-hold portfolio" because rebalancing keeps buying into stocks by selling bonds.![[Screenshot 2023-05-16 at 2.00.29 PM.png]]
	- "Granger et al. (2014) formally show that rebalancing is similar to starting with a buy-and-hold portfolio and adding a short straddle (selling both a call and a put option) on the relative value of the portfolio assets"
- [[Strategic Rebalancing#1. Comparing Rebalanced and Buy-and-Hold Returns]]: "the return difference between a rebalanced and a buy-and-hold portfolio is concave in the relative stock-bond performance"
- [[Strategic Rebalancing#2. Impact of a Simple Trend Strategy Allocation]]: "a modest allocation to a trend strategy can effectively counter the negative convexity induced by rebalancing"
- [[Strategic Rebalancing#3. Strategic Rebalancing]]: "explore different heuristics as well as trend-based strategic rebalancing"
- [[Strategic Rebalancing#4. Strategic Rebalancing Versus a Direct Allocation to Trend]]: compare the results of sections 2 & 3.

## 1. Comparing Rebalanced and Buy-and-Hold Returns
- "monthly rebalancing to a constant asset mic ('Rebal') and buy-and-hold ('Hold')"
- R$^R$$^E$$^B$$^A$$^L$ – R$^H$$^O$$^L$$^D$ = -w$^S$w$^B$k$_1$k$_2$
	Where,
	w$^S$ and w$^B$ are allocations to bonds and stocks, respectively.
	k$_t$ is the stock-bond return difference in the period *t*. (R$^S$$_t$ – R$^B$$_t$)
	"if the relative performance is trending (k$_1$, k$_2$ are either both positive or both negative), then the rebalanced portfolio underperforms"
- "Figure 3 we plot the Rebal-Hold return difference when both have a 60-40 stock-bond mix at the start of the period (vertical axis) versus the stock-bond relative return (horizontal axis)"![[Screenshot 2023-05-16 at 2.13.59 PM.png]]
	- "looks a lot like the payoff of a short straddle on the relative performance"

## 2. Impact of a Simple Trend Strategy Allocation
- "momentum (trend) signal for asset k, as the return over the past N months, divided by a volatility estimate which we set equal to the standard deviation of the past 12 monthly returns and the square-root of N to make it approximately unit standard deviation"
	- "For the asset returns, we will use the stock and bond data used before, but in excess of 1-month Treasury bill returns, which is a proxy of the return on an unfunded futures contract"
- For the trend strategy, position sizes are calculated to target a volatility level of 15-20%.
- Features of the trend strategy:
	1. "floor and cap on the signal value of -1 and +1 respectively"
	2. "for annualized security volatility […], floor of 10% in case of stocks and the stock-bond spread asset, and 5% in case of bonds"
- "In Figure 4, we plot the 1-year return of various trend strategies (vertical axis) versus the 1-year relative stock-bond return (horizontal axis) […]. We use 3-month trend signals" #idea_tactical_asset_allocation ![[Screenshot 2023-05-16 at 2.15.57 PM.png]]
	- "a trend strategy with a stock weighting looks like a natural complement to a rebalancing strategy"
	- "The payoff of these strategies [ones in Panels E & F] mimics not so much a long straddle (put plus call) anymore, but rather that of just a put (in case of negative trend) and call (in case of positive trend)"
- "we next combine a monthly-rebalanced portfolio (90%) and the various trend strategies (10%)"
	- "the benefit of the trend allocation is not so much a higher Sharpe ratio, but rather a more benign risk profile with more shallow drawdowns"

## 3. Strategic Rebalancing
- "we now study if one can get similar benefits by smartly timing and sizing rebalancing trades, which we call 'strategic rebalancing'".
- "Threshold-based rules seem slightly less potent, where we consider if the fraction of stocks is outside of the 60±2% and 60±4% range (but we considered other ranges also, which did not materially improve performance)".
	- "In all cases, the correlation to the monthly, fully-rebalanced strategy is near 1 (not reported in the table) and the average return is barely impacted"
- "In Table 3, we show results when rebalancing is delayed if the stock-bond spread trend is negative, positive, or continues to be in the same direction (i.e., to rebalance only when the trend direction now is in the opposite direction of a month ago, which likely corresponds to a not so strong or inconsistent trending environment)"![[Screenshot 2023-05-16 at 2.16.49 PM.png]]

## 4. Strategic Rebalancing Versus a Direct Allocation to Trend
- "In Figure 8, we show the impact of adding the two different types of trend exposures considered in this paper to a monthly-rebalanced 60-40 stock bond portfolio, as a function of the 1-year stock-minus-bond return"![[Screenshot 2023-05-16 at 2.17.55 PM.png]]

## 5. Concluding Remarks
- "We show that the negative convexity induced by rebalancing is effectively countered with a trend exposure, which exhibits convexity and can be either implemented as a direct allocation to a trend strategy or with a strategic trend-based rebalancing rule"
- Other ways to mitigate downside risk:
	- "a more diversified portfolio that includes more asset classes and has an international exposure"
	- "An allocation to a broader trend strategy that benefits from trends in other macro assets at times of equity market distress […] see" [[Trend Following Equity and Bond Crisis Alpha]]
	- [[The Impact of Volatility Targeting]] "study volatility targeting and show that it can help manage the risk of a 60-40 stock-bond portfolio"
- Even though the stock-bond spread trend trading (only if negative) acts like a put option on the 60-40 stock-bond portfolio, it could be the case that stocks underperform bonds during a crises. In such a scenario, the futures trend overlay might not deliver the 'put' protection.
	- If a stock-bond spread futures trend strategy overlay were to be used, the one depicted in Figure 4 Panel D must be used.