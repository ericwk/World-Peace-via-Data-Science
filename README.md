# World Peace via Data Science

This project develops a categorical model that predicts the outcome of militarized interstate disputes based on characteristics of countries that originated disputes during 1914 to 2011.

A random forest model was developed with parameters selected to produce optimum accuracy (0.62 on the validation data set) that predicts, based upon characteristics of countries at the time that they enter into a dispute, whether the dispute will result in fatalities or not ("war" or "peace").

The country characteristics used in the model are:
* Military Expenditures (thousands US$)
* Military Personnel (thousands)
* Iron and Steel Production (thousands of tons)
* Primary Energy Consumption (thousands of coal-ton equivalents)
* Total Population (thousands)
* Urban Population (thousands)
* Composite Index of National Capability Score
* Total Imports (millions $US)
* Total Exports (millions $US)

The project takes data from the Correlates of War (COW) Project.  Information about COW can be found [here](http://www.correlatesofwar.org/).  

Data for the hostility level of disputes from 1914 thru 2010 was taken from the COW Militarized Interstate Disputes (v4.2) data set "MIDB_4.2.csv" that can be downloaded [here](http://www.correlatesofwar.org/data-sets/MIDs/militarized-interstate-disputes-4-2/at_download/file).  This dataset provides dispute data by participating country.  Data included in the data set for the year in which the dispute began (during 1914 thru 2010) and whether or not a country was an originator of the dispute was used to select records to include in developing the model.  Data for the "hostility level" of disputes is given in five categories, two that produce fatalities and three that do not produce fatalities.  The two categories that produced fatalities were combined into a new category "war" labelled as (1) and the three categories that did not produce fatalities were combined into a new category "peace" labelled as (1) to develop the model.

Country characteristics for each selected dispute originating country for the year in which the dispute started were selected for developing the model.  Data for these characteristics were taken from two COW tables:
* Data for imports and exports [here](http://www.correlatesofwar.org/data-sets/bilateral-trade/cow_trade_4.0/at_download/file)
* Data for all other country characteristics [here](http://www.correlatesofwar.org/data-sets/national-material-capabilities/nmc-v5-1/at_download/file)

The analysis process for developing the model, progressing from top to bottom, was:

[image](Images/Analysis_Process)
 
**Jupyter Notebooks**  

peace_combine_split.ipynb - Querys tables located in a database on AWS to create a data frame with features and target data to be used for modeling.  Assigns dispute outcomes in five categories ('hostlev' column) as target ('y') values and 9 feature columns to 'X' values and creates test/train split for modeling.

 peace_2cats_split.ipynb - Combines five categories for dispute outcomes ('hostlev' column) into two categories as the target ('y') values, assigns feature columns to 'X' values and creates test/train split for modeling.

 peace_logistic.ipynb - Evaluates five category target values via logistic regression model with default parameters to generate baseline model on which to evaluate improved models.

 peace_logistic_2cats.ipynb - Evaluates two category target values via logistic regression model for comparison to baseline model.

 peace_2cats_multiple_models.ipynb - Evaluates five alternative categorical models along with logistic regression for comparison with baseline model.

 peace_2cats_random_forest_gridsearch.ipynb - Identifies optimum model parameters for a random forest model via grid search with cross validation.

 peace_2cats_random_forest_model.ipynb - Creates charts for optimum random forest model to support presenting results.
