---
type: video-transcript
specialization: Deep Learning Specialization
course: Sequence Models
week: 1
section: Recurrent Neural Networks
item_title: Backpropagation Through Time
duration: 6 min
source_url: https://www.coursera.org/learn/nlp-sequence-models/lecture/bc7ED/backpropagation-through-time
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Backpropagation Through Time — Transcript

**[0:00]** You've already learned about the basic structure of an RNN.
**[0:03]** In this video, you'll see how backpropagation in a recurrent neural network works.
**[0:08]** As usual, when you implement this in one of the programming frameworks, often,
**[0:12]** the programming framework will automatically take care of backpropagation.
**[0:16]** But I think it's still useful to have a rough sense of how backprop works in RNNs.
**[0:21]** Let's take a look.
**[0:23]** You've seen how, for forward prop,
**[0:25]** you would computes these activations from left to right as follows in the neural network,
**[0:33]** and so you've outputs all of the predictions.
**[0:37]** In backprop, as you might already have guessed,
**[0:40]** you end up carrying
**[0:42]** backpropagation calculations in basically the opposite direction
**[0:46]** of the forward prop arrows.
**[0:49]** So, let's go through the forward propagation calculation.
**[0:52]** You're given this input sequence x_1, x_2,
**[0:56]** x_3, up to x_tx.
**[1:01]** And then using x_1 and say, a_0,
**[1:06]** you're going to compute the activation, times that one,
**[1:11]** and then together, x_2 together with a_1 are used to compute a_2,
**[1:17]** and then a_3, and so on, up to a_tx.
**[1:24]** All right. And then to actually compute a_1,
**[1:27]** you also need the parameters.
**[1:29]** We'll just draw this in green, W_a and b_a,
**[1:32]** those are the parameters that are used to compute a_1.
**[1:35]** And then, these parameters are actually used for every single timestep so,
**[1:39]** these parameters are actually used to compute a_2, a_3,
**[1:45]** and so on, all the activations up to last timestep depend on the parameters W_a and b_a.
**[1:52]** Let's keep fleshing out this graph.
**[1:55]** Now, given a_1, your neural network can then compute the first prediction, y-hat_1,
**[2:01]** and then the second timestep, y-hat_2, y-hat_3,
**[2:07]** and so on, with y-hat_ty.
**[2:14]** And let me again draw the parameters of a different color.
**[2:18]** So, to compute y-hat,
**[2:22]** you need the parameters,
**[2:24]** W_y as well as b_y,
**[2:27]** and this goes into this node as well as all the others.
**[2:32]** So, I'll draw this in green as well.
**[2:34]** Next, in order to compute backpropagation,
**[2:36]** you need a loss function.
**[2:39]** So let's define an element-wise loss force,
**[2:42]** which is supposed for a certain word in the sequence.
**[2:45]** It is a person's name,
**[2:46]** so y_t is one.
**[2:48]** And your neural network outputs some probability of maybe
**[2:51]** 0.1 of the particular word being a person's name.
**[2:55]** So I'm going to define this as the standard logistic regression loss,
**[3:00]** also called the cross entropy loss.
**[3:04]** This may look familiar to you from where we were previously
**[3:07]** looking at binary classification problems.
**[3:10]** So this is the loss associated with
**[3:12]** a single prediction at a single position or at a single time set,
**[3:15]** t, for a single word.
**[3:17]** Let's now define the overall loss of the entire sequence,
**[3:21]** so L will be defined as the sum overall t equals one to,
**[3:28]** i guess, T_x or T_y.
**[3:29]** T_x is equals to T_y in this example of the losses
**[3:33]** for the individual timesteps, comma y_t.
**[3:38]** And then, so, just have to L without this
**[3:42]** superscript T. This is the loss for the entire sequence.
**[3:47]** So, in a computation graph,
**[3:48]** to compute the loss given y-hat_1,
**[3:52]** you can then compute the loss for
**[3:54]** the first timestep given that you compute the loss for the second timestep,
**[3:59]** the loss for the third timestep,
**[4:03]** and so on, the loss for the final timestep.
**[4:07]** And then lastly, to compute the overall loss,
**[4:11]** we will take these and sum them all up to compute the final L using that equation,
**[4:19]** which is the sum of the individual per timestep losses.
**[4:23]** So, this is the computation problem
**[4:25]** and from the earlier examples you've seen of backpropagation,
**[4:29]** it shouldn't surprise you that backprop then just requires
**[4:34]** doing computations or parsing messages in the opposite directions.
**[4:39]** So, all of the four propagation steps arrows,
**[4:43]** so you end up doing that.
**[4:46]** And that then, allows you to compute all the appropriate quantities that lets you then,
**[4:53]** take the riveters, respected parameters,
**[4:55]** and update the parameters using gradient descent.
**[4:59]** Now, in this back propagation procedure,
**[5:02]** the most significant message or the most significant recursive calculation is this one,
**[5:08]** which goes from right to left,
**[5:11]** and that's why it gives this algorithm as well,
**[5:13]** a pretty fast full name called backpropagation through time.
**[5:17]** And the motivation for this name is that for forward prop,
**[5:20]** you are scanning from left to right,
**[5:22]** increasing indices of the time, t, whereas,
**[5:25]** the backpropagation, you're going from right to left,
**[5:27]** you're kind of going backwards in time.
**[5:29]** So this gives this, I think a really cool name,
**[5:31]** backpropagation through time, where you're going backwards in time, right?
**[5:36]** That phrase really makes it sound like you need a time machine to implement this output,
**[5:40]** but I just thought that backprop through time is
**[5:42]** just one of the coolest names for an algorithm.
**[5:45]** So, I hope that gives you a sense of how forward prop and backprop in RNN works.
**[5:50]** Now, so far, you've only seen this main motivating example in RNN,
**[5:54]** in which the length of the input sequence was equal to the length of the output sequence.
**[6:00]** In the next video,
**[6:01]** I want to show you a much wider range of RNN architecture,
**[6:06]** so I'll let you tackle a much wider set of applications. Let's go on to the next video.
