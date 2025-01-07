# Predictive-Analytics-2025

## Article Selection

Original article: Ramirez, P., Reade, J.J., Singleton, C., Betting on a buzz: Mispricing and inefficiency in online sportsbooks, International Journal of Forecasting, 39:3, 2023, pp. 1413-1423.

Correction study: Cartlidge, J., Clegg, L., Not feeling the buzz: Correction study of mispricing and inefficiency in online sportsbooks, 2024, International Journal of Forecasting.

## Introduction

This project examines inefficiencies in the tennis betting market using crowd-sourced data. Building on the work of Ramirez et al. (2023) and Clegg & Cartlidge (2024), we replicate and extend their findings, focusing on the predictive power of the Wikipedia Relative Buzz Factor (WikiBuzz). The original study demonstrated that WikiBuzz—a metric based on pre-match Wikipedia page views—could predict systematic mispricing in bookmakers' odds, achieving a remarkable return on investment (ROI) of up to 29.38%. However, a correction study by Clegg & Cartlidge (2024) revealed data issues that reduced profitability, highlighting the transient nature of market inefficiencies as bookmakers refine their odds-setting processes.

Our work seeks to enhance the correction analysis by incorporating Lasso regression for variable selection and regularization. This methodology allows us to systematically evaluate additional predictors and identify the most impactful variables while minimizing overfitting. Using third-party tennis match data, we aim to contribute new insights into predictive modeling in betting markets and further the discussion on the importance of replication studies in sports forecasting research.

## Python Libraries with versions

### Shared Libraries

- FuncFormatter from matplotlib.ticker 3.8.3
- IV2SLS from linearmodels 6.1
- matplotlib.ticker 3.8.3
- defaultdict collections 3.4
- pandas  2.2.1
- numpy 1.26.4
- statsmodels.api 0.14.4
- statsmodels.formula.api 0.14.4
- matplotlib.dates 3.8.3

### Libraries the authors used

- seaborn 0.13.2
- fixedeffect.fe

### Libraries we added

- combinations from itertools 10.5.0
- matplotlib.pyplot 3.8.3
- train_test_split from sklearn.model_selection 1.7
- LassoCV from sklearn.linear_model 1.7
- StandardScaler from sklearn.preprocessing 1.7

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

['inverse_avg', 'rankdist', 'wikibuzz', 'b365_ratio', 'avg_ratio',  'elo_diff', 'b365_margin', 'avg_margin', 'wiki_diff_yesterday_w',  'elo_ratio', 'elo_diff_squared', 'total_games', 'surface_encoded',  'round_encoded', 'bestof_encoded', 'total_points_diff', 'points_ratio',  'streak', 'dynamic_streak', 'tournament_and_year', 'overround_b365',  'overround_avg', 'overround_best']

### Selected Regressors

['inverse_avg', 'rankdist', 'wikibuzz', 'avg_ratio', 'elo_diff',  'avg_margin', 'wiki_diff_yesterday_w', 'elo_ratio', 'elo_diff_squared',  'overround_avg']
