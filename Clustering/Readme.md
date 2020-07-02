In this assignment, I implemented some clustering methods using python.   

The clustering methods I implemented are:   
Method 1: K-means   
Method 2: Agglomerative Hierarchical Clustering   
Method 3: Spectral Clustering   

Data Preprocessing   
The data sets we managed, concern binary classification problems ie they contain data from two (2) categories. It's the spam dataset and the occupancy detection dataset.   
  About spam dataset:
   It has a total of 4601 entries (examples) of which the first 1813 are spam category and the remaining 2788 are non-spam category.    
   Each example has 58 features, where the 58th is the category to which it belongs.
  About the occupancy detection dataset:
    It has a total of 8143 entries (examples). Each example has 6 features where the
    6th is the category to which it belongs (0 or 1).

To evaluate the algorithms I will use the following metrics:   
a) Purity: category of each group is determined, after the end of the grouping by majority real category among team members. Then the (purity) of the above definition is calculated by measuring the average of the correctly sorted points.    
b) F-measure: For each cluster j, after defining the majority category as a category cluster (as in the previous measure), find TP (true positive), FP (false positive) and FN (false negative) find the F-measure. In the end, the evaluation of the clustering method under consideration will result from the sum of F-measures for each cluster.
