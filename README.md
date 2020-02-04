# Hackathon_UCI_Adult_Data_Set
Magnus Bigelow &amp; John Wertz Hackathon Project, Predicting whether or not individuals make more than $50k using the UCI Adult Data Set and a constraint of using 20 or fewer features. Used 1 day (9-5) to complete project.

# Problem Statement¶

Predict if a person's income is in excess of $50,000 given certain profile information, and more specifically to generate predicted probabilities of income being above $50,000 for each row in the test set, given an artificial constrain and an 8 hour period to complete the model and predictions.

**Constraint**
- Using a max of 20 features

## Data Sources 

The data used for this project was compiled using the PushShift API: 
    [PushShift](https://pushshift.io/api-parameters/)

10,000 most recent post were collected from r/woodworking, r/mtb, and r/bicylcing and the title and selftext (i.e. original post) columns were concatenated into a single 'text' column that was used for our analysis.

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

| **Vectorizer**    | **Estimator**             | **Test Accuracy** | **Test Sensitivity** | **Test Specificity** |
|-------------------|---------------------------|-------------------|----------------------|----------------------|
| *CountVectorizer* | *Logistic Regression*     | 0.921             | 0.919                | 0.922                |
| *CountVectorizer* | *KNN*                     | 0.820             | 0.847                | 0.794                |
| *CountVectorizer* | *Multinomial Naive Bayes* | 0.914             | 0.925                | 0.903                |
| *CountVectorizer* | *Random Forest*           | 0.917             | 0.932                | 0.903                |
| *TfidfVectorizer* | *Logistic Regression*     | 0.919             | 0.917                | 0.920                |
| *TfidfVectorizer* | *KNN*                     | 0.737             | 0.787                | 0.686                |
| *TfidfVectorizer* | *Gaussian Naive Bayes*    | 0.737             | 0.999                | 0.475                |
| *TfidfVectorizer* | *Random Forest*           | 0.918             | 0.930                | 0.906                |
| *CountVectorizer* | *Voting (LR, MNB, RF)*    | 0.923             | 0.922                | 0.923                |

**Production Model**


## Conclusions

