# Hackathon_UCI_Adult_Data_Set
Magnus Bigelow &amp; John Wertz Hackathon Project, Predicting whether or not individuals make more than $50k using the UCI Adult Data Set and a constraint of using 20 or fewer features. Used 1 day (9-5) to complete project.

# Problem Statement¶

Predict if a person's income is in excess of $50,000 given certain profile information, and more specifically to generate predicted probabilities of income being above $50,000 for each row in the test set, given an artificial constrain and an 8 hour period to complete the model and predictions.

**Constraint**
- Using a max of 20 features

## Data Sources 

The primary dataset come from University of California Irvine and contains almost 50,000 observations of people from 1996 and whether or not they made above $50k: 
    [UCI Dataset](https://archive.ics.uci.edu/ml/datasets/Adult)

Additional Data was collected to correlate native country to per-capita GDP, sources below:
    [World Bank Data](https://www.kaggle.com/sdorius/globses)
    [Puerto Rico](https://www.google.com/publicdata/exploreds=d5bncppjof8f9_&met_y=ny_gdp_pcap_cd&idim=country:PRI:CUB:DOM&hl=en&dl=en)
    [Taiwan](https://www.indexmundi.com/g/g.aspx?c=tw&v=67)
    
## Repo Structure

code
- Folder jupyter notebooks for data collection & EDA, modelling and testing the model on our second set of subreddit's

data
- Folder with csv's from web scrapping

visuals
- Folder with pictures for presentation and choice visuals from analysis

## Executive Summary



**Model Performance**

We first fit 7 different types of classification models using the sklearn standard hyperparameters:
- Logistic Regression
- K-Nearest Neighbors
- Decision Tree
- Bagged Decision Trees
- Random Forest
- AdaBoost
- Support Vector Machine

Using the results from these simple models we decided to ignore the decision tree and support vector machine models as they performed much worse than the other 5 models. We then performed grid searches on the remaining 5 model types in order to tune hyperparameters and find the best model. Further we attempted 2 voting classifiers combining some of our best model and hyparameters. The results of our *best* model of each type are sumarized below:

| **Model**    | **Non-Standard Hyperparemeter(s)**     | **Test Accuracy** | **Test F1 Score** | **Test Sensitivity** |
|-------------------|---------------------------|-------------------|----------------------|----------------------|
| **Bagged Decision Trees** | *n_estimators = 250*      | 0.816             | 0.600             |  0.574          |
| **K-Nearest Neighbors** | *n_neighbors = 25*          | 0.837             | 0.635             |  0.589          |
| **Logistic Regression** | *Standard*                  | 0.841             |                   |                 |
| **Random Forest** | *max_depth = 11, min_samples_leaf = 5, warm_start = True* |  0.847 | 0.635 | 0.552          |
| **AdaBoost** | *n_estimators = 50*                    | 0.847             | 0.646             |  0.581          |
| **Voting** | *Bagged Trees, Random Forest, AdaBoost*  | 0.847             | 0.639             |  0.562          |
| **Voting** | *KNN, Random Forest, AdaBoost*           | 0.847             | 0.635             |  0.551          |

**Production Model**
We chose our K-Nearest Neighbors model with 25 neighbors as our production model. While this model did not have the highest accuracy or F1 score, it was comparable to the other top models and had the additional bonus of scoring the highest on sensitivity. Given our imbalanced dataset we wanted to have a higher sensitivy as none of our models were great at classifying the positive cases.

Having decided on a production model we fit the model again in a new notebook and loaded our test data before generating predictions.

## Conclusions

