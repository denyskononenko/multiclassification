# Multiclass classification project

The following classification models are realized with [scikit-learn](https://scikit-learn.org/stable/index.html)
* SVM (`linear` an `rbf` kernel)
* Random forest classifier
* logistic regression classifier

### Summary

The grid search method is applied for optimization of SVM model with RBF kernel. 
The isomap method is used for initial dimention space reduction.
The cross validation of model is performed.
Comparison of selected methods with simple artificial neural network is made.


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

### Conclusions

Selected models have approximately the same accuracy score. 

|Model|Score|
|:---|---:|
|Random Forest|0.537181|
|SVM linear kernel|0.561918|
|SVM radial basis functions|0.552761|
|Logistic regression|0.549108|

SVM model with linear kernel has the largest accuracy of **56.19%** for selected dataset.
Evidently, this  means that the question-vectors of dimension $n$ presented by tf-idf metod are best separated by hyperplanes of dimension $n - 1$.

We compare also compare the obtained results for classic algorithms with the model based on simple neural network which consists of two hidden layers. Number of neurons in hidden layers is equal to the dimension of question-vector. Output layer dimension equals to the number of classes.

The realization of neural network architecture as well as its training is presented in the notebook `nn_classifier.ipynb` of the repository.
**The classifier based on the artificial neural network has larger accuracy in comparision with methods described below**
Its accuracy **87.56%***.

