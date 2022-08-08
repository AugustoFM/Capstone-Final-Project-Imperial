# Datasheet Template

This data set was downloaded from https://www.kaggle.com/datasets/arslanali4343/real-estate-dataset, to be used in investigate to which degree the features that most impact a given outcome varies in a subset of the data. As I work in the real estate sector, and particularly in industrial real estate sector, we are very interested in indentify the feature that most impact in price. In order to verify our hypothesis this data set was selected from the internet.

## Motivation

This data was originally taken from http://lib.stat.cmu.edu/datasets/. It is also further mentioned the below:

Sources: (a) Origin: This dataset was taken from the StatLib library which is maintained at Carnegie Mellon University. (b) Creator: Harrison, D. and Rubinfeld, D.L. 'Hedonic prices and the demand for clean air', J. Environ. Economics & Management, vol.5, 81-102, 1978. (c) Date: July 7, 1993 Past Usage: - Used in Belsley, Kuh & Welsch, 'Regression diagnostics ...', Wiley, 1980. N.B. Various transformations are used in the table on pages 244-261. - Quinlan,R. (1993). Combining Instance-Based and Model-Based Learning. In Proceedings on the Tenth International Conference of Machine Learning, 236-243, University of Massachusetts, Amherst. Morgan Kaufmann.

The data set creator was Harrison, D. and Rubinfeld, D.L. and it collects them to be a part of his publication 'Hedonic prices and the demand for clean air', that was made public in 1.978

## Composition

There is currently 511 instances in the dataset, (in kaggle it informs 506 I dont know why). It represents real estate data for properties in the Boston region. There are 13 continuous attributes (including "class" attribute "MEDV"), 1 binary-valued attribute.
There are 5 missing values in the RM attribute, and it was replaced by the average of the values.
There are no private information on this data set.

## Collection process

There is no information about how the data was acquired in kaggle. It was also not informed the sampling strategy.

## Preprocessing/cleaning/labelling

There is no information about the preprocessing/cleaning/labeling of the data. But there is no categorical values except for CHAS Charles River dummy variable (= 1 if tract bounds river; 0 otherwise).
As there is just 5 missing values I understand that the data set was cleaned and prepared to be upload, and maybe this is the reason it has been used for different predictive training tasks

## Uses

The dataset has Real estate prices and also relates it to the Crime rate. So, most usage of the data set in kaggle has been for prediction tasks. There is also so Correlation analysis and KNN clustering. I used it to do a feature importance analysis in the entire data in subsets of it that was obtained throught Kmeans. I also did a Shap analysis in the end. I used it to educate my company in the potetial of using features analysis to define the main attributes of a real estate product. Along with Shap analysis it could potentially help price trade-off while designing the product.

The data set provide some features that might be potentially used to generate biased analysis as there is not enought information on how the data was collected, as for example: 
- B 1000(Bk - 0.63)^2 where Bk is the proportion of blacks
by town 
- LSTAT % lower status of the population

My understanding that this data should be used only for educational usage, as it was collected a long time ago (1978) and it would not reflect by any means the current market situation of the Boston area, and its main features.


## Distribution

The data set is available at kaggle and has been used a fair amount of times for different purposes

This data set has a usability of 10.00 according to kaggle, no license is requested and it is expected to be update anually

## Maintenance

The data set is available at kaggle and it is mentioned that it is mantained anually, but it does not informed by whom.

