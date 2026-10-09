---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Neural network model
item_title: More complex neural networks
duration: 8 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/a5AfY/more-complex-neural-networks
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# More complex neural networks — Transcript

**[0:00]** In the last video,
**[0:02]** you learned about the neural network layer and how
**[0:06]** that takes this inputs a vector of numbers and in turn,
**[0:09]** outputs another vector of numbers.
**[0:12]** In this video, let's use
**[0:13]** that layer to build a more complex neural network.
**[0:17]** Through this, I hope that
**[0:18]** the notation that we're using for
**[0:21]** neural networks will become clearer
**[0:23]** and more concrete as well. Let's take a look.
**[0:26]** This is the running example
**[0:27]** that I'm going to use throughout
**[0:29]** this video as an example
**[0:31]** of a more complex neural network.
**[0:33]** This network has four layers,
**[0:36]** not counting the input layer,
**[0:37]** which is also called Layer 0,
**[0:40]** where layers 1,
**[0:42]** 2, and 3 are hidden layers,
**[0:44]** and Layer 4 is the output layer,
**[0:47]** and Layer 0, as usual,
**[0:48]** is the input layer.
**[0:50]** By convention, when we say that
**[0:52]** a neural network has four layers,
**[0:55]** that includes all the hidden layers in the output layer,
**[0:57]** but we don't count the input layer.
**[1:00]** This is a neural network with four layers in
**[1:02]** the conventional way of counting layers in the network.
**[1:06]** Let's zoom in to Layer 3,
**[1:10]** which is the third and final hidden layer
**[1:13]** to look at the computations of that layer.
**[1:16]** Layer 3 inputs a vector,
**[1:19]** a superscript square bracket 2
**[1:22]** that was computed by the previous layer,
**[1:25]** and it outputs a_3,
**[1:29]** which is another vector.
**[1:31]** What is the computation that Layer 3 does in order to
**[1:35]** go from a_2 to a_3?
**[1:39]** If it has three neurons or we call it three hidden units,
**[1:45]** then it has parameters w_1,
**[1:48]** b_1, w_2, b_2, and w_3,
**[1:50]** b_3 and it computes a_1 equals sigmoid of w_1.
**[1:56]** product with this input to the layer plus b_1,
**[2:02]** and it computes a_2 equals sigmoid of w_2.
**[2:06]** product with again a_2,
**[2:08]** the input to the layer plus b_2 and so on to get a_3.
**[2:13]** Then the output of this layer
**[2:15]** is a vector comprising a_1,
**[2:18]** a_2, and a_3.
**[2:22]** Again, by convention,
**[2:24]** if we want to more
**[2:26]** explicitly denote that all of these are
**[2:28]** quantities associated with Layer 3
**[2:31]** then we add in all of these superscript,
**[2:33]** square brackets 3 here,
**[2:36]** to denote that these parameters
**[2:38]** w and b are the parameters associated with
**[2:40]** neurons in Layer 3 and that
**[2:43]** these activations are activations with Layer 3.
**[2:47]** Notice that this term here
**[2:49]** is w_1 superscript square bracket 3,
**[2:52]** meaning the parameters associated with Layer 3.
**[2:55]** product with a superscript square bracket 2,
**[3:00]** which was the output of Layer 2,
**[3:02]** which became the input to Layer 3.
**[3:04]** That's why it has a_3 here because it's
**[3:06]** a parameter associator of Layer 3. product with,
**[3:10]** and there's a_2 there because is the output of Layer 2.
**[3:13]** Now, let's just do
**[3:15]** a quick double check on our understanding of this.
**[3:18]** I'm going to hide the superscripts and subscripts
**[3:22]** associated with the second neuron
**[3:26]** and without rewinding this video,
**[3:28]** go ahead and rewind if you want,
**[3:30]** but prefer you not.
**[3:31]** But without rewinding this video,
**[3:34]** are you able to think through what are
**[3:36]** the missing superscripts and
**[3:38]** subscripts in this equation and fill them in yourself?
**[3:41]** Once you take a look at
**[3:43]** the end video quiz and see if you can figure out
**[3:46]** what are the appropriate superscripts and
**[3:47]** subscripts for this equation over here.
**[3:51]** If you chose the 1st option, then you got it right!
**[3:54]** The activation of the 2nd neuron at layer 3 is denoted
**[3:58]** by 'a' three two.
**[4:01]** To apply the activation function, g, lets use the
**[4:05]** parameters of this same neuron. So w and b  will have the same
**[4:11]** subscript 2 and superscript square bracket 3.
**[4:16]** The input features will be the output vector from the previous
**[4:20]** layer, which is layer 2.
**[4:23]** So that will be the vector 'a' superscript 2.
**[4:27]** The second option is using vector ‘a’ 3 which is not the
**[4:32]** output vector from the previous layer. The input to
**[4:35]** this layer is 'a' two.
**[4:38]** And the 3rd option has a two two as input,
**[4:43]** which is a single number rather than the vector
**[4:48]** Because recall that the correct input is a vector, a two,
**[4:52]** with the little arrow on top, and not a single number.
**[4:58]** To recap, a_3 is
**[5:02]** activation associated with Layer 3
**[5:04]** for the second neuron hence,
**[5:06]** this a_2 is a parameter associated with the third layer.
**[5:11]** For the second neuron,
**[5:12]** this is a_2,
**[5:13]** same as above and then
**[5:15]** plus b_3 too. Hopefully, that makes sense.
**[5:19]** Just the more general form of this equation for
**[5:23]** an arbitrary Layer 0 and for an arbitrary unit j,
**[5:27]** which is that a deactivation outputs of layer l,
**[5:32]** unit j, like a32,
**[5:35]** that's going to be the sigmoid function
**[5:38]** applied to this term,
**[5:40]** which is the wave vector of layer l,
**[5:43]** such as Layer 3 for the jth unit so there's a_2 again,
**[5:47]** in the example above, and so that's
**[5:50]** dot-producted with a deactivation value.
**[5:54]** Notice, this is not l,
**[5:55]** this is l minus 1,
**[5:57]** like a_2 above here because you're
**[6:00]** dot-producting with the output from
**[6:02]** the previous layer and then plus b,
**[6:05]** the parameter for this layer for that unit j.
**[6:08]** This gives you the activation of layer l unit j,
**[6:14]** where the superscript in square brackets l denotes
**[6:17]** layer l and a subscript j denotes unit j.
**[6:21]** When building neural networks,
**[6:23]** unit j refers to the jth neuron,
**[6:26]** so we use those terms a little bit
**[6:27]** interchangeably where each unit
**[6:29]** is a single neuron in the layer.
**[6:31]** G here is the sigmoid function.
**[6:33]** In the context of a neural network,
**[6:35]** g has another name,
**[6:37]** which is also called the activation function,
**[6:40]** because g outputs this activation value.
**[6:44]** When I say activation function,
**[6:46]** I mean this function g here.
**[6:48]** So far, the only activation function you've seen,
**[6:52]** this is a sigmoid function but next week,
**[6:54]** we'll look at when other functions,
**[6:56]** then the sigmoid function can be
**[6:58]** plugged in place of g as well..
**[7:00]** The activation function is just that function
**[7:03]** that outputs these activation values.
**[7:06]** Just one last piece of notation.
**[7:10]** In order to make all this notation consistent,
**[7:14]** I'm also going to give
**[7:17]** the input vector X and another name which is a_0,
**[7:20]** so this way, the same equation
**[7:23]** also works for the first layer,
**[7:25]** where when l is equal to 1,
**[7:27]** the activations of the first layer,
**[7:29]** that is a_1,
**[7:30]** would be the sigmoid times
**[7:32]** the weights dot-product with a_0,
**[7:35]** which is just this input feature vector X.
**[7:39]** With this notation, you now know how to compute
**[7:42]** the activation values of any layer in
**[7:45]** a neural network as a function of
**[7:47]** the parameters as well as
**[7:49]** the activations of the previous layer.
**[7:51]** You now know how to compute the activations of
**[7:54]** any layer given the activations of the previous layer.
**[7:58]** Let's put this into
**[8:00]** an inference algorithm for a neural network.
**[8:02]** In other words, how to get
**[8:04]** a neural network to make predictions.
**[8:06]** Let's go see that in the next video.
