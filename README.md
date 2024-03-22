## **RICE TYPE CLASSIFICATION & EXTENT PREDICTION**

The project explores the use of machine learning and deep learning capablities for the prediction of the rice type. The Project begins with as follows;
- The exploration of the dataset using Python for Exploratory Data Analysis
- Treating of outliers using the IQR treatment as the recommended approach to treat skewness discovered in eccentricity and major axis length. There was a trade-off using this approach namely;
    - Lost of some data points
    - Skewness level of other features increasing
- Feature engineering, data normalisation and dimensionality reduction approaches were used to prepare the data for unsupervised and supervised learning approaches
- Unsupervised learning (KMeans) was used on the normalised data so as to create more features to be added back to the outlier treated dataset (outlier_treat.csv), **(Feature engineering)**.
- Having loaded the *cluste.csv* file, the same approach for data normalisation awas used to prepared the dataset using a Pipeline and using a Grid Search to search the best estimator. The following was discovered.
    - **Gradient Boosting Classifier** was the best approach.
    - Most of the classes were correctly classified based of the confusion matrix. 
    - Precision and Recall for both classes on the test data; **gonen and jasmine** were significantly high, so as for the ROC curve and AUC score having a value of 1; indicatingthe classifier is not a random classifier.

- For regession analysis, the target values was **Extent**. The following was done;
    -  Prepared the data via a pipeline and search for optimal classifier using a grid search; best estimator was **Linear Regression**
    - The RMSE score was extremely low and the $r^2$ score; 0.132 was horrible 
    - By adding polynomial features, the $r^2$ score improved to 0.135; still horrible.

### DEEP LEARNING
- The deep learning appraoch for classification was done in two approaches as followings
    - Using the same pipline apporoach as previously used, which gave similar results to the machine learning approach, less misclassification on test data.
    - Using a different pipeline approach; removing PCA, thereby feeding the mode with more features. Deep learning network architecture remained the same. But performance dropped as more misclassification were seen on the test data.

- For the regression analysis, the deep learning approach did yield a better RMSE score, 0.0989 with a loss of nearly 0; **0.0098**


All saved models can be found in the models folder and all saved pipelines for deep learning approaches can be found in the pipeline folder