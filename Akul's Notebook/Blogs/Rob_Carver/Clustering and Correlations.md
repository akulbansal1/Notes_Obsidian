
Published: 20220118
Tags: #Risk_Management #Rob_Carver 
[Link](https://qoppac.blogspot.com/2016/08/trend-following-and-correlation.html)

[Code](https://gist.github.com/robcarver17/97ea44466d7f0c31b8414409f2a727a8) for this post
[Clustering code](https://github.com/robcarver17/pysystemtrade/blob/master/sysquant/estimators/clustering_correlations.py)

- Recently on [[Ep 175, Rob Carver]] Rob talked about using a clustering algorithm to cluster all 140 futures markets at his disposal into n groups.
- The author tested with n=2 to n=10. His hierarchy:
	- <u>Risk-on</u>
		- Core equities (cluster 1)
		- Mostly FX (cluster 2)
		- Random risk-on commodities
			- Italian bonds, Asian equity, Asian FX (cluster 3)
			- Asian equities, FX, some energies (cluster 4)
	- <u>Risk-off</u>
	- Generic risk-off commodities (cluster 7)
	- Bonds + flight to safety FX
		- US and German bonds (cluster 9 and 10)
		- Non US/German/Italian bonds (cluster 8)
	- Vol + Asian FX
		- US/EU vol (cluster 5)
		- Asian vol, Asian FX (cluster 6)

- "the traditional grouping of asset classes may not make as much sense as you think"