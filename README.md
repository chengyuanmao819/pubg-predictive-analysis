# Exploring Predictive Models on PUBG Dataset

**Author:** Chengyuan Mao  
**Affiliation:** University of California, San Diego

## Abstract
This report presents an exploratory analysis and predictive modeling task on the PUBG dataset. I analyze the dataset's properties, propose a predictive model to estimate players' win placement percentage based on in-game statistics, compare it with baselines, and discuss my findings and conclusions. My approach demonstrates that key features like kills, damage dealt, and distance traveled significantly impact player performance, paving the way for better understanding of success factors in battle royale games.

## Dataset Description and Exploratory Analysis
Selected the PlayerUnknown's Battlegrounds (PUBG) dataset containing game statistics from over 4.4 million observations, capturing various in-game activities and performance metrics.

Key findings from exploratory data analysis:

* **Basic statistics:** Large number of features with varying scales and distributions. High variance in features like damageDealt, walkDistance, and kills.
* **Missing values:** Only one missing value in winPlacePerc column, which was dropped.
* **Data distributions:** Most features showed skewed distributions, suggesting outliers.
* **Correlation Analyses:** Significant positive correlations between walkDistance, kills, damageDealt, and winPlacePerc.
* **Feature Selection:** Dropped low-correlation features like roadKills, teamKills, killPoints, rankPoints, and winPoints.

**Interesting Findings:**
* Players covering more distance tend to achieve better final placements
* Certain features had negligible impact on outcomes

## Predictive Task and Evaluation
Task: Predict player's final placement percentage (winPlacePerc) based on in-game statistics.

### Evaluation Strategy
* **Performance Metric:** Mean Squared Error (MSE)
* **Train-Test Split:** 80% training, 20% validation
* **Baselines:** Linear Regression, Ridge Regression, Lasso Regression

## Model Description
Experimented with various models:

**Linear Models:**
* Linear Regression: Baseline model
* Ridge Regression: Added L2 regularization
* Lasso Regression: Used L1 regularization for feature selection

**Ensemble Models:**
* Random Forest: Captured non-linear relationships
* LightGBM: Optimized for training speed and performance

## Results and Conclusions

### Model Performance
* **Random Forest:** Best MSE of 0.000052
* **LightGBM:** MSE of 0.000596
* **LightGBM with Optuna:** Improved MSE to 0.000278

### Key Features
* walkDistance
* KillPlace
* survival_efficiency
* totalDistance

### Final Conclusions
* Ensemble models outperformed linear models
* LightGBM provided best balance of performance and efficiency
* Movement and strategic positioning crucial for success
* Future work could explore deep learning approaches

## References
1. PUBG Finish Placement Prediction, Kaggle
2. Chocozzz, "How to Save Time and Memory with Big Datasets," Kaggle