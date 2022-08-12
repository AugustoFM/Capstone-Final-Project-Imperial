# Final capstone Project: Clusering and Feature analysis using Real estate transaction data


## NON-TECHNICAL EXPLANATION OF YOUR PROJECT
At my current job position we have a problem to price real estate products developed in places lacking an existing market. I work for is public funded industrial real estate developer that foster the diversification of country’s economy.

We studied an existing real estate data set to see if a features importance analysis after a clustering process would deliver relevant insights in terms of product design. The clustering was relevant, as we intent to cluster locations where we might have more information on prices, to others that we don’t, and use the learning from the previous to apply to the later. The Elbow rule and Kmeans was used to define the number of clusters and the clusters.

We also use Shap analysis to shadow some lights in the pricing trade-offs of some designing features. We use an Ensemble of Random Forest Regressor tuned by grid search to predict the transaction values.


## DATA

The data was taken from kaggle and it is from a set of real estate transactions of the Boston area. This data set was particularly interesting as despite the transactions are not similar to the ones my company performs, it has some features very relevant to our company. As this project was used for internal thought-provoking purpose it was quite insightful that those features were present.

More information on the data set can be found on the RE data-sheet file loaded in this directory.


## MODEL 

This model has 2 main blocks:

1. A clustering phase, where we used the Dendrogram to have a visual understanding of the clusters, but we settle for K-means and used the Elbow rule to define the appropriate number of clusters. The final selected seemed an interesting set of the clusters that highlighted some interesting differences in term of possible product design.

2. The Ensemble of Random Forest Regressor was used because we were looking for a possible best fit for the predicted value, but more importantly because it allows a features importance analysis. This was the main reason for selection.

We incorporated Grid search to fine tune the hyper parameters and the Shap analysis to be able to transform the feature relevance into economical value for the predict transaction price.

This model was not particularly interested in the prediction per se, but rather in the methodology and the potential findings that it could deliver. I am using the proceedings of it to motivate my colleagues and leadership to evaluate the option of use it to fit our internal data and shape our products.

For more information on the model please review the RE model_card file in this directory



## HYPERPARAMETER OPTIMSATION
Description of which hyperparameters you have and how you chose to optimise them. 

The grid search has used to optimize the parameters of the Ensemble of Random Forest regressor. The following parameters were selected to be optimized:

hp_candidates = [{'n_estimators'      : [100, 200, 300],
                  'criterion'         : ['squared_error', 
                                         'absolute_error',
                                         'poisson'],
                  'max_features'      : ['sqrt', 
                                         'log2', 
                                          None]  
                 }]

The best recommened parameters was used for the value transaction prediction.

## RESULTS

This project was intended to educate my company on the possibilities of data analysis for real estate product design. It was indeed also shown that it could help in pricing policy preparation and support.

As a main a most relevant results it showed that clustering a real estate transaction data set can lead to uncover relevant features for different existing products and the SHAP analysis can be a powerful tool to price product design trade-offs. 

Below it is a sample of results, and in the image folder of the directory all related figures can be seen. 

The overall data set feature analysis:

![alt text](https://github.com/AugustoFM/Capstone-Final-Project-Imperial/blob/9d505a6fe155510189cd231923062296e63a52fb/images/Feature%20importance%20All%20data%20set.png) 

The Shap analysis for the entire set:

![alt text](https://github.com/AugustoFM/Capstone-Final-Project-Imperial/blob/f071f546f2714b0e4aa5e4c765096ff1e6b8e720/images/Shap%20values%20All%20data.png)

The feature analysis for cluster 1:

![alt text](https://github.com/AugustoFM/Capstone-Final-Project-Imperial/blob/f071f546f2714b0e4aa5e4c765096ff1e6b8e720/images/Feature%20importance%20Cluster%201.png)

The Shap analysis for the cluster 1:

![alt text](https://github.com/AugustoFM/Capstone-Final-Project-Imperial/blob/f071f546f2714b0e4aa5e4c765096ff1e6b8e720/images/Shap%20values%20Cluster%201.png)

As it can be seen it is quite different one from another and we claim it would be quite relevant to shadow some lights in the product design phase as well as in pricing policy and transparency. Those aspects are even more relevant in a context of public financed real estate developers.



## (OPTIONAL: CONTACT DETAILS)

If you wish to know more about me, you can visit my linked in profile:
https://www.linkedin.com/in/flaviano-moreira-b2a4b94/

Alternatively, if you are interested in AI and Real Estate related topics feel free to contact me at:
flaviano.a.moreira@gmail.com
