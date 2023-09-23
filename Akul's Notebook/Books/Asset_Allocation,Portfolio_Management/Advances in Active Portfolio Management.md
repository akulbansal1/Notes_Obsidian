
[Book Link](obsidian://open?vault=Akul's%20Notebook&file=Library%2Fbooks_Personal%2Fquant%2FRichard%20Grinold%2C%20Ronald%20Kahn%20-%20Advances%20in%20Active%20Portfolio%20Management_%20New%20Developments%20in%20Quantitative%20Investing-McGraw-Hill%20Education%20(2020).pdf)
Author(s): Grinold, and Kahn
Publish Year: 2019
Tags: #Portfolio_Management #Quant recommended by Navneet Arora (head of Quant at Citadel)

## <u>Chapter 1: Introduction: Advances in Active Portfolio Management</u>
- "The fundamental law of active management (...) shows that high information ratios require some winning combination of skill in making investment decisions; breadth of those decisions, for diversification; and efficiency of implementation, so that the portfolio accurately captures the manager's views".
- Section 1: "recaps *Active Portfolio Management*"
- Section 2: "covers advances in active portfolio management"
- Section 3: "covers applications of active portfolio management"
- "equation numbers and exhibit numbers begin anew with each chapter. Because the chapters began as independent articles, there is no referencing of equations in one chapter by another chapter."


# <u>Section 1: Recap of Active Portfolio Management</u>
## <u>Chapter 2: Introduction to the Recap of <i>Active Portfolio Management</i> section</u>
- articles that "recap some of the key elements of that predecessor book"
	1. "Seven Insights into Active Management" by Ronald N. Kahn
	2. "A Retrospective Look at the Fundamental Law of Active Management" by Richard C. Grinold and Ronald N. Kahn
	3. "Breadth, Skill, and Time" by Richard C. Grinold and Ronald N. Kahn
- "High information ratios follow from high levels of skill and/or high breadth or diversification"
- "Every active manager, no matter their investment style, must articulate some winning combination of skill, breadth, and efficiency. Quantitative strategies tend to focus on all three of these. Fundamental strategies aim in particular for high *IC*—deep understanding of the relatively few stocks they hold—in combination with lower breadth and efficiency."


## <u>Chapter 3: Seven Insights into Active Management</u>
- Framework
	- "We separate asset (and portfolio) returns into a systematic (benchmark) component and a residual component", denoted by $\theta$, here:![[Screenshot 2023-09-14 at 7.03.52 PM.png]]
	- CAPM states that "the expected residual return is zero. However, the active manager, having identified some useful information, *g*, forecasts residual returns not equal to zero.  ![[Screenshot 2023-09-22 at 1.47.10 PM.png]]
		- "Much of the job of an active manager is to forecast residual returns. Active managers can also forecast market returns, and some do. (...) however, it's difficult to deliver consistent performance by implementing such forecasts (timing the market)"
	- "to connect forecast residual returns with optimal portfolios", they use Markowitz mean-variance optimisation. "Given out alpha forecast and risk forecasts for any possible portfolio, we can find the portfolio that achieves the highest expected alpha for any given risk level"
- **Insight 1: Active Management is Worse Than a Zero-Sum Game**
	- "Sharpe concluded that the (asset-weighted) *average* active manager matches the market's performance before fees and costs"
	- Fama and French (2010) "showed that active US equity mutual funds have produced a realised alpha of roughly zero on average before fees over the period from 1984 through 2006. They estimated average realised alpha after fees to be somewhere between -0.81% and -1.13% per year". "Our definition of alpha controls for only one factor—the market (or a broad market index)—but Fama and French also controlled for size and value factors and, in their four-factor analysis, momentum"
- **Insight 2: Information Ratios Determine Added Value**
	- "the consistency of performance is a monotonic function of the information ratio: the highest the information ratio, the more likely it that the manager will realise positive residual return in any period"
	- "typical before-expenses distribution of information ratios"![[Screenshot 2023-09-22 at 2.17.35 PM.png]]![[Screenshot 2023-09-22 at 2.18.26 PM.png]]
- **Insight 3: Allocate Risk Budget in Proportion to Information Ratios**
	- "Investors allocate risk in proportion to information ratios. [...] She allocates the most risk to [highest Information Ratio] manager but still diversifies among other managers"
- **Insight 4: Alphas Must Control for Skill, Volatility, and Expectations**
	- "Raw signals, such as analyst earnings forecasts, broker buy/sell recommendations, and the number of cars in a Walmart parking lot the week before Christmas, hopefully contain information useful in forecasting returns. But these raw data are not alphas (expected residual returns)"
	- "The basic forecasting formula provides the best linear unbiased estimate (BLUE) of the residual return, given the raw signal, *g*:"![[Screenshot 2023-09-22 at 2.31.44 PM.png]]![[Screenshot 2023-09-22 at 2.39.07 PM.png]] "As discussed, [...] the unconditional expected residual return is zero, and alpha is the expected residual return conditional on the manager's information, *g*"
	- Using equation 16:![[Screenshot 2023-09-22 at 2.40.19 PM.png]]"We commonly refer to the correlation of the signal and the subsequent realisation as the *information coefficient* (IC), and the standard deviation of the residual return is the residual risk, $\omega$ ". "We refer to the standardised raw signals as a z-score because by construction it has a mean of 0 and a standard deviation of 1. [...] Putting this together, we get:"![[Screenshot 2023-09-22 at 2.46.30 PM.png]]"We have decomposed alpha into three components: an information coefficient, a volatility, and a score"
	- "if the information coefficient is zero, the manager correctly forecasts the sign of the residual return 50% of the time. [...] Exhibit 6 converts information coefficients into probabilities of forecasting the correct sign"![[Screenshot 2023-09-22 at 2.53.29 PM.png]]
- **Insight 5: The Fundamental Law of Active Management: Information Ratios Depend on Skill, Diversification, and Efficiency**
	- "information coefficient, a measure of skill; breadth, a measure of diversification; and the transfer coefficient, a measure of efficiency of implementation"![[Screenshot 2023-09-22 at 5.51.30 PM.png]]
	- "Old information decays as new information arrives. In equilibrium, the two are in balance, and so the information turnover rate, $\gamma$ captures both the decay rate of old information and the arrival rate of new information". "old information decays over time and new information, s(t), arrives over time"![[Screenshot 2023-09-22 at 5.58.24 PM.png]]"we can show that the breadth of this forecast is:"![[Screenshot 2023-09-22 at 6.05.31 PM.png]]
	- "Given a signal for *N* assets over time, we can estimate the coefficient, $\gamma$ , using Equation (23) and then estimate breadth via Equation (24). For example, if we run a cross-sectional regression of $\alpha$(*t*) against $\alpha$ (*t* - $\Delta$t), we can estimate *e*^(- $\gamma$ $\Delta$t) as a regression coefficient"
		- "imagine we follow 300 stocks and every week we receive new information on 12 of those stocks. We don't know ahead of time which 12 stocks the new information will cover. Our breadth is 12 x 52 = 624"
	- 