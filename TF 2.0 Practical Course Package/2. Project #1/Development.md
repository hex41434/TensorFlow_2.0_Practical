Typically we would have a training set of data and testing sets of data. Then we would make sure that the model doesn’t see the testing set of data until the end. For this straightforward project, we aren’t doing a train/test split. 

* We use the ***Scikit learn package*** to divide data into training and testing data. (In this case, we aren’t using Scikit learn, we are using the entire column.) 


* Google uses ***Keras*** as the standard API to train our models. Keras sits on top of TensorFlow. It makes training a lot easier. We don’t have to import Keras because it is already included with the TensorFlow package. Sequential means that we build the model layer by layer. Dense means fully connected; every input layer is mapped by a weight to all of the neurons in the next hidden layer. All the neurons in that layer are linked to the neurons in the next layer, and so on. Units is the number of neurons. One neuron means that I will have one weight and one bias. With model. summary (), we can see the two parameters that the model has. The weight connects the input to the neuron. The bias shifts the network up and down. There are two parameters to tune in this linear regression problem. Now we will run an optimizer to retrieve the parameters, weight, and bias. We used Adam optimizer with a learning rate of 0.5. We will cover the topic of training the network with gradient descent and backpropagation later. The learning rate is how fast we want the system to update the weights or how aggressively we want it to learn. For the loss function, we use the mean squared error. I looked at this article about “Mean Squared Error and Root Mean Squared Error.” https://www.oreilly.com/library/view/machine-learning-with/9781785889936/669125cc-ce5c-4507-a28e-065ebfda8f86.xhtml

You can get the performance of the network as it trains across all of the epochs. Scrolling through all of the epochs, you can see the loss going down, starting at 1072.8605 for the first epoch. It goes all the way down to 1.4593 at the 100th epoch. Within 100 epochs, using only two parameters, the model maps the input to the output, and the loss goes way down. 

***Mini Challenge: Experiment with this model***
Increase the number of neurons to 2 or 3
Change the learning rate 
(Try something like .1)
500 epochs 
See if this reduces the loss.
With a less aggressive learning rate, the error was higher than the more aggressive 0.5 rate even though we did 500 epochs instead of 100 epochs. The loss got tiny with the optimizer at one over 500 epochs. 
