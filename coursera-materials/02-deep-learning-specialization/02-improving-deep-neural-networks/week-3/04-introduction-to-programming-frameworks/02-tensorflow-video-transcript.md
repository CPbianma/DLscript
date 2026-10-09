---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 3
section: Introduction to Programming Frameworks
item_title: TensorFlow
duration: 15 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/zcZlH/tensorflow
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# TensorFlow — Transcript

**[0:00]** Hi and welcome back. There are
**[0:02]** few deep learning program frameworks that can help
**[0:05]** you be much more efficient in how you
**[0:07]** develop and use deep learning algorithms.
**[0:10]** One of these frameworks is TensorFlow.
**[0:13]** What I hope to do in this video is step
**[0:16]** through with you the basic structure of
**[0:18]** a TensorFlow program so that you know how
**[0:21]** you could use TensorFlow to implement such programs,
**[0:25]** implements neural networks yourself.
**[0:28]** Then after this video,
**[0:30]** I'll leave you to dive into
**[0:31]** some more of the details and gain
**[0:33]** practice programming with TensorFlow
**[0:35]** in this week's program exercise.
**[0:38]** This week's program exercise
**[0:40]** does require a law extra time.
**[0:42]** Please do plan or budget for
**[0:44]** a little bit more time to complete it.
**[0:47]** As a motivating problem,
**[0:49]** let's say that you have
**[0:51]** some cost function J that you want to minimize.
**[0:54]** For this example, I'm going to use
**[0:56]** this highly simple cost function,
**[0:58]** J of w equals w squared minus 10w plus 25.
**[1:05]** That's the cost function.
**[1:07]** You might notice that this function is actually
**[1:09]** w minus five squared.
**[1:14]** If you expand out this quadratic,
**[1:15]** you get the expression above.
**[1:16]** The value of w that minimizes this,
**[1:19]** is w equals five.
**[1:21]** But let's say we didn't know that,
**[1:23]** and you just have this function.
**[1:25]** Let us see how you can implement something in
**[1:28]** TensorFlow to minimize this.
**[1:30]** Because a very similar structure,
**[1:32]** a program can be used to
**[1:33]** train neural networks where you can have
**[1:35]** some complicated cost function J of wb
**[1:39]** depending on all the parameters of your neural network.
**[1:43]** Then similarly, you build a use
**[1:45]** TensorFlow to automatically try
**[1:48]** to find values of w and
**[1:50]** b that minimize this cost function,
**[1:53]** but let's start with the simpler example on the left.
**[1:57]** Here I am in Python in my Jupyter Notebook.
**[2:02]** In order to startup TensorFlow,
**[2:05]** you type import NumPy or NumPy as NP,
**[2:10]** import TensorFlow as TF.
**[2:14]** This is idiomatic.
**[2:16]** This is what pretty much everyone tags
**[2:18]** exactly to import TensorFlow as TF.
**[2:21]** Next thing you want to do is define
**[2:24]** the parameter W. Intensive though
**[2:27]** you're going to use tf.variable
**[2:32]** to signify that this is a variable initialize it to zero,
**[2:37]** and the type of the variable is
**[2:39]** a floating point number, dtype equals tf.
**[2:43]** float 32, says a TensorFlow floating-point number.
**[2:48]** Next, let's define
**[2:50]** the optimization algorithm you're going to use.
**[2:52]** In this case, the Adam optimization
**[2:54]** algorithm, optimizing equals tf.keras.optimizers.Adam.
**[3:01]** Let's set the learning rate to 0.1.
**[3:06]** Now we can define the cost function.
**[3:09]** Remember the cost function was w
**[3:12]** squared minus 10w plus 25.
**[3:16]** Certainly write that down.
**[3:18]** The cost is w squared minus 10w plus 25.
**[3:27]** The great thing about TensorFlow is
**[3:29]** you only have to implement forward prop,
**[3:32]** that is you only have to write the code to
**[3:34]** compute the value of the cost function.
**[3:37]** TensorFlow can figure out how to do
**[3:39]** the backprop or do the gradient computation.
**[3:42]** One way to do this is to use gradient tape.
**[3:45]** Let me show you the syntax with tf.GradientTape as tape,
**[3:54]** computes the causes follows.
**[3:57]** The intuition behind the name gradient tape
**[3:59]** is by an analogy to the old-school cassette tapes,
**[4:03]** where Gradient Tape will record the sequence of
**[4:06]** operations as you're computing
**[4:08]** the cost function in the forward prop step.
**[4:10]** Then when you play
**[4:12]** the tape backwards, in backwards order,
**[4:14]** it can revisit the order of operations in reverse order,
**[4:18]** and along the way, compute backprop and the gradients.
**[4:22]** Now let's define a training step function to loop over.
**[4:27]** We're going to define a single training step
**[4:30]** as this function.
**[4:32]** In order to carry out one iteration of training,
**[4:37]** you have to define what are the trainable variables.
**[4:40]** Trainable variables is just a list with only w. We are
**[4:49]** then going to compute the gradients
**[4:52]** with the tape cost trainable variables.
**[4:59]** Having done this, you can now use the optimizer to apply
**[5:04]** the gradients and the gradients are
**[5:07]** grads and trainable variables.
**[5:12]** The syntax we are going to use,
**[5:14]** is we're actually going to use the zip functions,
**[5:16]** built-in Python function to take the list of gradients,
**[5:19]** to take the lists are trainable variables and
**[5:21]** pair them up so that the gradients and zip
**[5:24]** the function just takes two lists
**[5:26]** and pairs up the corresponding elements.
**[5:29]** I'm going to type print w here just to print
**[5:31]** the initial value of w
**[5:33]** we've not actually run train_step yet.
**[5:35]** Hopefully I've no syntax errors.
**[5:38]** W is initially the value of 0,
**[5:41]** which is what we have initialized it to.
**[5:43]** Now let's run one step
**[5:46]** of our little learning algorithm
**[5:49]** and print the new value of w,
**[5:52]** and now it's increased a little bit from 0 to about 0.1.
**[5:57]** Now let's run 1000 iterations of our train_step.
**[6:02]** If I arrange 1000 train step print W,
**[6:10]** let's see what happens.
**[6:12]** Run pretty quickly. Now W is nearly
**[6:17]** five which we knew was the minimum of this cost function.
**[6:22]** Isn't that cool? We just specify the cost function.
**[6:25]** Didn't have to take derivatives and TensorFlow,
**[6:29]** figured out how to minimize this for us.
**[6:31]** I hope this gives you a sense of
**[6:33]** the broad structure of a TensorFlow program.
**[6:36]** As you do this week's program exercise
**[6:38]** and play more with TensorFlow code yourself,
**[6:41]** some of these functions that I just used
**[6:43]** here will become more familiar.
**[6:46]** Just a couple things to notice,
**[6:49]** w is the parameter you want to optimize.
**[6:53]** That's why we declared w as a variable.
**[6:58]** All we had to do was use a GradientTape to record
**[7:01]** the order of the sequence of
**[7:03]** operations needed to compute the cost function,
**[7:06]** and that was the only problem and TensorFlow could
**[7:10]** figure out automatically how to take
**[7:11]** derivatives with respect to the cost function.
**[7:14]** That's why in TensorFlow,
**[7:17]** you basically had to only implement the fore prop step,
**[7:21]** and it will figure out how to
**[7:23]** do the gradient computation.
**[7:25]** Now, there's one more feature
**[7:27]** of TensorFlow that I wanted to show you.
**[7:29]** In the example we went through so far,
**[7:32]** the cost function is
**[7:33]** a fixed function of the parameter or the variable
**[7:37]** w. But what are the function you want to minimize
**[7:40]** is a function of not just w,
**[7:44]** but also a function of your training step.
**[7:47]** Unless you have some training data x,
**[7:49]** and x or x, and y,
**[7:52]** and you're training a neural network with
**[7:54]** a cost function depends on your data,
**[7:57]** x or x and y,
**[7:58]** as well as the parameters
**[8:01]** w. How do you get
**[8:03]** that training data into a TensorFlow program?
**[8:07]** Let's go through another version
**[8:09]** of how to implement all this.
**[8:12]** I'm still going to define w as the variable.
**[8:19]** Also I'm going to add them optimizer,
**[8:22]** but now I'm going to define x as a list of numbers as
**[8:29]** array and I'm going to plug in 1 negative 10 and 25.
**[8:38]** This will be another float 32.
**[8:43]** These three numbers, 1 negative 10 and 25,
**[8:47]** will play the role of
**[8:49]** the coefficients of the cost function.
**[8:51]** You can think of x as being like data that
**[8:56]** controls the coefficients of
**[8:58]** this quadratic cost function.
**[9:00]** Let me now define
**[9:03]** the cost function which will minimize as same as before,
**[9:08]** except that now I'm going to write x of 0 times w
**[9:13]** plus x of 1
**[9:19]** times w plus x2.
**[9:24]** This is the same cost function as the one above,
**[9:27]** except that the coefficients are now controlled by
**[9:30]** this little piece of data x that we have.
**[9:34]** Now this cost function computes
**[9:37]** exactly the same cost function as you had above,
**[9:39]** except that this little piece of data in
**[9:43]** the array x controls
**[9:45]** the coefficients of the quadratic cost function.
**[9:48]** Now, let me write print w this should do nothing
**[9:51]** because w is still 0,
**[9:54]** is just initial value.
**[9:56]** But if you then use the optimizer to take
**[10:00]** one step of the optimization algorithm,
**[10:05]** then let's print double again and see if that works.
**[10:10]** Great, now this has taken one step of
**[10:14]** Adam Optimization and so w is again roughly 0.1.
**[10:20]** This syntax, optimizer dot minimize cost function,
**[10:25]** and then then list of variables W,
**[10:28]** that is a simpler alternative piece of syntax,
**[10:33]** or that's the same thing as these lines up above with
**[10:35]** the gradients tape and apply gradients.
**[10:39]** Now that we have a single training set implementer,
**[10:42]** let's put the whole thing in a loop.
**[10:44]** Training, X, W optimizer,
**[10:52]** define the cost function
**[10:54]** within the scope of this function,
**[10:56]** and then for I in the range 1000,
**[11:03]** lets run a thousand iterations and
**[11:07]** then lets run W.
**[11:26]** Lets see what that does.
**[11:30]** There you go, and now W is nearly at the minimum set,
**[11:36]** roughly the value of five.
**[11:37]** Hopefully this gives you a sense
**[11:39]** of what TensorFlow can do,
**[11:41]** and the thing that makes it so powerful is,
**[11:44]** all you need to do is specify
**[11:45]** how to compute the cost function,
**[11:47]** and then it takes derivatives and it can apply
**[11:49]** an optimizer with
**[11:51]** pretty much just one or two lines of codes.
**[11:53]** Here's the code again, and in
**[11:55]** case some of these functions of
**[11:57]** variables still seem a little bit mysterious to you,
**[11:59]** they will become more familiar
**[12:01]** after you've practiced with it
**[12:02]** a couple of times by
**[12:04]** working through the programming exercise.
**[12:06]** What is this code really doing?
**[12:09]** Let's focus on this equation.
**[12:13]** The heart of the TensorFlow program
**[12:16]** is something to compute the cost,
**[12:18]** and then TensorFlow automatically figures out
**[12:21]** the derivatives and how to minimize the cost.
**[12:23]** What this line of code is doing is allowing
**[12:26]** TensorFlow to construct a computation graph.
**[12:29]** What a computation graph does is the following,
**[12:33]** it takes X (0) and it takes W,
**[12:37]** and W gets squared.
**[12:39]** There's W squared and then X (0)
**[12:43]** and W squared can multiply together to
**[12:47]** give X (0) times W
**[12:51]** squared and so one
**[12:55]** through multiple steps until eventually,
**[12:59]** this gets built up to compute the cost function.
**[13:04]** I guess the last step would have been adding
**[13:08]** in that last coefficient X (2).
**[13:11]** The nice thing about TensorFlow is that by
**[13:14]** implementing base the four a prop,
**[13:16]** through this computation graph,
**[13:18]** TensorFlow will automatically figure out
**[13:21]** all the necessary backward calculations.
**[13:25]** It'll automatically be able to figure out
**[13:29]** all the necessary backward steps
**[13:33]** needed to implement back-prop.
**[13:35]** Isn't that nice? That's why you don't
**[13:38]** need to explicitly implement back-prop,
**[13:41]** TensorFlow figures it out for you.
**[13:44]** This is one of the things that makes
**[13:46]** the programe frameworks help you become really
**[13:48]** efficient and there are also a lot of things
**[13:50]** you can change with just one line of codes.
**[13:53]** For example, if you don't want to use
**[13:56]** the Adam Optimizer and you want to use a different one,
**[14:01]** then just change this one line of
**[14:03]** code and you can quickly
**[14:06]** swap it out for a different optimization algorithm.
**[14:09]** All of the popular
**[14:11]** modern deep learning programming frameworks
**[14:13]** support things like these and
**[14:15]** it makes it much easier to
**[14:18]** develop even pretty complex neural networks.
**[14:22]** I hope that gave you a sense of
**[14:25]** the typical structure of a TensorFlow program.
**[14:28]** To recap material from this week,
**[14:31]** you saw how to systematically
**[14:33]** organize the hyperparameter search process.
**[14:36]** You also saw batch normalization and how you
**[14:39]** can use that to speed up your neural network training.
**[14:43]** We also chatted about
**[14:44]** deep learning and programming frameworks,
**[14:46]** and you learned about TensorFlow.
**[14:48]** I hope that you go on and
**[14:51]** try out and enjoy this week's programming exercise,
**[14:54]** which will help you to gain
**[14:55]** even greater familiarity with these ideas.
