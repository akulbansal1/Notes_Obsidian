
[Book Link](obsidian://open?vault=Akul's%20Notebook&file=Library%2Fbooks_Personal%2Fquant%2Ffactor%20investing%2FAntti%20Ilmanen%20-%20Investing%20Amid%20Low%20Expected%20Returns_%20Making%20the%20Most%20When%20Markets%20Offer%20the%20Least-Wiley%20(2022).pdf)
Author(s): Anti Ilmanen
Publish Year: 2022
Tags: #AQR #Factor_Investing #Quant #Equities 

# Part I: Setting the Stage
## <u>Chapter 1: Introduction</u>
- "Inconsistently chasing different long-run successful strategies would likely turn out worse than sticking with one mediocre strategy"

## <u>Chapter 2: The Secular Low Expected Return Challenge</u>
- "The baby-boomer generation benefited from windfall gains over decades which sustained high returns even through the 2010s"
- Historical and expected returns of US bonds and equities![[Screenshot 2023-12-07 at 1.28.58 PM.png]]
- "We cannot know whether the low expected returns will materialise through 'slow pain' or 'fast pain'"
	- Slow pain: "low or non-existent coupons and dividends for decades"
	- Fast pain: "mean reversion to historically more normal (higher) bond yields and (lower) risky-asset multiples, implying speedy capital losses followed by fairer returns thereafter"
- "Horizon matters: The yield-based approach seems most relevant for a ten-year horizon, while for longer horizons, starting yields and valuations matter less, whereas for shorter horizons, momentum and macro forces can be important"

## <u>Chapter 3: Major Investor Types and Their Responses to This Challenge</u>
----Skipped this chapter----

# Part II: Building Blocks of Long-Run Returns
## <u>Chapter 4: Liquid Asset Class Premia</u>
- ### Equity Risk Premium
	- ##### Forward-looking Equity Premia (or Real Yields)
		- "often based on either dividend discount model (dividend plus growth) or the cyclically adjusted earnings yield (CAEY)"
		- DDM: "expected real return on equities is given by $E(R) \approx DY + g + E(\Delta V)$, where $DY=$ dividend yield, $g=$ trend growth in real dividends per share (DPS) or earnings per share (EPS), and $E(\Delta V)=$ expected change in valuation multiples"
		- "CAEY is the inverse of the better-known 'Shiller CAPE' [...] CAEY is more robust to the buyback revolution than the $DY + g$ model"
		- "contrast these yield-based 'objective' return forecasts with survey-based 'subjective' return forecasts. My first book and Greendwood-Shleifer (2014) emphasise that these appear inversely related"![[Screenshot 2023-12-08 at 12.22.22 PM.png]]
		- "DPS and EPS growth rates have not quite matched the GDP-per-capita growth rate, but all have long-run values of 1.5-1.9%"![[Screenshot 2023-12-08 at 12.26.18 PM.png]]
		- "the evidence from the Dimson-Marsh-Staunton (2021) that outside the US the long-run real DPS growth has been near zero"
	- ##### Refine the Expected Return Estimates
		- Sources of research: AQR Portfolio Solutions Group (2017a), Straehl-Ibbotson (2017), and L'Her et al. (2018)
		1. <u>Broader income yield including buybacks</u>
			- "relax the Gordon growth model is to allow the number of shares to vary over time, with a knock-on impact on $k$ and $g_{EPS}$"
			- "naïve payout ratio ($k=D/E$)" is not stable. "Broader income yields that include net buybacks besides dividends have been more stable"
			- Straehl-Ibbotson (2017); expected return equation: $E(R) \approx NTY + g_{TPagg}$ where $NTY=$ net total (payout) yield and $g_{TPagg}=$ growth in real *aggregate* total payouts
		2. <u>Growth estimates differing between DPS and GDP</u>
			- "The long-term *per-share* dividend or earnings growth has historically lagged *aggregate* dividend or earnings growth by up to 2% annually"
			- "part of economic growth accrues to new enterprises rather than existing shareholders in listed firms"
			- "The index divisor is one way to track the net impact of all these effects over time." Index market capitalisation divided by index level.
			- "Dilution effects vary a lot across countries — and tend to be larger in emerging markets." Mee (2017)
			- "Dilution effects also vary over time"
		3. <u>One framework for decomposing growth/returns</u>
			- "L'Her et al. (2018) gives a useful framework and helps us better understand equity market returns" [[Net Buybacks and the Seven Dwarfs]]
			- "split the nominal return into real return and inflation/currency effects", which is further split "into dividend yield (dy), DPS growth (dps), and valuation change (p/d), following the dividend discount model". dps re-expressed as a DPS gap versus the real GDP per capita growth (gdp pc).
			- The authors split total returns into eight components. "this framework could be extended further if we believe that some components are unpredictable (which points to using the long-run average growth or the current level as the best prediction), while other components are subject to structural changes (which points to using a recent average as the best prediction), while yet other are mean-reverting (which points to expecting some normalisation)"
		4. <u>Mean-reversion and structural change arguments</u>
			- "The choice not to include mean reverting valuations in the expected return estimate is a nod to the idea that some structural changes may move valuations sustainably higher"
			- "Academic research has found limited predictability in dividends/earnings/payout growth beyond the long-term average. Thus, I often assume 1.5% real growth rate for EPS, in line with more than a century of evidence in the US."

- ### Bond Risk Premium
	- "The bond risk premium (BRP), or term premium, is the (realised or expected) excess return of a long-term government bond over cash. [...] The simplest forward-looking measure of this premium is yield curve steepness or the term spread [...]. The yield curve reflects both the required BRP and market's interest rate expectations"
	- "The long-run excess return for bonds mainly reflects the positive carry over time (the yield curve tends to be upward-sloping), but is further accentuated during periods of falling yields"
	- "Over the full century 1920-2020, the realised bond risk premium was 1.8% per annum, despite multiple-decades long drawdown"![[Screenshot 2023-12-08 at 4.46.14 PM.png]]
	- ##### Decomposing Forward-looking Treasury Yields
		- "the term spread is a noisy measure of the required term premium"
		- Survey-based bond risk premium (obtained by subtracting expected average T-bill rate over next decade from 10-year Treasury yield) is a cleaner measure.![[Screenshot 2023-12-08 at 5.15.36 PM.png]]
	- ##### Focus on the Drivers of Required Bond Risk Premia
		- BRP turned negative for three reasons: a low inflation risk premium, a negative safe-haven premium, and exceptional demand effects offsetting rising bond supply.
		- "Treasuries became safe-haven assets when the stock-bond correlation turned negative near the turn of the century. Treasuries have since then had a negative equity market beta, which according to the CAPM would justify a lower expected return than cash".
		- "Bond markets for a long time ignored fiscal deficits and debt levels in major economies— witness Japan's high debt ratio and low yields, though the Greek experience shows that markets can change their tune"
	- "Empirically, a steep yield curve has been a good predictor of strong excess bond returns, not a very reliable market timing indicator but as good as it gets"

- ### Credit Premium
	- "excess return of corporate bonds over comparable (similar duration) government bonds"
	- "The two parts of the blend — rates and credit — tend to be negatively correlated, providing inbuilt diversification for corporate bonds"
	- "Despite its positive (0.25) correlation with equities, the credit premium has been a useful contributor to investor portfolios"
	- "Credits are effectively short volatility in equity and bond option markets, and they benefit from leverage aversion"
	- ##### Forward-looking Estimates of Credit Premia
		- "Since mid-1998, we have 'option-adjusted spreads' (OAS) which match corporate bonds to Treasuries with similar durations and adjust for any embedded options in these bonds"
		- "IG corporates earned 75 bp (arithmetic) average excess return, more than half of the average OAS of 132bp"![[Screenshot 2023-12-11 at 1.47.02 PM.png]]"The second column shows that HY corporates earned about 2.8% excess return, compared to 5.2% average credit spread. The 54% spread capture is broadly in line with the long-run default losses"
		- The spread widenings "often end by central bank help, and the role of central banks has increased over time, especially in the response to the Covid-19 crisis"![[Screenshot 2023-12-12 at 11.01.49 AM.png]]"There is a clear link \[between the HY spreads and actual default experiences] but the market spread anticipates rather than reacts to evolving defaults"
	- ##### Has 2010s Changed My Storyline?
		- --ADD LINK TO THESE SECTIONS FROM [[Expected Returns]]
		- #### Fallen angels
			- Strong performance of "BB-rated bonds, which has just been downgraded from IG to HY"
			- "profitable opportunity has persisted. Fallen-angel bonds earned double the excess the return of all-HY bond index between 1997 and 2020 (4.6% versus 2.3%); the edge remained unchanged between 2010 and 2020 (6.5% versus 4.2%)"
		- #### Front-end opportunity
			- "The risk-adjusted return (information ratio) has declined monotonically with maturity"
			- "0.45 IR for one- to three-year corporates and 0.05 for over 25-year corporates between 1989 and 2020. The patterns are similar since 2010 (IRs of 0.74 and 0.12)"
			- "front-end credits are most vulnerable to a sharp increase in default risk"
			- "profitability of these strategies depends on money-market financing spreads. If these are not much narrower than the bond spreads, there is little opportunity to exploit"
	- Active Credit Managers
		- See: [[Active Fixed Income Illusions]] and [[Looking Under the Hood of Active Credit Managers]]
		- "Most institutional FI funds with IG benchmarks take a persistent positive credit beta tilt in their active positioning, which explains much of their historical outperformance". Although, diversification benefits have decreased.
		- "The same pattern holds for credit hedge funds"

- ### Commodity Premium
	- ##### Historical Average Excess Return
		- Multiple studies "point to a long-run commodity premium of 3-5%"
		- "most of the long-run return came from spot return. The negative contribution of a negative roll is consistent in recent decades, reflecting the 'contango' shape in the term structure"![[Screenshot 2023-12-12 at 12.05.19 PM.png]]
	- "With no statistical evidence of time-varying expected return, the best forward-looking estimate for the long-term future is the historical average premium"
	- ##### Gold
		- "The long-run return on gold is understandably modest, near zero real returns (i.e. matching inflation) over centuries and millennia. This still makes gold a compelling store of value for those with a long horizon."
		- "The gold price is inversely related to the real interest rate. This makes sense since the opportunity cost of holding gold is lower when interest rates are low"![[Screenshot 2023-12-12 at 12.40.22 PM.png]]
	- ##### Inflation Hedging Premium Angle
		- Different commodities "hedge against different types of inflation"
			- Oil: energy-driven cost-push inflation
			- Industrial metals: demand-pull inflation
			- Precious metals: when central bank credibility is questioned
		- "Most assets that dominate investor portfolios — bonds, stocks, and real estate — tend to get hurt by inflation surprises"![[Screenshot 2023-12-12 at 1.04.49 PM.png]]

## <u>Chapter 5: Illiquidity Premia</u>
- "Measuring illiquidity is hard but measuring illiquidity premia is harder because these tend to be blended with other risk premia"
- ### Illiquid Alternative/Private Assets
	- three largest illiquid alternative asset classes:
		- Real estate (residential and commercial, farmland, infrastructure, etc.)
		- Private equity (buyouts, venture capital, etc.)
		- Private credit (plus other illiquid debt)
	- ##### Does Housing Beat Equities in the Long Run?
		- "for equities the contributions of real income and real capital gains are roughly comparable, but for housing real capital gains are only a small fraction of real return"
	- ##### Real Estate Returns in Recent Decades
		- "Francis-Ibbotson (2020) report more recent evidence 1991-2018: real compound return for housing of 3.8%, commercial real estate of 1.5%, and farmland of 4.4%. In all cases, the net rental income yield exceeded the total return. Average net rental yield over this period were near 5% for housing but even 7% for commercial real estate and farmland."
		- "In general, I argue that unlike equities, real estate may earn all (and more than all) of it long-run return from income (and nothing sustainable from real capital gains). Empirically, the long-run real price appreciation or real income growth have been modest, and there are opposite estimates on their sign after quality adjustment. The real quality-adjusted growth rates may well be negative and offset the abundant net rental yield"
	- ##### Private Equity (Buyout) Returns
		- US buyouts funds "outperformed the S&P500 index by 2-3% annually over 30+ years, and this is after 5-6% annual all-in fees, and for all buyout funds – not just the top quartile"
		- "after David Swensen's Yale Model popularised private assets among institutional investors. The industry has been hard-pressed to deliver any net outperformance over pubic equities in fund vintages since 2006"![[Screenshot 2023-12-12 at 2.30.30 PM.png]]
		- "Empirical analysis of PE fund holdings reveals plenty of market beta (though partly hidden by smooth returns), plenty of leverage (though less than in the olden days), factor tilts toward small-cap and value stocks, as well as persistent sector tilts that could be replicated in public markets"
	- "Asness (2019b) even raises the possibility that the sign gets flipped and PE funds may offer and illiquidity *discount* – that is, lower expected returns than public equity in exchange for their lack of mark-to-market volatility"
	- "while many investors consider illiquidity premia to be among the more reliable long-run return sources, supportive empirical evidence is surprisingly limited"

- ### Liquidity Provision Strategies
	- "Only a small subset of market participants with either an intermediary position (crossing end-investor flows), or a niche specialist role, or a superior technology with low trading costs are likely to make net profits".
	- Short-term reversal and Pastor-Stambaugh factors in stock selection
	- Arbitrage strategies such as merger arbitrage (buy target and sell acquirer); convertible arbitrage (buy convertible bonds at issuance and hedge); and fixed-income arbitrage (off-the-run and on-the-run bond arbitrage).
	- Even regularities: index rebalancing, government bond auctions, prices pressures with 'fallen angels' in credits, or futures rolls (GSCI monthly roll to new contract)
	- Long/short strategies favouring the back contracts in many futures.
	- "Calendar or seasonal strategies come in many forms and frequencies \[but] trading costs often make them unimplementable for most investors"
		- "Same-month seasonality refers to the tendency of observing high returns in the same calendar month each year"
		- "Overnight returns predict positively the next overnight returns but negatively the next intraday returns"

## <u>Chapter 6: Style Premia</u>
- "Style premia are publicly known dynamic long/short strategies with expected positive rewards"
- "Long-only portfolios that blend asset class premia and style tilts are often called 'smart beta' strategies"
- "four major styles — value, momentum, carry, defensive — perform empirically well in several asset classes"
	- "broadening to 6-10 factors is possible. One path involves splitting each factor into two parts: value and reversal, momentum and trend, carry and volatility selling, (statistical) low risk and (fundamental) quality"

- ### Value and Other Contrarian Strategies
	- "In a typical academic implementation of the value style, we sort a set of stocks by some measure of fundamental value to price"
	- "Composite value measures may be more robust to evolving markets and accounting practices"
	- "Within-industry comparisons subtract the industry mean or median value ratio from each stock before ranking stocks, resulting in industry-neutral positions" #idea_factor_investing 
		- "Israel-Jiang-Ross (2017) and Kessler-Scherer-Harries (2020) explore the many design decisions and show that the indicator choice and sector neutrality matter most empirically"
	- "Mikhail Samonov (2020) has compiled into one cumulative return series two centuries of research on the performance of simple US stock selection value strategies"![[Screenshot 2023-12-13 at 6.28.42 PM.png]]
	- "The multi-metric composite (which combines book, earnings, forward earnings, cash flow, and sales multiples) outpaces the book/price ratio, and the industry-neutral design outpaced raw"![[Screenshot 2023-12-13 at 6.33.41 PM.png]]
	- "Some argue \[that because intangibles has become more important than in the past, it] makes the book/price ratio obsolete. Yet, even studies that argue for the intangibles-adjusted book/price ratio report only mildly better long-run performance and somewhat lower recent losses"
	- Across countries: aggregate measure of B/P or CAEY for the entire market can be used
	  Bonds: real bond yields
	  Currencies: purchasing power parity
	  Commodities: long-run (5 years) mean reversion![[Screenshot 2023-12-13 at 6.45.40 PM.png]]
	- "Stock selection value strategies performed very poorly between 2018 and 2020, raising investor doubts about these strategies' long-run viability"
		- "My best reading of the situation is that there may have been some fundamental underpinning to the value-growth relative performance, but during 2018-2020 markets took things too far"
		- "the ex-ante opportunity has become record-high – or at least competing for that honour with the 1999 dot-com era"![[Screenshot 2023-12-13 at 6.59.31 PM.png]]

- ### Momentum and Other Extrapolative Strategies
	- "value and momentum work well at different horizons"
	- "momentum is close to market neutral, whereas trend following can be highly market directional at any point in time, though in the long run it average near zero market beta"
	- "when we use a magnifying glass, what now looks like some dips in momentum returns turn out to be 'momentum crashes'"![[Screenshot 2023-12-14 at 11.00.39 AM.png]]
	- "Trend-following has even more compelling-looking history. \[...] Last decade performance has been relatively flat, as commodity trend losses offset fixed income trend gains"![[Screenshot 2023-12-14 at 11.04.31 AM.png]]
	- "Lazy thinking about flow momentum may ignore the fact that net flows add up to zero \[...]. Thus, flow momentum can only be useful if we can identify a subset of investors worth following"
	- "Stock selection momentum had relatively good 2010s, while trend following disappointed after its excellent 2008 performance"

- ### Carry and Other Income Strategies
	- "typically by buying high-yielding assets against selling low-yielding assets"
	- "An asset's yield \[...] is a good proxy for carry, but a broader definition of carry includes *an asset's return in unchanged capital market conditions*"
		- Currencies: "yield income of short-term deposits"
		- Bonds and commodity futures: "unchanged term structure means that an asset may also earn a predictable rolldown return over time as it ages"
		- Equities: dividend yield; ideally includes other payout yields related to net buybacks, cash acquisitions, and so on
		- Index option selling: "time decay of the option cost as well as the rolldown along the implied volatility surface"
		- [[Carry|Koijen et al. (2018)]] for more.
	- "Naïve yield-seeking could push investors to a foreign market suffering from hyperinflation, or to the debt of a company at the brink of default"
	- "Empirically, currency carry is significantly exposed to equity market risk as well as to volatility risks in both equity and currency markets"
	- "Carry positions tend to be persistent. In extreme, BBB credits always have higher yields than AAA credits (and more than expected default losses imply), and selling index puts always earns positive income (and most of the time the implied volatility exceeds the recent realised volatility)"
	- "carry reflects an asset's return in an unchanged capital market environment. \[...] So, carry reflects an unknown blend of market expectations of a changing environment as well as required risk premia"
	- Comparison of "the cumulative ex-ante carry and ex-post return for yield-seeking strategies in each asset class"![[Screenshot 2023-12-18 at 11.50.40 AM.png]]"for commodities, cumulative carry clearly exceeds cumulative return, suggesting that much of the carry advantage reflected market expectations of carry-offsetting capital market developments"
	- "Volatility selling is arguably the ultimate yield-seeking strategy, and one whose reward is clearly compensation for risk"
	- "Few carry strategies had an inspired performance" between 2008 GFC and 2020 Covid crash.

- ### Defensive and Other Low-Risk/Quality Strategies
	- "within most asset classes, 'boring' assets have earned better risk-adjusted returns than their speculative peers"
	- "The defensive concept may be extended beyond statistical measures (low beta, low volatility) to include more fundamental measures of risk – or of high *quality*"
	- "high-risk stocks offer embedded leverage and lottery characteristics"
	- "BAB has offered a higher SR and better out-of-sample performance than other core factors like Value and Momentum. QMJ strategy has also performed well \[...] looks even better when the alpha series credits it for its negative market beta"![[Screenshot 2023-12-18 at 12.17.26 PM.png]]
	- "Defensive equity strategies have performed extremely well in the 2010s but also over much longer histories"

## <u>Chapter 7: Alpha and Its Cousins</u>
- "alpha is often blended inside a broader portfolio that contains simple market exposures (betas)"
- "If you are an investor with limited allocations to ARP \[Alternative Risk Premia], they are 'alpha to you' and may improve your portfolio as much as any alpha"
- "Raw hedge fund returns have persisted in the 2010s, but the CAPM alpha has been modest. Performance may, however, be better for fund not reporting to hedge fund databases"![[Screenshot 2023-12-18 at 2.13.33 PM.png]]

- ### Classification of Portfolio Return Sources
	- "The boundary between ARP and alpha is fuzzy. \[...] If we count ARP as part of a given multi-factor model, then by definition their reward cannot be multi-factor alpha"
	- "ARP is thus alpha-like in being near market-neutral but beta-like in being widely known"
	- "The key trade-off is between the *overfitting* risk in proprietary alpha and the *overcrowding* and obsolescence risks in ARP"
- "the world's most famous value investor actually earned more of his long-run returns from the market exposure and from quality and low-beta titles than from a value tilt. \[...] Quantum fund's performance over two apparently golden decades could be more than fully explained by a handful of systematic factors mainly reflecting his self-professed macro trend chasing style"![[Screenshot 2023-12-18 at 2.33.16 PM.png]]

## <u>Chapter 8: Theories Explaining Long-run Return Sources</u>
- --skipped 3 sections--
- ### Who Is on the Other Side? — and Related Crowding Concerns
	- "non-market factors are zero sum in their returns. If someone profits, someone else must lose. However, all exchanges need to be zero sum in *utility*; both sides can benefit for example in risk transfer trades or trading off expected return for liquidity"
	- ![[Screenshot 2023-12-18 at 5.55.46 PM.png]]