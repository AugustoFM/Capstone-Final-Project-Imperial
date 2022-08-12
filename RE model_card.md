# Model Card

Features identification that are relevant to real estate products princing is a relevant exercize during the product design phase. It is specially relevant when it is a green field market and the product information is rather non existing. If on top of those constrains price transparency is an issue, as for example for a public funded industrial development real estate company, this can become a challenge.

This model was create to educate real estate practicioners on how efective could be clustering real estate data for product identification purpose, along with features analysis and Shap analysis to understand the most relevant features and its impact in price leading to maximizing the product design to enhance its final price and marketability. There is a rather long time to market and failing to meet the requirement of clients brings relevant loses.

## Model Description

**Input:** The model use a data set composed of 511 entrys of real estate transactions in the Boston area with the following attributes:

1.	Number of Instances: 511
2.	Number of Attributes: 13 continuous attributes (including "class"
attribute "MEDV"), 1 binary-valued attribute.
3.	Attribute Information:
a.	CRIM per capita crime rate by town
b.	ZN proportion of residential land zoned for lots over 25,000 sq.ft.
c.	INDUS proportion of non-retail business acres per town
d.	CHAS Charles River dummy variable (= 1 if tract bounds river; 0 otherwise)
e.	NOX nitric oxides concentration (parts per 10 million)
f.	RM average number of rooms per dwelling
g.	AGE proportion of owner-occupied units built prior to 1940
h.	DIS weighted distances to five Boston employment centres
i.	RAD index of accessibility to radial highways
j.	TAX full-value property-tax rate per $10,000
k.	PTRATIO pupil-teacher ratio by town
l.	B 1000(Bk - 0.63)^2 where Bk is the proportion of blacks by town
m.	LSTAT % lower status of the population
n.	MEDV Median value of owner-occupied homes in $1000's
4.	Missing Attribute Values: 5 RM replaced by average value in the data cleaning process



**Output:** The model presents the Shap graph for the entire data set and for the selected subset data. An example is provided below:
1. Shap graphic for the entire Cluster 2 data set

![alt text](https://github.com/AugustoFM/Capstone-Final-Project-Imperial/blob/249b883cd66594f1bba08235bcd053b033fa0a51/images/Shap%20values%20Cluster%202.png)

2. Example of Shap analysis for one sample of cluster 2:

![alt text](https://github.com/AugustoFM/Capstone-Final-Project-Imperial/blob/9d505a6fe155510189cd231923062296e63a52fb/images/Shap%20value%20example%20Cluster%202.png)


**Model Architecture:** The model has the following steps:

1. Data understanding and preprocessing
2. Clustering and Elbow rule to select the number of cluster
3. The new data subset for the cluster were created
4. A Grid search was used to optimize the fit of a Random Forest ensemble 
5. The feature importance graphic was built along with the Shap analysis for the entire data set and for each of the data subset.

## Performance

This model was created to understand the how the various features impacts the price in the entire data set and in Kmeans cluesterized data, using the Elbow rule to decide the number of clusters. Below it can be seen those same features in the entire data and in any of the subset:

Features impacting on price composition in the entire data set:

![alt text](https://github.com/AugustoFM/Capstone-Final-Project-Imperial/blob/9d505a6fe155510189cd231923062296e63a52fb/images/Feature%20importance%20All%20data%20set.png) 

Features impacting on price composition in cluster 0:

![alt text](https://github.com/AugustoFM/Capstone-Final-Project-Imperial/blob/278154a5f7c92af6a2402cf08c483a663108918b/images/Feature%20importance%20Cluster%200.png)

As it can be seen the features are significant different from the entire set to cluster 0. Therefore this information is very valuable in product design, and in combination with the shap value it can be used to price different trade-offs when evaluating different product configuration. This can be a very strong profit optimization tool for real estate developers. It would potentilly increase the commercialization of the products with a consequent increase in return. 

A grid search was used to select the best hyperparements in each case and the accuracy was implemented as below:

acc = np.round(100*(1-np.mean(abs(y_pred-y_test)/y_test)), 1)

It was selected a mean absolute error estimator becuase it has a higher mean absolute error but a smaller average error so it is less biased. Moreover it tends to overestimates the truth so despite for this exercise it is not particularly relevant, we decided to be conservative in our choices. This accuracy we used for the ensemble.RandomForestRegressor. 

It was achieve an accuracy of 86.9% for all data, 85.3% cluster 0, 91.1% cluster 1 and 76.7% in Cluster 2. 

## Limitations

This model aims to indentify and quantify the impact of most relevant features impacting the real estate product design. Our preliminary results shows that it can uncover many aspects that the product desing team might be not so aware. This information will feed a broader product and cost desing analysis, therefore one can not upfront any limitations beyound the size of data set and its sub set. As it happens here, cluster 2 has fewer samples and the results are not so estable as there is not to of a big training set, nonetheless the results of the feature and Shap analysis are very insigthful.

## Trade-offs

Cluster 2 has fewer data points so its accuracy to predict price is lower that the others 76.7% which might imply that not all features impacting the prices are being captured. But for the sake of this exercise the results shows that there are a great variation on the features and how those impact in the prices and it is definitly interesting knowing more. 
