
### 2.1 Portfolio sorting method

**The factor-simulating portfolio should meet two conditions:**
- Condition 1: The portfolio has an exposure greater than zero only on the target factor and zero exposure on other factors
- Condition 2: Among all portfolios that meet Condition 1, the portfolio has the lowest idiosyncratic risk

**One method for constructing factor-simulating portfolios is the portfolio sorting method. We will use the book-to-market ratio (BM) valuation to introduce the sorting method. We call BM the sorting variable. The core idea of ​​the sorting method is to use the value of the individual stock on the BM variable to replace the exposure of the individual stock to the factor. The sorting method is divided into three steps:**
1. Sorting: Sort all the stocks in the stock pool from high to low according to the sorting variable (which can be a feature or factor, in this case BM)
2. Grouping: Divide all the stocks into L groups according to the ranking (all the stocks can be divided into 10 groups according to the deciles of the variable value distribution, L=10, or other methods can be used for grouping). Go long on the stocks in the first group with the highest ranking, and go short on the stocks in the last group with the lowest ranking. We call this method of constructing a long-short hedge portfolio a spread portfolio. We know that the returns of the spread portfolio are the returns of the highest $\frac{1}{N}$ stock and the lowest $\frac{1}{N}$ stock, respectively. Their difference reflects the return of the factor constructed around the variable, and the spread portfolio is the factor simulation portfolio constructed using the sorting method. The return of the spread portfolio is the return of the factor.
3. Update: In terms of time series, since the exposure of stocks to the factor changes over time, we use a method called rebalancing to update. The frequency of balancing is divided into monthly or annual (it can also be daily, define the frequency according to your own thinking). After constructing such a factor simulation portfolio in each period, calculate the return of the portfolio between the current moment and the next balancing moment, and go back and forth in time series to obtain the time series of factor returns.

**Through the sorting method, we can easily construct factor-simulated portfolios. Once we have calculated the factor returns and the returns of the L portfolios obtained by the sorting method, we can use a method called the portfolio sort test**

**The most important purpose of the portfolio sort test is to test the expected returns of the factors. The test focuses on whether the factor returns calculated based on the sample data can reject the null hypothesis at a given significance level. We Set ${\lambda_t} (t = 1, 2, ..., T)$ represents the factor return time series, then the estimated factor return $\hat{\lambda}$ and the standard error s.e.($\hat{\lambda}$) are:**
$$
\begin{align*}
\hat{\lambda} = \frac{1}{T}\sum^{T}_{t=1}\lambda_t \tag{2.1} \\
s.e.(\hat{\lambda}) = \frac{std(\lambda_t)}{\sqrt{T}} \tag{2.2}
\end{align*}
$$
- $std(\lambda_t)$ represents the standard deviation of $\lambda_t$. The above formula shows that taking the average of ${\lambda_t}$ will give an estimate of the expected rate of return.

**We can calculate t-statistic under the null hypothesis ($\lambda = 0$) and perform t-test:**
$$t-statistic = \frac{\hat{\lambda}}{s.e.(\hat{\lambda})} \tag{2.3}$$
- Based on t-statistic, we can directly calculate p-value, p-value in Range$(0.05, 0.1)$, t-statistic in Range$(2.0, 2.6)$. Such a range indicates a significant level

**The high and low rankings of the returns of L investment portfolios are called $X_r$, and the high and low rankings of them grouped by the ranking variable are called $X_g$. The correlation coefficient between the two is the Rank correlation coefficient $\rho_s$ of the return and the ranking variable grouping:**
$$\rho_s = \frac{cov(X_r, X_g)}{\sigma x_r \sigma x_g} \tag{2.4}$$
- When the returns of L investment portfolios increase perfectly with the variable grouping, the Rank correlation coefficient between the two is 1, and when it decreases, it is -1

**In order to solve the problem that univariate sorting is difficult to control the influence of other factors, we propose a multiple sorting method**

...