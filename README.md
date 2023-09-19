# Daily Climate with LSTM
Hey guys, in this notebook, I will do some EDA and use LSTM to predict and analyze daily climate.  
First, Let's take a look at this data. 

### Part 1: Time Sereis Analysis
Let's do some seasonal decomposition. Breaking down the 'meantemp' data into its underlying trend, seasonality, and residuals. The Seasonal-Trend decomposition using LOESS (STL) provides a way to study the underlying trend in the mean temperature over time. This helps us understand how the mean temperature has been changing, excluding seasonal variations and random noise.
![download](https://github.com/Elvis-YAL/Daily_Climate-LSTM/assets/40426433/bac81ba1-e393-4927-ab07-1078a5dd139e)
We can find:  
1.**Original:** This is the original time series data of the mean temperature.  

2.**Trend:** This component shows the general upward or downward movement of the data over time. Here, we can see some slight long-term fluctuations.  

3.**Seasonal:** This represents the regular pattern in the data that repeats over time. The seasonal component is quite pronounced, indicating yearly cyclical changes.  

4.**Residual:** These are the remaining random fluctuations after removing the trend and seasonal components.   

### Part 2: Seasonal Analysis 
Investigate whether there are seasonal variations, like whether summers are generally hotter or more humid.
![download](https://github.com/Elvis-YAL/Daily_Climate-LSTM/assets/40426433/2eaf0af1-e9cc-4e3e-a0f3-dcf383e2a8c1)

1. **Mean Temperature:** There is a noticeable increase in temperature during specific months each year (usually in the summer) and a decrease during the winter.

2. **Humidity:** Humidity exhibits significant variations in certain months, especially during the rainy season.

3. **Wind Speed:** Wind speed appears to have some slight variations in specific months, but they are not as pronounced as temperature and humidity.

4. **Mean Pressure:** Mean pressure also shows some fluctuations in different months.

### Part 3: Correlation Analysis  
Explore the relationships between different climate variables, like whether temperature and humidity are correlated.  
![download](https://github.com/Elvis-YAL/Daily_Climate-LSTM/assets/40426433/377cd157-e245-44d3-bdde-dc77ea1fe06d)

1. **Mean Temperature and Humidity:** The correlation coefficient is -0.51, indicating a **strong negative** correlation between these two variables.

2. **Mean Temperature and Mean Pressure:** The correlation coefficient is -0.44, indicating a negative correlation, although **it is not as strong as the correlation with humidity.**

3. **Humidity and Mean Pressure:** The correlation coefficient is 0.23, indicating **a weaker positive correlation** between these two variables.

4. **Wind Speed and Other Metrics:** Wind speed shows weaker correlations with the other meteorological metrics.

### Part 4: Anomaly Detection
Identify any outliers or extreme events in the data, like unusually high or low temperatures.  
![download](https://github.com/Elvis-YAL/Daily_Climate-LSTM/assets/40426433/98c702f8-a016-4589-af67-17a5def88cc8)

**It can be observed that there are some anomaly values in wind speed and mean pressure when using 1.5 times the IQR as a criterion.**  

### Part 5: LSTM Forecasting  
Use the historical data to build predictive models, like forecasting future average temperatures or humidity levels.  

![download](https://github.com/Elvis-YAL/Daily_Climate-LSTM/assets/40426433/0ca6ada6-34f8-4494-9c8b-f077bf16e8e7)
**Finally, we can plot the predicted charts.**  
![download](https://github.com/Elvis-YAL/Daily_Climate-LSTM/assets/40426433/100b0056-428e-4b37-a70e-11bebccc11b3)


