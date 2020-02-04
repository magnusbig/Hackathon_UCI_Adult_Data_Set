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
    Puerto Rico](https://www.google.com/publicdata/exploreds=d5bncppjof8f9_&met_y=ny_gdp_pcap_cd&idim=country:PRI:CUB:DOM&hl=en&dl=en)
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

//TBU//

| **Model**    | **Non-Standard Hyperparemeter(s)**     | **Test Accuracy** | **Test F1 Score** | **Test Sensitivity** |
|-------------------|---------------------------|-------------------|----------------------|----------------------|
| **Bagged Decision Trees** | *n_estimators = 250*      | 0.816             | 0.600             |  0.574          |
| **K-Nearest Neighbors** | *n_neighbors = 25*          |                   |                   |                 |
| **Logistic Regression** | *Standard*                  |                   |                   |                 |
| **Random Forest** | *max_depth = 11, min_samples_leaf = 5, warm_start = True* |  0.847 | 0.635 | 0.552          |
| **AdaBoost** | *n_estimators = 50*                    | 0.847             | 0.646             |  0.581          |
| **Voting** | *Bagged Trees, Random Forest, AdaBoost*  | 0.847             | 0.639             |  0.562          |
| **Voting** | *KNN, Random Forest, AdaBoost*           | 0.847             | 0.635             |  0.551          |

**Production Model**


## Conclusions

