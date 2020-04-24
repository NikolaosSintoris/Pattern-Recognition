In this assignment, i implemented some classification methods using python.

The data set we managed concern binary classification problems, ie they contain data from two (2) categories. It's the spam dataset.
It has a total of 4601 entries (examples) of which the first 1813 are spam category and the remaining 2788 are non-spam category. Each example has 58 features where the 58th is the category to which it belongs.
For the data, a pre-proccessing was done to get to the final form used.
You can download the data from https://archive.ics.uci.edu/ml/machine-learning-databases/spambase/   

The classification methods i implemented:   
1) Variant LVQ method.   
2) Nearest Neighbor k-NN with Euclidean distance.   
3) Neural networks with sigmoid activation function in each neuron, and test with 1 hidden layer, and with 2 hidden layers.   
4) SVM with linear kernel.  
5) SVM with gaussian kernel.   
6) Naïve Bayes classifier.   

Variant LVQ method:
This algorithm is a variant that aims to divide the space into spherical areas as large and clear as possible in terms of the data category.   
The steps of the algorithm are as follows:   
Α) Initially you have K areas, an area for each category j, described by the mean, the radius and the corresponding category.   
Β) Repeat   
1. Select an example from the whole training, where x its characteristics and y its actual category.   
2. Identification of the Gaussian region (from the current set of K regions) belonging to the example according to the Gaussian similarity function.   
Let j* be the "winning region", ie the one with the greatest similarity.   
3. Adaptation of the parameters of the winning area according to the correctness of the decision:   
	a. If y = Cj* then (success) we change the parameters of the area, rewarding (reward) the decision, as follows:
		μj∗ = (1 - a) μj∗ + ax and σj∗ = σj∗ + adist (x, μj∗)   
	b. If y ≠ Cj* then (failure) then we change the parameters of the area, punishing (penalty) the decision:
		μj∗ = (1 + a) μj∗ - ax and σj∗ = σj∗ - adist (x, μj∗)   
We also create a new Gaussian region (K = K + 1) centered at point x, σ is a small default value.   

We will follow the 10-folds cross validation strategy: in particular, we will randomly divide the original data set into ten (10) foreign subsets (10 folds) and in each one we will measure the performance set (testing set) by doing training in the remaining 9 subsets (training set). It is fairer to separate the proportions for each category, so that in each fold the ratio of data per category is the same. The total performance of each ranking method will result from the percentage average value at 10 folds.

For the evaluation we will use accuracy and f1_score.
