# Naive-Bayes
Naive Bayes classifiers performed on DoonarChoose datasets
# Basic Concepts:
Over Fitting:
small change in train data results in large change in the model. if alpha is 0, we have over fitting or high variance problem.

Under Fitting:
High Bias. Alpha is very large - problem of under flitting. How to find right Alpha: Using K in k-fold validation or Alpha in Naive Bayes theorem..

# How to get feature importance in Naive Bayes?
p(Wi/Y=1) sort by desc order, top features will have higher imp features for positive class. p(Wi/Y=0) sort by desc order, top features will have higher imp features for negative class.

# Intemperatibility:
Sq -> Yq Sq = [w1,w,2,w3,w,4....sn]

I am concluding, Yq=1 because Xq containing words w3,w6,w10 which have a high value of P(w3|y=1) , P(w6|y=1), P(w10|y=1) similarly we can say for negative where y=0

# Imbalance Data:
N has n1 and n2 data. if n1>>> n2, data is imbalance. P(y=1|w1,w2,w3,...wn) = P(y=1)P(w1|y=1)P(w2|y=1)P(w3|y=1)...P(wn|y=1) = p(n1) P(y=0|w1,w2,w3,...wn) = P(y=0)P(w1|y=0)P(w2|y=0)P(w3|y=0)...P(wn|y=0) = p(n2) say p(n1) = 0.9 so p(n2) =0.1

# Solution:
(1) Try up-sampling and down-sampling make P of both =0.5 ( I do not like this idea) (2) Modified NB to account for class imbalance.

# Outliers:
Xq = w1,w2,w3,....w' if w' does not exist , Laplace smoothing can take care of it. w' is the outlier since I have mot seen it in my training data set. (1) if w8 does not occur many times, we can say it is outlier. If word(Wj) say occur fewer than 10 times, just ignore/drop that word. do not keep in your set. this is one way to reduce outlier.

(2) Laplace smoothing can take care of it..

# Missing Values:
(1) If I have text-data, no issue. no case of missing data. (2) If I have categorical features, f1 belongs to (a1,a2,a3) categories. if we have missing values of any categorical feature, we can say it is part of NaN. (3) Numerical Features: we can use mean, median, naive bayes etc.

# NB Built Numerical Features:
very powerful way to get PF from Gaussian dist of Bayes data.

Multi-Class Classification in NB.
we can do in NB.

# Similarity Matrix and Distance Matrix in NB:
can be done in K-neighbor. NB can not handle it. we need to compute prob for f1,f2,,, NB does no use distances. it is a probability based method. We need actual feature values.

# Large Dimensions in NB:
Can be used easily. better use log probability since data is huge because of multiplication. D is large, prod will be super huge. we would not have underflow or numerical stability issue if we use log.

# Good and Bad about NB:
Conditional independence of features , if True NB works very well. If false, NB performance degrades.
Even if some features are dep, still NB works well. Text classification Problem: :Like mail spam email, prod review - works very well. Categorical or binary features: works very well. Real-values features - seldom used. we do not use much Gaussian dist, but used power law. NB is super interpret able, in medical where to tell doc, super simple to understand. just about continue. we can easily over fit if we do not do lap-lase smoothing to find right alpha using cross validation. so we need to use laplase smoothing in every case. sktlearn takes care if it. knn we need whole data at run time.
# Scikit-learn very good doc.
https://scikit-learn.org/stable/modules/naive_bayes.html
