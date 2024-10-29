
[Book Link](obsidian://open?vault=Akul's%20Notebook&file=Library%2Fbooks_Personal%2Fportfolio%20management%2F(Chapman%20and%20Hall_CRC%20Financial%20Mathematics%20Series)%20Edward%20E.%20Qian%2C%20Ronald%20H.%20Hua%2C%20Eric%20H.%20Sorensen%20-%20Quantitative%20Equity%20Portfolio%20Management_%20Modern%20Techniques%20and%20Applications-Chapman%20and%20Hall_CRC%20.pdf)
Author(s): Qian, Hua, Sorensen
Publish Year: 2007
Tags: #Factor_Investing #Quant #Portfolio_Management #Portfolio_Construction 

## <u>Chapter 1: Introduction: Beliefs, Risk, and Process</u>
- To be successful, investment team must have 1) strong philosophy based on beliefs; 2) approach in translating uncertainty into an appropriate risk/returns trade-off; 3) comprehensive investment process
- #### Beliefs
	- "it is difficult to win consistently if we account for the proper risks"
	- "One must have the best information as well as the best way to process and implement them in a portfolio"
- #### Risk
	- "It was Markowitz (1952) who inaugurated the vast body of literature we know as modern portfolio theory (MPT)"
	- "The expected return of a security (or a portfolio) consists of two parts: (1) market price of time — the risk-free rate and (2) market price of risk — beta times the market excess return"
	- "Equity market neutral managers (mostly quants) manage zero-beta funds with refined risk management systems, and often deliver pure alpha. \[...] we have the rise of market-neutral hedge funds with a new benchmarks — cash"
- #### Quantitative Investment Process
	- **Alpha models**: "that forecasts excess return of stocks"
	- **Risk models**: "sophisticated risk tools that embody many 'drivers' of risk beyond the one factor CAPM. \[...] commercial risk models such as BARRA serve to isolate and control stock specific factors that measure unwanted risk, such as size, value and the like. However, some BARRA factors, first estimated in the mid-1980's, overlap with potential stock-specific alpha factors"
	- **Portfolio optimisation**: "calculates the tradeoff between alpha factors (wanted risk) with risk factors (unwanted risk)" — the optimisation tool. "These tools allow managers to dissect the ex ante risks, and place their exposure with their alphas"
	- **Portfolio implementation**: "Asset management firms and brokerage firms are increasingly relying on proprietary or commercial models to implement trades with the goal of minimising implementation shortfall under certainty"
	- **Performance attribution**: "Modern mangers perform attributions regularly to ascribe ex post returns to ex ante factor exposures"
	- "Some of the most valuable information, quantitative or fundamental, is only garnered through painstaking analysis of financial statements"
- #### Information Capture
	- "The key to investment success is consistency in forecasting (skill) applied repeatedly (breadth)"
	- Skill is measured by "the information Coefficient ($\text{IC}$) — the cross-sectional correlation coefficient between forecasts and subsequent returns."
	- "Consistency is measured by the information ratio ($\text{IR}$) — the ratio of average excess return to the standard deviation of excess return"$$\text{IR} = \text{IC} \sqrt{N}$$"where $N$ is the number of independent securities"
	- "A one-size-fits-all model assumes that all stocks respond to the factor exposure in the same way all the time. Practitioners know this is not true, and are beginning to analyse factor significance within this context"
	- "Alpha can also be allusive, and today's alpha could be gone tomorrow or reclassified as beta in the future"

# Part I

## <u>Chapter 2: Portfolio Theory</u>
- "two versions of the mean-variance optimisations: one for total risk and total returns, and the other for active risk and active return. The latter version can be used for both an active portfolio managed against a traditional benchmark and long-short hedge funds."
- #### Distribution of Investment Returns
	- "The most attractive feature of modelling security return with normal distribution is that the return distribution of a portfolio investing in a number of stocks would also be normal"
	- The portfolio returns distribution $$ r_p \sim N(\boldsymbol{w' \cdot \mu , w' \Sigma w}) \tag{2.1}$$ where $\boldsymbol{\mu} = (\mu_1,\cdots,\mu_N)'$  is the expected return vector, and $\boldsymbol{\Sigma} =\big(\sigma_{ij} \big)^N_{i,j=1}$ is the covariance matrix among returns of different stocks.
	- "Some of these issues \[of normal distribution] are negated if we use a lognormal distribution for stock returns, i.e., $\ln(1+r)$ obeys a normal distribution function"
		- "a linear combination of lognormal variables is not lognormal. Therefore, portfolio returns will not be lognormal even if individual stock returns are"
	- The equivalent of $\rho_{1,2} = \frac{\sigma_{12}}{\sigma_1 \sigma_2}$ "in the matrix form gives the correlation matrix of $N$ assets:" $$ C = \text{diag} \big( \sigma_1^{-1} , \cdots , \sigma_N^{-1} \big) \ \Sigma \ \text{diag}  \big( \sigma_1^{-1} , \cdots , \sigma_N^{-1} \big) \tag{2.3} $$
	- <u>How portfolio variance changes with correlation:</u>
		- When correlation is $1$, portfolio volatility is the weighted sum of the stock volatilities. When the correlation is $-1$, portfolio volatility is the absolute difference of the two. When the correlation is $0$, variances are additive.$$ \sigma^2_p = w^2_1 \sigma^2_1 \ + \ 2\rho_{1,2}w_1 w_2 \sigma_1 \sigma_2 \ + \ w^2_2 \sigma^2_2 \tag{2.4} $$
	- <u>How portfolio variance changes with security weights:</u>
		- "the variance as a function of $w_1$ with $\sigma = 40\%, \sigma = 30\%$, and $\rho = 0.3$":![[Screenshot 2024-02-08 at 6.20.46 PM.png]]
		- "The portfolio variance (2.4) is a quadratic function of the weight, and it attains minimum when" $$ w_1 = \frac{\sigma^2_2 - \rho_{1,2} \sigma_1 \sigma_2}{\sigma^2_1 - 2 \rho_{1,2} \sigma_1 \sigma_2 + \sigma_2^2}, w_2 = 1-w_1  \tag{2.7}$$
- #### Optimal Portfolios
	- <u>Minimum Variance</u>
		- Optimisation problem: $$ \begin{multline} \text{Minimize} \ \frac{1}{2} \boldsymbol{w' \Sigma w} \\ \text{subject to:}\ \boldsymbol{w'} \cdot \boldsymbol{i} = w_1 + w_2 + \cdots + w_N =1 \end{multline} \tag{2.8}$$where $\boldsymbol{\Sigma}$ is the covariance matrix and $\boldsymbol{i}=\big( 1, \cdots , 1 \big)'$.
		- By the Lagrangian multiplier method, form a new objective function: $$ Q\big(\boldsymbol{w},l \big) = \frac{1}{2} \boldsymbol{w' \Sigma w} - l\big(\boldsymbol{w'}\cdot \boldsymbol{i} - 1 \big) \tag{2.9}$$Partial derivative w.r.t weight vector and equating to zero: $$ \boldsymbol{\Sigma w} - l \boldsymbol{i} = 0 \tag{2.10} $$ $$ \boldsymbol{w} = l \boldsymbol{\Sigma^{-1} i} \tag{2.11}$$Substituting weight vector in the constraint {$\boldsymbol{w'} \cdot \boldsymbol{i} = 1$} to determine the Lagrangian multiplier $l$: $$ l = \frac{1}{\big( \boldsymbol{i' \Sigma^{-1} i} \big)} \tag{2.12} $$Substituting (2.12) into (2.11) yields minimum variance portfolio weight vector $$ \boldsymbol{w}^\star_\min = \frac{\boldsymbol{\Sigma^{-1}i}}{\boldsymbol{i' \Sigma^{-1}i}} \tag{2.13} $$the minimum variance is equal to the Lagrangian multiplier $$ \sigma^2_\min = \frac{1}{\boldsymbol{i' \Sigma^{-1}i}} \tag{2.14} $$
	- <u>Mean-Variance with Cash</u>
		- "main tool for finding the optimal portfolio with the maximum expected return for a given level for risk".
		- Return of cash = $r_f$ and weight = $w_0$
		- Expected return vector of $N$ stocks is denoted by $\boldsymbol{f} = \big(f_1, \cdots, f_N \big)$
		- "The mean-variance optimal portfolio with a risk-aversion parameter $\lambda$ is"$$ \begin{flalign} \text{Maximize} \ & w_0 r_f + \boldsymbol{w'} \cdot \boldsymbol{f} - \frac{1}{2} \lambda \big(\boldsymbol{w' \Sigma w}\big) \\ \text{subject to:}\ & w_0 + \boldsymbol{w'} \cdot \boldsymbol{i} = 1 \end{flalign} \tag{2.15}$$
		- Writing the constraint as {$w_0 = 1 - \boldsymbol{w'} \cdot \boldsymbol{i}$} and substituting it into objective function: $$\text{Maximize}\ \boldsymbol{w'} \cdot \boldsymbol{f}_e - \frac{1}{2} \lambda \big(\boldsymbol{w' \Sigma w} \big), \quad \text{with}\ \boldsymbol{f}_e = \boldsymbol{f} - \boldsymbol{r}_f \boldsymbol{i} \tag{2.16} $$The vector $\boldsymbol{f}_e$ represents the stocks' excess returns above cash. Partial derivative: $$ \begin{multline} \boldsymbol{w}^\star = \frac{1}{\lambda} \boldsymbol{\Sigma}^{-1} \boldsymbol{f}_e \\ w^\star_0 = 1 - \boldsymbol{w'^\star} \cdot \boldsymbol{i}\ =\ 1 - \frac{1}{\lambda} \boldsymbol{i' \Sigma^{-1} f}_e \end{multline} \tag{2.17} $$
		- When the covariance matrix is diagonal (returns are uncorrelated), optimal weight of a stock is: $$ w_i^\star  = \frac{1}{\lambda} \frac{f_i - r_f}{\sigma^2_i} =  \frac{1}{\lambda} \frac{f_{e,i}}{\sigma^2_i} \tag{2.18} $$
	- <u>Mean-Variance without Cash</u>
		- Can be formulated "by simply setting $w_0 = 0$ in (2.15)" $$\boldsymbol{w}^\star = \frac{\boldsymbol{\Sigma^{-1}i}}{\boldsymbol{i' \Sigma^{-1}i}} + \frac{1}{\lambda} \frac{ \big(\boldsymbol{i' \Sigma^{-1}i} \big) \boldsymbol{\Sigma^{-1}f} - \big(\boldsymbol{i' \Sigma^{-1}i} \big) \boldsymbol{\Sigma^{-1}i}}{\boldsymbol{i' \Sigma^{-1}i}}  \tag{2.22} $$The first term "is just the minimum variance solution" and the "second term is affected by the forecast and the risk-aversion parameter"
		- Two cases in which (2.22) reduces to the minimum variance weights
			1. When $\lambda \to \infty$ and the second term vanishes.
			2. When all the return forecasts are identical, i.e., $\boldsymbol{f} = k \boldsymbol{i}$
		- Expected return and variance of the optimal portfolio: $$ \begin{multline} \mu^\star = \boldsymbol{f' \cdot w^\star} \\ \big( \sigma^\star \big) ^2 = \boldsymbol{w'^\star\ \Sigma w^\star} \end{multline} \tag{2.23} $$"As we change the risk-aversion parameter, the pair $\big(\sigma^\star , \mu^\star\big)$ forms a curve called the efficient frontier in the risk/return space"
		- Example: $$\boldsymbol{f} = \begin{pmatrix} 10\% \\ 0\% \\ -10\% \end{pmatrix} ,\ \boldsymbol{\sigma} = \begin{pmatrix} 30\% \\ 30\% \\ 30\% \end{pmatrix}, \ \boldsymbol{C} = \begin{pmatrix} 1 & 0.5 & 0.5 \\ 0.5 & 1 & 0.5 \\ 0.5 & 0.5 & 1 \end{pmatrix}. $$![[Screenshot 2024-04-12 at 1.33.29 PM.png]]"As the risk-aversion parameter descends from infinity, both the expected return and risk of the optimal portfolio increase in a concave shape that is typical of efficient frontiers"
	- <u>Active Mean-Variance</u>
		- "The return and risk of these portfolio are measured relative to the benchmark and are called *active return* and *active risk*"
		- "decompose the portfolio weights into benchmark weights and active weights: $\boldsymbol{w = b + a}$ \[...] active weights must be dollar neutral, i.e., $\boldsymbol{a' \cdot i} = 0$"
		- "Given the expected return vector $\boldsymbol{f}$, the expected active return is $\boldsymbol{a' \cdot f}$. The active risk in variance is $\boldsymbol{a' \Sigma a}$" $$\begin{flalign} \mathrm{Maximize}\ & \boldsymbol{a' \cdot f} - \frac{1}{2} \lambda \big( \boldsymbol{a' \Sigma a} \big)   \\ \text{subject to:}\ & \boldsymbol{a' \cdot i} = 0 \end{flalign} \tag{2.24} $$
		- Solution of (2.24): $$ \boldsymbol{a}^\star = \frac{1}{\lambda} \frac{ \big(\boldsymbol{i' \Sigma^{-1}i} \big) \boldsymbol{\Sigma^{-1}f} - \big(\boldsymbol{i' \Sigma^{-1}f} \big) \boldsymbol{\Sigma^{-1}i}}{\boldsymbol{i' \Sigma^{-1}i}}  \tag{2.25} $$
		- "alternative from of optimal active weights" $$ \boldsymbol{a}^\star = \frac{1}{\lambda} \boldsymbol{\Sigma}^{-1} \big( \boldsymbol{f} - l \boldsymbol{i} \big), \quad \text{with}\ l = \frac{\boldsymbol{i' \Sigma^{-1}f}}{\boldsymbol{i' \Sigma^{-1}i}} \tag{2.26} $$"similar to the unconstrained optimal weights (2.17). \[...] Here, we adjust the forecasts by the Lagrangian multiplier to ensure the active weights are dollar neutral"
		- Expected active return from the optimal weights (2.25): $$ \alpha^\star = \boldsymbol{f' \cdot a}^\star = \frac{1}{\lambda} \frac{ \big(\boldsymbol{i' \Sigma^{-1}i} \big) \big(\boldsymbol{f'\Sigma^{-1}f}\big) - \big(\boldsymbol{i' \Sigma^{-1}f} \big)^2}{\boldsymbol{i' \Sigma^{-1}i}} \tag{2.27} $$The active risk (a.k.a. expected tracking error of the portfolio to the benchmark): $$ \sigma^\star = \sqrt{\boldsymbol{a'^\star \Sigma a^\star}} = \frac{1}{\lambda} \sqrt{\frac{\big(\boldsymbol{i' \Sigma^{-1}i} \big) \big(\boldsymbol{f'\Sigma^{-1}f}\big) - \big(\boldsymbol{i' \Sigma^{-1}f} \big)^2}{\boldsymbol{i' \Sigma^{-1}i}}} \tag{2.28} $$
		- Figure 2.2 plots the efficient frontier curve for this long-short portfolio, alongside the fully-invested portfolio.
- #### Capital Asset Pricing Model
	- Two inputs required to use mean-variance optimisation: "expected return forecasts and return covariance matrix"
	- Portfolio of $N$ stocks has $N(N+1)/2$ variances and covariances, "the estimation of so many parameters proves to be an impossible task". CAPM provides a simple structure for the covariance matrix.
	- Individual stocks' returns $r_i$ $$ r_i = r_f + \beta_i (r_M - r_f) + \epsilon_i, \quad \text{where}\ \epsilon_i \sim N(0,\theta_i^2) \tag{2.30} $$Beta is given as a regression coefficient $$ \beta_i = \frac{\mathrm{Cov}(r_i,r_M)}{\mathrm{Var}(r_M)} \tag{2.31} $$
	- under CAPM, the covariance matrix is $$ \begin{flalign} \boldsymbol{\Sigma} &= \boldsymbol{\beta \beta'}\sigma^2_M  + \mathrm{diag}\big(\theta^2_1, \ldots, \theta^2_N \big) \\ &= \boldsymbol{\beta \beta'}\sigma^2_M + \boldsymbol{S} \\ &= \begin{pmatrix} \beta_1 \beta_1 & \ldots & \beta_1 \beta_N \\ \vdots & \ddots & \vdots \\ \beta_N \beta_1 & \ldots & \beta_N \beta_N \end{pmatrix} \sigma^2_M + \begin{pmatrix} \sigma^2_1 & 0 & \large0 \\ 0 & \ddots & 0 \\ \large0 & 0 & \theta^2_N \end{pmatrix}  \end{flalign}  \tag{2.34} $$have used $\boldsymbol{S}$ for the diagonal matrix consisting of specific variances (market-neutralised variance).
	- For a portfolio with weight $\boldsymbol{w}$, portfolio beta $\beta_P = \boldsymbol{w'} \cdot \boldsymbol{\beta}$. The portfolio variance can be separated into systematic variance and specific variance $$ \sigma^2_p = \beta^2_p \sigma^2_M + \sum^N_{i=1} w^2_i \theta^2_i \tag{2.35}$$
	- "typically a long-short market-neutral portfolio, would have no systematic or market risk. All its risk is specific risk. Of course, **this depends heavily on the accuracy of beta estimation**"
	- <u>Optimal Portfolios Under CAPM</u>
		- For mean-variance, we must first find the inverse of the new covariance matrix under CAPM $$ \boldsymbol{\Sigma}^{-1} = \boldsymbol{S}^{-1} - \frac{\sigma^2_M}{1 + \kappa} \boldsymbol{\beta}_s \boldsymbol{\beta}_s'\ ,  \tag{2.36}$$where $$ \kappa = \sum^N_{i=1} \frac{\sigma^2_M \beta^2_i}{\theta^2_i}, \quad \boldsymbol{\beta}_s = \begin{pmatrix} \frac{\beta_1}{\theta^2_1} & \cdots & \frac{\beta_N}{\theta^2_N} \end{pmatrix}' \tag{2.37} $$In the sum $\kappa$, each term is the ratio of systematic variance to specific variance. In the vector $\boldsymbol{\beta}_s$, the components are beta scaled by the specific variance.
		- Example 2.6
			- Consider the case of optimal portfolios including cash in which the weights of the risky assets is given by an unconstrained optimisation. According to (2.17): $$ \boldsymbol{w}^\star = \frac{1}{\lambda} \boldsymbol{\Sigma}^{-1} \boldsymbol{f}_e = \frac{1}{\lambda} \bigg(\boldsymbol{S}^{-1} \boldsymbol{f}_e - \frac{\sigma^2_M}{1 + \kappa} \boldsymbol{\beta}_s \boldsymbol{\beta}_s' \cdot \boldsymbol{f}_e \bigg) \tag{2.38} $$ Denote as the "partial solution":$$ \boldsymbol{w}^\star_0 = \frac{1}{\lambda} \boldsymbol{S}^{-1} \boldsymbol{f}_e \tag{2.39} $$Then, $$ \frac{1}{\lambda} \boldsymbol{\beta}_s' \cdot \boldsymbol{f}_e = \frac{1}{\lambda} \sum^N_{i=1} \frac{\beta_i f_{e,i}}{\theta^2_i} = \sum^N_{i=1} \beta_i w^\star_{0,i} = \beta_0 \tag{2.40} $$
			- Combining (2.39) and (2.40), rewrite the optimal solution as in (2.38) $$ \boldsymbol{w}^\star = \boldsymbol{w}^\star_0 - \frac{\sigma^2_M \beta_0}{1+\kappa} \boldsymbol{\beta}_s  \tag{2.41} $$
			- Weight of a single stock $$ w^\star_i = w^\star_{0,i} - \frac{1}{1 + \kappa} \frac{\sigma^2_M \beta_0 \beta_i}{\theta^2_i} = w^\star_{0,i} - \frac{1}{1+\kappa} \frac{\mathrm{Cov}\big(r_i,r_{\boldsymbol{w}^\star_0}\big)}{\theta^2_i}  \tag{2.42} $$"Optimal weight of a stock is the partial weight less the ratio of its covariance with the partial portfolio to its specific variance times a scalar". Remarks:
				- If excess returns forecasts adjusted by specific variances are uncorrelated with stock's beta estimates, then $\beta_0 = 0$
				- Optimal weights can be derived in two steps:
					1. Derive the partial weights based only on the specific risks.
					2. Modify the partial weights by the covariance term.
			- Beta of optimal portfolio is $$ \beta^\star = \sum^N_{i=1} w_i^\star \beta_i = \sum^N_{i=1} w^\star_{0,i} \beta_i - \frac{\beta_0}{1+\kappa} \sum^N_{i=1} \frac{\sigma^2_M \beta_i}{\theta^2_i} = \beta_0 - \frac{\beta_0 \kappa}{1+\kappa} = \frac{\beta_0}{1+\kappa} \tag{2.43} $$
			- Specific risk of the optimal portfolio: $$ \sum^N_{i=1} \big( w^\star_i \theta_i \big)^2 = \sum^N_{i=1} \big( w^\star_{0,i} \theta_i \big)^2 - \sigma^2_M\beta^2_0 \bigg[ \frac{1}{1+\kappa} + \frac{1}{(1+\kappa)^2} \bigg]  \tag{2.44} $$
		- Example 2.7
			- Using an example of three stocks. Assuming a market risk of 15%. Combining the systematic and specific risks yields the total risk of each stock.![[Screenshot 2024-05-06 at 3.54.55 PM.png]]
			- Choosing $\lambda=2.5$ for the optimal portfolio.
			- Beta of the partial portfolio is 0.44, and beta of the optimal portfolio is 0.23.
			- "The optimal portfolio has a systematic risk of 3.6%, a specific risk of 17.9%, and a total risk of 18.2%. The majority of the total risk is attributed to the specific risk, at 96%"
	- <u>Beta-Neutral Portfolios</u>
		- Mean-variance optimisation with beta-neutral constraint under CAPM.
		- Reformulate the optimisation problem with the diagonal matrix $\boldsymbol{S}$ in (2.34) as $$ \begin{flalign} \mathrm{Maximize}\ &  \boldsymbol{w}' \cdot \boldsymbol{f} - \frac{1}{2} \lambda \big( \boldsymbol{w'Sw} \big) \\ \text{subject to:}\ & \boldsymbol{w}' \cdot \boldsymbol{\beta} = 0 \end{flalign} \tag{2.46} $$
		- Using Lagrangian multiplier method: $$ \boldsymbol{w}^\star = \frac{1}{\lambda} \boldsymbol{S}^{-1} \big( \boldsymbol{f} - l \boldsymbol{\beta} \big), \quad \text{with}\ l = \frac{\boldsymbol{f}' \boldsymbol{S}^{-1} \boldsymbol{\beta} }{\boldsymbol{\beta}' \boldsymbol{S}^{-1} \boldsymbol{\beta}}  \tag{2.47} $$
- #### Characteristic Portfolios
	- The form of solutions so far, using the method of Lagrangian multipliers: $$ \begin{multline} \boldsymbol{w}^\star = \frac{1}{\lambda} \big( \boldsymbol{f} - l_1 \boldsymbol{i} - l_2 \boldsymbol{\beta} \big), \text{or} \\ \boldsymbol{w}^\star = c_1 \boldsymbol{\Sigma}^{-1} \boldsymbol{f} + c_2 \boldsymbol{\Sigma}^{-1} \boldsymbol{i} + c_3 \boldsymbol{\Sigma}^{-1} \boldsymbol{\beta} \end{multline} \tag{2.51} $$"This suggests that optimal weights are a linear combination of a generic — the inverse of the covariance matrix times a vector of attributes. \[...] Other examples of attributes can be additional risk factors and alpha factors"
	- For a given attribute $\boldsymbol{t}$, we define the *characteristic portfolio* as the portfolio that has unit exposure to $\boldsymbol{t}$ and has the minimum variance. $$ \boldsymbol{w}_t = \frac{\boldsymbol{\Sigma}^{-1} \boldsymbol{t}}{\boldsymbol{t}' \boldsymbol{\Sigma}^{-1} \boldsymbol{t}} \tag{2.52} $$
	- If the attribute is $1$, then the characteristic portfolio is the minimum variance portfolio of (2.13)
	- If the attribute is beta, then the characteristic portfolio is $$ \boldsymbol{w}_\beta = \frac{\boldsymbol{\Sigma}^{-1} \boldsymbol{\beta}}{\boldsymbol{\beta}' \boldsymbol{\Sigma}^{-1} \boldsymbol{\beta}} \tag{2.53} $$
	- "characteristic portfolio has unit exposure in its own attributes. We can also calculate its exposures in other attributes. \[...] the beta exposure for the characteristic portfolio of $f$ is $\boldsymbol{\beta}' \cdot \boldsymbol{w}_f$ \[...] we can form optimal weights with desired exposure to various attributes"
	- Example 2.8
		- Find the optimal portfolio with unit exposure to attribute $z$ and zero exposure to beta. $\boldsymbol{w}_z - \big(\boldsymbol{\beta}' \cdot \boldsymbol{w}_z \big)\boldsymbol{w}_\beta$ `(basically calculating the weighted sum beta of the portfolio and then shorting the proportional amount of beta)` has zero beta exposure, and its exposure to $z$ is $1 - \big(\boldsymbol{\beta}' \cdot \boldsymbol{w}_z \big) \big( \boldsymbol{f}'  \cdot \boldsymbol{w}_\beta \big)$. Therefore, optimal weights: $$ \boldsymbol{w}^\star = \frac{1}{1 - \big(\boldsymbol{\beta}' \cdot \boldsymbol{w}_z \big) \big( \boldsymbol{f}'  \cdot \boldsymbol{w}_\beta \big)} [\boldsymbol{w}_z - \big(\boldsymbol{\beta}' \cdot \boldsymbol{w}_z \big)\boldsymbol{w}_\beta] \tag{2.54} $$
		- combining characteristic portfolio of $z$, beta and membership, we can find the optimal portfolio with unit exposure to $z$ with both beta and dollar neutral. $$ \boldsymbol{w}^\star = c_1 \boldsymbol{w}_f + c_2\boldsymbol{w}_\beta + c_3 \boldsymbol{w}_1   \tag{2.55} $$
		- Imposing exposure constraints leads to a system of linear equations $$ \begin{multline}  c_1 + c_2\big( \boldsymbol{f}' \cdot  \boldsymbol{w}_\beta \big) + c_3\big( \boldsymbol{f}' \cdot  \boldsymbol{w}_1 \big)  =1 \\   c_1 \big(\boldsymbol{\beta}' \cdot \boldsymbol{w}_z\big) + c_2 + c_3\big( \boldsymbol{\beta}' \cdot  \boldsymbol{w}_1 \big)  = 0 \\   c_1 \big( \boldsymbol{i}' \cdot \boldsymbol{w}_z \big) + c_2\big( \boldsymbol{i}' \cdot  \boldsymbol{w}_\beta \big) + c_3  = 0  \end{multline}\tag{2.56} $$
		- "Both optimal weights (2.55) and (2.54) have unit exposure to the forecast. Normally, we need to scale these weights by a risk-aversion parameter so that the final optimal portfolios have the targeted level of risk"

## <u>Chapter 3: Risk Models and Risk Analysis</u>
- CAPM "was originally developed as an equilibrium pricing model and not as a risk model *per se*"
- "CAPM states that the market should set prices of stocks in a way such that their expected returns are proportional to their systematic risks measured by beta"
- In the previous chapter, we used CAPM as a risk model, "the total risk of a stock consists of systematic risk measured by beta and stock-specific risk"
	- "the pricing model interprets the equation by expectation but the risk model interprets the equation by variance"
- "some factors may not be priced or rewarded unconditionally through time, but they do differentiate cross-sectional security returns. \[...] there are non-priced risk factors whose returns exhibit a low unconditional mean but high unconditional variance"
- "many alpha models take on the same form as the risk models" #Stat_Arb 
- #### Arbitrage Pricing Theory and APT Models
	- "returns of any stock can be linearly related to a set of factors or indices" $$ r_i = b_{i0} + b_{i1}I_1 + \cdots + b_{iK}I_K + \epsilon_i  \tag{3.2} $$there are $K$ factors, $I_1, \cdots, I_K$, and $b_{ij}$ is the exposure of the $i$-th stock to the $j$-th factor.
	- The covariance matrix of stock returns is $$ \boldsymbol{\Sigma} = \boldsymbol{B \Sigma}_I \boldsymbol{B}' + \boldsymbol{S} \tag{3.3} $$The matrix $\boldsymbol{B}$ is the exposure matrix given by $$ \boldsymbol{B} = \begin{pmatrix} b_{11} & \cdots & b_{1K} \\ \vdots & \ddots & \vdots \\ b_{N1} & \cdots & b_{NK} \end{pmatrix}_{N \times K} = \big( \boldsymbol{b}_1 , \ldots , \boldsymbol{b}_K  \big)  \tag{3.4} $$The vector $\boldsymbol{b}_k$ consists of stocks' exposures to the $k$-th factor. Matrix $\boldsymbol{\Sigma}_I$ is the factor return covariance matrix $$ \boldsymbol{\Sigma}_I = \begin{pmatrix} \sigma_{11} & \cdots & \sigma_{1K} \\ \vdots & \ddots & \vdots \\ \sigma_{K1} & \cdots & \sigma_{KK}  \end{pmatrix}_{K \times K}  \tag{3.5} $$
	- Three categories of multifactor risk models:
		1. Macroeconomic factor models: the most intuitive
		2. Fundamental factor models: captures stock attributes
		3. Statistical factor models: derived factors by statistical techniques like PCA
		- "once the factors are selected, all three model approaches use the same method to derive factor returns and their covariance matrix"
	- <u>Macroeconomic Factor Models</u>
		- Stock prices are sensitive to macroeconomic factors such as interest rates, inflation, and growth of the economy.
		- Including different macro-factors creates an econometric problem due to a multicolinearity of factors. Researchers often use advanced econometric procedures to iteratively purge some macro-factors from the influence of the others (Sorensen et al. 1998).
		- Then, estimate the "exposures of each stock to the select factors through a time-series regression". When done for each stock, we obtain exposure matrix in the form of (3.4). $$ r_{it} - r_{ft} = \alpha_i + \beta_i \big( r_{Mt} - r_{ft} \big) + \sum_{k=1}^{K} b_{ki} I_{kt} + \epsilon_{it} \tag{3.6} $$<u>"The historical macroeconomic factor covariance matrix is the factor return covariance matrix, and the standard error of each regression gives rise to specific risk of each stock"</u>
		- "because factor values are predetermined, the cross-sectional return variation associated with a factor depends on the cross-sectional variation of the factor exposures". cross-sectional variation associated with the market factor for the time period $t$ is $$\mathrm{Var}  \big( \boldsymbol{\beta} \big) \big( r_{Mt} - r_{ft} \big)^2   \tag{3.7} $$The vector $\boldsymbol{\beta}$ consists of betas for all stocks.
	- <u>Fundamental Factor Models</u>
		- Two groups of fundamental factors: industry factors and style factors.
		- "A stock's exposures to these factors are quite simple: they are simply the values of these attributes"
		- "a cross-sectional regression against the actual return of stocks is run to fit cross-sectional returns with cross-sectional factor exposures. The regression coefficients are called *returns on factors* for the time period. \[...] For a given period, $t$, the regression is run for the returns of the subsequent period against the factor exposure known at the time $t$" $$ r_i^{t+1} = b_0^t + b_1^t I^t_{i,1} + \cdots + b^t_{K} I^t_{i,K} + \epsilon_i \tag{3.8} $$
		- Factor return covariance matrix: run cross-sectional regression for multiple periods and calculate the covariance matrix based on the time series of factor returns. Remarks:
			- use a weighted regression, with weights being the market cap of the stock.
			- most recent factor returns are more informative to future return variances and covariances. Hence, one can put higher weights on the more recent periods and lower weights on the distant periods. weight scheme that decays in the time, i.e., $\cdots, \omega^{t-T}, \cdots, \omega^2, \omega, 1$, with the weight for the most recent period being 1 and $\omega<1$
			- "specific risks are not estimated directly and individually \[for stocks]. They are partially estimated based on some of the same fundamental characteristics that go into the factor model"
		- construction of a multifactor model is a daunting task, that is why "many quantitative managers rely on commercially available risk models and spend most of their time and energy on finding an alpha model for forecasting future returns"
	- <u>Statistical Factor Models</u>
		- "purely based on historical returns"
		- Raw covariance matrix of stock returns: $N \times N$ symmetric matrix $\boldsymbol{\Sigma}$. PCA would decompose it into $$ \boldsymbol{\Sigma} = \boldsymbol{LPL}' \tag{3.9} $$where $\boldsymbol{P}$ is a diagonal matrix $\boldsymbol{P} = \mathrm{diag} \big( \lambda_1, \cdots, \lambda_N \big)$, with $\lambda_1 > \lambda_2 > \cdots > \lambda_N > 0$ being the eigenvalues of $\boldsymbol{\Sigma}$. The matrix $\boldsymbol{L}$ is an orthogonal matrix consisting of the eigenvectors.
		- Denote $\boldsymbol{l}_i$ as the row vector and $\boldsymbol{L}_j$ as the column vector of the matrix $\boldsymbol{L}$. The row vector $\boldsymbol{l}'_j$ is the exposure of the $j$-th stock to the $N$ factors, a.k.a. *factor loadings* for each stock.
		- Each column vector of $\boldsymbol{L}$ represents "security exposures" of each individual orthogonal principal component factor.
		- Big difference between Equation 3.9 and Equation 3.3 is that there is no specific risk in Equation 3.9 because we have the same number of factors as the number of stocks.
		- Selection of principal components as statistical factors is an important step. "One mathematical tool that offers some help is the theory of random matrix (see, for example, Plerou et al. 1999)"
		- Assuming $\boldsymbol{R} = \big( r_{jt} \big)_{N \times T}$ is representing returns of $N$ securities during $T$ non-overlapping periods, and $\boldsymbol{Q} = \big( q_{jt} \big)_{N \times T}$ is reflecting return of the $N$ orthogonal principal component factors during the same $T$ periods: $$ \boldsymbol{R} = \boldsymbol{LQ} \tag{3.13} $$Factor return matrix $\boldsymbol{Q}$ can be derived by $$ \boldsymbol{Q} = \boldsymbol{L}' \boldsymbol{R} \tag{3.14} $$
- #### Risk Analysis
	- "An efficient portfolio should have risks in places where we expect excess returns, whether it is in sectors, alpha factors, or individual stocks"
	- <u>Marginal Contribution to Risk</u>
		- 