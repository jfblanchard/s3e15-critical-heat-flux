# s3e15-critical-heat-flux


### Background 
In two-phase boiling systems such as nuclear reactors, nucleate boiling is the responsible mechanism for providing the necessary heat flow.  Departure from nucleate boiling (DNB) in a two-phase flow boiling system spells trouble (meltdown) due to a sharp drop in the heat transfer coefficient. Methods to accurately predict the Critical Heat Flux (CHF) corresponing the the occurance of DNB is essential for safe operations.  

Previous designers have relied on a combination of domain knowledge, extensive experimentation, and look up tables (LUT's), but there has been recent interest in applying machine learning models to achieve better predictions.  

There is a similar paper [here](https://www.sciencedirect.com/science/article/abs/pii/S1359431119332065), in which they used NN's and Random Forest (RF) models. Their best-estimate standalone ML-based models comprised the following configuration:
* NN: 6/50/50/50/1 architecture, Adam optimizer (learning rate = 0.001), ReLU activation, no regularization
* RF: 100 trees/estimators, 50%-70% features in each individual tree, no regularization.
* 10 fold cross validation

### Data

Dataset has 31644 samples and 10 features, x_e_out is the target:

![data](https://github.com/jfblanchard/s3e15-critical-heat-flux/blob/main/images/s3e15%20data.JPG)

### Metric
* Root Mean Squared Error (RMSE)

### Model
The notebook file in this repo uses XGB for imputation, then a weighted blend of 3 regression models
*   Catboost
*   RF
*   LightGBM




