# Ironhack project 7 Forest Cover Type clustering

![GitHub Logo](https://csfs.colostate.edu/media/sites/22/2014/02/subalpine-road.jpg)

### Project description

In this project the goal was to build a model to predict values or classes for any dataset, and implement in a way a step of clustering/unsupervised learning. I choosed to work with a dataset about forest cover type and build a model to predict classes of forest type from their other features, and compare models with and without a step of clustering to reduce the number of features. I also tried to cluster the whole dataset and visually compared the result to the actual classes.

Steps of the project :
- Data cleaning and handling (shape, nan, multicollinearity)
- Simple data exploration ; display the classes, repartition of forest classes, distribution of the numerical variables
- Data preparation for the model ; sampling/creating a balanced dataset, scaling of the data, test of 2 methods of feature selection to get the less important features
- Clustering of the least important features, with elbow method and kmeans
- Model building ; random forest with and without the least important features clustered, metrics to evaluate and compare them
- Kmeans on the whole dataset and comparison with the actual classes

### Libraries

- pandas
- numpy
- matplotlib
- seaborn
- boxcox (from scipy.stats)
- sklearn
  - train_test_split
  - RFE
  - SelectKbest
  - StandardScaler
  
  Models
  - RandomForestClassifier
  
  Metrics
  - confusion_matrix
  - accuracy_score
  - precision_score

### Code details

OPEN A JUPYTER INSTANCE TO BE ABLE TO READ THE .ipynb FILE HERE ON GITHUB

- correlation matrix for the features was made with seaborn's heatmap
- test for sampling were made with the sample method, but the creation of the balanced dataset that was eventually used was made with groupby and a lambda function using itself the sample method
- scaling of the data was made with the StandardScaler(), and only the numerical variables were scaled
- feature selection ; both RFE () and Kbest methods were tested, and the common least important features were select for the clustering

Clustering
- number of cluster for the different kmeans was done with elbow method (evolution of the inertia for different number of clusters)
- for the scatter plot representing the least important features clusters, different x and y variables were tested and the one that seemed to represent the best the clusters were kept
- clusters were added to the dataset a categorical variable, and replaced the least important features

- confusion matrix for the classification were made with the function from sklearn and represented with seaborn's heatmap
- for the random forest without the least important features clustered, the dataset used was the one with the data scaled

### Links

Source page : https://www.kaggle.com/uciml/forest-cover-type-dataset

Presentation : https://docs.google.com/presentation/d/1OLZmi-6AsAbGr5WkZ7AZUpQN5x31vqlp7dxy-bCizS4/edit?usp=sharing

