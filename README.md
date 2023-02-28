# deep-learning-challenge

## Overview

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. Machine learning and neural networks are applied to the dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

## Results

### Data Preprocessing

The target variable for this model is the feature 'IS_SUCCESSFUL', which indicates if past applicants were successful in their venture with funding from Alphabet Soup.

The features considered for this model were:
APPLICATION_TYPE
AFFILIATION
CLASSIFICATION
USE_CASE
ORGANIZATION
STATUS
INCOME_AMT
SPECIAL CONSIDERATIONS
ASK_AMT

The EIN and NAME variables were removed from the input data since they were just identification columns and they were neither targets nor features.

![image](https://user-images.githubusercontent.com/10065386/221783701-ad35ebe1-0a82-4e6f-ad17-5428fac92b92.png)


### Compiling, Training, and Evaluating the Model

We used a neural network model for this application.
We started the analisys input with 2 hidden layers, 80 nodes on the first one and 30 on the second one.
We used 'Relu' activation because is the most commonly used.

For the output we started with 1 layer and 1 node, we used 'Sigmoid' activation because it exists between (0 to 1). Therefore, it is especially used for models where we have to predict the probability as an output.

![image](https://user-images.githubusercontent.com/10065386/221781617-def0c3ef-c1e6-477e-b1d2-47831733f524.png)


A target predictive accuracy higher than 75% was expected, but we we not able to achieve it.
We initially achieved a 72.93% accuracy so we made a new optimized model.

We used kerastuner to try to find the best parameters for this model.

We set a first layer with nodes between 1 and 10 in steps of 2, we did the same for a hidden layer.

The activations included were 'Relu', 'tanh', 'sigmoid'.

For output we kept the same configuration of 1 layer, 1 node and 'sigmoid' activation.

![image](https://user-images.githubusercontent.com/10065386/221781892-930a726d-98ff-443c-9f7d-1a59916d6940.png)
![image](https://user-images.githubusercontent.com/10065386/221782014-51d2a24c-21a6-4f1c-82c7-e39f99b1a8d0.png)


After 56 trials, the best parameters found were:

![image](https://user-images.githubusercontent.com/10065386/221782127-9b1f38d2-3d62-4141-90a6-3ec8438b56a0.png)

![image](https://user-images.githubusercontent.com/10065386/221780230-bf1f62f1-a996-4fd7-8fc6-361f171f22ca.png)

However, still we were not able to reach the expected accuracy. The best result we got was 73.36%

### Summary

The initial model we tried had a good accuracy, even with optimization we did not go too far from that result.

![image](https://user-images.githubusercontent.com/10065386/221782814-d5a893c4-7bda-4f29-90d4-985e9d6ad41c.png)

It would be a good idea to run a different model, maybe a random forest classifier would work better, since this application requests a binary output based on independent features.



