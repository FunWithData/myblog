# General Principles of Performance Evaluation
## For Prediction - 
##### (prediction methods are used for generating numerical predictions)
### a) MAE (mean absolute error/deviation)=   ![ \frac{1}{n}\sum_{i=1}^{n}|{e}_i|](https://latex.codecogs.com/svg.latex?\dpi{400}&space;\frac{1}{n}\sum_{i=1}^{n}|{e}_i|)
		MAE gives the magniture of the average absolute error

### b) Mean Error =  ![ \frac{1}{n}\sum_{i=1}^{n}{e}_i](https://latex.codecogs.com/svg.latex?\dpi{400}&space;\frac{1}{n}\sum_{i=1}^{n}{e}_i)
		the Mean Error is similar to MAE except that it returns the sign of the error, and therefore gives an indication 
		of whether the prediction are over or underpredicting the outcome variable on average.

### c) MPE (mean percentage error)= ![100 \frac{1}{n}\sum_{i=1}^{n}\frac{{e}_i}{y}_i](https://latex.codecogs.com/svg.latex?\dpi{400}&space;100&space;\frac{1}{n}\sum_{i=1}^{n}\frac{{e}_i}{y_i})
		MPE gives the percentage score of how predictions deviate from the actual values from the actual values, 
		taking into account the direction of the error.

### d) MAPE (mean absolute percentage error) =![100\frac{1}{n}\sum_{i=1}^n|\frac{e_i}{y_i}|](https://latex.codecogs.com/svg.latex?\dpi{400}&space;100\frac{1}{n}\sum_{i=1}^n|\frac{e_i}{y_i}|)
		MAPE gives a percentage score of how predictions deviate from the actual values (on average).

### e) RMSE (root mean squared error) =![\sqrt{\frac{1}{n}\sum_{i=1}^n{e_i}^2}](https://latex.codecogs.com/svg.latex?\dpi{400}&space;\sqrt{\frac{1}{n}\sum_{i=1}^n{e_i}^2})
		RMSE is similar to the standard error of estiamte in linear regression, except that it is computed on the 
		validation data rather than on the training data. It has the same units as the outcome variable. 

**All of these measures can be used to compare models and to assess their degree of prediction accuracy, but be aware that they are influenced by outliers. To deal with outliers, we can calculate the median-based measures and compare them with the mean-based measures or plot a histogram or boxplot of the errors.**


### Training Performance - Errors that are based on the training set measure the model fit
### Validation Performance- Errors based on the validation set measure the model's ability to predict new data (predictive performance).

### Lift Chart - When the goal is to find a subset of records that gives the highest cumulative predicted values. The graphical way to assess predictive performance is called a lift chart. The method compares the model's predictive performance to a baseline model that has no predictors. This is accomplished by ordering the set of records (usually validation data) by their predicted value, from high to low, after accumulating the actual values, plotting their cumulative value on the y-axis as a function of the number of records accumulated (the x-axis value). The resulting curve is compared to another curve calculated by assigning a naive prediction (y_bar) to each record and accumulating these average values, which results in a diagonal line. If the lift curve is further away from the benchmark line, then the model is performing better at separating records with high-value outcomes from those with low-value results. 

### Decile Lift Chart - presents the same information as the lift chart, but the ordered records are grouped into deciles, and for each decile, the chart presents the ratio of model lift to naive benchmark lift. 


{{<divider>}}

## For Classification - 
##### (classification methods (“classifiers”) are used for generating propensities and, using a cutoff value on the propensities, we can generate predicted class memberships)

### Metrics Based on the Confusion Matrix

### a) Overall Accuracy
### b) Specificity and Sensitivity
### c) ROC  curve

<!--more-->

Content from [wikipedia](https://en.wikipedia.org/wiki/Circle).
