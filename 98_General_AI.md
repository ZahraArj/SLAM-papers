## NN
* Linear function
* Activation function: to make the network non-linear and fit complex data

## Linear Fun.
* Multiplication of input data with the weight matrix and addition of the bias term for each layer.
![image](https://user-images.githubusercontent.com/46463022/144874276-bf7d66f9-58de-489e-bcd4-398c9c53183a.png)

## Activation: 1_Relu NN
![image](https://user-images.githubusercontent.com/46463022/144874444-85fc50f5-3b26-4f19-8e60-efaf8a736084.png)

## [Batch Normalization](https://www.youtube.com/watch?v=sdXfAY_VD58)
### Problem: The distribution of each layer's input changes during training
### Solution: Fix the distribution
*  internal covariate shift
*  standardizes the inputs to a layer for each mini-batch  
![image](https://user-images.githubusercontent.com/46463022/144901870-56f293e1-778c-4e29-849c-0a4704f870e2.png)

* Probably Use Before the Activation
  * It may be more appropriate to use batch normalization after the activation function if for s-shaped functions like the hyperbolic tangent and logistic function.
  * It may be appropriate before the activation function for activations that may result in non-Gaussian distributions like the rectified linear activation function.

* Use Large Learning Rates
  * Using batch normalization makes the network more stable during training. This may require the use of much larger than normal learning rates, that in turn may further speed up the learning process.
  * The faster training also means that the decay rate used for the learning rate may be increased.

* Alternate to Data Preparation
  * If the mean and standard deviations calculated for each input feature are calculated over the mini-batch instead of over the entire training dataset, then the batch size must be sufficiently representative of the range of each variable.
  * It may not be appropriate for variables that have a data distribution that is highly non-Gaussian, in which case it might be better to perform data scaling as a pre-processing step.

## Residual block
8 layer feeds into the next layer and directly into the layers about 2–3 hops away. 
*  allow memory (or information) to flow from initial to last layers.
*  The skip connections help to address the problem of vanishing and exploding gradients.
![image](https://user-images.githubusercontent.com/46463022/144903171-bc1d67a2-a5c1-44f2-bfc7-e2ab23b42aaa.png)

## WHEN

### MLPs:
* Use MLPs For:
  * Tabular datasets
  * Classification prediction problems
  * Regression prediction problems
* Use MLPs On:
  * Image data
  * Text Data
  * Time series data
  * Other types of data



