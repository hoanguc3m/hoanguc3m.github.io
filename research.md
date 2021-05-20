---
layout: page
title: Research
permalink: /research/
---

**[6. A dynamic leverage stochastic volatility model]()**, 

<span style="font-size:0.5em;"> 
Hoang Nguyen, Trong-Nghia Nguyen, Minh-Ngoc Tran\\
Abstract: Stock returns are considered as a convolution of two random processes that are the return innovation and the volatility innovation. The correlation of these two processes tends to be nega-
tive which is the so-called leverage effect. In this study, we propose a dynamic leverage stochastic volatility (DLSV) model where the correlation structure between the return innovation and the
volatility innovation is assumed to follow a generalized autoregressive score (GAS) process. We find that the leverage effect is reinforced in the market downturn period and weakened in the
market upturn period.
</span>


**[5. Dynamic relationship between Stock market and Bond market: A GAS MIDAS copula approach]()**, 

<span style="font-size:0.5em;"> 
Hoang Nguyen, Farrukh Javed \\
[Paper]() - [Slides]() - [Code](https://github.com/hoanguc3m/GASCopula) \\
Abstract: There is evidence that macroeconomic variables influence the relationship among financial variables, however they are sampled at different frequencies. This study proposes a generalized autoregressive score mixed frequency data sampling (GAS MIDAS) copula approach to analyze the dynamic relationship between Stock returns and Bond returns. A GAS MIDAS copula decomposes their dependence into a short-run and a long-run correlation. While the long term effect is updated at a lower frequency using MIDAS, the short term effect follows a GAS process. Asymmetric dependence at different quantiles are taken into account. The model helps to improve the in-sample goodness of fit and the out-of-sample forecast.
</span>

**[4. VAR models with fat tails and asymmetry](https://hoanguc3m.github.io/Talk/05_fatbvars/WP5-20-05-2021.pdf)**

<span style="font-size:0.5em;"> 
Sune Karlsson, Stepan Mazur, Hoang Nguyen \\
[Paper](https://hoanguc3m.github.io/Talk/05_fatbvars/WP5-20-05-2021.pdf) -
[Slides](https://hoanguc3m.github.io/Talk/05_fatbvars/WP5-slides-04-11-2020.pdf) -  [Code](https://github.com/hoanguc3m/fatBVARS) \\
Abstract: With the uncertain changes of the economic environment, macroeconomic downturns during recessions and crises can hardly be explained by a Gaussian structural shock. There is evidence that the distribution of macroeconomic variables is fat-tailed and asymmetric. 
In this paper, we contribute to the literature by extending the VAR models to account for a more realistic assumption of the multivariate distribution of the macroeconomic variables. We propose a general class of Generalized Hyperbolic Skew Student's-t distribution with stochastic volatility (Skew-t.SV) VAR that allows us to take into account fat tails and asymmetry. The Bayesian inference using a Gibbs sampler is extended to make inferences of model parameters. 
We present evidence of fat tails and asymmetry for monthly macroeconomic variables. The analysis also gives a clear message that asymmetry should be taken into account to have a better prediction during recession and crisis. .
</span>

**[3. What are the drivers of the Swedish sustainable development path? New evidence from Bayesian Dynamic Linear Models](https://hoanguc3m.github.io/Talk/00_econ/20170308.pdf)**, 

<span style="font-size:0.5em;"> 
Jesper Stage, Magnus Lindmark, Hoang Nguyen, Huong Nguyen Thu \\
[Paper](https://hoanguc3m.github.io/Talk/00_sustaindev/20170308.pdf) - 
[Slides](https://hoanguc3m.github.io/Talk/00_sustaindev/slide20170623.pdf) 
<!---
According to my knowledge, we are the first who aim to find out the dynamic relationship between genuine savings (GS) and long term well-being represented by future consumptions (PVC). By extending the measure of GS to account for wider range of impacts on natural resource, human capital and technological progress, we  apply Bayesian approach to estimate Dynamic Linear Models (DLMs). We discover that there are increasing dependent trends with all explanatory GS variables and provide a new empirical evidence on the technological progress that underpin Swedish sustainable development.  The dynamic model also provides a trivial framework for testing the hypothesis that their relationship approach to one as the net investment term includes more types of capital. 
-->
</span>


**[2. Variational Inference for high dimensional structured factor copulas](https://hoanguc3m.github.io/Talk/02_vifcop/WP2-04-05-2020.pdf)**

<span style="font-size:0.5em;"> 
Hoang Nguyen, M. Concepcíon Ausín and Pedro Galeano \\ 
[Computational Statistics & Data Analysis (2020)](https://www.sciencedirect.com/science/article/abs/pii/S0167947320301031). \\
[Paper](https://hoanguc3m.github.io/Talk/02_vifcop/WP2-04-05-2020.pdf) -
[Appendix](https://hoanguc3m.github.io/Talk/02_vifcop/WP2_onlineAp.pdf) -
[Slides](https://hoanguc3m.github.io/Talk/02_vifcop/slides2.pdf) - 
[Poster](https://hoanguc3m.github.io/Talk/02_vifcop/poster2.pdf) - [Code](https://github.com/hoanguc3m/vifcopula) 
<!---
In this paper, we make two contributions to the literature of factor copula models. First, we employ a Variational Bayesian algorithm to make fast inference for multi-factor and structured factor copulas. Compared to the Markov chain Monte Carlo (MCMC) approach, the VI approximation is much faster and could handle a sizeable problem in a few seconds with high accuracy. Second, we derive an automated procedure to recover the dependence structure. By taking advantage of the posterior sample means, we inspect the initial assumption of bivariate copula functions and switch for a better one by minimizing Bayesian information criterion (BIC). The simulation in different context shows that the procedures of bivariate copula selection could be at least 80% accuracy compared to the true generated copula model.
-->
</span>


**[1. Parallel Bayesian inference for high dimensional dynamic factor copulas](https://hoanguc3m.github.io/Talk/01_Dyfacopula/WP1-31-10-2018.pdf)**

<span style="font-size:0.5em;"> Hoang Nguyen, M. Concepcíon Ausín and Pedro Galeano \\
[Journal of Financial Econometrics (2019)](https://doi.org/10.1093/jjfinec/nby032) \\
[Paper](https://hoanguc3m.github.io/Talk/01_Dyfacopula/WP1-31-10-2018.pdf) -
[Appendix](https://hoanguc3m.github.io/Talk/01_Dyfacopula/WP1_onlineAp.pdf) -
[Slides](https://hoanguc3m.github.io/Talk/01_Dyfacopula/sevilla_pre.pdf) - 
[Poster](https://hoanguc3m.github.io/Talk/01_Dyfacopula/poster_ISBA.pdf) - [Code](https://github.com/hoanguc3m/FactorCopula) 
<!---
We propose a class of dynamic factor copulas for financial data where the dynamic correlation are modelled as generalized autoregressive score (GAS) processes. The model could account for the asymmetric dependence in extreme events. We implement an parallel algorithm to estimate the different pamameters of the factor copula models. An empirical example is illustrated for the stock price of 140 companies listed in S&P500. 
-->
</span>





 

