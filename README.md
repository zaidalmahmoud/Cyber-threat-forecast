Code of paper "A holistic and proactive approach to forecasting cyber threats
and trend analysis".

**This project contains univariate and multivariate implementation of Bayesian Long short-term memory (B-LSTM) for forecasting cyber-threats**.


# Project overview
Each of the univariate and multivariate folders contains 2 jupyter-notebooks. The first is for optimising the model, called "hp_optimisation_u" or "hp_optimisation_m", and the second for the final forecast, called "forecast_u" or "forecast_m". The dataset is in the directory "input_data" and is read in the code. The model optimisation code writes the results to 2 folders, which are "output_validation_results" and "output_hyperparameters". The "output_validation_results" contains some plots and hyperparameters of good performing models (error below some threshold), while the folder "output_hyperparameters" contains the hyperparameters of the final optimised models. The "forecast" code reads the optimised model hyperparameters from the folder "output_hyperparameters" to train the final model on the complete data and generate future trend forecasts using 3 different seeds (to choose the most reasonable from the 3 results). These forecasts are saved to the folder "output_forecast" as text files and plots.

# Notes
In the model optimisation code, 42 models for 42 attack types are optimised and saved. In the forecast code, the attacks included (see "attacks" list) in the univariate approach are those that were better forecasted (had a model with lower error) when using the univariate approach. Similarly, the attacks included in the multivariate approach are those that were better forecasted (had a model with lower error) when using the multivariate approach. However, it is possible to modify the code to forecast all the 42 attacks for each approach, by optimising the model of all attacks in the optimisation code and then adding the missing attacks (their column names) manually in the forecast code to the "attacks" list.




