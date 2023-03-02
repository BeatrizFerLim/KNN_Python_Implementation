# KNN_Python_Implementation

## Description
This project is aimed to understand how the K-Nearest Neighbors (KNN) algorithm works on classification models. To achieve this, the algorithm was implemented following the rules the built-in metric does, once we have a trained model.

## Used Technologies
* **Python** - The source code is written in Python
* **Jupyter Notebook** - The platform of choice to implement this project
* **Python libraries** - Numpy, Pandas, Matplotlib, Scikit Learn, Statistics

## The algorithm
The KNN classifier algorithm works based on a simple logic: to classificate an element, we can look at the classification of its neighbors. The smaller the distance, the greater the similarities. So, to classificate new data, we use the data that is already classified, calculating the distance between the new and the known information and using the classification of the K nearest data to determine the class of the new data. 

To do so, a lot of distance metrics can be used, the most common are Manhattan Distance and Euclidean Distance.
The generalized formula of Euclidean Distance is given as:

<p align="center"><img width="250px" src="https://user-images.githubusercontent.com/46689116/222013738-25ff711b-4680-496e-9a52-7b547706178c.png"/></p>

And, the generalized formula of Manhattan Distance is given as:

<p align="center"><img width="250px" src="https://user-images.githubusercontent.com/46689116/222013751-49a2491e-e6bf-42e1-b3b5-25b1b3c37625.png"/></p>

Where, in both, **p** and **q** are the points whose distance between them we want to calculate, and **n** is the number of points. Both are widely used in the field of Machine Learning, along with the Minkowski Distance that combines both (the difference lies only in the exponential value used: 2 in Euclidean, 1 in Manhattan, but it can be greater than that, since it is chosen by the user).

To implement this project, both of the metrics ― Euclidean and Manhattan ― were considered.

After calculating the distance between the points, the k first ones are selected to get their classes evaluated. The most popular class among them are the chosen one for the new data. The process is then repeated for any other new data.

## Steps followed
To build this project, a few steps were followed:
1. The functions to calculate the Euclidean and Manhattan were defined
2. Then, the fuction to perform the calculation of the k-nearest neighbors was written, where:
    - The distance functions were called
    - The distances and classifications were organized
    - The k smaller distances were selected
    - The most popular class among them was found
3. After this, sample of data was generated, so we could perform the tests
4. This samples was splitted into train and test sets
5. The parameters for the algorithm were chosen
6. The score to evaluate its performance were calculated, by a function written with this purpose
7. Then, the algorithm was compared to the built-in version

## Preview of the analysis
The generated dataset was splitted into Train and Test sets, with a proportion of 70-30. Considering that this project has a didactic purpose, to ease the code, the dataset has only two attributes and four classes.
A sample of the dataset can be seen below:

![dataset_sample](https://user-images.githubusercontent.com/46689116/222148135-b2a37a76-d78e-43dc-a7d2-78ebdef46621.png)

It has 500 rows and three columns, considering the two attributes and the classification column (target).
To help and understand the distribution of the dataset, it has been plotted as follows:

![Data_visualization](https://user-images.githubusercontent.com/46689116/222148346-5c71b6f7-8328-4482-8e48-ec884c632221.png)

After the implementation, a few tests were runned to evaluate if the algorithm was working in the right way. Then, it was compared with the built-in version to see if the classification was correct. Some outputs:

- Comparing the algorithms with Euclidean Distance and k = 3

![Comparision_Euclidean](https://user-images.githubusercontent.com/46689116/222150769-f9a1f332-305c-41db-8ca6-c1d0c4f85bf3.png)

- Comparing the algorithm with Manhattan Distance and k = 5

![Comparision_Manhattan](https://user-images.githubusercontent.com/46689116/222149335-4dc53138-bbba-4ae8-b510-1ebbcf8de934.png)


## Conclusion
Since this algorithm has simple logic, it works perfectly with small datasets composed of numerical data, but not so well with larger datasets. This happens because of how the calculations are done. Since we have to compare each of the rows in the test set with each row in the training set, it loses performance and takes a long time to complete the classification. This lack of optimization prevents its use in a scalable way. Other than that, it works great for smaller analyses.

Furthermore, implementation requires more than just calculating distances. The more attributes, the greater the distance calculation and the more complex the algorithm becomes, with more loops. Therefore, it is important to note that the algorithm can and should be implemented manually to help understand its logic, but for real case scenarios, the built-in algorithm is a better choice.
