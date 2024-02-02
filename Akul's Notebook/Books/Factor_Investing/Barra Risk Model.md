
[Book Link](obsidian://open?vault=Akul's%20Notebook&file=Library%2Fjournals%2Cmagazines%2FFactor%2Fbarra-risk-model-handbook.pdf)
Author(s): Barra
Publish Year: 2007
Tags: #Factor_Investing #Risk_Management 

## <u>Chapter 1: Forecasting Risk with Multiple-Factor Models</u>
- "Barra equity models are fundamental factor models, which outperform the macroeconomic and statistical models in terms of explanatory power"
- "Barra derives MFMs (Multiple Factor Models) from asset patterns observed over time. [...] The asset exposures to these factors are specified or calculated. Then, a cross-sectional regression is performed to determine the returns to each factor over the relevant time period." `Describing the Fundamental Factor Model as described in [[Quantitative Equity Portfolio Management]]`
- Advantages of MFMs:
	- more thorough breakdown of risk than single-factor model
	- not limited by purely historical analysis
	- adapts to reflect changing asset characteristics
- MFMs "predict risk, not return; investors must choose the investment strategies themselves"
- Estimating covariance matrix of security returns using historical variance and covariance suffers from lack of data and significant estimation error.
- "The total excess return equation for a multiple-factor model can be summarised with"$$r_i =   \sum_{k=1}^K x_{ik} f_k \ + u_i   \tag{EQ 1-3}$$where $x_{ik}$ is risk exposure of security $i$ to factor $k$; $f_k$ is rate of return to factor $k$; and $u_i$ is non-factor or specific return of security $i$
- Exposures ($x_{ik}$): "By observing patterns over time, common factors can be identified and exposure to these factors can be determined. These factors are based on market or fundamental data."
- Factor Returns ($f_k$): must be estimated using asset exposures. "This is done with a cross-sectional regression of asset returns over the months on the exposures of the assets to the factors."
- Multi-asset portfolio:
	- "weights $h_{P1}, h_{P2}, \ldots, h_{PN}$ reflect weights of $N$ securities in portfolio $P$, we express the excess portfolio return:"$$ r_P = \sum_{k=1}^K x_{Pk} f_k  +  \sum_{i=1}^N h_{Pi}u_i   \tag{EQ 1-4} $$where
	  $x_{Pk} = \sum_{i=1}^N h_{Pi} x_{ik}$
	  $f_k =$ return of factor $k$
	  $h_{Pi}=$ weight of security $i$
	  $u_i =$ non-factor or specific return of security $i$
- "A central part of the model is its factor covariance matrix. This matrix contains the variances and covariances of the common factors."
- The Covariance Matrix #idea_factor_modelling 
	- "Each month, the _**estimation universe**_, which is the set of representative assets in each local market, is used to attribute asset returns to common factors and to a specific, or residual, return."
	- "The monthly returns for the estimation universe are formulated as a single matrix equation of $n$ assets and $k$ factors. Each row represents one of the assets in a portfolio or universe"
	- "The return of each asset at the end of a month, along with its factor exposures at the beginning of the month, is known. The factor returns, which are the values that best explain the asset returns, are estimated via regression. The time series of factor returns are then used to generate factor variances and covariances in the covariance matrix" `This is the 'Fundamental Factor Model as explained in [[Quantitative Equity Portfolio Management]]'`$$\begin{pmatrix} r_{(1)} \\ r_{(2)} \\ \vdots \\ r_{(n)}\end{pmatrix}    =  \begin{pmatrix} x_{(1,1)} & x_{(1,2)} &\cdots& x_{(1,k)} \\ x_{(2,1)} & x_{(2,2)} &\cdots& x_{(2,k)} \\ \vdots&\vdots&\vdots&\vdots \\ x_{(n,1)} & x_{(n,2)} &\cdots& x_{(n,k)}\end{pmatrix}      \begin{pmatrix} f_{(1)} \\ f_{(2)} \\ \vdots \\ f_{(n)}\end{pmatrix}   +  \begin{pmatrix} u_{(1)} \\ u_{(2)} \\ \vdots \\ u_{(n)}\end{pmatrix} $$
- Variance-covariance matrix of assets
	- $Risk = XFX^T + \Delta$
	  where
	  $X =$ matrix of factor exposures of $n$ assets to $k$ factors:$$\begin{pmatrix} x_{(1,1)} & x_{(1,2)} &\cdots& x_{(1,k)} \\ x_{(2,1)} & x_{(2,2)} &\cdots& x_{(2,k)} \\ \vdots&\vdots&\vdots&\vdots \\ x_{(n,1)} & x_{(n,2)} &\cdots& x_{(n,k)}\end{pmatrix}$$$F =$ factor return variance-covariance matrix of $m$ factors: $$\begin{pmatrix} Var(f_1) & Cov(f_1,f_2) &\cdots& Cov(f_1,f_k) \\ Cov(f_2,f_1) & Var(f_2) &\cdots& Cov(f_2,f_k) \\ \vdots&\vdots&\vdots&\vdots \\ Cov(f_k,f_1) & Cov(f_k,f_2) &\cdots& Var(f_{k})\end{pmatrix}$$$X^T$ transposition of $X$ matrix
	  $\Delta$ diagonal matrix of specific risk variances
- Final Risk
	- risk of portfolio:$$\sigma_P = \sqrt{h_p (XFX^T + \Delta) h^T_p }$$where
	  $\sigma_P =$ volatility of portfolio returns
	  $h_P =$ vector of portfolio weights for $N$ assets: $\begin{pmatrix} h_1 \\ \vdots \\ h_n\end{pmatrix}$


# Equity Risk
## <u>Chapter 2: Forecasting Equity Risk</u>
- Historical Beta vs. Predicted Beta:
	- Historical beta: "calculated after the fact by running a regression (often over 60 months) on a stock's excess returns against the market's excess returns"
	- Predicted beta: "a forecast of a stock's sensitivity to the market"; a.k.a fundamental beta. "In the Barra model, these risk factors include attributes–such as size, yield, and volatility–plus industry exposure."
- "Barra's equity risk models decompose asset returns into components due to common factor and a specific, or idiosyncratic, factor"
- Common Factors:
	- "Many of the influences that affect the volatility of a stock or portfolio are common factors which are prevalent across the entire market. The common factors—industry membership (and trends in that industry) and risk indices—not only help explain performance, but also anticipate future volatility"
	- Risk indices: "common dimension of style such as growth/value and smallcap/largecap can be described using risk indices"
	- "Each security is classified into an appropriate industry as defined by its operations, although a number of models support multiple-industry classification for large conglomerates"
- Specific Risk:
	- "first estimate the average specific risk of all assets covered in a model, then the specific risk of each asset relative to the universe of assets. Finally, we combine the average and relative components and scale the product to adjust for average bias."

## <u>Chapter 3: Equity Risk Modelling</u>
- 