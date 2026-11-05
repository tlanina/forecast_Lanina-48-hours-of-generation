
# Solar Generation Forecasting

This project focuses on forecasting solar electricity generation for the next 48 hours using historical generation data and weather information.
The project explores different forecasting methods, including HistGradientBoostingRegressor, LightGBM, SEASONAL REGRESSION + XGBOOST RESIDUAL
. The models are evaluated using rolling validation and compared with the Seasonal Naive benchmark.
## Repository Structure

## How to Run the Project

1. Download or clone this repository.
2. Make sure that `train.csv` and `weather_forecast.csv` are in the same folder as the notebook.
3. Open `forecast_lanina.ipynb` in Jupyter Notebook or Google Colab.
4. Install the required libraries if they are not already installed:

```python
!pip install pandas numpy matplotlib scikit-learn xgboost statsmodels
```

5. Run the notebook cells from top to bottom.
6. The notebook trains the forecasting model using the historical data and weather variables.
7. The final forecast for the next 48 hours is saved as `LANINA_project.csv`.

The output file contains the following columns:

- `ds` — forecast timestamp
- `forecast` — predicted electricity generation
- `lower_95` — lower bound of the 95% prediction interval
- `upper_95` — upper bound of the 95% prediction interval

## Data

The project uses two input files:
- `train.csv` — historical solar generation data and weather variables.
- `weather_forecast.csv` — weather forecast data for the next 48 hours.

Both files must be uploaded to the repository and placed in the same folder as the notebook.

## Evaluation
The models are evaluated using:
- RMSE
- MAPE
- Prediction interval coverage
- Winkler score

Rolling validation is used to test the models on different 48-hour windows. The results are compared with the Seasonal Naive benchmark.

## Limitations

Solar generation depends strongly on weather conditions. Changes in cloud cover and other weather variables can lead to large forecasting errors.
HistGradientBoostingRegressor was tested with historical generation, time-based features, and weather variables. However, its performance was not consistent across all validation windows.
Classical ARIMA and ETS methods were also considered, but they do not naturally include multiple weather variables in their standard forms.
## Use of LLMs

ChatGPT was used to assist with understanding forecasting methods, debugging Python code, improving the model evaluation process and writing parts of the project documentation. All the interpretations of the 
graphs were thought out by me and translated with the help of ChatGPT.
The data analysis, model experiments, validation, and final forecast were performed using Python.
