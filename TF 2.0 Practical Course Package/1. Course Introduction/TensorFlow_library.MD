
***TensorFlow***: Google Brain's free and open-source software library for numerical computation. It is a symbolic math library and is also used for building and deploying machine learning applications such as neural networks. 

The ***TensorFlow framework*** makes it easier to acquire data, train models, serve predictions, and refine future results. The library bundles together a number of machine learning and deep learning model and algorithms. It uses Python to provide a convenient front-end API for building applications with the framework and executes those applications in high-performance C++. TensorFLow supports production prediction at scale, with the same models used for training. 

With TensorFLow, developers create dataflow graphs. ***Dataflow graphs*** are structures that describe how data moves through a graph or series of processing nodes. Each model in the graph represents a mathematical operation, and each connection or edge between nodes is a multidimensional data array or tensor. Nodes and tensors in TensorFlow are Python objects, and TensorFlow applications are Python applications. The math operations are written as high-performance C++ binaries. The article says, "Python just directs traffic between the pieces, and provides high-level programming abstractions to hook them together." 

The article says, "The single biggest benefit TensorFlow provides for machine learning development is abstraction. Instead of dealing with the nitty-gritty details of implementing algorithms, or figuring out proper ways to hitch the output of one function to the input of another, the developer can focus on the overall logic of the application. TensorFlow takes care of the details behind the scenes." 

The three major framework competitors of TensorFlow are PyTorch, CNTK, and MXNet. 

In the course, we went through this TensorFlow tutorial for a supervised learning image classification task: 
https://www.tensorflow.org/tutorials/keras/classification

We are using ***Fashion MNIST*** as a drop-in replacement for the classic MNIST dataset, which is often used as the "Hello, World" of machine learning programs for computer vision. The MNIST dataset contains images of handwritten digits. 

Here, 60,000 images train the network, and 10,000 images evaluate how accurately the system learned to classify images. 

Loading the dataset returns four NumPy arrays:
* The train_images and train_labels arrays are the training set- the data the model uses to learn.
* The model is tested against the test set, the test_images, and test_labels arrays. 
The images are 28x28 NumPy arrays with pixel values ranging from 0 to 255. The labels are an array of integers, ranging from 0 to 9. These correspond to the class of clothing the image represents. Each image maps to a single label.

* The basic building block of a neural network is the ***layer***. Layers extract representations from the data fed into them. A neural network learns to map examples of inputs to outputs. We sequentially built the model, chaining together simple layers. 

We fed the 28 x 28-pixel images into the input layer, and then we added a Dense layer with 128 neurons and a relu activation function — the first layer in this network, tf.keras.layers.Flatten transforms the format of the images from a two-dimensional array (of 28 by 28 pixels) to a one-dimensional array (of 28 * 28 = 784 pixels). Visually you could picture this unstacking rows of pixels in the image and lining them up. This layer has no parameters to learn; it only reformats the data. 

After flattening the pixels, the network consists of a sequence of two tf.keras.layers.Dense layers. These are densely connected, or fully-connected, neural layers. The first Dense layer has 128 nodes (or neurons). For a given node, the inputs are multiplied by the weights in a node and summer together. This value is the summed activation of the node. The summed activation is then transformed via an activation function and defines the specific output or "activation" of the node.  

This article gives a brief introduction to the ***RELU activation function***: "The rectified linear activation function is a piecewise linear function that will output the input directly if it is positive. Otherwise, it will output zero. It has become the detail activation function for many types of neural networks because a model that uses it is easier to train and often achieves better performance." 
https://machinelearningmastery.com/rectified-linear-activation-function-for-deep-learning-neural-networks/
 
The article also discusses reasons to choose the Rectified Linear Activation Function instead of alternative functions. "To use stochastic gradient descent with backpropagation of errors to train deep neural networks, an activation function is needed that looks and acts like a linear function, but is a nonlinear function allowing complex relationships in the data to be learned. The function must also provide more sensitivity to the activation sum input and avoid easy saturation." (Looks like an excellent introduction to the math as we dive into this further.")  

The second layer is a 10-node softmax layer that returns an array of 10 probability scores that sum to 1. Each node contains a score that indicates the probability that the current image belongs to one of the ten classes. 

This article has the fundamentals of "Logits" of Logistic Regression:
https://towardsdatascience.com/logit-of-logistic-regression-understanding-the-fundamentals-f384152a33d1

I looked at the resource "Understand the Softmax Function in Minutes": https://medium.com/data-science-bootcamp/understand-the-softmax-function-in-minutes-f3a59641e86d
The ***Softmax function*** is "a wonderful activation function that turns numbers aka logits into probabilities that sum to one. Softmax function outputs a vector that represents the probability distributions of a list of potential outcomes." 


Before the model is ready for training, you need to add a few more settings during the model's compile step. The optimize is how the model is updated based on the data it sees and its loss function. In this case, the optimizer set to 'Adam.' This article is an introduction to the Adam algorithm: https://towardsdatascience.com/adam-latest-trends-in-deep-learning-optimization-6be9a291375c
"Adam [1] is an adaptive learning rate optimization algorithm that's been designed specifically for training deep neural networks." 

We specified the loss function as 'sparse_categorical_crossentropy.' The loss function measures how accurate the model is during training. We want to minimize this function to 'steer' the model in the right direction. We can use this loss function because we are classifying different categories of classes. For a binary classification, you could use 'binary_crossentropy' instead. 

Metrics monitor the training and testing steps. For metrics, we were looking at 'accuracy.' We want the predictions coming out of our model to match the labels. Accuracy is the fraction of the images that are correctly classified. 

Training the neural network model requires feeding the training data to the model. The model then learns to associate images and labels. Then you ask the model to make predictions about a test set and verify that the predictions match the tags from the test_labels array. After defining and compiling the model, you fit the model. To start training, the .fit method "fits" the model to the training data. In this case we used five epochs. We built a mini-brain to classify fashion images in just ten lines of code.

As the model trains, loss and accuracy metrics are displayed. The model reached an accuracy of about 0.8279 or 83% after just five epochs. 
