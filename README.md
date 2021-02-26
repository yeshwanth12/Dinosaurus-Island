# Dinosaurus-Island
Creating a character level language model using a Recurrent Neural Network (RNN)

# Objective
Welcome to Dinosaurus Island! 65 million years ago, dinosaurs existed, and they are back. You are in charge of a special task. Leading biology researchers are creating new breeds of dinosaurs and bringing them to life on earth, and your job is to give names to these dinosaurs.

<table>
<td>
<img src="images/dino.jpg" style="width:250;height:300px;">

</td>

</table>

Luckily you have learned some deep learning and you will use it to save the day. Your assistant has collected a list of all the dinosaur names they could find, and compiled them into this [dataset](dinos.txt). To create new dinosaur names, you will build a character level language model to generate new names. Your algorithm will learn the different name patterns, and randomly generate new names.

# Model Overview
The model has the following structure: 

- Initialize parameters 
- Run the optimization loop
    - Forward propagation to compute the loss function
    - Backward propagation to compute the gradients with respect to the loss function
    - Clip the gradients to avoid exploding gradients
    - Using the gradients, update your parameters with the gradient descent update rule.
- Return the learned parameters 
    
<img src="images/rnn.png" style="width:450;height:300px;">

* At each time-step, the RNN tries to predict what is the next character given the previous characters. 
* The dataset $\mathbf{X} = (x^{\langle 1 \rangle}, x^{\langle 2 \rangle}, ..., x^{\langle T_x \rangle})$ is a list of characters in the training set.
* $\mathbf{Y} = (y^{\langle 1 \rangle}, y^{\langle 2 \rangle}, ..., y^{\langle T_x \rangle})$ is the same list of characters but shifted one character forward. 
* At every time-step $t$, $y^{\langle t \rangle} = x^{\langle t+1 \rangle}$.  The prediction at time $t$ is the same as the input at time $t + 1$.

After the model is trained. You would like to generate new text (characters). The process of generation is explained in the picture below:
<img src="images/dinos3.png" style="width:500;height:300px;">

# References
- This exercise took inspiration from Andrej Karpathy's implementation: https://gist.github.com/karpathy/d4dee566867f8291f086. To learn more about text generation, also check out Karpathy's [blog post](http://karpathy.github.io/2015/05/21/rnn-effectiveness/).
- Sequence Models, Deep learning Specialization by Deeplearning.AI : https://www.coursera.org/learn/nlp-sequence-models
