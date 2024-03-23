# KERNEL Competition
KERNEL Data Scientist interview position 

KERNEL3.ipynd - contain pipline for yield forecasting. 

Сoefficient of determination R2 ~ 83%.

Basics:

Pipeline utilizes XGBoost and CatBoost for the crop yield regression task, and stacked them finally by LinearRegression for the final yield forecasting.

Pipeline use initial XGBoost with added random noise feature to detect and drop low impact features.

XGBoost and CatBoost use Optuna for fine-tune hyperparameters and then they stacked for the final forecasting.

All steps are commented with TODO proposals.

Comments for some points:

1. Data cleanning: NaNs have been identified only in the FAO, P, and K variables, which are related to agricultural practices.
Gap filling can be performed for P and K by using the average values within each Cluster, Geozone.
For FAO, gap filling can be done by using the most common value within the respective Cluster, Geozone.
Extreme outliers in K_[kg/ha] (< 0) were found and removed, but if the sign is an error, it can be changed or flagged as NaN and gap filling can be applied.
N.B. Can't understand the scale of the yearly aggregate features.

2. Feature extraction: implemeted PCA only (for pipeline fast test), but because the crop growth process is divided into critical periods, the selection of specific basis function can be more suitable: 1. Piecewise Aggregate Approximation, 2. Adaptive Piecewise Constant, 3. Discrete Wavelet (Haar‐Wavelets)

3. TODO: features importance training experiments.


