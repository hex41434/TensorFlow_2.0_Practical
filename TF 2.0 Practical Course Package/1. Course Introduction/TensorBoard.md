***TensorBoard: TensorFlow’s visualization toolkit***
https://www.tensorflow.org/tensorboard
Tensorboard is integrated with TensorFlow 2.0. Tensorboard lets us track network progress like accuracy and loss throughout various epochs along with graphs showing multiple layers of the network. Tensorboard provides a built-in performance dashboard. 

I used this tutorial introduction to Tensorboard:
https://www.tensorflow.org/tensorboard/get_started

While training with Keras’s Model.fit(), you can create and store logs with tf.keras.callback.TensorBoard. Place the logs in a timestamped subdirectory to allow easy selection of different training runs. 

The documentation gives these brief descriptions of some of the available dashboards:
A brief overview of the dashboards shown (tabs in top navigation bar):
The Scalars dashboard shows how the loss and metrics change with every epoch. You can use it to also track training speed, learning rate, and other scalar values.
The Graphs dashboard helps you visualize your model. In this case, the Keras graph of layers is shown, which can help you ensure it is built correctly.
The Distributions and Histograms dashboards show the distribution of a Tensor over time. This can be useful to visualize weights and biases and verify that they are changing in an expected way.

There are lots more tools to explore! 
