***Building a single neuron model*** 
In a biological neuron, dendrites collect signals from neighboring neurons. Neurons communicate with one another through electrical and chemical signals. The neuron processes the information within the nucleus. The output then goes through the axon, which processes the data and sends it to other neighboring neurons. Fully connected networks communicate with one another. The values of weights and connections change over time. That’s where learning comes into play. 

For this straightforward neuron model, we have inputs going into a neuron to perform summation. We take the information and multiply it by the weight. We normalize these weights so that they fall into a range. Then we feed this value into the neuron. We also have another input to the neuron, the bias. Think of the bias as a way to shift the function up and down. 
Output = Input * W1 + Bias

For our very simple model,
Temperature in degrees F = Temperature in degrees C * W1 + Bias
Temperature in degrees F = Temperature in degrees C * 9/5 + 32

We are going to try to use our model to reverse engineer the values of the weight and the bias. We are going to use the model to retrieve the weight and bias.

Take the input/output data, show it to the network, and update weights. Error comes down a little bit, and you keep repeating. It is an optimization problem; it is looking for the best value of weights to minimize the error. 
