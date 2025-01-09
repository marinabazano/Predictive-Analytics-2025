# Still No Buzz: Correction study of mispricing and inefficiency in online sportsbooks

## Article Selection  

- **Original Article**: Ramirez, P., Reade, J.J., Singleton, C., *Betting on a Buzz: Mispricing and Inefficiency in Online Sportsbooks*, *International Journal of Forecasting*, 39(3), 2023, pp. 1413-1423.  
- **Correction Study**: Cartlidge, J., Clegg, L., *Not Feeling the Buzz: Correction Study of Mispricing and Inefficiency in Online Sportsbooks*, 2024, *International Journal of Forecasting*.  

## Introduction  

This project investigates inefficiencies in the tennis betting market through the lens of crowd-sourced data, with a focus on replicating and extending the findings from two influential studies. The original article by Ramirez et al. (2023) introduced the Wikipedia Relative Buzz Factor (WikiBuzz), a novel metric based on pre-match Wikipedia page views. The study demonstrated that WikiBuzz could predict systematic mispricing in bookmakers' odds, achieving an impressive return on investment (ROI) of up to 29.38%. However, the correction study by Clegg & Cartlidge (2024) identified data quality issues, specifically a single erroneous bet, which significantly altered the reported profitability. Their findings emphasized the importance of replication studies and highlighted how market inefficiencies evolve as bookmakers refine their odds-setting methodologies.  

Building on these studies, our project extends the correction analysis using Lasso regression for variable selection and regularization. This methodology systematically evaluates additional predictors and identifies the most impactful variables while minimizing the risk of overfitting. Leveraging third-party tennis match data, we aim to provide deeper insights into predictive modeling in betting markets and contribute to the growing discourse on the value of reproducible research in sports forecasting.  

## Python Libraries with Versions  

### Shared Libraries  

- `FuncFormatter` from `matplotlib.ticker` 3.8.3  
- `IV2SLS` from `linearmodels` 6.1  
- `matplotlib.ticker` 3.8.3  
- `defaultdict` from `collections` 3.4  
- `pandas` 2.2.1  
- `numpy` 1.26.4  
- `statsmodels.api` 0.14.4  
- `statsmodels.formula.api` 0.14.4  
- `matplotlib.dates` 3.8.3  

### Libraries the Authors Used  

- `seaborn` 0.13.2  
- `fixedeffect.fe`  

### Libraries We Added  

- `combinations` from `itertools` 10.5.0  
- `matplotlib.pyplot` 3.8.3  
- `train_test_split` from `sklearn.model_selection` 1.7  
- `LassoCV` from `sklearn.linear_model` 1.7  
- `StandardScaler` from `sklearn.preprocessing` 1.7  

## Extension with Lasso  

### Feature Engineering  

python
b365_ratio = b365w / b365l  
avg_ratio = avgw / avgl  
b365_margin = b365w - b365l  
wiki_trend_diff_w = wiki_mean7_w - wiki_mean30_w  
wiki_diff_yesterday_w = wiki_yesterday_w - wiki_twodays_w  
elo_diff = elo_pi_hat - elopredict  
set_diff = wsets - lsets  
outcome = 1 for winners; 0 for losers  


### Candidate Regressors

['inverse_avg', 'rankdist', 'wikibuzz', 'b365_ratio', 'avg_ratio',  'elo_diff', 'b365_margin', 'avg_margin', 'wiki_diff_yesterday_w',  'elo_ratio', 'elo_diff_squared', 'total_games', 'surface_encoded',  'round_encoded', 'bestof_encoded', 'total_points_diff', 'points_ratio',  'streak', 'dynamic_streak', 'tournament_and_year', 'overround_b365',  'overround_avg', 'overround_best']

### Selected Regressors

['inverse_avg', 'rankdist', 'wikibuzz', 'avg_ratio', 'elo_diff',  'avg_margin', 'wiki_diff_yesterday_w', 'elo_ratio', 'elo_diff_squared',  'overround_avg']
