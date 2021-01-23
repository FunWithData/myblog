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


## For Classification - 
##### (classification methods (“classifiers”) are used for generating propensities and, using a cutoff value on the propensities, we can generate predicted class memberships)

### Metrics Based on the Confusion Matrix
### a) Overall Accuracy
### b) Specificity and Sensitivity
### c) ROC  curve

<!--more-->

Content from [wikipedia](https://en.wikipedia.org/wiki/Circle).
