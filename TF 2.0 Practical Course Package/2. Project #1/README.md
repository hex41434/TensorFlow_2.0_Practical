**Build Your First Simple Perceptron (Single Neural Layer Model)
Project 1: Convert Celsius to Fahrenheit**


In this project, we will build a simple machine learning model to convert temperatures from Celsius to Fahrenheit. 
The equation is as follows:
T(degrees Fahrenheit) = T(degrees Celsius) * 9/5 + 32 

We are building a simple neural network that takes an input temperature in Celsius and gives us an output temperature in Fahrenheit. 

The objective is to predict the value of one variable Y based on another variable X. X is called the independent variable, and Y is called the dependent variable. Mapping one value to another like this is called ***"regression."***
"Regression is a statistical measurement that attempts to determine the strength of the relationship between one dependent variable (usually denoted by Y) and a series of other changing variables (known as independent variables.) Regression takes a group of random variables, thought to be predicting Y, and tries to find a mathematical relationship between them. This relationship is typically in the form of a straight line (linear regression) that approximates all the individual data points." https://www.investopedia.com/terms/r/regression.asp

***What are Artificial Neural Networks, and How Do They Learn?***
At an elementary level, we multiple inputs by weights and sum that up. Then we add a bias. The output generated is the weighted summation of all of the contributions. We apply an activation function f, and that creates an output y. 

For this straightforward project, we assume that we have one input, one bias, and we don’t even have an activation function f. Later we will scale this up to projects that have something like fifteen million weights. 

ANNs learn by example. ***Supervised learning*** involves giving the system labeled data so that it can associated inputs with the desired correct output label. At first, the system will have deviated outputs. If the given output does not match the desired output, we calculate an error signal and then repeat until the system provides the “desired output,” and the error approaches zero. Deploy the fully trained network.
