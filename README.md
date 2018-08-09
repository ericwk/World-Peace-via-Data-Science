# World Peace via Data Science

Predicting the outcome of militarized interstate disputes from characteristics of disputing countries.


**Jupyter Notebooks**
peace_combine_split.ipynb - Querys tables located in 'mcnulty' database on AWS to create a data frame with features and target data to be used for modeling.  Assigns dispute outcomes in five categories ('hostlev' column) as target ('y') values and 9 feature columns to 'X' values and creates test/train split for modeling.

 peace_2cats_split.ipynb - Combines five categories for dispute outcomes ('hostlev' column) into two categories as the target ('y') values, assigns feature columns to 'X' values and creates test/train split for modeling.

 peace_logistic.ipynb - Evaluates five category target values via logistic regression model with default parameters to generate baseline model on which to evaluate improved models.

 peace_logistic_2cats.ipynb - Evaluates two category target values via logistic regression model for comparison to baseline model.

 peace_2cats_multiple_models.ipynb - Evaluates five alternative categorical models along with logistic regression for comparison with baseline model.

 peace_2cats_random_forest_gridsearch.ipynb - Identifies optimum model parameters for a random forest model via grid search with cross validation.

 peace_2cats_random_forest_model.ipynb - Creates charts for optimum random forest model to support presenting results.
