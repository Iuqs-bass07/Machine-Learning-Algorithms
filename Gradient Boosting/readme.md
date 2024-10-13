# Grdient Boosting Regressor

This is a Boosting model which mean it is trained sequentially on a data and then converges. The model works on the concept of the additive modelling which is that if a composite function is divided into different smaller fucnction then added together it will give an approximate to that function.

## Steps Involved
   
### Step 1- Computation of the first function(f0)
        
        The first fuction will be simple mean of the target values and then residual will be calculated as actual - predicted
        
### Step 2- Training the decison tree

        After the first residual calculation total decision trees with max_leaf_nodes in between 8 to 32 are trained on the x as input and previous residual values as target and after this prediction for this tree is done and the again residual is calculated and this process repeats iteratively
        
### Step 3- Inference 

        Inference is done for the data as the sum of the multiplication of prediction of all the functions and learnign rate
