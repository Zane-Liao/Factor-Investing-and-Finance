### Linear Factor Model

**CAPM asset pricing option formula$$E[R_i] - R_f= \beta (E[R_M] - R_f) \tag{1.1}$$
- $R_i$ is the rate of return of an asset $i$
- $R_f$ is the risk-free rate of return
- $R_M$ is the rate of return of the market portfolio
- $\beta_i = \frac{\text{Cov}(R_i, R_m)}{\text{Var}(R_m)}$ the degree of exposure of asset $i$ to market risk

**APT arbitrage pricing theory$$E[R^{e}_i] = \beta^{'}_i \lambda \tag{1.2}$$
Pricing Error$$E[R^{e}_i] = \alpha_i + \beta^{'}_i \lambda \tag{1.3}$$
- The expected excess return of an asset is the weighted average of its exposure to systematic risk factors ($\beta_i$​) multiplied by the premium of each factor ($\lambda$)

**Factors are to assets as food is to nutrients, and we define the two necessary conditions that factors must meet as follows:

- Factors drive the co-movement of asset returns, so factors must be related to the covariance matrix of asset returns
- In the long run, factors can obtain positive returns, which means that factors must be priced.

**Pricing factors and anomaly factors

- The academic community has rigorously divided the general types of factors, but the industry does not. The industry believes that factors that can obtain excess returns are good factors, and does not pay attention to the type of factors themselves
- We need to know that $\beta^{'}_i \lambda$ is a pricing model, so the factors it contains are called pricing factors, and $\alpha_i$ represents assets that can obtain multi-factor models but cannot explain excess returns, which are called anomaly factors

**Multi-factor models are models of the mean. From the perspective of time series, asset excess returns and factor returns satisfy the following in time series:
$$R^{e}_{it} = \alpha_i + \mathbf{\beta^{'}_i} \lambda_t + \epsilon_{it} \tag{1.4}$$
- $R^{e}_{it}$ represents the excess return of asset $i$ at time $t$
- $\lambda_t$ represents the factor return at time t
- $\epsilon_{it}$ represents the random disturbance at time t

**We put the time series multivariate regression model of N assets together:
$$R^{e}_{t} = \mathbf{\alpha} + \mathbf{\beta^{'}} \lambda_t + \mathbf{\epsilon_{t}} \tag{1.5}$$
- $R^{e}_t = [R^{e}_{1t}, R^{e}_{2t}, ...,R^{e}_{Nt}]$ Excess Return (With N-Dimension Vector)
- $\mathbf{\alpha} = [\alpha_1, \alpha_2, ..., \alpha_N]$ Pricing (With N-Dimension Vector)
- $\beta = [\beta_1, \beta_2, ..., \beta_N] is the N \times K$ factor exposure matrix (Matrix)
- $\mathbf{\epsilon_t} = [\epsilon_{1t}, \epsilon_{2t}, ..., \epsilon_{Nt}]$ random perturbation (With N-Dimension Vector)

**The above formula satisfies $E[\epsilon_t] = 0$ and $cov(\lambda_t, \epsilon_t) = 0$. We calculate the Covariance Matrix ($\Sigma$) on both sides and get:
$$\Sigma = \beta\Sigma_\lambda\beta^{'} + \Sigma_\epsilon \tag{1.6}$$
- $\Sigma$ is the Covariance Matrix of N assets (With N-Order Matrix)
- $\Sigma_\lambda$ is the Covariance Matrix of K factors (With K-Order Matrix)
- $\Sigma_\epsilon$ is the Covariance Matrix of N random perturbations (With N-Order Diagonal Matrix, Because $\epsilon_{it}$ are independent of each other)
