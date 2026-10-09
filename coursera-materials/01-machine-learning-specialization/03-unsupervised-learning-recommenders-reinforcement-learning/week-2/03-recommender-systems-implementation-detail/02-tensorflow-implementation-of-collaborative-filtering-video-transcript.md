---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Recommender systems implementation detail
item_title: TensorFlow implementation of collaborative filtering
duration: 12 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/wmHWA/tensorflow-implementation-of-collaborative-filtering
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# TensorFlow implementation of collaborative filtering — Transcript

**[0:02]** In this video, we'll take a look at how you can use TensorFlow to implement
**[0:06]** the collaborative filtering algorithm.
**[0:09]** You might be used to thinking of TensorFlow as a tool for
**[0:12]** building neural networks.
**[0:13]** And it is.
**[0:14]** It's a great tool for building neural networks.
**[0:17]** And it turns out that TensorFlow can also be very helpful for
**[0:20]** building other types of learning algorithms as well.
**[0:23]** Like the collaborative filtering algorithm.
**[0:26]** One of the reasons I like using TensorFlow for talks like these is that for
**[0:31]** many applications in order to implement gradient descent,
**[0:36]** you need to find the derivatives of the cost function, but TensorFlow
**[0:41]** can automatically figure out for you what are the derivatives of the cost function.
**[0:47]** All you have to do is implement the cost function and without needing to know
**[0:51]** any calculus, without needing to take derivatives yourself,
**[0:55]** you can get TensorFlow with just a few lines of code
**[0:58]** to compute that derivative term, that can be used to optimize the cost function.
**[1:02]** Let's take a look at how all this works.
**[1:05]** You might remember this diagram here on the right from course one.
**[1:10]** This is exactly the diagram that we had looked at when we talked
**[1:14]** about optimizing w.
**[1:16]** When we were working through our first linear regression example.
**[1:21]** And at that time we had set b=0.
**[1:24]** And so the model was just predicting f(x)=w.x.
**[1:29]** And we wanted to find the value of w that minimizes the cost function J.
**[1:34]** So the way we were doing that was via a gradient descent update,
**[1:38]** which looked like this, where w gets repeatedly updated as w minus
**[1:43]** the learning rate alpha times the derivative term.
**[1:47]** If you are updating b as well, this is the expression you will use.
**[1:52]** But if you said b=0, you just forgo the second update and
**[1:56]** you keep on performing this gradient descent update until convergence.
**[2:01]** Sometimes computing this derivative or partial derivative term can be difficult.
**[2:08]** And it turns out that TensorFlow can help with that.
**[2:12]** Let's see how.
**[2:13]** I'm going to use a very simple cost
**[2:17]** function J=(wx-1) squared.
**[2:22]** So wx is our simplified f w of x and
**[2:27]** y is equal to 1.
**[2:30]** And so this would be the cost function if we had f(x) equals
**[2:35]** wx,y equals 1 for the one training example that we have, and
**[2:40]** if we were not optimizing this respect to b.
**[2:43]** So the gradient descent algorithm will repeat until convergence
**[2:48]** this update over here.
**[2:50]** It turns out that if you implement the cost function J over here,
**[2:54]** TensorFlow can automatically compute for
**[2:57]** you this derivative term and thereby get gradient descent to work.
**[3:02]** I'll give you a high level overview of what this code does, w=tf.variable(3.0).
**[3:09]** Takes the parameter w and initializes it to the value of 3.0.
**[3:14]** Telling TensorFlow that w is a variable is how we tell
**[3:19]** it that w is a parameter that we want to optimize.
**[3:24]** I'm going to set x=1.0, y=1.0, and the learning rate alpha to be equal to 0.01.
**[3:31]** And let's run gradient descent for 30 iterations.
**[3:34]** So in this code will still do for iter in range iterations, so for 30 iterations.
**[3:40]** And this is the syntax to get TensorFlow to automatically compute derivatives
**[3:45]** for you.
**[3:46]** TensorFlow has a feature called a gradient tape.
**[3:49]** And if you write this with tf our gradient tape as tape f.
**[3:54]** This is compute f(x) as w*x and
**[3:59]** compute J as f(x)-y squared.
**[4:04]** Then by telling TensorFlow how to compute to costJ, and
**[4:08]** by doing it with the gradient taped syntax as follows,
**[4:12]** TensorFlow will automatically record the sequence of steps.
**[4:16]** The sequence of operations needed to compute the costJ.
**[4:21]** And this is needed to enable automatic differentiation.
**[4:25]** Next TensorFlow will have saved the sequence of operations in tape,
**[4:30]** in the gradient tape.
**[4:32]** And with this syntax, TensorFlow will automatically
**[4:37]** compute this derivative term, which I'm going to call dJdw.
**[4:42]** And TensorFlow knows you want to take the derivative respect to w.
**[4:47]** That w is the parameter you want to optimize because you had told it so
**[4:52]** up here.
**[4:52]** And because we're also specifying it down here.
**[4:55]** So now you compute the derivatives, finally you can carry out this
**[5:00]** update by taking w and subtracting from it the learning rate
**[5:05]** alpha times that derivative term that we just got from up above.
**[5:10]** TensorFlow variables, tier variables requires special handling.
**[5:14]** Which is why instead of setting w to be w minus alpha times
**[5:18]** the derivative in the usual way, we use this assigned add function.
**[5:23]** But when you get to the practice lab, don't worry about it.
**[5:25]** We'll give you all the syntax you need in order to implement the collaborative
**[5:29]** filtering algorithm correctly.
**[5:31]** So notice that with the gradient tape feature of TensorFlow,
**[5:35]** the main work you need to do is to tell it how to compute the cost function J.
**[5:41]** And the rest of the syntax causes TensorFlow to
**[5:45]** automatically figure out for you what is that derivative?
**[5:50]** And with this TensorFlow we'll start with finding the slope of this,
**[5:56]** at 3 shown by this dash line.
**[5:58]** Take a gradient step and update w and compute the derivative again and
**[6:04]** update w over and over until eventually it gets to
**[6:08]** the optimal value of w, which is at w equals 1.
**[6:12]** So this procedure allows you to implement gradient descent without ever
**[6:17]** having to figure out yourself how to compute this derivative term.
**[6:22]** This is a very powerful feature of TensorFlow called Auto Diff.
**[6:27]** And some other machine learning packages like pytorch also support Auto Diff.
**[6:33]** Sometimes you hear people call this Auto Grad.
**[6:36]** The technically correct term is Auto Diff, and
**[6:39]** Auto Grad is actually the name of the specific software package for
**[6:43]** doing automatic differentiation, for taking derivatives automatically.
**[6:47]** But sometimes if you hear someone refer to Auto Grad, they're just referring to this
**[6:51]** same concept of automatically taking derivatives.
**[6:54]** So let's take this and look at how you can implement to collaborative
**[6:59]** filtering algorithm using Auto Diff.
**[7:01]** And in fact, once you can compute derivatives automatically,
**[7:04]** you're not limited to just gradient descent.
**[7:07]** You can also use a more powerful optimization algorithm,
**[7:10]** like the adam optimization algorithm.
**[7:13]** In order to implement the collaborative filtering algorithm TensorFlow,
**[7:19]** this is the syntax you can use.
**[7:21]** Let's starts with specifying that the optimizer is keras
**[7:26]** optimizers adam with learning rate specified here.
**[7:30]** And then for say, 200 iterations,
**[7:33]** here's the syntax as before with tf gradient tape, as tape,
**[7:38]** you need to provide code to compute the value of the cost function J.
**[7:43]** So recall that in collaborative filtering,
**[7:47]** the cost function J takes is input parameters x, w, and
**[7:51]** b as well as the ratings mean normalized.
**[7:55]** So that's why I'm writing y norm, r(i,j) specifying which values have a rating,
**[8:01]** number of users or nu in our notation, number of movies or nm in our notation or
**[8:06]** just num as well as the regularization parameter lambda.
**[8:10]** And if you can implement this cost function J,
**[8:13]** then this syntax will cause TensorFlow to figure out the derivatives for you.
**[8:18]** Then this syntax will cause TensorFlow to record the sequence of operations used to
**[8:23]** compute the cost.
**[8:24]** And then by asking it to give you grads equals tape.gradient,
**[8:29]** this will give you the derivative of the cost function with respect to x, w, and b.
**[8:36]** And finally with the optimizer that we had specified up on top,
**[8:40]** as the adam optimizer.
**[8:42]** You can use the optimizer with the gradients that we just computed.
**[8:47]** And does it function in python is just a function that rearranges the numbers into
**[8:52]** an appropriate ordering for the applied gradients function.
**[8:55]** If you are using gradient descent for collateral filtering,
**[9:00]** recall that the cost function J would be a function of w, b as well as x.
**[9:05]** And if you are applying gradient descent,
**[9:07]** you take the partial derivative respect the w.
**[9:10]** And then update w as follows.
**[9:12]** And you would also take the partial derivative of this respect to b.
**[9:16]** And update b as follows.
**[9:18]** And similarly update the features x as follows.
**[9:22]** And you repeat until convergence.
**[9:24]** But as I mentioned earlier with TensorFlow and
**[9:28]** Auto Diff you're not limited to just gradient descent.
**[9:32]** You can also use a more powerful optimization algorithm like the adam
**[9:36]** optimizer.
**[9:37]** The data set you use in the practice lab is a real data set comprising
**[9:42]** actual movies rated by actual people.
**[9:45]** This is the movie lens dataset and it's due to Harper and Konstan.
**[9:49]** And I hope you enjoy running this algorithm on a real data set of movies,
**[9:54]** and ratings and see for yourself the results that this algorithm can get.
**[9:58]** So that's it.
**[9:59]** That's how you can implement the collaborative filtering algorithm in
**[10:03]** TensorFlow.
**[10:03]** If you're wondering why do we have to do it this way?
**[10:06]** Why couldn't we use a dense layer and then model compiler and model fit?
**[10:11]** The reason we couldn't use that old recipe is, the collateral filtering algorithm and
**[10:17]** cost function, it doesn't neatly fit into the dense layer or
**[10:20]** the other standard neural network layer types of TensorFlow.
**[10:24]** That's why we had to implement it this other way where we would
**[10:27]** implement the cost function ourselves.
**[10:29]** But then use TensorFlow's tools for automatic differentiation,
**[10:33]** also called Auto Diff.
**[10:34]** And use TensorFlow's implementation of the adam optimization algorithm
**[10:39]** to let it do a lot of the work for us of optimizing the cost function.
**[10:44]** If the model you have is a sequence of dense neural network layers or
**[10:48]** other types of layers supported by TensorFlow, and
**[10:52]** the old implementation recipe of model compound model fit works.
**[10:57]** But even when it isn't, these tools TensorFlow give you a very effective way to
**[11:02]** implement other learning algorithms as well.
**[11:05]** And so I hope you enjoy playing more with the collaborative filtering exercise in
**[11:10]** this week's practice lab.
**[11:11]** And looks like there's a lot of code and lots of syntax, don't worry about it.
**[11:15]** Make sure you have what you need to complete that exercise successfully.
**[11:20]** And in the next video, I'd like to also move on to discuss more of the nuances of
**[11:25]** collateral filtering and specifically the question of how do you find related items,
**[11:31]** given one movie, whether other movies similar to this one.
**[11:35]** Let's go on to the next video
