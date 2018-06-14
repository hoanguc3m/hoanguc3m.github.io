---
layout: page
title: Research
permalink: /research/
---


* *Parallel Bayesian inference for high dimensional dynamic factor copulas*, joint with [M. Concepcíon Ausín](http://portal.uc3m.es/portal/page/portal/dpto_estadistica/personal/Concepcion_Ausin) and [Pedro Galeano](http://portal.uc3m.es/portal/page/portal/dpto_estadistica/home/members/pedro_galeano_san_miguel) (UC3M)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  We propose a class of dynamic factor copulas for financial data where the dynamic correlation are modelled as generalized autoregressive score (GAS) processes. The model could account for the asymmetric dependence in extreme events. 
We implement an parallel algorithm to estimate the different pamameters of the factor copula models.
An empirical example is illustrated for the stock price of 150 companies listed in S&P500. 


More information: [Paper](https://github.com/hoanguc3m/Talk/raw/master/01_Dyfacopula/WP1-24-09-2017.pdf) -
[Appendix](https://github.com/hoanguc3m/Talk/raw/master/01_Dyfacopula/WP1_onlineAp.pdf) -
[Slides](https://github.com/hoanguc3m/Talk/raw/master/01_Dyfacopula/sevilla_pre.pdf) - 
[Poster](https://github.com/hoanguc3m/Talk/raw/master/01_Dyfacopula/poster_ISBA.pdf) - [Code](https://github.com/hoanguc3m/FactorCopula) 

* *What are the drivers of the Swedish sustainable development path? New evidence from Bayesian Dynamic Linear Models*, joint with Jesper Stage, Magnus Lindmark, Huong Nguyen Thu

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  According to my knowledge, we are the first who aim to find out the dynamic relationship between genuine savings (GS) and long term well-being represented by future consumptions (PVC). By extending the measure of GS to account for wider range of impacts on natural resource, human capital and technological progress, we  apply Bayesian approach to estimate Dynamic Linear Models (DLMs). We discover that there are increasing dependent trends with all explanatory GS variables and provide a new empirical evidence on the technological progress that underpin Swedish sustainable development.  The dynamic model also provides a trivial framework for testing the hypothesis that their relationship approach to one as the net investment term includes more types of capital.

More information: [Paper](https://github.com/hoanguc3m/Talk/raw/master/00_sustaindev/20170308.pdf) - 
[Slides](https://github.com/hoanguc3m/Talk/raw/master/00_sustaindev/slide20170623.pdf) 


 
* *Variational Bayesian inference for high dimensional structured factor copulas*, joint with [M. Concepcíon Ausín](http://portal.uc3m.es/portal/page/portal/dpto_estadistica/personal/Concepcion_Ausin) and [Pedro Galeano](http://portal.uc3m.es/portal/page/portal/dpto_estadistica/home/members/pedro_galeano_san_miguel) (UC3M)

Factor copula models have been recently proposed for describing the joint distribution of a large number of variables in terms of a few common latent factors. 
In this paper, we employ a Bayesian procedure to make a fast inference for multi-factor and structured factor copulas. 
To deal with the high dimensional structure, we apply a Variational Inference (VI) approximation to estimate the different specifications of factor copula models. 
Compared to the Markov chain Monte Carlo (MCMC) approach, the VI approximation is much faster and could handle a sizeable problem in a few seconds.
Another issue of factor copulas is that the bivariate links among the nodes are unknown in high dimensions. We derive an automated procedure to recover the dependence structure. By taking advantage of the posterior samples, we inspect the initial assumption of bivariate copula functions and switch for a better one by minimizing Bayesian information criterion (BIC). 
The simulation in different context shows that the procedures of bivariate copula selection could be at least 80\% accuracy compared to the true generated copula model. We illustrate our proposed procedure with high dimensional real data sets in different contexts.

More information: [Paper]() -
[Slides]() - 
[Poster](https://github.com/hoanguc3m/Talk/raw/master/02_vifcop/poster2.pdf) - [Code](https://github.com/hoanguc3m/vifcopula) 

