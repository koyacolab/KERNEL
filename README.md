# KERNEL
KERNEL Competition

KERNEL2.ipynd contain pipline for yield forecasting. 

Basics:

Pipeline utilizes XGBoost and CatBoost for the yield regression task, and stacked them finally by LinearRegression for the final yield forecasting.

Pipeline use initial XGBoost with added random noise feature to detect and drop low impact features.

XGBoost and CatBoost use Optuna for fine-tune hyperparameters and then they stacked for the final forecasting.

Notes:

All steps commented with TODO proposals.

Comments for some key points:

1. Cleanning dataset: NaNs have been identified only in the FAO, P, and K variables, which are related to agricultural practices.
Imputation can be performed for P and K by using the average values within each Cluster, Geozone.
For FAO, imputation can be done by using the most common value within the respective Cluster, Geozone.

Can't understand the scale of the yearly aggregate characteristics.

2. Feature extraction: implemeted PCA only (for fast test pipeline), but because the growth process of the crops is divided into critical periods, the selection of specific bases function can be more suitable: 1. Discrete Wavelet (Haar‐Wavelets), 2. Piecewise Aggregate Approximation, 3. Adaptive Piecewise Constant
