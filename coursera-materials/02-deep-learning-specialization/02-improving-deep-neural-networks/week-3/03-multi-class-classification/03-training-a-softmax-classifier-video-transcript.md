---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 3
section: Multi-class Classification
item_title: Training a Softmax Classifier
duration: 10 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/LCsCH/training-a-softmax-classifier
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Training a Softmax Classifier — Transcript

**[0:00]** In the last video, you learned about the soft master,
**[0:02]** the softmax activation function.
**[0:04]** In this video, you deepen your understanding of softmax classification,
**[0:08]** and also learn how the training model that uses a softmax layer.
**[0:13]** Recall our earlier example where the output layer computes z[L] as follows.
**[0:18]** So we have four classes,
**[0:19]** c = 4 then z[L] can be (4,1) dimensional vector and we said we compute t
**[0:24]** which is this temporary variable that performs element y's exponentiation.
**[0:30]** And then finally, if the activation function for your output layer,
**[0:34]** g[L] is the softmax activation function, then your outputs will be this.
**[0:40]** It's basically taking the temporarily variable t and normalizing it to sum to 1.
**[0:45]** So this then becomes a(L).
**[0:49]** So you notice that in the z vector, the biggest element was 5, and
**[0:53]** the biggest probability ends up being this first probability.
**[0:57]** The name softmax comes from contrasting it to what's called a hard
**[1:02]** max which would have taken the vector Z and matched it to this vector.
**[1:07]** So hard max function will look at the elements of Z and just put a 1 in
**[1:12]** the position of the biggest element of Z and then 0s everywhere else.
**[1:18]** And so this is a very hard max where the biggest element gets a output of 1 and
**[1:23]** everything else gets an output of 0.
**[1:25]** Whereas in contrast,
**[1:27]** a softmax is a more gentle mapping from Z to these probabilities.
**[1:33]** So, I'm not sure if this is a great name but at least, that was the intuition
**[1:37]** behind why we call it a softmax, all this in contrast to the hard max.
**[1:43]** And one thing I didn't really show but had alluded to is that softmax regression or
**[1:47]** the softmax identification function generalizes the logistic activation
**[1:52]** function to C classes rather than just two classes.
**[1:56]** And it turns out that if C = 2, then softmax with
**[2:01]** C = 2 essentially reduces to logistic regression.
**[2:07]** And I'm not going to prove this in this video but the rough outline for
**[2:12]** the proof is that if C = 2 and if you apply softmax,
**[2:18]** then the output layer, a[L], will output two numbers if C = 2,
**[2:23]** so maybe it outputs 0.842 and 0.158, right?
**[2:28]** And these two numbers always have to sum to 1.
**[2:31]** And because these two numbers always have to sum to 1, they're actually redundant.
**[2:34]** And maybe you don't need to bother to compute two of them,
**[2:37]** maybe you just need to compute one of them.
**[2:39]** And it turns out that the way you end up computing that number reduces to
**[2:43]** the way that logistic regression is computing its single output.
**[2:48]** So that wasn't much of a proof but the takeaway from this is that softmax
**[2:53]** regression is a generalization of logistic regression to more than two classes.
**[2:58]** Now let's look at how you would actually train a neural network
**[3:02]** with a softmax output layer.
**[3:04]** So in particular,
**[3:04]** let's define the loss functions you use to train your neural network.
**[3:08]** Let's take an example.
**[3:09]** Let's see of an example in your training set where the target output,
**[3:15]** the ground true label is 0 1 0 0.
**[3:17]** So the example from the previous video,
**[3:20]** this means that this is an image of a cat because it falls into Class 1.
**[3:25]** And now let's say that your neural network is currently outputting y hat equals,
**[3:31]** so y hat would be a vector probability is equal to sum to 1.
**[3:35]** 0.1, 0.4, so you can check that sums to 1, and this is going to be a[L].
**[3:42]** So the neural network's not doing very well in this example because this is
**[3:46]** actually a cat and assigned only a 20% chance that this is a cat.
**[3:49]** So didn't do very well in this example.
**[3:52]** So what's the last function you would want to use to train this neural network?
**[3:56]** In softmax classification,
**[3:58]** they'll ask me to produce this negative sum of j=1 through 4.
**[4:03]** And it's really sum from 1 to C in the general case.
**[4:07]** We're going to just use 4 here, of yj log y hat of j.
**[4:14]** So let's look at our single example above to better understand what happens.
**[4:20]** Notice that in this example,
**[4:22]** y1 = y3 = y4 = 0 because those are 0s and only y2 = 1.
**[4:32]** So if you look at this summation,
**[4:35]** all of the terms with 0 values of yj were equal to 0.
**[4:39]** And the only term you're left with is -y2 log y hat 2,
**[4:47]** because we use sum over the indices of j,
**[4:47]** all the terms will end up 0, except when j is equal to 2.
**[4:52]** And because y2 = 1, this is just -log y hat 2.
**[4:58]** So what this means is that,
**[5:00]** if your learning algorithm is trying to make this small
**[5:04]** because you use gradient descent to try to reduce the loss on your training set.
**[5:09]** Then the only way to make this small is to make this small.
**[5:12]** And the only way to do that is to make y hat 2 as big as possible.
**[5:18]** And these are probabilities, so they can never be bigger than 1.
**[5:20]** But this kind of makes sense because x for this example is the picture of a cat,
**[5:26]** then you want that output probability to be as big as possible.
**[5:31]** So more generally, what this loss function does is it looks at whatever is the ground
**[5:35]** true class in your training set, and it tries to make the corresponding
**[5:39]** probability of that class as high as possible.
**[5:42]** If you're familiar with maximum likelihood estimation statistics,
**[5:46]** this turns out to be a form of maximum likelyhood estimation.
**[5:49]** But if you don't know what that means, don't worry about it.
**[5:51]** The intuition we just talked about will suffice.
**[5:54]** Now this is the loss on a single training example.
**[5:57]** How about the cost J on the entire training set.
**[6:00]** So, the class of setting of the parameters and so on, of all the ways and
**[6:05]** biases, you define that as pretty much what you'd guess,
**[6:09]** sum of your entire training sets are the loss,
**[6:12]** your learning algorithms predictions are summed over your training samples.
**[6:18]** And so,
**[6:18]** what you do is use gradient descent in order to try to minimize this class.
**[6:23]** Finally, one more implementation detail.
**[6:26]** Notice that because C is equal to 4, y is a 4 by 1 vector, and
**[6:30]** y hat is also a 4 by 1 vector.
**[6:34]** So if you're using a vectorized limitation, the matrix capital
**[6:38]** Y is going to be y(1), y(2), through y(m), stacked horizontally.
**[6:45]** And so for example, if this example up here is your first training example
**[6:50]** then the first column of this matrix Y will be 0 1 0 0 and then maybe the second
**[6:56]** example is a dog, maybe the third example is a none of the above, and so on.
**[7:01]** And then this matrix Y will end up being a 4 by m dimensional matrix.
**[7:08]** And similarly, Y hat will be y hat 1 stacked up horizontally
**[7:13]** going through y hat m, so this is actually y hat 1.
**[7:19]** All the output on the first training example then y hat will these 0.3,
**[7:25]** 0.2, 0.1, and 0.4, and so on.
**[7:29]** And y hat itself will also be 4 by m dimensional matrix.
**[7:33]** Finally, let's take a look at how you'd implement gradient descent when you
**[7:37]** have a softmax output layer.
**[7:38]** So this output layer will compute z[L] which is C by 1 in our example, 4 by 1 and
**[7:46]** then you apply the softmax attribution function to get a[L], or y hat.
**[7:53]** And then that in turn allows you to compute the loss.
**[7:58]** So with talks about how to implement the forward propagation
**[8:02]** step of a neural network to get these outputs and to compute that loss.
**[8:07]** How about the back propagation step, or gradient descent?
**[8:10]** Turns out that the key step or
**[8:11]** the key equation you need to initialize back prop is this expression,
**[8:16]** that the derivative with respect to z at the loss layer, this turns out,
**[8:20]** you can compute this y hat, the 4 by 1 vector, minus y, the 4 by 1 vector.
**[8:26]** So you notice that all of these are going to be 4 by 1 vectors when
**[8:30]** you have 4 classes and C by 1 in the more general case.
**[8:34]** And so this going by our usual definition of what is dz,
**[8:37]** this is the partial derivative of the class function with respect to z[L].
**[8:42]** If you are an expert in calculus, you can derive this yourself.
**[8:47]** Or if you're an expert in calculus, you can try to derive this yourself, but
**[8:50]** using this formula will also just work fine,
**[8:52]** if you have a need to implement this from scratch.
**[8:54]** With this, you can then compute dz[L] and then sort of start off the back prop
**[8:59]** process to compute all the derivatives you need throughout your neural network.
**[9:05]** But it turns out that in this week's primary exercise, we'll start to use one
**[9:09]** of the deep learning program frameworks and for those primary frameworks,
**[9:13]** usually it turns out you just need to focus on getting the forward prop right.
**[9:17]** And so long as you specify it as a primary framework, the forward prop pass,
**[9:21]** the primary framework will figure out how to do back prop,
**[9:24]** how to do the backward pass for you.
**[9:27]** So this expression is worth keeping in mind for if you ever need to implement
**[9:32]** softmax regression, or softmax classification from scratch.
**[9:35]** Although you won't actually need this in this week's primary exercise because
**[9:39]** the primary framework you use will take care of this derivative
**[9:42]** computation for you.
**[9:43]** So that's it for softmax classification,
**[9:46]** with it you can now implement learning algorithms to characterized inputs
**[9:51]** into not just one of two classes, but one of C different classes.
**[9:56]** Next, I want to show you some of the deep learning programming frameworks which
**[10:01]** can make you much more efficient in terms of implementing deep learning algorithms.
**[10:05]** Let's go on to the next video to discuss that.
