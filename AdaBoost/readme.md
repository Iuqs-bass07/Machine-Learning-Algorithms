This Repo consists of the implementation of the AdaBoost algorithm. AdaBoost is a Boosting ensemble model which focusion on taking a decision stumps and then giving it direction based on its error and updating the data(Upsampling) ad then feeding to subsequent decision stumps

Steps:

  1- Intitialize the weight for each row
  2- Train a decision stumps and calculate the predcition
  3- Calculate the error and error rate(Alpha)
  4- Upsample the misclassified data
  5- Genrate random points to take the data and take iloc 
  6- Repeat this process iteratively 
