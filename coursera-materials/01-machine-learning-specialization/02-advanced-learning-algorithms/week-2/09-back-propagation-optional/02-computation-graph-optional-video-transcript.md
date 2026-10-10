---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Back Propagation (Optional)
item_title: Computation graph (Optional)
duration: 19 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/rhcTZ/computation-graph-optional
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Computation graph (Optional) — Transcript

**[0:00]** The computation graph is a key idea in deep learning,
**[0:04]** and it is also
**[0:05]** how programming frameworks like TensorFlow,
**[0:08]** automatic compute derivatives of your neural networks.
**[0:12]** Let's take a look at how it works.
**[0:14]** Let me illustrate the concept of
**[0:16]** a computation graph with a small neural network example.
**[0:20]** This neural network has just one layer,
**[0:24]** which is also the output layer,
**[0:26]** and just one unit in the output layer.
**[0:30]** It takes us inputs x,
**[0:32]** applies a linear activation function
**[0:34]** and outputs deactivation a.
**[0:36]** More specifically this output is a equals wx plus b.
**[0:44]** This basically linear regression,
**[0:47]** but expressed as a neural network with one output unit.
**[0:53]** Given the output, the cause function is then 1/2a,
**[0:59]** that is the predicted value minus
**[1:01]** the actual observed value of y.
**[1:04]** For this small example,
**[1:06]** we're only going to have a single training example,
**[1:09]** where the training example
**[1:10]** is the input x equals negative 2.
**[1:13]** The ground truth output value y equals 2,
**[1:17]** and the parameters of this network are;
**[1:20]** w equals 2 and b equals 8.
**[1:23]** What I'd like to do is show how the computation of
**[1:29]** the cause function J can be
**[1:31]** computed step by step using a computation graph.
**[1:36]** Just as a reminder, when learning,
**[1:39]** we like to view the cause function J
**[1:42]** as a function of the parameters w and b.
**[1:46]** Let's take the computation of
**[1:49]** J and break it down into individual steps.
**[1:54]** First, you have the parameter w
**[1:57]** that is an input to the cause function J,
**[2:00]** and then we first need to compute w times x.
**[2:05]** Let me just call that c as follows;
**[2:08]** w is equal to 2,
**[2:10]** x is equal to negative 2,
**[2:12]** and so c would be negative 4.
**[2:14]** I'm just going to write the value here on top of
**[2:17]** this arrow to show
**[2:20]** the value that is your output on this arrow.
**[2:24]** The next step is then to compute a,
**[2:26]** which is wx plus b.
**[2:27]** So let me create another node here.
**[2:31]** This needs to input b,
**[2:34]** the other parameter that
**[2:35]** is input to the cause function J,
**[2:37]** and a equals wx plus b is equal to c plus b.
**[2:43]** If you add these up,
**[2:45]** that turns out to be 4.
**[2:48]** This is starting to build up a computation graph in which
**[2:53]** the steps we need to compute the cause function
**[2:55]** J are broken down into smaller steps.
**[2:58]** The next step is to then compute a minus y,
**[3:02]** which I'm going to call d. Let me have that node d,
**[3:07]** which computes a minus y. Y is equal to 2,
**[3:11]** so 4 minus 2 is 2.
**[3:14]** Then finally, J is the cause is 1/2 of a minus y squared,
**[3:20]** or 1/2 of d squared,
**[3:22]** which is just equal to 2.
**[3:26]** What we've just done is build up a computation graph.
**[3:30]** This is a graph, not in a sense
**[3:33]** of plots with x and y axes,
**[3:35]** but this is the other sense of
**[3:37]** the word graph using computer science,
**[3:39]** which is that this is a set of nodes that is
**[3:42]** connected by edges or connected by arrows in this case.
**[3:46]** This computation graph shows
**[3:49]** the forward prop step of how we
**[3:52]** compute the output a of the neural network.
**[3:56]** But then also go further than that so also
**[3:59]** compute the value of the cause function J.
**[4:03]** The question now is,
**[4:04]** how do we find the derivative of
**[4:06]** J with respect to the parameters w and b?
**[4:11]** Let's take a look at that next.
**[4:13]** Here's the computation graph from the previous slide
**[4:17]** and we've completed for
**[4:18]** a problem where we've computed that J,
**[4:21]** the cause function is equal to
**[4:22]** 2 through all these steps going
**[4:24]** from left to right for a prop in the computation graph.
**[4:28]** What we'd like to do now is
**[4:30]** compute the derivative of J with
**[4:32]** respect to w and the derivative of J with respect to b.
**[4:37]** It turns out that whereas for a prop
**[4:40]** was a left to right calculation,
**[4:43]** computing the derivatives will be
**[4:45]** a right to left calculation,
**[4:48]** which is why it's called backprop,
**[4:50]** was going backwards from right to left.
**[4:53]** The final computation nodes
**[4:56]** of this graph is this one over here,
**[4:58]** which computes J equals 1/2 of d squared.
**[5:02]** The first step of backprop will ask if the value of d,
**[5:08]** which was the input to
**[5:09]** this node where the change a little bit.
**[5:11]** How much does the value of j change?
**[5:14]** Specifically, will ask if
**[5:16]** d were to go up by a little bit,
**[5:18]** say 0.001, and that'll
**[5:20]** be our value of Epsilon in this case,
**[5:23]** how would the value of j change?
**[5:26]** It turns out in this case if d goes from 2-2.01,
**[5:31]** then j goes from 2-2.02.
**[5:37]** So if d goes up by Epsilon,
**[5:41]** j goes up by roughly two times Epsilon.
**[5:46]** We conclude that the derivative of J with respect
**[5:50]** to this value d that is inputted
**[5:52]** this final node is equal to two.
**[5:55]** The first step of backprop would be to
**[5:59]** fill in this value two over here,
**[6:02]** where this value is the derivative of j with respect to
**[6:06]** this input value d. We know if d changes a little bit,
**[6:11]** j changes by twice as
**[6:13]** much because this derivative is equal to two.
**[6:15]** The next step is to look at the node
**[6:17]** before that and ask what is
**[6:19]** the derivative of j with respect to a?
**[6:24]** To answer that, we have to ask, well,
**[6:26]** if a goes up by 0.001,
**[6:29]** how does that change j?
**[6:31]** Well, we know that if a goes up by 0.001,
**[6:35]** d is just a minus y.
**[6:38]** If a becomes 4.001,
**[6:42]** d which is a minus y,
**[6:45]** becomes 4.001 minus y equals 2,
**[6:49]** so becomes 2.001,
**[6:51]** sub a goes up by 0.001,
**[6:54]** d also goes up by 0.001.
**[6:57]** But we'd already concluded
**[6:59]** previously that the d goes up by 0.001,
**[7:02]** j goes up by twice as much.
**[7:05]** Now we know if a goes up by 0.001,
**[7:08]** d goes up by 0.001,
**[7:10]** then j goes up roughly by two times 0.001.
**[7:15]** This tells us that the derivative of j with
**[7:19]** respect to a is also equal to two.
**[7:23]** So I'm going to fill in that value over here.
**[7:26]** That this is the derivative of j with respect to a.
**[7:30]** Just as this was the derivative of
**[7:31]** j respect to d. If you've
**[7:34]** taken a calculus class before and if
**[7:37]** you've heard of the chain rule,
**[7:39]** you might recognize that
**[7:41]** this step of computation that I just did
**[7:43]** is actually relying on the chain rule for calculus.
**[7:48]** If you're not familiar with
**[7:49]** the chain rule, don't worry about it.
**[7:51]** You won't need to know it for the rest of these videos.
**[7:53]** But if you have seen the chain rule,
**[7:55]** you might recognize that the derivative of j
**[7:58]** with respect to a is asking,
**[8:01]** how much does d change respect to a,
**[8:05]** which is derivative of d respect to
**[8:06]** a times the derivative of j with respect to d,
**[8:12]** and does little calculation on top showed
**[8:14]** that the partial of t with respect to a is one,
**[8:17]** and we'd show EZ that
**[8:19]** the derivative of J with respect to d is equal to two,
**[8:22]** which is why the derivative of J with respect
**[8:24]** to a is one times two,
**[8:26]** which is equal to two.
**[8:27]** That's the value we got.
**[8:29]** But again, if you're not familiar with
**[8:31]** the chain rule, don't worry about it.
**[8:33]** The logic that we just went through here is why we
**[8:36]** know j goes up by twice as much as a does.
**[8:40]** That's why this derivative term is equal to two.
**[8:42]** The next step then is to keep on going
**[8:45]** right to left as we do in backprop.
**[8:47]** We'll ask, how much does a little change
**[8:50]** in c cause j to change,
**[8:52]** and how much does y change in b cause j to change?
**[8:57]** The way we figure that out is to ask,
**[9:00]** what if c goes up by Epsilon 0.001,
**[9:03]** how much does a change?
**[9:05]** Well, a is equal to c plus b.
**[9:08]** It turns out that if c ends up being negative 3.999,
**[9:13]** then a, which is negative 3.999 plus 8, becomes 4.001.
**[9:21]** If c goes up by Epsilon,
**[9:24]** a goes up by Epsilon.
**[9:26]** We know if a up by epsilon,
**[9:29]** then because the derivative of
**[9:31]** J with respect to a is two,
**[9:33]** we know that this in turn causes
**[9:35]** j to go up by two times Epsilon.
**[9:39]** We can conclude that if c goes up by a little bit,
**[9:42]** J goes up by twice as much.
**[9:45]** We know this because we know
**[9:47]** the derivative of J with respect to a is 2.
**[9:50]** This allows us to conclude that the derivative of J
**[9:54]** with respect to c is also equal to 2.
**[9:59]** I'm going to fill in that value over here.
**[10:02]** Again, only if you're familiar with chain rule
**[10:06]** another way to write this is
**[10:07]** derivative of J respect to c,
**[10:10]** is the derivative of a respect to c.
**[10:14]** This turns out to be 1 times
**[10:16]** the derivative of J respect to a,
**[10:19]** which we have previously figured out was equal to 2,
**[10:22]** so that's why this ends up being equal to 2.
**[10:25]** By a similar calculation,
**[10:27]** the b goes up by 0.001,
**[10:30]** then a also goes up by
**[10:32]** 0.001 and J goes up by 2 times 0.001,
**[10:37]** which is why this derivative is also equal to 2.
**[10:41]** We filled in here the derivative of J respect to b,
**[10:44]** and here the derivative of J respect to
**[10:47]** c. Now one final step,
**[10:50]** which is, what is the derivative of J with respect to w?
**[10:55]** W goes up by 0.001. What happens?
**[11:00]** C which is w times x,
**[11:03]** if w were 2.001,
**[11:06]** c which is w times x,
**[11:08]** becomes negative 2 times 2.001,
**[11:12]** so it becomes negative 4.002.
**[11:16]** If w goes up by epsilon,
**[11:19]** c goes down by 2 times 0.001,
**[11:25]** or equivalently c goes up by negative 2 times 0.001.
**[11:30]** We know that if c goes up by negative 2 times 0.001,
**[11:35]** because the derivative of J with respect to c is 2,
**[11:39]** this means that J will go up by negative 4 times 0.001,
**[11:46]** because if c goes up by a certain amount,
**[11:50]** J changes by 2 times as much,
**[11:53]** so negative 2 times this is negative 4 times this.
**[11:57]** This allows us to conclude that if w goes up by 0.001,
**[12:01]** J goes up by negative 4 times 0.001.
**[12:05]** The derivative of J with respect to w is negative 4.
**[12:12]** I'm going to write negative 4 over
**[12:14]** here because has the derivative
**[12:16]** of J with respect to w. Once again,
**[12:21]** the chain rule calculation,
**[12:23]** if you're familiar with it, is this.
**[12:26]** It is the derivative of
**[12:28]** c respect to w times derivative of J with respect to
**[12:32]** c. This is 2 and this is negative 2,
**[12:38]** which is why we end up with negative 4,
**[12:40]** but again, don't worry about it
**[12:41]** if you're not familiar with chain rule.
**[12:43]** To wrap up what we've just done this manually
**[12:47]** carry out backprop in this computation graph.
**[12:50]** Whereas forward prop was
**[12:52]** a left-to-right computation where we had w equals 2,
**[12:56]** that allowed us to compute c. Then we had
**[12:58]** b and that allows us to compute a and then d,
**[13:01]** and then J backprop
**[13:04]** went from right-to-left and we would first
**[13:06]** compute the derivative of J with respect to d
**[13:09]** and then go back to
**[13:10]** compute the derivative of J with respect to a,
**[13:13]** then the derivative of J with respect to b,
**[13:15]** derivative of J with respect to c and
**[13:17]** finally the derivative of J with respect to
**[13:19]** w. So that's why backprop is a right-to-left computation,
**[13:23]** whereas forward prop was a left-to-right computation.
**[13:27]** In fact, let's double-check
**[13:29]** the computation that we just did.
**[13:32]** J with these values of w, b,
**[13:36]** x and y is equal to
**[13:39]** one-half times wx plus b minus y squared,
**[13:45]** which is one-half times 2 times
**[13:49]** negative 2 plus 8 minus 2 squared,
**[13:53]** which is equal to 2.
**[13:55]** Now if w were to go up by 0.001,
**[13:59]** then J becomes one-half times,
**[14:02]** w is now 2.001 times x,
**[14:07]** which is negative 2,
**[14:09]** plus b which is 8 minus y squared.
**[14:14]** If you calculate this out,
**[14:16]** this turns out to be 1.996002.
**[14:20]** Roughly J has gone from 2 down to 1.996,
**[14:26]** and then an extra 002 and J has
**[14:30]** therefore gone down by 4 times epsilon.
**[14:33]** This shows that if W goes up by Epsilon,
**[14:36]** J goes down by four times Epsilon ball equivalent
**[14:39]** the J goes up by
**[14:41]** negative four times Epsilon, which is y.
**[14:44]** The derivative of j with respect to w is negative 4,
**[14:48]** which is what we have worked out over here.
**[14:50]** If you want, feel free to pause
**[14:52]** the video and double-check this math
**[14:55]** yourself as well for what happens in b,
**[14:58]** the other parameter goes up by Epsilon,
**[15:01]** and hopefully you'll find that
**[15:04]** the derivative of j with respect to b is indeed two.
**[15:08]** That b goes up by Epsilon,
**[15:11]** j goes up by two times Epsilon as
**[15:14]** predicted by this derivative calculation.
**[15:17]** Why do we use the backprop algorithm
**[15:21]** to compute derivatives?
**[15:22]** It turns out that backdrop is
**[15:25]** an efficient way to compute derivatives.
**[15:28]** The reason we sequence this as
**[15:31]** a right-to-left calculation is,
**[15:33]** if you were to start off and ask
**[15:36]** what is the derivative of j with respect to w?
**[15:39]** Then to know how much change in w affects change in j,
**[15:45]** if w were to go up by Epsilon,
**[15:46]** how much does j go by Epsilon?
**[15:48]** Well, the first thing we want to know is,
**[15:51]** what is the derivative of j with respect to c?
**[15:55]** Because change in w will change
**[15:57]** c this first quantity here.
**[16:00]** To know how much change in w affects j,
**[16:03]** we want to know how much does change in c affects j.
**[16:07]** But to know how much change in c affects j,
**[16:10]** the most useful thing to know to compute this
**[16:13]** would be change in c changes a.
**[16:16]** You want to know how much this change in
**[16:18]** a effect j and so on.
**[16:21]** That's why backprop a sequence
**[16:23]** as a right-to-left calculation.
**[16:25]** Because if you do the calculation from right to left,
**[16:28]** you can find out how does change in d affect change in j.
**[16:33]** Then you can find out how much this change
**[16:36]** in a effect j and so on.
**[16:39]** Until you find the derivatives
**[16:41]** of each of these intermediate quantities,
**[16:43]** c, a, and d,
**[16:46]** as well as the parameters w and b.
**[16:49]** That you can find out with one right-to-left
**[16:52]** calculation how much change
**[16:54]** in any of these intermediate quantities,
**[16:57]** c, a, or d,
**[16:59]** as well as the input parameters w and b.
**[17:02]** How much change in any of these things will
**[17:04]** affect the final output value j.
**[17:07]** One thing that makes backprop efficient is you
**[17:11]** notice that when we do the right-to-left calculation,
**[17:14]** we had to compute this term,
**[17:17]** the derivative of j with respect to a just once.
**[17:21]** This quantity is then used to compute both the derivative
**[17:25]** of g with respect to w and
**[17:28]** the derivative of j with respect to b.
**[17:31]** It turns out that if a computation graph has n nodes,
**[17:36]** meaning your n of these boxes and p parameters,
**[17:41]** so we have two parameters in this case.
**[17:43]** This procedure allows us to compute
**[17:45]** all the derivatives of j with
**[17:47]** respect to all the parameters in roughly n plus p steps,
**[17:52]** rather than n times p steps.
**[17:55]** If you have a neural network with, said,
**[17:58]** 10,000 nodes and maybe 100,000 parameters.
**[18:03]** This would not be considered even a
**[18:06]** very large neural network by modern standards.
**[18:08]** Being able to compute the derivatives and
**[18:10]** 10,000 plus 100,000 steps,
**[18:14]** which is punch and 10,000 is much
**[18:17]** better than meeting 10,000 times 100,000 steps,
**[18:21]** which would be a billion steps.
**[18:24]** The backpropagation algorithm done using
**[18:27]** the computation graph gives you
**[18:28]** a very efficient way to compute all the derivatives.
**[18:31]** That's why it is such a key idea in
**[18:34]** how deep learning algorithms are implemented today.
**[18:37]** In this video, you saw how
**[18:38]** the computation graph takes
**[18:40]** all the steps of the calculation
**[18:41]** needed to compute the output of
**[18:44]** a neural network a as well as the cost function j.
**[18:47]** Takes a step-by-step computations and
**[18:50]** breaks them into the different nodes
**[18:52]** of computation graph.
**[18:53]** Then uses a left-to-right computation
**[18:57]** for a prop to compute the cost function J.
**[19:00]** Then a right-to-left or
**[19:01]** backpropagation calculation
**[19:03]** to computes all the derivatives.
**[19:05]** In this video, you saw these ideas apply
**[19:08]** to a small neural network example.
**[19:11]** In the next video, let's take these ideas
**[19:14]** and apply them to a larger neural network.
**[19:16]** Let's go on to the next video.
