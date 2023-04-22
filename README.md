## Binary-Classification-with-the-Keras

### 1. Description of the Dataset

This is a dataset that describes sonar chirp returns bouncing off different services. The 60 input variables are the strength of the returns at different angles. It is a binary classification problem that requires a model to differentiate rocks from metal cylinders.

It is a well-understood dataset. All the variables are continuous and generally in the range of 0 to 1. The output variable is a string “M” for mine and “R” for rock, which will need to be converted to integers 1 and 0.

### 2. Neural Network Model Performance

- We will use scikit-learn to evaluate the model using stratified k-fold cross validation. This is a resampling technique that will provide an estimate of the performance of the model. It does this by splitting the data into k-parts and training the model on all parts except one, which is held out as a test set to evaluate the performance of the model. This process is repeated k-times, and the average score across all constructed models is used as a robust estimate of performance. It is stratified, meaning that it will look at the output values and attempt to balance the number of instances that belong to each class in the k-splits of the data.
- To use Keras models with scikit-learn, we must use the KerasClassifier wrapper from the SciKeras module. This class takes a function that creates and returns our neural network model. It also takes arguments that it will pass along to the call to fit(), such as the number of epochs and the batch size.
- The weights are initialized using a small Gaussian random number. The Rectifier activation function is used. The output layer contains a single neuron in order to make predictions. It uses the sigmoid activation function in order to produce a probability output in the range of 0 to 1 that can easily and automatically be converted to crisp class values.
- 
