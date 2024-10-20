A regression model that creates a linear function that fits the middle of the given datapoints.

$$y = m_{1}x_{1} + m_{2}x_{2} ... + b$$
The *m* coefficients and *b* intercept are optimized by minimizing the sum of the squared residuals

Assumes that *x* and *y* are linearly related and that residuals follow a normal distribution

If performed via statistical modeling, one gets the following metrics:
- r2
- Adjusted r2
- F-statistic
- Coefficients
- P-values
- Confidence Intervals

Can work with unstandardized variables and a mix of categorical and quantitative variables, though categorical ones must be dummy-encoded.

Can be used for forecasting. Can be made to work with seasonal data by doing a linear forecast, finding the ratio between each point and its estimate, take the average of these ratios for a period, and multiply the forecasts by the resulting weight.

- Background
	- [[Regression]]
	- [[Coefficient]]
	- [[Residual]]
	- [[Coefficient of Determination]]
	- [[Adjusted r2]]
	- [[F-Statistic]]
	- [[P-value]]
	- [[Confidence Interval]]
	- [[Standardization]]
	- [[Categorical Variable]]
	- [[Quantitative Variable]]
	- [[Dummy-Encoding]]
	- [[Normal Distribution]]
	- [[Forecasting]]