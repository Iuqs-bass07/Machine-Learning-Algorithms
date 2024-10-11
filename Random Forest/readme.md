Random Forest Implementation

This repo contains the implementation of random forest on the top of a decision tree. Random forest is a bagging algorithm which is built on the top of decision tree. Bagging name comes from the

B- Bootstrap

This means that the sampling of the whole dataset is done and the then the samples data is fed to the model. Each model is trained on a different set of sampled data

Agg- Aggregate

This means that the whole set of models are train on a different set of data and then while making their inference the aggregate of the result has been taken

Components

Decision Tree Class:  

Constructs individual decision trees based on specified parameters like minimum samples and maximum depth.

Random Forest Function:

Builds a random forest using multiple decision trees trained on bootstrap samples.

Prediction Function:

Aggregates predictions from all decision trees in the forest to provide the final prediction using a majority vote approach
