# Predictive-Analytics-2025

## Article Selection

Original article: Ramirez, P., Reade, J.J., Singleton, C., Betting on a buzz: Mispricing and inefficiency in online sportsbooks, International Journal of Forecasting, 39:3, 2023, pp. 1413-1423.

Correction study: Cartlidge, J., Clegg, L., Not feeling the buzz: Correction study of mispricing and inefficiency in online sportsbooks, 2024, International Journal of Forecasting.

## Introduction

## Python Libraries with versions

### Shared Libraries

### Libraries the authors used

### Libraries we added


## Extension with LASSO

### Feature Engineering

b365_ratio = b365w/b365l
avg_ratio = avgw/avgl
b365_margin = b365w-b365l
wiki_trend_diff_w = wiki_mean7_w - wiki_mean30_w
wiki_diff_yesterday_w = wiki_yesterday_w - wiki_twodays_w
elo_diff = elo_pi_hat - elopredict
set_diff = wsets - lsets
outcome = 1 for winners ; 0 for losers

### Candidate Regressors

### Selected Regressors
