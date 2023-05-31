
[Book Link](<file://Users/akul/Desktop/Work Work Work/books/Asset Allocation/Sebastien Page - Beyond Diversification-McGraw-Hill Education (2020).pdf>)
Author: Sebastian Page
Publish Year: 2019
Tags: #WifeyAlpha #Global_Macro #Asset_Allocation

# Part One: Return Forecasting
- "because we can't estimate expected returns with any reasonable level of confidence (grabage in), the output of portfolio optimization models will always be wrong (garbage out)".
- "it's hard to call yourself an investor if you don't think you have insights about expected returns".

## <u>Chapter 1: Equilibirum</u>
- "For multi-asset investors, a basic way to estimate expected returns is to use the capital asset pricing model (CAPM) […] because it link expected returns to an objective measure of risk and current interest rate levels".
- CAPM makes numerous "convenient but unrealistic assumptions"; Markowitz "focuses on one of the key, yet rarely discussed, building blocks of the model: the (clearly unrealistic) assumption that investors can borrow all they want at the risk-free rate".
- "When taken literally, the [CAPM] model dictates that all investors should buy a combination of cash and the market portfolio, mixed together in proportions consistent with their risk aversion"
- Fama and French "show that the average month-to-month returns of portfolios of individual stocks ranked on the basis of their CAPM expected returns do not line up with the model's predictions"
- "Taleb's concern is that modern portfolio theory and the CAPM were derived under Gaussian assumptions"
- "under the CAPM, risk isn't defined as the asset's volatility or exposure to loss. It's defined as its contribution to a diversified portfolio's volatility"
	-   Beta = (asset volatility / market volatility) x correlation
	-   Expected return = risk-free rate + beta x (market expected return - risk free rate)
- "this example [a positive relationship between beta and the relative returns of stocks and bonds] suggests the CAPM may work better across asset classes than for individual stocks"
- "The risk-free rate is the anchor, and when it's low, it holds down expected returns across markets"
- Simple valuation models:
	- Jeremy Siegel: earnings yield (inverse of P/E) + market-implied or 'breakeven' inflation rate ("measured by the difference between the yield of a nominal bond and an inflation-linked bond")
	- Robert Shiller: "uses a P/E ratio that normalizes earnings over the last 10 years and adjusts for inflation (the cyclically adjusted price-earnings ratio, or CAPE)"
	- "my recommendation is to tilt the forecast toward Siegel's estimate. A split of 80% Siegel, 20% Shiller seems to be reasonable to me […]; the 80-20 blend is clearly not 'robust' from a quantitative perspective"
	- Ex-ante equity reis premium (using the 80-20 blend) is 6.2% for US stocks.
	
- What About bonds?
	- "To estimate the total market risk premium, we also need to forecast bond returns"
	- "yield to maturity is a reasonably good predictor of future returns"
	- "contrary to conventional wisdom, […] rising rates are good for bonds: higher rates mean higher reinvestment rates and, ultimately, higher expected returns". Read [[Bond Investing in a Rising Rate Environment]] for more on this.
		- "if rates rise gradually, or f the increase occurs later in the investment horizon, then it takes longer for the reinvestment effect to heal the price shock(s)"
		- "impact of rising rates on bonds is both bad (in the short run) and good (in the long run)"
		- "returns have converged to the initial yield to maturity at a time horizon that matched duration"
	- "the yield to maturity on the Barclays Global Aggregate is a meager 1.9%, (as of April 3, 2018)"
	- "stocks appear expensive after a nine-year bull market. But as we stare down the barrel of a 30-year bull market in bonds, bonds appear even more expensive"
	- "Yields are especially low outside the United States, due to unprecedented monetary easing in Europe, Japan, China, and the United Kingdom"
	
- The Market Portfolio: It's Not What it Used to Be
	- "Asset weights within the market portfolio should be based on their relative market capitalization"
	- "From an asset allocator's perspective, clearly we should use the multi-asset market portfolio, not just equities. Unfortunately, it's difficult to estimate the relative weights of asset classes within multi-asset market portfolio, due to a lack of reliable data"
		- [[The Global Multi-Asset Market Portfolio, 1959-2012]] "reveals that these weights [relative weights of asset classes] have changed over time. In 2000, the market portfolio was close to 60% stocks, 40% bonds. […] Nowadays, these weights have flipped to about 40% stocks, 60% bonds"
	- Expected returns on a market portfolio = 3.6% = (40% x 6.2%) + (60% x 1.9%)
		- Current 3-months T-bill = 1.7%; "we get a market risk premium of 1.9%"
	- "It's not clear to me whether cash rates are the appropriate risk-free rate for long-term investors. Over a relatively long investment horizon, the cash return depends on rate change, due to reinvestment effects (i.e., the three-month yield resets many times before the end of the horizon)"
		- "From that perspective, cash is riskier than a zero coupon bond that matches the investment horizon"
	- Next section focuses "on a US investor who wants to forecast nominal returns"
	
- Betas and Depressingly Low Expected Returns
	- Table 1.1 shows "betas for 21 asset classes, based on monthly data from February 2002 to January 2017 [and] each asset class's CAPM expected return": <img src= "file:////Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_1.1_CAPM_Expected_Returns.png">
	- "the numbers [in Table 1.1] aren't entirely consistent with the return expectations I put in the model"
		- "The main reason is that I use a valuation approach to determine the market risk premium while the CAPM is valuation-agnostic"
		- "To CAPM purists, [valuations don't matter]. Their betas are all that matter. From that perspective, CAPM forecasts are most relevant for long investment horizons, say, over 10 years"
	- "the betas are just statistical estimates preduced by a risk model. They're not very forward-looking"
	- "Most of them [factors models, extensions of CAPM] focus on the cross section of equity returns; they are more appropriate for equity risk models and stock-picking strategies than for cross-asset expected returns"
	
- The CAPM *Is* Useful
	- CAPM "has influenced how we think about indexing, how we evaluate managers, and how we sepearate alpha from beta"

## <u>Chapter 2: Valuation</u>
- "Shiller uses a ratio that's adjusted for cycles and inflation (the CAPE), while Siegel uses a more current P/E ratio. Also, Shiller doesn't simply invert the ratio. Instead, he models the relationship between the initial CAPE and subsequent returns, based on a regression model"
- "Rob Arnott, Vitali Kalesnik, and Jim Masturzo (2018) point out that:  
	Since 1996, the U.S. CAPE ratio has been above its long-term average (16.6) 96% of the time, and above 24, roughly one standard deviation above its historical norm, more than two-thirds of the time"
- "we must keep in mind that the CAPE is not perfect, and there are decades in history during which it failed as a predictor of forward returns"
- "If the economy continues to grow at a sluggish 2-3% rate due to long-term, persistent trends such as high levels of global debt […], demographics […], and technology disruption […], how can earnings continue to grow in the 10-15% range, especially when profit margins are already high"
- "Relative to bond yields, stocks are much cheaper than they appear on the basis of the CAPE alone"
- "CAPE gives us a back-of-the-envelope signal that we shouldn't ignore, and it's on the pessimistic side"
- The Simplest Vaulation-Based Model: Building Blocks
	- "The building block model decomposes equity returns into three components: income, growth, and valuation change"  
	    Price change = growth + valuation change  
	    Realized return = dividend yield + growth + valuation change  
	    
	    growth = change in book value  
	    valuation change = change in price-to-book ratio
	    
	- "we can forecast each of these components [income, growth and valuation change]"
	- "companies tend to adjust their payout ratio to smooth dividend yields over time. […] For the S&P 500, based on data going back to the 1970s, the correlation between one year's dividend yield and the following year's is 92%"
	- "sustainable growth rate, defined as the return on equity (ROE) multiplied by the retention rate (the percentage of earnings that's not paid out as dividends). My estimate of the year-over-year predictability/autocorrelation in the S&P 500's sustainable growth rate is 48%, based on data going back to the 1990s"
	- "valuation changes aren't correlated from one year to the next. […] over the long run, there's a powerful mean-reversion effect in valuation levels. Hence, a fair assumption is that valuation changes average out to zero over time"
		- #idea_value_investing"two valuation change models: one that assumed mean reversion and another that used proprietary data on institutional investor flows"  
		    "if a country received significant inflows from institutional investors, its valuation level should increase more than that of other countries, especially those with significant outflows. We made the implicit assumption that institutional investors flows were persistent"  
		    "I assumed that flows and year-over-year valuation changes were mostly driven by sentiment […]. I measured a beta between flows and subsequent valuation changes across countries. Then I applied this beta to recent flows"
	- "the building block approach can be applied to longer horizons. […] Table 2.1 shows long-run building block expected returns for the same equity asset classes used in Chapter 1 for the CAPM":<img src= "file:////Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_2.1_Building_Block_Model_Expected_Returns.png">
	- Buybacks and share issuance can significantly impact the income part of the model. It also impacts the growth estimate. "if we expect a dilution effect [net increase in number of shares], we must adjust earnings or dividend growth estimates down (more shareholder mouths to feed), while if we expect positive buybacks, we should adjust them up (fewer shareholder mouths to feed)"
	- "In the absence of a strong view on margins, it's common practice to assume that total market earnings will grow at the same rate as GDP"
- Earnings Forecasts and the Role of Fundamental Analysis
	- "to forecast earnings growth, we need fundamental analysis. Yet clients and novice quants often look for formulaic approaches, because there's comfort in replicable methodologies"
	- "My view is that the ROE-based sustainable growth rate, calculated from public, precooked, index-level data, is as good as any other formulaic approach"
	- #idea_value_investing When forecasting valuation change (valuation change = realized return - income - growth), out of P/E, P/CF, or P/B, "the results were clear: P/CF won. Its average correlation with subsequent valuation changes was over 10% stronger than for the second-best ratio (P/B), and it won across seven out of nine asset classes (exceptions were small caps and non-US growth stocks)"
	- "In the end, to harness fundamental analysis sometimes seems more ad hoc than historical analysis, but it is the key to building block to forecast return"
- Back to Bonds
	- "Harvey and Stonacek conclude that 'current yields are most highly correlated with future returns for higher-quality and hedged bond indexed. As these indexes follow stricter maturity, duration, and quality rules, they present a more stable risk/return profile than unhedged and lower quality indexes'"
	- "over a finite horizon of one year, a good starting point to proxy return:  
	    Return = initial yield - (initial duration x change in yield)  
	    We earn the carry (yield) plus or minus the change in price (-duration x change in yield)"
	- #idea_bond_investing And expansion of the simple decomposition above into a model "that increases the in-sample fit from 94% to 96%":
		Return = (average yield) + (roll yield) + (interest rate duration * change in yield) + (credit spread duration * change in credit spread)
		where,
		average yield = (yield in 5 years per survey - current yield) / 2  
		Roll down = duration * current slope (9 - 10-year yield)  
		Change in yield = (yield in 5 years per survey - current yield) / 5  
		Change in spread = (spread in 5 years per survey - current spread) / 5

## <u>Chapter 3: Shorter-Term Valuation Signals</u>
- Forecasting in chapters 1 and 2 were "focused on relatively long-term return forecasts, or 'capital market assumption'. These types of forecasts are useful for strategic asset allocation"
- How the Tactical Process Works in Practice
	- "At its core, our TAA approach [at T. Row Price] is discretionary–it's not systematic, rules-based, or 'quant'. Investment judgement is key"
	- "We implement tactical changes almost every month, but rarely across all asset classes. […] The crux of our approach is to take advantage of relative valuation opportunities. We look for extreme value dislocations, and we like to lean against the wind–we overweight asset classes when they're cheap"
	- "we trade everything on a relative basis, and we almost always discuss asset class pairs. Our discussions often start with stocks versus bonds, or, broadly speaking, whether we want to position the portfolios 'risk-on' […] or 'risk-off'"
		- "Then we look for relative value opportunities at a more granular level"
	- #idea_macro_trading #idea_tactical_asset_allocation"While valuation is the main driver for our decisions, we account for
		- Macro Factors (growth, inflation, central bank policy, geopolitical factors, etc.);
		- Index-Level Fundamentals (sales, earnings, margins, leverage, etc.); and
		- Technicals (sentiment, positions, flows, momentum, etc.)"
	- "Non-valuation factors are used to confirm our valuation-based assessment"
	- "in practice, many (perhaps most) multi-asset investors don't forecast shorter-term returns explicitly. Rather, they evaluate a variety of factors, and they scale positions in a risk-aware framework"
	- "There's also evidence that valuation works particularly well when momentum agrees"
- Which Valuation Signal Works Best for Tactical Asset Allocation?
	- Table 3.1 shows the equity asset classes used to test which valuation signal (from P/E, P/B and P/CF) works best on different time horizons.<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_3.1_List_of_Equity_Asset_Classes_and_Relative_Bets.png">
	- #idea_value_investing "to forecast absolute returns, P/CF worked better than P/B and P/E. At the one-year horizon, P/CF had an average correlation of over -43% with forward returns, compared with -26% for P/B and -22% for P/E"
	- "to forecast relative returns, for example, large cap versus small cap stocks, the results surprised me. P/E worked better than P/CF at the six-month, one-year, and two-year horizons and worked about the same as P/CF at the three-year horizon"
		- "Adjusted positive earnings may be more comparable across asset classes, even though they're less predictive from a time series perspective, for a given asset class"
		- "time series forecasts may be completely off for two asset classes, but if the bias is systemwide–if it affects both the asset classes the same way–then the comparison between the two can still be meaningful"
	- "Good cross-sectional forecasts can be poor time series forecasts, and vice versa"
- Relative Valuation Between Stocks and Bonds and Across Bond Markets
	- #idea_tactical_asset_allocation "For US stocks versus bonds, […] a 35% correlation between the ratio of forward equity earnings yield to bond yield and the subsequent 12-month relative returns"
		- "It's a decent signal, but it's far from perfect. It's mostly useful from a big-picture perspective"
		- "in early stages of Fed rate hikes, risk assets can rise alongside risk-free rates […]. If growth data stabilize/improve in the near term, […] rates and risk assets can rise together. The challenge is when policy becomes tighter […] and economic fundamentals begin to roll over"
		- "yield ratio for stocks versus bonds should be used with caution, and in the context of other factors"
	- #idea_value_investing [[King of the Mountain Shiller PE and Macroeconomic Conditions]] "show that the Shiller P/E performs better as a short-term timing signal if we adjust it for inflation and real rates"
	- #idea_bond_investing "yield ratios across fixed income asset classes work quite well as stand-alone signals"
		- "the yield ratio between emerging markets bonds and US investment-grade bonds has a 70% correlation with 12-month forward relative returns"
		- "for US high yield versus US investment-grade bonds, the correlation is 61%"
		- "for US high yield versus emerging market bonds, the correlation id 50%"
	- #idea_bond_investing [[Factor Investing and Asset Allocation A Business Cycle Perspective]] "use a definition of carry that includes roll down, based on the difference between spot and 12-month forward swap rates"
		- "The strategy goes long the top three carry markets and short the bottom three. It generates a Sharpe ratio of 0.73 between 2002 and 2015"

## <u>Chapter 4: Shorter-Term Macro Signals</u>
- "I wouldn't make the statement that investors can make a lot of money if they mechanically follow simple valuation-based strategies, but [...] systematic strategies that combine valuation with momentum signals have worked well in back-tests and in practice"
- "short-term return forecasts and tactical asset allocation decisions must account for macro factors"
- #idea_macro_dashboard [[Macroeconomic Effects of Falling Long-term Inflation Expectations?]] shows "how to build dashboard to integrate macro factors into a broader, discretionary TAA process"
- Academic Research on Macro Factors
	- "Fama and French (1989) […] show that business conditions, as approximated by dividend yield, rates, and credit spreads, forecast broad market returns"
	- Prior studies on the influence of Macroeconomic Factors on Asset Returns
		- [[The Inconsistency of Small-Firm and Value Stock Premiums]] show that the size and value effects depend largely on monetary conditions.
		- [[Economic Factors, monetary policy and expected returns on stocks and bonds]] emphasize the importance of monetary policy in explaining stocks and bond returns.
		- [[Consumption, Aggreggate Wealth and Expected Stock Returns]] shows how consumption patterns forecast excess equtiy market returns.
		- [[Global Tactical Asset Allocation]] show that movements in the yield curve are predictive of stock returns.
		- [[The Link Between Macro-economic Factors and Style Returns]] find a link between macro variables and the size and style premiums.
		- [[The Stock Market's Reaction to Unemployment News Why Bad News is Usually Good for Stocks]] find that the effect of unemployment on stocks depends on the economic cycles.
		- [[Macro Factors in Bond Risk Premia]] shows that 'real' and 'inflation' factors have predictive powers for bond returns.
		- [[Regime Shifts Implications for Dynamic Strategies]] shows that GDP and inflation regime-switching models can be used for TAA.
		- [[Macro-Based Parametric Asset Allocation]] shows that macro factors can be used to dynamically optimize investors' stock versus bonds allocations.
		- Page (2013) shows a significant link between GDP and inflation surprises and bond, stock, and commodity returns.
		- [[Factor Investing and Asset Allocation A Business Cycle Perspective]] relate the business cycle to returns, risks, and correlations for a broad list of risk factors.
		- [[The Relationship Between Stocks and Oil Prices]] shows that oil and stocks have a common exposure to aggregate demand.
		- [[Return Predictability and Market-Timing A One-Month Model]] build a stock market timing model with 20 factors, including oil, inflation, rates, and spreads.
- Challenges with Practical Applications
	-   "many practitioners still struggle to use these [macro] factors for tactical investment decisions at the 6- to 18-month horizons"
		- "the question of what macro expectations are priced in market  is often left unanswered"
		- "the sheer amount of macro data makes it difficult to separate noise from signal and anticipate which variables will drive returns"
	- "in our paper, we suggested that the same could be said of any macro factor–depending on the prevailing regime, the impact on asset returns will differ"
		- "To map macro factors to expected asset returns, we proposed using dashboards"
	- "Unlike historical regression analyses based on static data samples, our dashboards are meant to be dynamically updated such that investors can rely on them as a research tool"
		- "We focus on the relative returns between pairs of asset classes"
		- "we incorporate, current conditions, as reflected in macro factors' levels"
	- #idea_macro_dashboard"For each pair trade, we partition historical asset returns to match a given scenario and current conditions"
		- "In total, we map 18 pair trades to 10 key macro factors, for a total of 180 'cells,' produced for each of 4 scenarios (full sample, as well as stable, rising, and declining macro factors)–a grand total of 720 cells"
		- "our dashboards answer the following question: if an investor has a one-year view on the direction of the macro factor, what is the corresponding forward one-year return?"
	- "in general, statistical significance between macro variables and asset returns is low, especially if we don’t expect a significant move in the macro factors"
- Caveats
	- "With our macro dashboards, we don't claim to identify causation […]. Rather, we merely identify correlations that appear meaningful and leave it to the investor to assess causation"
		- #idea_tactical_asset_allocation "**Investors shouldn't build systematic tactical asset allocation strategies based solely on these macro data**. Instead, macro factors are often used to confirm relative valuation signals"
	- "we don’t model expectations directly. In theory we should run our scenarios against the expectations that are priced into the market"
	- "we've selected investable asset class pairs. […] But in theory, it would be more elegant to isolate market factors and scale positions based on volatility"

## <u>Chapter 5: Momentum</u>
- "Macro factors give us a lot more context to interpret valuation signals, i.e., what's priced into markets"
- "momentum is a useful building block for return forecasting in an asset allocation context, especially when combined with valuation and other signals"
- "The key to momentum, however, is not to ignore valuation. [...] buy a cheap asset when its momentum turns positive rather than on the way down, or sell an expensive asset with negative momentum"
- A Momentum Horse Race
	- "Did the momentum signals beat the valuation signals [used in the analysis in chapter 3]? No, not even close."
		- "momentum is a short-term signal than valuation", showing the best performance for 6-month and 1-year lookback windows"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_5.1_List_of_Asset_Classes_and_Relative_Bets.png">
	- "Average correlation for the best-performing lookback (six months) was only 7% for absolute bets (market timing) and 6% for relative bets. As the lookback expanded, the results got progressively worse"
		- "In contrast, we saw in Chapter 3 that valuation signals generated correlations in the 20-40% range"
- Overreaction, or Valuation by Another Name?
	- "In my momentum study, I found the most predictability [...] for market timing with three-year lookbacks, applied to a three-year horizon [i.e.,] asset classes with *high* three-year returns tend to generate *low* forward three-year returns"
	- "Aside from the observation that a six-month lookback with a one-month forecast horizon worked best, I didn't find much consistency in my results across relative bets"
- Bond Momentum: Weak Evidence at Best
	-   "In general, at the asset class level, valuation works better for bonds than stocks"
	- "From a time series/market timing perspective, results on one-month momentum were similar to that for equities: consistently positive across market, but weak, with predictive correlation–averaged across markets–in the 2-8% range"
	- "Only high yield and global high yield showed mean reversion"
	- "for relative fixed income bets, momentum did not work at all"
	- Key takeaways on momentum:
		- "works well when combined with valuation in equity markets"
		- "in fixed income markets, if the objective is to invest across markets with a 6-18-month horizon, investors should focus on mean reversion"
- Real-Life Example of Mean Reversion and Valuation and How We Put It All Together
	- "we use mean reversion in yields and spreads to guide several of our investment decisions"
	- Pages 112 to 118 of the book show notes from the author's Asset Allocation Committee meeting. It shows how to put all the pieces of the puzzle together to come up with an investment thesis.
		- "Net bank tightening is bullish on stocks vs high yield bonds […] Historically, net bank tightening has had a 44% correlation with the forward relative returns on stocks vs. high yield"
		- "The 7-year real yield differential between Treasuries and bonds is bullish on USD […] The signals has a 48% correlation with forward USD appreciation"
		- "Historically, relative [EBIDTA] margins revert to a mean [in this case the author is talking about relative margins of EAFE value and growth]. This signals has a 52% correlation with forward returns for EAFE value relative to EAFE growth"

## <u>Chapter 6: Thoughts on Return Forecasting</u>
- "One of the great misconceptions on portfolio theory is that it preludes the use of judgement and experience"
- "In his recent book *Principles*, legendary investor Ray Dalio (2017) explains the evolution of hig approach to marry quantitative analysis with judgement: Rather than blindly following computer's recommendation, I would have the computer work in parallel with my own analysis and then compare the two. When the computer's decision was different from mine, I would examine why. Most of the time, it was because I had overlooked something. In those cases, the computer taught me. But sometime I would think about some new criteria my system would've missed, so I would teach the computer. We helped each other"
- #quote_quant"My view is that those who hope for a consistently effective return forecasting algorithm may suffer from [...] physics envy"
- #idea_strategic_asset_allocation Rules of thumb for long-term return forecasting:
	1. "When in doubt, assume that return will be proportional to risk (beta)"
	2. "For stocks, check that your estimate is not too facr from the inverse of the P/E ration plus inflation"
	3. "For earnings, don't rely on optimistic, short-run, or noise sell-side estimates"
	4. "break down returns into building blocks: income and long-term growth"
	5. "Valuation changes are harder to model. When in doubt, assume valuations revert to a mean"
	6. "For bonds, make sure your estimate is not too far from the asset class's yield to maturity"
	7. "Beware of large credit and currency risk exposures"
	8. "If possible, ask experienced investors for their forecasts of earnings growth, rates, spreads, etc."
	9. "Use these forecasts as the key inputs to transparent building blocks models that can be debated"
- #idea_tactical_asset_allocation Rules of thumb for tactical forecasting:
	1. "For short-term equity forecasts, focus on valuation changes more than on income and growth"
	2. "Use valuations ratios (P/E, P/CF, P/B) to evaluate whether and asset class is cheap or expensive"
	3. "Pay close attention to P/CF for relative bets and to P/E for absolute (market timing) decisions"
	4. "Use 6- and 12-month momentum as secondary factors, to better time valuation-based trades"
	5. "With macro factors, account for current conditions and how macro factors affect asset prices"
	6. "Don’t blindly assume that rising rates are bad for risk asset such as stocks and credit bonds"
	7. "When fundamentals (such as margins) reach extreme levels, assume they might revert to a mean"
	8. "For bonds, use yield-to-maturity ratios to forecast one-year relative returns between asset classes"
	9. "Don't expect return momentum to work in bond markets, expect weakly in the very short run"
- General rules of thumb:
	1. "*Use data and models to estimate factor relationships, asses signal quality, and remove biases*"
	2. "*Use judgement to account for current condition across monetary, fiscal, and geopolitical factors*"

# Part Two: Risk Forecasting
- "Risk is easier to forecast than return"
- "Historical [risk] models perform better than ARCH-types models in at least half the studies reviewed by Poon and Granger"
- "the ARCH models more explicitly for the short-term persistence (predictability) in volatility, sometimes referred to as volatility clustering"
- "Aside from a slight advantage for volatility estimates derived from options prices, Poon and Granger find that across 93 academic studies, there's no clear winner of the great risk forecasting horse race"
	- "And option-implied volatilities aren't a silver bullet either"
	- "Marra's results reveal that the option-implied approach performed the worst out of the eight models he backtested"
- "*short-term volatility, from one month to one year ahead, is quite predictable, even with simple models*"

## <u>Chapter 7: Risk-Based Investing</u>
- "managed volatility and covered call writing are two of the few systematic investment approaches that have been shown to perform well across a variety of empirical studies [...] it turns out that they're negatively correlated. When combined, they create a powerful toolset for portfolio enhancements"
- "a constant (fixed weight) asset allocation does not deliver a constant risk exposure"
- Managed Volatility Backtests
	- "The managed volatility strategy is designed for [...] the short-term predictability in volatility"
	- Table 7.1 summarized a sample of 11 studies on managed volatility.
		- #idea_tactical_asset_allocation "any asset allocation process can be improved if we incorporate volatility forecasts"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_7.1_Prior_Studies_on_Manged_Volatility.png">
	- "managed volatility has been shown in practice to reduce exposure to loss and smooth the ride for investors, at a very low–or even positive–cost in terms of returns"
	- "When we mix high-volatility and low-volatility distributions and randomly draw from either, we get a fat-tailed distribution. By adjusting risk exposures, managed volatility essentially 'normalizes' portfolio returns to one single distribution and thereby significantly reduces tail risk"
	- "think of time diversification as similar to cross-asset diversification. […] the realized variance of the portfolio is basically the sum of the point-in-time variances. To get the highest Sharpe ratio through time, we should allocate equal risk to each period"
- Covered Call Writing (Volatility Risk Premium)
	- "gives exposure to the volatility risk premium, one of the 'alternative betas'"
	- #idea_vol_trading Table 7.2 shows "results from several empirical studies on the performance of covered call writing"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_7.2_Prior_Studies_on_the_Volatility_Risk_Premium.png">
	- Selling volatility earns a premium for two reasons: "the demand for hedging and the compensation for tail risk"
- A Powerful Combo of Risk-Based Strategies
	- "Investors can use managed volatility to reduce the tail-risk exposure in covered call writing"
	- "Based on data from January 1996 to December 2015, the risk-return ratio of the S&P is 0.41"
		- Covered call writing strategy (with gross exposure capped at 125%) "increase from 0.41 to 0.49"
		- Adding managed volatility, "risk-return ratio jumps from 0.49 to 0.69, [...] downside risk is reduced substantially"
	- "Combining managed volatility and covered call writing can be extremely effective, because these two strategies are negatively correlated and can easily be added to conventional portfolios"
- Takeaways and Q&A
	- "It is generally better to sell options when implied volaitlity is overpriced relative to expected realized volatility. For example, when investors are nervious over a high-volatility event or a market drawdown, options may be overpriced. The determinant is not necessarily high or low volatility, but rather the effect investor behavior is having on option prices relative to the real economic volatility in the underlying investment"
		- "To get the timing right is not easy, of course, but active management may add value over a simple approach that keeps a constant exposure to the volaitlity risk premium"

## <u>Chapter 8: Longer-Term Risk Forecasting</u>
- "calculate the correlatio between past and future volatility, skewness, and kurtosis for each of these 33 returns series [10 equity assets, 10 fixed income assets, and 12 relative bets (Tables 3.1 and 5.1), and stocks versus bonds]. I also asked him to vary the forecast horizons in the same way and repeat the entire experiment for daily, wekkly, and monthly data"
- Results from our Risk Forecasting Horse Race
	- "The conclusions differed depending on whether we looked at short-to-medium time horizons (one months to three years) or the longer horizson of five years"
	- "persistence in volatility was highest at short horizons"
		- "Across all combinations of data windows, forecast horizons, and data frequencies, *month-to-month volatility based on daily data showed the most persistence*"
		- "The average correlation between this month's daily volatility and the next month's was +68%"
	- "*shorter* estimation windows also produced better forecasts at *longer* horizons"
		- "investors should pay significant attention to recent volatility"
	- "We found that for short- and medium-term horizons, estimation windows based on daily data worked better than oens based on weekly data, which in trun worked better than ones based on monthly data"
		- "on average, daily data almost always produced the best forecasts, even for forward monthly volatility"
	- #idea_vol_trading"*persistence works best at short horizons, shorter estimatino windows work better even for longer horizons, and higher-frequency data work better than lower-frequency data*"
- Mean Reversion at Longer Horizons
	- Mean reversion in volatility "started to appear when we used a three-year estimation window to forecast three-year volatility. It became strongest with the five-year estimation window for five-year forward realized volatility, across daily, weekly, and monthly frequencies"
	- "in finance, all else being equal (particularly for the same time period), statistical estimates based on longer horizons–t-statistics, regression betas, or R-squares/correlations–are less reliable than shorter-horizon estimates and are more likely to show extreme values"
	- "But the negative correlation in the five-year estimation–five-year realized 'cells' in our results matrix–were remarkably strong"
		- In a longer dataset (1926-2018, as compared to 1993-2018), "we found mild *persistence* in long-run volatility"
		- "my view is that the 1993-2018 sample may be more representative of the future"
- What About Higher Moments?
	- "Out results were disappointing for 'higher moments' (skewness and kurtosis). We didn't find much predictability"
	- "Yet for asset allocation decisions, we can't ignore higher moments. As we will see in Chapter 11, scenario analysis is useful tool to address this problem. At the portfolio level, we can improve our estimation of higher moments if we account for how correlations can change in down markets"

## <u>Chapter 9: Correlations</u>
- "when we forecast risk at the portfolio level, we must estimate correlation, either directly or indirectly"
- "Most of these studies [showing an increase in correlation during crashes] were published before the 2008 global financial crisis. Yet the failure of diversification during the crisis, when left-tail correlation jumped significantly, seemed to surprise investors"
- "Full-sample (i.e., average) correlations are misleading. […] To enhance risk management beyond naïve diversification, investors should reoptimize portfolios with a focus on downside risk, consider dynamic strategies, and, […] evaluate the value of downside protection as an alternative to asset class diversification"
- The Myth of Diversification
	- "not only did correlations increase on the downside, but they also significantly decreased on the upside"
	- "despite the wide body of published research, many investors still do not fully appreciate the impact of correlation asymmetries on portfolio efficiency–in particular, on exposure to loss"
		- "During left-tail events, diversified portfolios may have greater exposure to loss than more concentrated portfolios"
	- "we can identify months during which both assets moved (up or down) by at least a given percentage, which is called 'double conditioning'. […] we conditioned on a single asset. We wanted to measure differences in tail correlations based on which of the two markets sold off (or rallied)"
	- "**We found that bonds diversify stocks when stocks sell off, but stocks do not diversify bonds when bonds sell off**"
	- Conditioning bias solution:
		- "simulated how correlations change when we move toward the left and right tails based on random data. For each asset pair, we simulated two normal distributions with the full-sample correlations, means, and volatilities as those we observed empirically"
		- Comparing "the actual subsample correlations with their simulated normal counterparts" reveals departures from normality.
	- "Another possible bias arises because extreme correlations rely on few data points":
		- "we augmented subsamples with data from the rest of the distribution"
		- "used an exponentially weighted approach. The closest the additional points were to the cutoff of interest, the more weight they received in our estimation. These weights decreased exponentially as we moved further from the threshold"
		- "data-augmentation methodology generated estimates similar to those calculated conventionally, in terms of magnitude and directionality. But our estimates tended be less noisy, and they were less sensitive to outliers"
- The Failure of Diversification Across Risk Assets
	- Took an example by looking at the correlation (and the changes thereof) between US stocks and non-US stocks.
		- "conditioned correlations by percentile, based on the returns of US stocks. […] correlations changed from the worst sell-off in US stocks (1st percentile) to their strongest rallies (99th percentile). […] In the normal [distribution] case, we would expect perfect symmetry between upside and downside correlations. Conditional correlations would gradually decrease as we moved toward the tails"
		- When US stocks were in their 99th percentile, correlation: -17%;  
		    1st percentile, correlation: +87%  
		    "This asymmetry revealed that international diversification works only on the upside"
	- Table 9.1 "show a comparison of left-tail and right-tail correlations for key asset classes, based on available data histories as of June 2017"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Table_9.1_Extreme_Correlations.png">
		- "Garcia-Feijoo, Jensen, and Johnson (2012) show that when US equity returns are in their bottom 5%, non-US equities, commodities, and REITs also experience significantly negative returns–beyond what would be expected from full-sample correlations"
		- "Hartmann, Straetmans, and de Vries (2010) show that currencies co-crash more often than would be predicted by a bivariate normal distribution"
		- "Hartmann, Straetmans, and de Vries (2004) estimate that stock markets in G5 countries are two times more likely to co-crash than bond markets"
		- "[[Systemic Risk and Bank Business Models]] extend pairwise analysis to joint tail dependence across multiple markets and reach similar conclusions"
	- "Merton [1964] defined a corporate bonds as a combination of:"
		- A risk-free bond; and
		- "A short put position on the company's assets"
	- "Diversification fails across styles, sizes, geographies, and alternative assets"
	- "asymmetry for the stock-MBS (mortgage-backed securities) correlation is notable. In 'The Myth of Diversification paper (2009), we had used precrisis data, and […] MBS was one of the few asset classes that seemed to decouple from stocks in down markets. During the fourth quarter of 2008, […] MBS clearly joined the ranks of risk-on assets"
	- "seven hedge fund styles: equity market neutral, merger arbitrage, event driven, macro, equity hedge, relative value convertible, and relative value. Unfortunately, we found that all these types of hedge funds, including the market-neutral funds, exhibited significantly higher left-tail than right-tail correlations"
		- Average right-tail correlation: -7%; left-tail correlation: +63%
		- #quote_general_gyaan "most hedge fund strategies are short volatility"
		- "Billio, Getmansky, and Pelizzon (2012) […] show that the average jump in correlation for hedge fund strategies in financial crises was +33%"
	- "Private assets' reported returns suffer from the smoothing bias. […] private assets' diversification is almost entirely illusory"
		- "In addition […] liquidity risk contributed to the failure of private asset diversification"
	- #idea_factor_investing"Our results did indeed reveal that risk factors (equity value, cross-asset value, equity momentum, currency value, and currency momentum) appear to be more immune to the failure of diversification than are asset classes"  
	    See for example: [[Portfolio of Risk Premia A New Approach to Diversification]]; Page Taborsky (2011): and [[The Death of Diversification Has Been Greatly Exaggerated]].
		- "In a sense, the argument in favor of risk factor diversification is more about the removal of the long-only constraint and the expansion of the investment universe than anything else"  
		    See for example: [[Factor-Based Allocation vs. Asset-Class-Based Allocation]]; and [[Facts about Factors]].
		-   "currency carry trade [buy high interest rate currencies and short low interest rate currencies] has an indirect equity beta exposure that remains dominant until risk assets sell off"
	-   "[[International Asset Allocation With Regime Shifts]] directly link the concept of regime shifts to rising left-tail correlations"
		-   Causes for regime shifts: macroeconomic fundamentals; and investor sentiment  
		    See for example: Kim (1993); and [[Dynamics of Persistence in International Inflation Rates]] and Hamilton (1989); [[An Empirical Analysis of the Demand for Multiple Peril Crop Insurance]];
		     Luginbuhl and de Vos (1999); and Lam (2004) on GDP/GNP growth.
- Is the Stock-Bond Correlation the Only True Source of Diversification?
	- "the stock-bond correlation is one of the most important inputs to asset allocation"
	- "Treasuries decouple from stocks in bad times and become positively correlation with stocks in good times"
	- [[Stock-Bond Correlation]] "demonstrates that when inflation and interest rates drive market volatility, the stock-bond correlation often turns positive"
		- "The 'taper tantrum' of 2013, when Ben Bernanke first mentioned the idea of tapering the Fed's stimulus, provides a good example"
	- "we estimated the stock-bond correlation as a function of percentiles in *bond* returns instead of stock returns"
		- "The correlation profile was not as desirable as when we conditioned on stock returns"
		- "during crises, diversification across risk assets almost always fail, and even the stock-bond correlation may fail in certain market environments"
		- "conditional correlations represents only one way to measure diversification. Conditional betas, for example, take into account changes relative volatility as well as correlations"
	- "Investors can prepare for the failure of diversification without the need to time markets"
- Recommendations for Asset Allocation and Tail-Risk-Aware Analytics
	- "I recommend that investors avoid the use of full-sample correlations in portfolio construction–or, at least, that they stress-test their correlation assumptions"
	- "Investors should use such tail-aware tools [e.g., full-scale optimization, discussed in Chapter 14] as part of 'pre-trade' decisions".
	- "In such situations [shocks to interest rates or inflation, turning stock-bond correlation positive], strategies that use leverage to increase the contribution to the risk of bonds–risk parity, for example–may experience unexpected drawdowns"
	- "investors should look beyond diversification to manage portfolio risk":
		- Tail-risk hedging
		- Risk-factors that embed short positions or defensive momentum strategies
		- Dynamic risk-based strategies all provide better left-tail protection than traditional diversification
	- Managed volatility "will scale down risk assets when volatility is high, it may offset left-tail correlation spikes"
	- Recommendations for Tail-Risk-Aware Analytics:
		1.  "Don’t blindly rely on full-sample correlations for portfolio construction.
		2. Give scenario analysis a meaningful role in asset allocation decisions.
		3. Estimate the end investors' risk tolerance accordingly against returns.
		4. Use portfolio optimization tools that account directly for left-tail risks.
		5. Beware of 'diversification of free lunches' in privately held asset classes.
		6. Evaluate interest rate risk and its impact on stock-bond diversification.
		7. Seek asset classes that provide upside 'unification'/anti-diversification"
	- #idea_tactical_asset_allocation Active Mangement Strategies:
		1. "Hedges with put options and proxies.
		2. Strategies that embed short positions.
		3. Momentum-based factors or strategies.
		4. Actively managed absolute return alts.
		5. Managed volatility overlays/strategies.
		6. Strategic or tactical cash allocations"

## <u>Chapter 10: Correlations Forecasts and Tail Risks</u>
- "the left-tail events that drive correlation shifts in the markets are basically impossible to predict"
- "we looked at realized (trailing) correlations at one point in time and calculated the degree at which they matched up with future correlations. In other words, we tested whether correlations were persistent"
- "Erb, Harvey, and Viskanta (1994) build a forecasting model for country-level equity market correlations, based on data from January 1970 to December 1993"
	- "use a multivariate model. In addition to lagged correlations, they add lagged country returns, lagged dividend yields, and lagged term spreads as predictors of future correlations. These additional variable improved the forecasts significantly–an important result, as it suggests a link between fundamentals (valuation and macro variables) and future correlations"
- "*net of the effect of the fundamental variables* [on a stand-alone basis], correlations appear to mean-revert"
- Our analysis of Correlation Predictability
	- Used the 19 asset class pairs. Six relative bets from Table 3.1, six relative bets from Table 5.1, stock-bond correlation; and "six pairs from the longer Ken French data series, which cover factors and asset classes within US equities only:
		1. Market versus small-minus-big [Mcap];
		2. Market versus high-minus-low (value factor);
		3. Market versus big;
		4. Market versus small;
		5. Small versus big; and
		6. Value versus growth"
	- "we mixed frequencies between lookback and forecast data"
		- "The month-to-month correlation in daily volatility was +68% (across asset classes and bets), compared with +4% for skewness, +2% for kurtosis, and +40% for correlations"
		- "correlation were more persistent at short horizons than at long horizons, with some mean reversion observed at the three-year and five-year horizons (when we used three-year and five-year lookback windows)"
		- "shorter windows generally worked better, the 'sweet spot' for correlation predictability was between six months and one year"
		- "holding everything else constant (for the same lookback and forecast windows), the higher the data frequency, the better the correlation forecast, especially at time horizons of one year or less. This rule of thumb was consistent with our results for volatilities"
		- #idea_risk_management "*The rule of thumb for asset allocators is that correlations show some useful predictability when we use daily data from the last 6 to 12 months*"

- Exposure to Loss Is What Matters
	- "Conditional value at risk (CVaR) [...] is a popular risk measure. [...] is a function of volatility, skewness, kurtosis, and correlation"
	- #idea_risk_management Is "CVaR itself predictable?"
		- "found similar, albeit slightly weaker, patterns for CVaR as for volatility: persistence in the short run, mean reversion in the long run […], and better forecasting performance for higher-frequency and more recent data"

- Takeaways on the Importance of Basic Parameter Choices for Risk Forecasting
	- "Basic rules of thumb, such as the common practice of matching estimate and forecast parameters, do not perform best empirically"

## <u>Chapter 11: Fat Tails</u>
- "Nassim Taleb (2010) argues that we can't predict higher moments"
- "We don't know when extreme losses will occur, but we should build resilience to them"
- "Our horse race showed we can't forecast the *timing* of these outliers (as evidenced by the lack of persistence or strong mean reversion in skewness and kurtosis)"
- "fat tails matter, and volatility is a poor proxy for exposure to loss"
- "*everybody involved in investment management must at some point determine their (or their end investor's) risk tolerance and align the portfolio's risk accordingly*"
	- "If we ignore fat tails, we underestimate exposure to loss and take too much risk relative to the investor's risk tolerance"
- #quote_general_gyaan "we should not use Sharpe ratios to compare strategies that sell optionality (like most alternative investments) with traditional asset classes, investment strategies, and products. But I continue to hear such comparisons everywhere"
- "Asset allocators can use the concept of risk regimes to model, and perhaps forecast, latent risks"
	- "the fat tails belong to another probability distribution altogether–the risk-off regime, which is characterized by investor panics, liquidity events, and flights to safety"  
	    "if we blend to normal distributions, (risk-on versus risk-off or 'quiet' versus 'turbulent') we can get a highly nonnormal distributions"
	- "our industry has underestimated the power of this regime-based framework for risk forecasting'
	- Changing the probabilities of which normal distributions the daily returns are coming from can help in forecasting returns.
- #idea_regime_shifts[[Regime Shifts Implications for Dynamic Strategies]] "explain how to use so-called Markov models to define regimes"
	- "we show that because they ignore regime persistence, thresholds give more false signals than advanced techniques"
	- "The advanced techniques we used in our paper account for the fact that asset returns (as well as fundamental and economic data) tend to cluster"
	- "regardless of how we define the regimes, the most interesting aspect of the approach is that we can specify regime probabilities to build a risk forecast. Historically, regimes are highly persistent month to month"
- "we can parse historical data into regimes and then apply forward-looking probabilities to reweigh them"
	- "These probabilities should depend on current conditions", i.e., moetary policy, valuations, equity earnings surprise, etc.
	- "Quants should use judgement and experience to determine forward-looking probabilities, and fundamental investors should be ready to rely on the data to define the regimes"

- Scenario Analysis
	- "there is a need for our industry to move scenario analysis from the back office (after-the-fact reporting) to the front office, where investment decisions are made"
	- The problem with a simple peak-to-trough start-date-to-end-date scenario analysis is that asset classes keep changing over time, e.g., sector weights in the S&P 500 index keep changing over time.
		- "These changes in sector weights also make time series analyses of valuation ratios on the S&P 500 less reliable"
		- "in practice, such adjustments [adjusting for sector weight changes when estimating valuation] can be helpful. […] For scenario analysis, valuations matter as well. High P/Es often indicate fragile markets with elevated probabilities of tail events"
		- "In fixed income markets, changes in factor exposures within asset classes can affect the fundamental nature of how they react to macroeconomic shock"  
		    Barclays Aggregate Index has increased its exposure to Treasuries relative to corporate bonds, due to greater issuance of government debt. "the duration of the […] index has increased, from an average of 4.5 years in 2005 to 6 years in 2019 […] which means that the index has become much more sensitive to interest rate shocks"  
		    "another way in which passive exposures to US bonds have become riskier: a degradation in credit quality [..] the weight of high-quality bonds (rated AAA or AA) has decreased from 21 to 2% [from 2008 to February 2020]. […] Therefore, a risk-off scenario based on historical returns for the index would likely underestimate exposure to loss"
		- "US small caps have deteriorated in quality; value stocks have become more cyclical; etc."
	- "For factor-based scenario analysis, we can replace asset class weights with risk factor exposures, and we can replace asset class returns with risk factor returns"
	- "for scenario analysis at T. Rowe Price, our risk systems produce security-level factor mappings. These mapping are then aggregated at the asset class and portfolio levels"
	- "Our model decomposes returns into contributions from security selection, tactical asset allocation, and strategic asset allocation. It further decomposes returns into asset class-, factor-, and security-level contribution"
	-   "drawbacks to this factor-based approach":
		1. "it's often difficult to map portfolios to risk factors"
		2. "every crisis is different. […] From December 31, 1999 to December 31, 2002, the S&P 500 crashed, losing 38%. Over the same period, the Barclays Commercial Mortgage Backed Securities (CMBS) Index was up 44%. […] In three months, from September 19 to November 20, 2008, the S&P 500 crashed, losing 40%. Over the same period, the Barclays CBMS Index lost 37%"
	- "robust scenario analysis requires forward-looking scenarios as well. Most quants are uncomfortable with 'made-up' scenarios, but the risk factor approach provides a useful compromise between art/fundamental judgement and science"
	- "specify shocks to one or two factors and then propagate these shocks to the other factors. Essentially, we use the betas (sensitivities) between factors. […] This approach also allows shocks to nonfinancial factors, such as GDP and inflation, as long as we can estimate the betas between the nonfinancial and the financial factors"  
	    "If we don't propagate shocks, we assume, very mistakenly, that other factors would remain stable under stress"
	- "When we shock a risk factor and infer movements in other related risk factors, we should use stress betas"
	- [[Allocating Assets in Climates of Extreme Risk]] explains how "the sensitivities (covariances/betas) […] can be adjusted based on the nature of the stress tests"
	- "The propagation framework allows the investor to express views on a limited number of factors"
	- "To the extent an investor lacks insights about possible future shocks, the framework will be of little help. […] It depends heavily on the investor's views, which as the true value-added. The framework itself is simply there to impose consistency and scale the approach to multiple portfolios and factors"

- Offense Versus Defense
	- "I've rarely ever seen scenario analysis influence portfolio construction in a meaningful way"
	- "In a tactical framework, we can specify various macro scenarios in quadrants across growth and inflation. Then we can may which trades would do well in which state of the world"
	- "understand market expectations and how deviations from market expectations can impact asset returns"

- The Most Common Risk Forecasting Error
	- "[Mark Kritzman and Don Rich (2002)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=316584) explain this important distinction between within-horizon and end-of-horizon risk measurement in 'The Measurement of Risk'"
		- "Within-horizon probability of loss […] is the probability that the asset or portfolio dips below a threshold at some time"
		- "continuous value at risk is an improved version of value at risk (minimum loss at a given confidence level) that measures exposures to loss throughout the investment horizon"
	- "The difference between within-horizon and end-of-horizon probabilities increases as the time horizon gets longer"
	- "time diversification does not work. The idea that over time, risk goes down as good years diversify bad years only holds if we use end-of-horizon estimates"

- Rules of thumb for risk forecasting
	1. "When in doubt, use short data windows, even for medium-term forecasts.
	2. Use higher-frequency data, including for low-frequency volatility forecasts.
	3. If available, use information derived from options prices (implied volatility).
	4. Account for the fact that volatility is more persistent over shorter horizons.
	5. Do not worry too much about the need to use highly sophisticated models.
	6. Expect some mean reversion for long-term forecasts (over five or more years).
	7. Recognize that fat tails matter and should be included in your risk forecasts.
	8. Separate your dataset into regimes, and assign probabilities to each regime.
	9. Build historical and forward-looking scenarios to stress-test exposure to loss.
	10. Model exposure to loss both at the end of and within the investment horizon.

# Part Three: Portfolio Construction
- "multi-asset investors must choose the building blocks": allocate across asset classes, or allocate across risk factors?

## <u>Chapter 12: Asset Classes Versus Risk Factors</u>
- "fixed income portfolio managers have long decomposed portfolios into risk factors […]. Almost all fixed income risk models are factor-based"
- "Over time, many fixed income investors have expanded their factor-based approach to multi-asset portfolio management"
- "why not diversify the portfolio directly across these [risk] factors?"
	- "used equity factors such as market beta, size, value, and momentum. For fixed income, I used interest rate duration, two slope factors, and a few flavors of credit spreads. I also added real estate and commodity as alternate factors"
	- #quote_risk_management"found that average correlation across risk factors was much lower than the average correlation across asset classes. Also, during periods of market stress, the average correlation across risk factors did not jump by nearly as much as the correlation across classes"
		- This lower correlation is majorly because risk factors allow short positions, while asset classes are long-only benchmarks.
- "asset classes' exposure to risk factors change over time"

- No Need to Build a New Optimizer–We Can Use Risk Factors Behind the Scenes
	- #idea_tactical_asset_allocation "if we can measure each asset class's risk factor exposures, as well as the non-factor-based ("idiosyncratic") risk, there is a simple mathematical transformation that allows us to estimate asset class volatilities, correlations, and tail risks from their current factor exposures"
		- "multiply current factor exposures with historical factor returns to rebuild an asset class return series"
		- "Then we can use our traditional asset class-based portfolio optimization tools on asset class risk estimates that have derived from risk factors"
	- The downside with this approach: "sometimes risk factor exposures can change rapidly [for example:] […] Hedge fund managers may shift their equity market beta up and down tactically as part of their mandate"
		- "The solution is to measure how exposures change over time"

- Smart Betas, Alt Betas, Style Premiums, Risk Premiums, and All the Hype
	- "Factors should deliver a positive return if they represent compensation for undiversifiable risk (risk premiums) or a persistent anomaly caused by investor behavior. In that context, not all factors qualify as risk premium"
	- "push and pull between momentum and value investors should lead to some equilibrium"
		- Because momentum investors can be aggressive in the short term, momentum risk premium "will persist at a relatively short time horizon–typically one month, as I showed in Chapter 5"
		- "At longer horizons, prices tend to revert to fundamentals"
	- #idea_factor_investing [[Betting Against Beta]] shows "that a strategy that levers low-risk assets and shorts high-risk assets […] 'delivers significant positive risk-adjusted returns' across market"
		- "they uncover similar risk premiums across a wide range of assets, including country bond indexes, commodities, and currencies"
	- "another risk premium with sound theoretical foundations and persistence over time: the volatility risk premium. […] can (and should) also hedge directional market risk"

- The Diversification Argument, Once Again
	- #idea_factor_investing [[Value and Momentum Everywhere]] "shows the power of diversification across risk premiums. When the authors combine value and momentum strategies across market [...], they obtain a stratospheric, hardly-ever-seen-in-practice Sharpe (return-to-risk) ratio of 1.59"

- Backtest Buyer Beware
	- [[Will Your Factor Deliver]] "find that size and quality [...] show 'weak robustness', while momentum, illiquidity, and low beta are more robust"
	- "after publication, risk premium performance deteriorates by 58%. They attribute 26% of this deterioration to data minins and the remaining 32% to crowding, or 'publication-infromed trading'"
	- #idea_risk_management "*Risk factors won't replace asset classes for portfolio construction. Investors should use the factor approach in risk models and roll up factor-based risk forecasts to the asset class level*"
		- "If someone shows you a back-tes, don't buy all the hype. Ask for a live track record and the theoretical foundations behind the risk premiums, as well as an analysis of tail risks and tail correlations"

## <u>Chapter 13: Stocks Versus Bonds</u>
- "the perennial, most fundamental debate in asset allocation is on stocks versus bonds"
	- "*It is, without a doubt, the most important portfolio construction decision an investor makes*"
- "There's a role for both stocks and bonds in balanced portfolios. Investors must calibrate their stock-bond allocation based on their risk tolerance"

- Some background on Personal Finance
	- "human capital—the present value of an individual's future salary income—is an 'asset' just like stocks and bonds and should be considered as part of the life cycle asset allocation decision"
	- "While bonds will always have their place in balanced portfolios, ultimately […] individuals are more likely to reach their retirement goals with stocks"
	- Low-rate environment in US and many other countries have pushed investors to risky assets, thirsting for yield so they can save enough for retirement. "In contrast, in countries with higher rates and a lower equity risk premium, portfolio construction focuses on bonds"

Human Capital: Does It Look Like a Bond or a Stock?
	- "human capital is more stock-like than bond-like. When stocks do well, salaries tend to increase due to earnings growth"
	- #quote_general_gyaan "We found that, net of inflation, the average-wage index was more correlated to stocks (+53%) than to bonds (+30%), based on data from 1952 to 2014"
	- "We believe the answer [to 'which is the best long-term retirement portfolio'] is a balanced portfolio with a healthy allocation to stocks"

- Target-Date Funds as the Default Allocation
	- "it was unreasonable to ask individuals to solve their life cycle portfolio construction problem on their own"
	- Individuals "don’t construct their portfolios; instead their employers (who are their plans' sponsors) must decide to allocate the funds"
	- "Figure 13.1 charts our stocks versus bonds mix for our flagship, higher-stocks glide path, as a function of how many years the individual is from retirement"<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Figure_13.1_Retirement_glide_path.png">
		- "Underfunded investors need high returns. When consultants say, 'Match the liability with bonds, and then invest the rest in risk asset," this advice can only apply to overfunded investors"

## <u>Chapter 14: Single-Period Portfolio Optimization</u>
- "With mean-variance optimization, we solve for the portfolio weights that maximize
	Expected return - risk aversion x volatility"
- "anyone with a basic version of Excel can build a remarkably powerful and flexible full-scale portfolio optimization tool"
- Table 14.1 replicates a simple example of portfolio weights that maximize utility, given the assumptions:
	<img src= "file:///Users/akul/Desktop/Work Work Work/Notes/Akul's Notebook/Books/Asset Allocation/Appendix/Figure_14.1.png">
	- Probability of recession = 10%; stocks = -20%; bonds = +9%  
	- probability of expansion = 90%; stocks = +11%; bonds = +7%
	- Terminal wealth = 1 + return
	- Portfolio wealth = weighted average return based on stocks and bond weights
	- Utility = natural log of portfolio wealth, i.e., ln(portfolio wealth)
	- Probability-weighted utility = "probability weighted sum of the utility numbers"

- A Middle Ground Between Simplicity and Complexity
	- "Problems with mean variance start to occur when the utility function includes a sharp drop, a kink that represents significant aversion to loss beyond a threshold"
	- "there are several modified versions of mean-variance optimization that account for fat tails but don't require us to define a utility function in detail"
	-   In [[Optimal Portfolio in Good Times and Bad]], the authors "modify mean-variance optimization to make it more sensitive to exposure to loss. To do so, they use two separate sets of volatilities and correlations ('covariance matrices'): one for the normal regime and one for the turbulent regime"
		- "The goal is to find the portfolio weights that maximize
			Expected return - [risk aversion 1 x volatility (quiet) + risk aversion 2 x volatility (turbulent)]"
		- "multiply the risk aversion terms by the relative probabilities of the quiet and turbulent regimes"
		- "They define the regimes based on a measure of multivariate distance, also called the Mahalanobis distance"
	- "There are several other modified versions of mean-variance optimization that account for nonnormal (non-Gaussian) higher moment, in particular fat tails. For example, we can replace volatility with a measure of tails risk"
		- "See Harvey, Liechty, Liechty, and Müller (2010); Beardsley, Field, and Xiao (2012); and Rachev, Menn, and Fabozzi (2005)"
	- "If we use CvaR as our measure of tail risk, we can modify mean variance to solve for the weights that maximize
		-risk aversion x CVaR"
	- "We can combine volatility and tail risk directly into one objective function"
		Expected return - [risk aversion 1 x volatility (quiet) + risk aversion 2 x tail risk]
		- "Within this approach, we optimize the portfolio in three dimensions: return, volatility, and tail risk. For the same return and volatility, we want the solution with the lowest possible tail risk. Hence, again we penalize assets with low volatility but high tail risk"
	- "Another methodology is to add higher moments directly into the objective function, as follows:
		Expected return - risk aversion x volatility + skewness aversion x skewness - kurtosis aversion x kurtosis"

- How Should We Address Issues with Concentrated and Unstable Solutions?
	- "we can apply constraints to the weights. For example, we can limit the hedge fund allocation to 10% of the portfolio"
	- "We can define 'group' constraints. […] all asset classes that are part of the 'alternatives' category [e.g. hedge funds, liquid alternatives, and real estate] we could set up a constraint such that no more than 20% of the portfolio should be allocated to alternatives"
	- "A popular approach, pioneered by Richard Michaud, has been to use resampling"
	- "The popular Black-Litterman model […] blends discretionary views with equilibrium returns […]. If we don't use views, or if we have very little confidence in them, the solution converges to market capitalization weights"
	- "These models aren't *that* useful for nonquants"
	- "Another way to avoid concentrated portfolios […] is to add a peer group risk (tracking error) constraint […] i.e., we can maximize:
		Expected return - risk aversion x volatility - tracking error aversion x tracking error"

- Are Optimizers Worthless?
	- "Optimizers are helpful tools is used correctly"
	- "I disagree with this conclusion [that equally weighted portfolios outperform mean-variance optimal portfolios] as well"
	- #idea_tactical_asset_allocation "In [[In Defense of Optimization]] […] we show that when we use basic expected returns instead of rolling short-term realized returns, mean variance outperforms equally weighted portfolios"
		- "We don't assume any forecasting skill. We model expected returns with long-run averages (estimated out-of-sample) and constant risk premiums"

- What About Risk Parity?
	- "asset allocators should not rely naïvely on the approach"
	- "Typically, we assume that all asset classes have the same expected return-to-risk ratio"
	- "The authors [[Will My Risk Parity Strategy Outperform]] showed that over an 80-year back-test, risk parity underperforms the 60% equities/40% bonds portfolio, after accounting for the historical cost of leverage and turnover"

