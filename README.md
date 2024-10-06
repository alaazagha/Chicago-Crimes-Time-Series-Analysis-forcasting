# Chicago-Crimes-Time-Series-Analysis-forcasting
This project its a study for helping Chicago law enforcement allocate resources for the next 6 months.
# For each of your selected crimes, perform the following steps to develop a forecast.
- Transform the data to obtain a time series of the crime count per month using .size().
- Check for and address null values.
- Decompose the Time series to detect seasonality and decide whether to use a seasonal model or not
- Determine if nonseasonal and/or seasonal differencing is required
-Use the ACF and PACF plots of stationarity data to estimate initial orders
-Split the time series into training and test data (Remember we want to predict 6 months)
-Fit a manual ARIMA/SARIMA model based on the orders determined during your exploration.
  - Make forecasts with your model.
  - Plot the forecasts versus the test data
  - Obtain metrics for evaluation
- Tune with pmdarima's auto_arima
  - Fit a model on training data with the best parameters from auto_arima
  - Obtain metrics for evaluation
  -Make forecasts with the auto_arima model
  - Plot the forecasts versus the test data
- Select the final model and justify your choice. (Which metrics or diagnostics support your choice?)
- Make true future forecasts using the entire dataset (for dates beyond the entire ts)
# For each of your two selected crimes, answer the following questions in a markdown cell:
- Calculate the predicted net change in the number (raw counts) of this type of crime from the beginning of the forecast to the end.
- Convert the raw delta into a percent change.
# Final Evaluation:
After completing both models and getting the forecasts for both crimes for 6 months into the future (beyond the data), answer the following questions in a Markdown cell:

- Of the two crimes, which is forecasted to have the highest monthly count of crimes at the end of the forecast?
- Of the two crimes, which is forecasted to have the highest net change by the end of the forecast?
- Of the two crimes, which is forecasted to have the highest percent change by the end of the forecast?
# Final Recommendations
- What recommendation would you make to the stakeholders?
- Include reporting-quality visual(s) to support your recommendation.

## Theft

![theft seasonality](https://github.com/user-attachments/assets/b6c2b4ee-9e68-4712-a049-960b4fbfa7b9)
The seasonal component is 2445.670289855072 which is ~30.78% of the variation in time series.

![ACF and PACF theft](https://github.com/user-attachments/assets/d825f5ff-cbbe-4f37-9d75-7b80eae7de81)

p = 1  # nonseasonal AR
d = 1  # nonseasonal differencing
q = 1  # nonseasonal MA

Orders for seasonal components
P = 1  # Seasonal AR
D = 0  # Seasonal differencing
Q = 1  # Seasonal MA
m = 12 # Seasonal period

![baseline model diagnostics theft](https://github.com/user-attachments/assets/cc339b1b-1823-404d-b12c-81c2ef9dcac0)
regarding the diagnostics the model is not bad still facing some issues in the residuals and the correlogram

![metrics t b](https://github.com/user-attachments/assets/2f1efdb1-1bed-4690-8660-c6bf4ad5af04)

![forecasting vs true baseline model theft](https://github.com/user-attachments/assets/aa777bb9-6760-4182-a808-cf2c9a49de57)


![bmd theft](https://github.com/user-attachments/assets/e8a88325-f5b7-4389-bec4-4afe2a29c0a6)
like this model still facing issues regarding the residuals, the other diagnostics graph are better than the baseline model

![metrics t best](https://github.com/user-attachments/assets/14210531-6e16-47c4-8143-2232b3e50b07)

![f vs t bm theft](https://github.com/user-attachments/assets/f6ecc205-86d0-4e66-b96c-8db5abc321d6)
comparing the models this model is doing better regardung the diagnostics,MAPE and r2, would recommend it over the baseline model

## Narcotics

![narcotics](https://github.com/user-attachments/assets/1803c1b7-2e0e-4ab4-806c-8e6486f5de7f)
The seasonal component is 519.2062747035574 which is ~9.20% of the variation in time series.

![acf and pacf narc](https://github.com/user-attachments/assets/818302bf-21a1-46a4-90f9-3feba2e23032)

p = 1  # nonseasonal AR
d = 1  # nonseasonal differencing
q = 1  # nonseasonal MA

Orders for seasonal components
P = 1  # Seasonal AR
D = 0  # Seasonal differencing
Q = 1  # Seasonal MA
m = 12 # Seasonal period

![dbm narc](https://github.com/user-attachments/assets/b0407e27-1ddb-4639-9a27-591fe4763d97)
observing the model diagnostics there's an issue with the residuals and normal q-q at the beginning

![narc met 1](https://github.com/user-attachments/assets/97e4309e-60df-4a40-867a-3810db511d65)

![forecast vs true bm narc](https://github.com/user-attachments/assets/782289d5-84d9-4fd4-aaa4-53ed14b2dd8e)

![dbm 2 narc](https://github.com/user-attachments/assets/4f57c7f3-b489-42a3-8a5e-f3f5686b4f53)
still this model is facing the same issues as the baseline model regaridng the diagnostics

![narc met 2](https://github.com/user-attachments/assets/63c47592-3a2f-43ed-9618-780203fa2736)

![forecast vs true bm2 narc](https://github.com/user-attachments/assets/f6b86619-bd5a-4181-a94c-afb46d0c8af0)
between the two models will choose the second model because it has lower MAE and MAPE, also higer R2 but it needs 4 lags to predict but overall its better than the baseline model
## Final Evaluation:
After completing both models and getting the forecasts for both crimes for 6 months into the future (beyond the data), answer the following questions in a Markdown cell:

- Of the two crimes, which is forecasted to have the highest monthly count of crimes at the end of the forecast?
Theft
- Of the two crimes, which is forecasted to have the highest net change by the end of the forecast?
Theft
- Of the two crimes, which is forecasted to have the highest percent change by the end of the forecast?
Narcotics
## Final Recommendations
- What recommendation would you make to the stakeholders?
  - that there should be a raise of the size of the DEA department in Chicago also should make the narcotics violations more strict in order for the crime rate decrease not increase like it will do


