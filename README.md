# Decomposing the Equity Yield Term Structure

## A calculation of equity yields on Eurostoxx 50 and a variance decomposition into risk premium and expected growth.


This project is about calculating **equity yields** $e_t^{(n)}$ on the Eurostoxx 50 and to decompose them into a its dividend **risk premium** $\theta_t^{(n)}$ and expected **dividend growth** $g_t^{(n)}$: 

$$ e_t^{(n)} = \theta_t^{(n)} - g_t^{(n)} $$

$e_t^{(n)}$ is derived from dividend futures data and $g_t^{(m)}$ is estimated using a prediction OLS model and a VAR(1) model. The methodology follows that of van Binsbergen et. al. (2013). The main part of the exercise is to do a variance decomposition of equity yields to gain insights into the predictability of dividend risk premium and expected growth rates.

## Replication Files




