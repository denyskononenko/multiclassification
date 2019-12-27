# Multiclass classification project

The following classification models are realized with (scikit-learn)[https://scikit-learn.org/stable/index.html]
* SVM (`linear` an `rbf` kernel)
* Random forest classifier
* logistic regression classifier

### Summary

The grid search method is applied for optimization of SVM model with RBF kernel. 
The isomap method is used for initial dimention space reduction.
The cross validation of model is performed.

## Dataset description

We will classify questions of users provided in the [dataset](https://www.kaggle.com/ananthu017/question-classification). According to the selected dataset questions are classified acoording their content into `6` classes:

|Class Abbreviation|  Description  |
|:-----:|:-----|
| ABBR | question asking for an *abbreviation* description|
| DESC | question asking for an *description* of smth.|
| ENTY | question asking for the name of *entity* (general facts)|
| HUMAN | question asking for the human related noun (name, profession etc.)|
| LOC | question asking for a *location* name|
| NUM | question asking for a *numerical* information (date, quantity)|

Questions are presented as a string.
We use utilize term frequency–inverse document frequency [(TF-IDF)](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html) method for representation of text string as vector.

## References