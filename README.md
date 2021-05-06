# README.md

# What's the CA Road Accidents Severity Prediction

Our project objective is to recognize key factors affecting the accident severity and develop a model predicting severity. By drawing an interactive map where outputs of the prediction models are integrated, users can quickly know which road sections are prone to traffic accidents and their corresponding severity levels.

The CA Road Accidents Severity Prediction is still in development. We have implemented an interactive map to show the severity of past traffic accidents on all road sections of California. In this map, users can filter the severity level or the road sections in certain cities to learn the information base on their needs. A prediction model for new data has also been implemented. It adopts Random Forest Algorithm to ensure that the prediction results have high credibility.

In a future release, we will integrate prediction models into the interactive map, allowing users to actually use our product to understand the current severity of traffic accidents on California roads.

# Content

**data_setup**: the folder contains the dataset used in this project and code that processes data cleaning, EDA, feature Engineering. The code will produce a CSV used in the prediction model.

**model:** the folder contains a processed dataset used in the prediction models and code that conducts three algorithms to figure out the best prediction model.

**UI:** the folder contains the implemented interactive map on the platform called CARTO.

# Concepts of Severity

**Severity I**: 

- No freeway towing is needed to move vehicles.
- Law enforcement involvement may or may not be necessary.
- No injuries reported.

**Severity II**: 

- Freeway towing and law enforcement involvement are necessary.
- No injuries reported.

**Severity III:**

- Law enforcement, including emergency medical service and fire, are necessary.
- Freeway towing is needed.
- Possible injuries or fatality.

**Severity IV:**

- Incidents last longer than above and may involve multiple disable vehicles.
- Freeway towing and law enforcement are necessary.
- Debris may require special clean up.
- Possible injuries or fatality.

# Solution Architecture

Our data is imported from online public data sources, including Kaggle and the united states census bureau. We then filtered and retained California-wide data through Excel.
We used 70% of the data to train our models and 30% of the data to select our final model. Traffic accident severity could be predicted by inputting the latest data of California roads into our best model. Results then could be visualized on our implemented UI to get a more intuitive result.

# Algorithms

We used three machine-learning algorithms when training our models, including logistic regression, random forest, and Naive Bayes. To improve the prediction accuracy, we also introduce a macro-economic feature, population density, to each model. Because county population density is the 5th important attribute that correlates to the accident severity. After testing, the random forest model performs the best among all the three models, based on metrics of prediction accuracy and f1 score. Gaussian Naïve Bayes model gets the worst performances.
