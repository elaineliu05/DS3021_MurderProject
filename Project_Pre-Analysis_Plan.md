Elaine, Ethan, Vinith, Jolie, Chelsea

Data Sources:
Murder Accountability Project:  https://www.murderdata.org/p/data-docs.html?m=1
Victim demographic
Offender demographic
Cases solved
Weapons used, relationship between offender / victim, etc
Observations:
An observation in our study is 1 homicide case (each row). There are 198,000 observations and 30 variables in our dataset.

Possible Research Questions:
1. What is the likelihood of a crime being solved?
2. How do crimes change over time for different parts of the US? (predicting crime counts)
3. Can we predict the demographic of the potential murderer in a cluster of unsolved cases?
4. Are there trends between urban/rural locations and homicide rates, i.e. suspicious clusters of murders?
5. Are there differences in victim-offender relationships across different demographics?

Machine Learning Method(s):
1. Supervised learning - train a random forest regression model on characteristics like agency, homicide, situation, etc., to predict the likelihood of a crime being solved
2. Supervised learning - train a linear regression model on geographic features to predict future crime counts in different areas of the US. 
3. Unsupervised and supervised learning - first find clusters of unsolved cases, then one hot encode categorical variables to predict the demographic of potential murderers. 
4. Unsupervised learning - use clustering to find clusters of high murder rates, whether those correlate with urban or rural areas. Or to find clusters of unsolved cases to find out what’s similar about the victims’ demographic and see what the corresponding murder might be 
5. Logistic Regression - binary classification of stranger vs acquaintance and get odds ratio of different demographics to see the likelihood of victim and offender having the same or different demographic
6. Neural Network - GNN to find out the relationships between selected features

Test for ‘Success’:
- Use a testing dataset and apply our model to compare accuracy to training model
- Derive a high R^2 value, a low MSE, or low RMSE value for regression models
- Visualize clustering results and see (visually observe) whether all clustered data points are clustered ‘reasonably’, i.e. whether there are outliers being clustered with a centroid that is way too far to be reasonable
- Finding the optimal k value for the amount of clusters

Weaknesses:
- Working with a large dataset in general ( 198,000 rows and 30 columns)- there will some challenges in the runtime ( slower and high latency) 
- Computational Cost: Having 30 features to work with may slow down operations/ functions ( such as calculating OLS)
- Multicollinearity: Having too many features may also be the case where one or more predictor variables are strongly correlated with each other- leading to inaccurate coefficients. More uncertainty in the importance of each feature in making predictions. 
- Biases in data: Since this dataset came from MAP ( Murder Accountability Project) - nonprofit, it’s more likely that the dataset displays information that is biased/ modified, and the results we’d be getting could be problematic
- Unbalanced ratio of data: Murder counts in cities vs. rural areas will have extreme differences, possibly affecting regression results. 

Mitigation: 
- We can isolate certain features / group similar states/regions and perform ML models. And use Recursive Feature Elimination (RFE) to keep only important features.
- PCA to reduce columns in the dataset 
- Isolate performing linear regressions in rural areas and cities - potentially comparing results as part of our findings 
- Take into account of potential biases from the data source in our conclusions and findings 

What can we learn:

Even though we don’t answer our original question, we could definitely use the insights/ methods to leverage ideas for alternative methods. 
