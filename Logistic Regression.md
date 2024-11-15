A classification model, statistical modeling or machine learning, that fits a sigmoid function to the data.

$$logodds = \beta_0 + \beta_1x1 + ... + \beta_nx_n$$
Where betas are the logarithm of the odds of a true outcome per unit increase in the related explanatory variable.

Once logodds are calculated, they can be converted into probabilities. Typically, <50% will generate a 0 prediction and >= 50% will generate a 1 prediction. An example might be not passing vs. passing a class.

- Background
	- [[Classification]]
	- [[Statistical Modeling]]
	- [[Machine Learning]]
	- [[Sigmoid Function]]
	- [[Odds]]
	- [[Explanatory Variable]]