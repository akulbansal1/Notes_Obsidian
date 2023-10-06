
[Paper Link](obsidian://open?vault=Akul's%20Notebook&file=Library%2Fjournals%2Cmagazines%2FFactor%2F'Long'%20Factors%2C%20not%20'Short'%20Change%20Long%20Only%20Factor%20Portfolios%20in%20India.pdf)
Author(s): Rajan Raju, Anish Teli
Publish Year: 202201
Tags: #Factor_Investing #Indian_Factor_Investing

## <u>Abstract</u>
- "monthly rebalanced, equal weighted, long-only winner portfolios, drawn from the top 200 stocks in India, built using systematic rules that underpin popular factors of momentum, low volatility, and quality deliver alpha for the period under study"

## <u>Introduction</u>
- "Practical expressions of factor investing are not market-neutral long-short portfolio. Rather they are usually long-only portfolio with significant market exposure"
- "There are significant implementation issues in India for strategies that short individual stock. So any implementation of factor strategies in the Indian context necessarily entails examining the long-only legs"
- "Using time-series data from December 2006 for the S&P BSE 200 constituents, we show that some long-only top decile portfolios deliver alpha in India"

## <u>Literature Review</u>
- "[Blitz et al. (2020)](https://www.tandfonline.com/doi/full/10.1080/0015198X.2020.1779560) found that most of the value-add from long-short factor strategies comes from the long legs"
- "Israel et al. (2017) argue that '*skillful targeting and capturing of style premia may constitute a form of alpha on its own — one we refer to as craftsmanship alpha*'"
- "Bender and Wang (2016) [[How a Multi-Factor Portfolio is Constructed Matters|related blog]] analyse this and find that interaction between individual factors impacts portfolio performance significantly. They conclude '*both intuition and empirical evidence favour bottom-up multi-factor portfolio construction*'"

## <u>Methodology and Data</u>
- ##### Methodology
	- "We look at the size, value, momentum, low-risk, quality, growth and beta factors for this study. Our universe is the S&P BSE 200 constituents which we have collated from December 2006 through to October 2021. The total number of firms in the universe is 405"
	- "We adopt the Equal Weight approach in our analysis"
	- "The S&P BSE 200 constituents, by definition, are skewed in size. To determine 'Big' and 'Small' size categories, [...] follow Edwards and Cavalli-Sforza (1965) suggestion that the best split of observations into two clusters is one which minimises the within-group sum of squares or maximises the between-group sum of squares"![[Screenshot 2023-09-26 at 2.43.01 PM.png]]
	- "The Refinitiv Business Classification (TRBC) schema is used to categorise all firms into 10 economic sectors: Basic Materials, Consumer Cyclicals, Consumer Non-Cyclicals, Energy, Financials, Healthcare, Industrials, Real Estate, Technology, Utilities"
	- Factor strategies and their definitions.![[Screenshot 2023-09-26 at 2.45.07 PM.png]]
	- "we apply a 3-month lag for accounting metrics from the month first appearing on Refinitiv consistently. So, if EPS was reported on Refinitiv at the end of March 2018, it will only be included effective June 2018"
	- "We use $z$-scores to normalise the variable before ranking firms [...]. We further transform the $z$-score to deal with negative values as follows:![[Screenshot 2023-09-26 at 2.52.33 PM.png]] All stocks in the universe for the month are ranked on $z$-scores and the ranks are used to create the decile portfolios".
	- "While we ignore costs for most part, we estimate the shrinkage arising from implementation"
- ##### Data
	- "All our data is from Refinitiv and Datastream"
	- "Price-to-Book (PB), Price-to-Earnings (PE), and Dividend Yields (DY) for all firms is as of every month end. The values are lagged by 3 months to avoid forward-looking bias. The price for the PB, PE, DY are adjusted using the firm's closing price for the previous month divided by the firm's closing price from 3 months ago to reflect the adjustment in the PB, PE, and DY values. [...] Annual Revenue from Business Activity, Return on Capital Employed (ROCE), Return on Equity (ROE), Earnings per Share (EPS), and Debt Equity Ratio (DE) are annual from financial statement data on Refinitiv. These are also lagged by 3 months for our calculations."
	- "We use survivorship-bias adjusted monthly data from Fama French and Momentum Factors: Data Library for Indian Market ([Agarwalla et al., 2013](https://faculty.iima.ac.in/iffm/Indian-Fama-French-Momentum/)) with data till March 2021 as our FF4 dataset."

## <u>Results and Discussion</u>
- "the wealth index (Dec 2006=100) for the winner portfolios across the various factor styles"![[Screenshot 2023-09-26 at 3.16.26 PM.png]]
- "Figure 2 shows the range of the rolling returns. [...] Empirically, *entry timing does play a role in realised alpha across strategies even over 'long' periods*"![[Screenshot 2023-09-26 at 4.38.47 PM.png]]
- ##### Long-only Systematic Decile Portfolios: Risk-adjusted returns
	- "Ideally, if factors affect performance, returns should increase monotonically across the deciles."![[Screenshot 2023-09-26 at 4.40.05 PM.png]]
	- "Momentum and low-volatility show moderate to strong monotonic increases in raw Sharpe across deciles. High Beta shows a generally reducing raw sharpe from the loser decile to the winner decile. Value's raw Sharpe does not have a clear trend and varies between the two variants. Size, reflective of the relative growth of returns in large-cap firms during the current decade, shows a downward trend in the raw Sharpe ratio across the deciles. Growth and quality show increasing raw Sharpe ratios across deciles, but the path is not linear"
- `skipped a bunch of different analyses that I didn't think were too relevant for me right now`
- "In the Indian context, while some long only factor strategies as we have constructed them show negative alpha, momentum, low volatility, and quality show healthy alphas to the broader market nett of key transaction costs."

## <u>Conclusion</u>
- "Despite our conservative estimates of costs, alpha remains positive after accounting for brokerage and impact costs for momentum, low volatility, and quality implementations. We are confident that real-world implementations, with more sophisticated trading algorithms, will generate positive expected alphas over the long term."
- "Factors are not a panacea or a silver bullet for investors. Factors work over long periods. Importantly, they do not work all the time. Investors with shorter time horizons tend to abandon strategies out of favour and switch to those in favour."
- "A logical extension of our study would be to explore factor rotation, multi-factor portfolio combinations and tactical management of single-factor portfolios by looking at factor behaviour over business and economic cycles."