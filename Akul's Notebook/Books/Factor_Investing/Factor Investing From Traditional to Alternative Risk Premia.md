
[Book Link](obsidian://open?vault=Akul's%20Notebook&file=Library%2Fbooks_Personal%2Fquant%2Ffactor%20investing%2FEmmanuel%20Jurczenko%20(editor)%20-%20Factor%20Investing_%20From%20Traditional%20to%20Alternative%20Risk%20Premia-ISTE%20Press%2C%20Elsevier%20(2017).pdf)
Author(s): multiple, different for each chapter
Publish Year: 2017
Tags: #Factor_Investing #Quant 

## <u>Introduction</u>
- "Factors are *traditional*: they results from economic rationales of a reward for bearing risk, a structural impediment, or investors' behaviour biases. [[Asset Management A Systematic Approach to Factor Investing]]"
- "Factors are also *alternative*, in the sense that they can represent a differentiated return stream to traditional stock and bond market indexes. It is not the economic concept that is alternative; rather, what is new is the way we can employ these factor strategies in multiple markets, often transparently, and generally at lower cost than traditional active strategies"
- "factors are like building blocks in that they can be assembled by different investors to meet different investment objectives"
- "predicting individual factor performance is difficult, especially done by timing only that factor. [...] combining different signals can lead to greater predictability. [...] the approach for signal combination is more effective for forecasting single factors compares to a portfolio of multiple factors." 

 
## <u>Chapter 1: The Price of Factors and the Implications for Active Investing</u>
By: Inigo Fraser-Jenkins
- "When smart beta indices have a fee close to that of traditional indices. then they implicitly become benchmarks. This causes a profound shift in asset management: the progression from a univariate to multivariate benchmark. In such a world, the goal of active management becomes generating idiosyncratic returns."
- "If a fund delivers returns that idiosyncratic to the available set of commoditised factors, then it is probably important for the asset owner."
- Smart beta: the Uber of asset management
	- "commoditised factors allow for a cheap replication of some of the style factors that have been used by active fund managers to drive outperformance over the last 20 years."
	- We need "a process for strategic allocation to smart beta"
	- "We do not need more indices"
	- "Equally, we have become bored and dejected by the stream of academic or semi-academic articles explaining why smart beta index *N* will outperform because of behavioural bias *X*"
	- "The final things we do not need is agonising more about whether smart beta is active or passive"
	- "there is a lot of hype about smart beta. This is right in the sense that it is a growing area, but it is growing because costs are falling so fast and it is 'disrupting' some areas of traditional asset management."
	- "we think a [business] opportunity may exist for the solutions businesses of asset management companies in putting together a strategic allocation to such factors."
	- "The other business opportunity for managers is to take market share back from index providers."
	- "The other business opportunity is for the long-short version of smart beta, which we turn to later."
- Allocating to smart beta: an unambiguously active decision
	- "Logically, more asset managers should move into the field of strategic and tactical allocation across smart beta as that gets back to active management with an ability to differentiate performance and earn at least some of the associated fees."
	- Combining factors: "This would involve measuring the exposure of each stock to the factors of interest and forming a return forecast on the stock as (usually linear) weighted combined product of factor coefficients and factor exposures."
		- "allows for a much more sophisticated approach to portfolio construction to better reflect risks"
		- "this 'proper' combination approach tends to outperform"
- Adoption of smart beta
	- "The long-term investment horizons for sovereign wealth and pension funds are particularly suited for smart beta allocations as they can withstand cyclicality in factor performance."
	- "Tomas Franzén, chief investment strategist at Swedish pension fund AP2 was quoted in the *FT* as saying, 'It's not that we thing alpha doesn't exist. But it would be naive to think that alpha would be cheap...and it's also difficult to identify those managers and then knowing if the alpha will persist'"
- Organisational issues for smart beta
	- "there may be an advantage in offering more sophisticated approaches to factor formation, factor combination and portfolio construction – in which case, it is closer to the natural domain of 'active' quant groups"
- Toward idiosyncratic returns
	- "as the cost of factors converges on the cost of buying a passive index, benchmarks will become multivariate whether people like it or not"
	- "the key measure of success in fund management becomes the ability to generate idiosyncratic returns, i.e. returns that are different from a linear set of systematic factors"
- Idiosyncratic returns: the emergence of a multivariate benchmark whether one likes it or not
	- "within equities there are broadly three categories of activity that are possible":
		1. strategic factor exposure (i.e. a persistent factor bias that is not timed);
		2. timing (e.g. of market risk, factor risk and themes);
		3. stock picking
	- "measure the idiosyncratic component of returns by running a regression of a fund's return on the market return and a set of risk factors"
		- which factors to use: "the set of factors that are cheap and liquid, because this is not a quant question about the best way to explain portfolio returns but a market question of how to positive active funds"
		- "rewarding a manager only for what was not explained by such a regression would do managers who got their factor allocation correct a disservice"
		- "not all tracking error is equal"![[Screenshot 2023-08-02 at 1.59.00 PM.png]]
	- "quant is changing the rules of the game for all fund management. There has been a subtle shit in the last couple of years from a univariate to a multivariate benchmark"
- Opportunities for asset managers and asset owners
	- Areas of growth for asset managers:
		- Smart beta: "will continue to see asset growth, though fees will also continue to fall at a fast rate. So, this will rapidly become a volume 'game'"
		- Risk premia: "distinct from smart beta in that it tends to be long short and also cross-asset"
		- Strategic factor allocation: "advice on how to build portfolios from these newly emergent strategies and products"
		- Tactical factor allocation: "equity quants have had a go at factor timing for years, applying this to the cross-asset risk premia space is new and we have not seen products with long track records"
		- Dynamic allocation: "one of the key aims of many fundamental fund managers"
		- Stock picking: "many people who think they picking stocks are really just running a strategy, but those who can [pick stocks], will be able to charge a premium"


## <u>Chapter 2: Factor Investing: The Rocky Road from Long-Only to Long-Short</u>
By: Marie Brière and Ariane Szafarz
- "Factor investing exhibits a remarkable propensity to beat the market in terms of enhancing expected returns a given level of volatility"
- Short-selling and factor investing
	- "the typical factor-investing strategies rely heavily on short sales, and the bulk of the empirical literature on risk factors disregards the additional constraints associated with shorting."
	- "Lo and Patel (2008) attribute the impressive growth of the 130/30 class of strategies to 'both [...] the historical success of long-short equity hedge funds and the increasing frustration of portfolio managers at the apparent impact of long-only constraints on performance'"
	- "To relax the necessity of short-selling in factor investing, we:"
		1. "disentangle the long and short legs of the five historical factors. Ten resulting long-only factors [...]"
		2. "short selling restrictions [...] are imposed separately on each of these 10 factors"
		3. "we consider separately any short-selling restrictions on the market index to show that shorting the market is much easier to do  than shorting any other factor"
- Data and methods
	- "five long-short risk factors proposed by Fama and French and Carhart: size, value, profitability, investment and momentum."
	- 10 long-only factors, and the market factor:![[Screenshot 2023-08-02 at 5.16.39 PM.png]]
	- 11 elementary styles, "each portfolio is defined by its vector of shares invested in each style:"![[Screenshot 2023-08-02 at 6.14.31 PM.png]]
		- 0 = market; 1 = small, 3 = value, 5 = conservative investment, and so on..
	- "mimicking the typical structure of the Fama and French (FF) long-short factors is easily done [...]. we obtain the constraints fulfilled by any FF portfolio:"![[Screenshot 2023-08-02 at 6.21.18 PM.png]]
	- Using equation 2.3, "examine the consequences on mean-variance performances of imposing five sets of short-selling-based restrictions. Table 2.3 presents the four groups of portfolio of interest according to both market exposure and the maximal admissible short-selling level"![[Screenshot 2023-08-07 at 2.29.11 PM.png]]
		- Group 1: long-only; Group 2: "no restriction on market exposure but excludes short positions in factors"; Group 3: 130% long and 30% short; Group 4: "no position is constrained"
	- benchmark portfolios: *FFminvol* (minimum-variance portfolio); *FFmktvol*; *FFhighvol* (volatility of the market equidistant from those of *FFminvol* and *FFhighvol*).![[Screenshot 2023-08-07 at 2.37.06 PM.png]]
		- "As expected, the magnitude of the short exposure increases with the level of volatility"
- Empirical results
	- "the frontier corresponding to the global long-short case (Group 4) dominates all the others"![[Screenshot 2023-08-07 at 3.18.00 PM.png]]
	- "all the tests run for Groups 1-3 exhibit underperformances (negative outperformances) that are significant at the 1% level, suggesting that the portfolios in the three groups fail to reach the performances of the FF benchmarks, in terms of expected returns as well as volatility"
	- "the way Fama and French built their factors for making their case in asset pricing holds up exceptionally well in the transitions to portfolio management".
	- "impressive amount of shorting is profitable in terms of excess returns"
- "long-short strategies are evidently superior to long-only ones because they capture investment opportunities that are otherwise inaccessible"

## <u>Chapter 3: Peering Under the Hood of Rules-Based Portfolio Construction: The Impact of Security Selection and Weighting Decisions</u>
By Jennifer Bender, Xialoe Sun and Taie Wang
- Framework
	- "weight of each security in the portfolio is written as:"![[Screenshot 2023-08-25 at 2.44.52 PM.png]] "where $z$ is a multiplier applied to a starting set of security weights, e.g. market cap weight or equal weight"
	- "Larger multipliers can be given to the stocks that deliver more exposure to the factor. Smaller multipliers can be given to the stocks that deliver negative exposure to the factor."
- Security selection and weighting
	- "the fewer stocks chosen, the higher the tracking error will be. [...] the higher the exposure to the targeted factor will generally also be, and if the return to the factor is positive, the higher the return will generally be."
	- "as more stocks are screened out, the stock-specific component becomes and increasingly greater driver of returns and risk. At the same time, systematic sources of risk and return becomes less important, including the target factor itself."
	- A way to quantify the aggressiveness of a weighting scheme: the MEM. "The MEM is the largest effective multiplier in the portfolio, i.e. the weight of the security in the portfolio with the largest weight (relative to its market cap weight), divided by its market cap weight."
		- "increasing the MEM is associated with an increase in the tracking error, factor exposure and excess return"![[Screenshot 2023-08-29 at 4.53.47 PM.png]]
	- "Figure 3.8 illustrates two types of portfolio as we successively remove securities from the universe. In one portfolio, we market cap weight the remaining securities and in the other, we apply a fixed moderate tilt toward value in the remaining securities."![[Screenshot 2023-08-25 at 3.12.57 PM.png]]
- MEM: Maximum Effective Multiplier
	- "As long as the starting weights are equal weights weights, the set of weights sums to 100% and the multipliers are linearly interpolated, then the MEM will always be 2." [[Factor Investing From Traditional to Alternative Risk Premia#^18bf8e|Appendix B]]
	- ![[Screenshot 2023-09-12 at 12.01.48 PM.png]]
	- There is a perfect linear relation between the multipliers and effective multipliers. This is basically multiplier of each stock (Z) divided by the sum(of multipliers multiplied by starting weights). Since sum(of multipliers multiplied by starting weights) is a constant, Z and E are linearly related. ![[Screenshot 2023-09-12 at 12.02.40 PM.png]]
	- "One clear case [of E > Z] occurs when all multipliers in the vector Z are greater than 1. But for typical weighting schemes, we observe that Z is centered around 1. (...) For instance, if the starting weights are market cap weights, this relationship would hold if larger cap securities generally receive higher multipliers as in a factor such as quality"                           ![[Screenshot 2023-09-12 at 12.03.44 PM.png]]
- Analysing the MEM for several popular cases
	- 

- Appendix B: Proof behind the limit to the MEM ^18bf8e
	- conditions:
		1. starting weights are equal weights;
		2. starting weights sum to 100%;
		3. the multipliers are linearly interpolated between the minimum and maximum multipliers.
	- a sample of set of weights:![[Screenshot 2023-08-29 at 5.18.06 PM.png]]
	- ...mathematical calculations for showing why the limit of MEM is, in fact, 2 under those conditions.
	- "By extension, in order to increase the MEM of a factor index, it must be the case that we:"
		1. use non-equal weights as a starting point;
		2. use a nonlinear multiplier scheme;
		3. use security selection such that we are not holding the entire universe.
- Appendix C: Deriving a general relationship between the initial multipliers and effective multipliers
	- 

## <u>Chapter 4: Diversify and Purify Factor Premium in Equity Markets</u>
By Raul Leotte De Carvalho, Xiao Lu, François Soupe and Patrick Dugnolle
- "Investors now increasingly realise that what really matter is the factor exposure that you choose for portfolios. Choosing the right factor exposures should on average lead to good returns in excess of those of market capitalisation indices."
- Traditional equity quantitative investing strategies based on cross-sectional regressions: Huagen and Baker 1996.
- Factor investing "is entirely focused on the optimal exposure of a portfolio to the factors that generate a positive factor premium."
- Factors
	- [[A Census of the Factor Zoo]] "list more than 200 factors that have been proposed in papers published in top academic journals to explain the cross-section of equity returns."
		- "many of these factors can be grouped into styles since they capture similar types of stock exposure"
	- #idea_factor_investing "the list of factors we used:"![[Screenshot 2023-08-16 at 3.40.24 PM.png]] ^42c917
- Results #idea_factor_investing 
	- "a z-score transformation is usually applied in the cross-section of factors to center and reduce them to a common scale." z-score of a stock for a factor is based on the distribution of all cross-sectional values for all the factors. "In practice, we use a more sophisticated, but robust version of this definition that relies on the cross-sectional median rather then average of factor [values] and removes the outliers from the distribution of z-scores."
	- **portfolio construction**
		- simplest strategy: "ranking stocks by factor scores and then build a long-short portfolio every month, changing the allocation according to changes in those ranking. [...]  [retain a number of highest and lowest ranked stocks] Equal weighting or market capitalisation weighting of each of the retained stocks is common".
		- slightly more sophisticated: weight of each stock proportional to the respective z-score.![[Screenshot 2023-08-16 at 4.34.03 PM.png]]
		- "sector neutrality is often imposed"![[Screenshot 2023-08-16 at 5.10.42 PM.png]]
		- constant volatility targeted portfolio:![[Screenshot 2023-08-16 at 5.21.12 PM.png]]
		- "before calculating the *ex ante* factor volatility, we hedge the beta of the long-short portfolio against the market capitalisation index. This is an important exposure to hedge away to the extent that is possible and was proposed for low-risk factors by Frazzini *et al.* [[Betting Against Beta]]. But hedging beta is also important for the other factors. [...] To hedge the beta of the long-short portfolio, we calculate an *ex ante* beta for each stock from:"![[Screenshot 2023-08-16 at 5.33.35 PM.png]] "To hedge the beta of the factor portfolio, we simply subtract from the factor long-short portfolio the allocation of *B* times a portfolio long the market capitalisation index"
		- To hedge the exposure to size: "We first estimate the beta of each stock to size at each rebalancing. We do this by regressing at that point in time the past stock returns in excess of cash returns against the past returns to a portfolio long the equally weighted (EW) index of all stocks in the universe and short the market capitalisation index over the 3 years. [...] This is done before the estimation of the *ex ante* volatility and calibration of leverage to target a constant volatility".
		- "It is the correlation of returns that needs to be handled. And the factor exposures should be targeted in terms of a risk budget allocation of factor returns, not factor scores."
	- Historical information ratios "based on the different approaches to factor portfolio construction"![[Screenshot 2023-08-16 at 5.45.52 PM.png]]
	- "factor investing approaches that pay attention to the purification of factor premiums can deliver higher risk-adjusted returns with a much lower correlation with equity market returns."
	- Sector neutralisation is the most important in value factors and, to some extent, on low-risk factors. "long-term biases toward interest rates sensitive stocks are known to form in low-risk equity factor strategies unless sector neutrality is imposed. Such biases tend to add to volatility and not to returns in the long term."
	- contribution from stocks with positive and negative factor scores
		- Table 4.6 "compare the information ratio generated by the long leg of the factor strategies, with the information ratio generated by the short leg of the strategy." *long-market* replaces the short leg with the market index. "The size of the short leg needs to be adjusted so as to neutralise the beta"![[Screenshot 2023-08-16 at 6.32.51 PM.png]]"Almost everywhere the information ratio of the long leg is higher than the information ratio of the short leg and in some cases quite significantly so"
	- Purification of factors (i.e., targeting a constant volatility, hedging market beta, and neutralising sector exposures) "while generating higher information ratios, also requires high levels of turnover". Some ways to control the turnover:
		- "shorting stocks can be replaced by shorting the market"
		- "the use of optimisers such as in Black-Litterman type approaches as described by De Cravalho *et al.* is also highly efficient in reducing turnover and associated costs while not sacrificing returns."
	- "we do not find evidence of a strong relationship between negative skewness and factor risk-adjusted returns"

## <u>Chapter 5: The Predictability of Risk-Factor Returns</u>
By Robert J. Bianchi, Michael E. Drew and Scott N. Pappas
- "single-variable forecasts can be combined to produce risk-factor return estimates that are economically and statistically significant."
- 