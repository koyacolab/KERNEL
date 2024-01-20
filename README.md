# KERNEL
KERNEL Competition

KERNEL2.ipynd contain pipline for yield forecasting. 

Basics:

Pipeline utilizes XGBoost and CatBoost for the yield regression task, and stacked them finally by LinearRegression for the final yield forecasting.

Pipeline use initial XGBoost with added random noise feature to detect and drop low impact features.

XGBoost and CatBoost use Optuna for fine-tune hyperparameters and then they stacked for the final forecasting.

Notes:

All steps commented with TODO proposals.


