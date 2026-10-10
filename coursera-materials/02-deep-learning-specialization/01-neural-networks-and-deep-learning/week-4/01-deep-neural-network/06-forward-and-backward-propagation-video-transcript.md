---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 4
section: Deep Neural Network
item_title: Forward and Backward Propagation
duration: 10 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/znwiG/forward-and-backward-propagation
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Forward and Backward Propagation — Transcript

**[0:00]** In a previous video, you saw
**[0:01]** the basic blocks of implementing a deep neural network,
**[0:04]** a forward propagation step for
**[0:07]** each layer and a corresponding backward propagation step.
**[0:09]** Let's see how you can actually implement these steps.
**[0:12]** We'll start with forward propagation.
**[0:14]** Recall that what this will do is input a^l minus 1,
**[0:18]** and outputs a^l and the cache, z^l.
**[0:21]** We just said that, from implementational point of view,
**[0:24]** maybe we'll cache w^l and b^l as well,
**[0:28]** just to make the function's call a
**[0:29]** bit easier in the program exercise.
**[0:31]** The equations for this should already look familiar.
**[0:35]** The way to implement a forward function is just this,
**[0:38]** equals w^l times a^l minus 1 plus b^l,
**[0:46]** and then a^l equals the activation function applied to z.
**[0:53]** If you want a vectorized implementation,
**[0:57]** then it's just that times a^l minus 1 plus b,
**[1:05]** b being a Python broadcasting,
**[1:09]** and a^l equals g,
**[1:12]** applied element-wise to z.
**[1:15]** You remember, on the diagram for the 4th step,
**[1:20]** remember we had this chain of boxes going forward,
**[1:22]** so you initialize that with feeding
**[1:25]** in a^0, which is equal to x.
**[1:29]** So you initialize this with,
**[1:31]** what is the input to the first one?
**[1:33]** It's really a^0, which is the input
**[1:37]** features either for one training example
**[1:40]** if you're doing one example at a time,
**[1:42]** or a^0 if you're processing the entire training set.
**[1:48]** That's the input to
**[1:49]** the first forward function in the chain,
**[1:51]** and then just repeating this allows you to compute
**[1:54]** forward propagation from left to right.
**[1:56]** Next, let's talk about the backward propagation step.
**[2:00]** Here, your goal is to input da^l,
**[2:03]** and output da^l minus 1 and dw^l and db^l.
**[2:07]** Let me just write out
**[2:09]** the steps you need to compute these things.
**[2:12]** Dz^l is equal to da^l element-wise product,
**[2:18]** with g of l prime z of
**[2:22]** l. Then to compute the derivatives,
**[2:27]** dw^l equals dz^l times a of l minus 1.
**[2:34]** I didn't explicitly put that in the cache,
**[2:36]** but it turns out you need this as well.
**[2:39]** Then db^l is equal to dz^l, and finally,
**[2:47]** da of l minus 1 is equal to
**[2:52]** w^l transpose times dz^l.
**[2:59]** I don't want to go through
**[3:00]** the detailed derivation for this,
**[3:02]** but it turns out that if you take this definition
**[3:04]** for da and plug it in here,
**[3:06]** then you get the same formula
**[3:08]** as we had in there previously,
**[3:10]** for how you compute
**[3:12]** dz^l as a function of the previous dz^l.
**[3:15]** In fact, well, if I just plug that in here,
**[3:18]** you end up that dz^l is equal
**[3:21]** to w^l plus 1 transpose dz^l
**[3:27]** plus 1 times g^l prime z
**[3:33]** of l. I know this looks like a lot of algebra.
**[3:36]** You could actually double-check for
**[3:37]** yourself that this is the equation
**[3:39]** we had written down for back propagation last week,
**[3:42]** when we were doing a neural network
**[3:44]** with just a single hidden layer.
**[3:45]** As a reminder, this times is element-wise product,
**[3:49]** so all you need is
**[3:50]** those four equations to implement your backward function.
**[3:54]** Then finally, I'll just write out a vectorized version.
**[3:58]** So the first line becomes dz^l
**[4:01]** equals da^l element-wise product with g^l prime of z^l,
**[4:11]** maybe no surprise there.
**[4:13]** Dw^l becomes 1 over m,
**[4:17]** dz^l times a^l minus 1 transpose.
**[4:22]** Then db^l becomes 1 over m np.sum dz^l.
**[4:32]** Then axis equals 1, keepdims equals true.
**[4:37]** We talked about the use of
**[4:39]** np.sum in the previous week, to compute db.
**[4:44]** Then finally, da^l minus 1 is w^l transpose times
**[4:51]** dz of l. This
**[4:57]** allows you to input this quantity, da, over here.
**[5:02]** Output dW^l, dp^l, the derivatives you need,
**[5:10]** as well as da^l minus 1 as follows.
**[5:15]** That's how you implement the backward function.
**[5:18]** Just to summarize, take the input x,
**[5:22]** you may have the first layer maybe
**[5:25]** has a ReLU activation function.
**[5:28]** Then go to the second layer,
**[5:30]** maybe uses another ReLU activation function,
**[5:33]** goes to the third layer maybe has
**[5:36]** a sigmoid activation function
**[5:37]** if you're doing binary classification,
**[5:39]** and this outputs y-hat.
**[5:41]** Then using y-hat, you can compute the loss.
**[5:46]** This allows you to start your backward iteration.
**[5:49]** I'll draw the arrows first.
**[5:51]** I guess I don't have to change pens too much.
**[5:54]** Where you will then
**[5:57]** have backprop compute the derivatives,
**[6:03]** compute dW^3,
**[6:07]** db^3, dW^2, db^2, dW^1, db^1.
**[6:16]** Along the way you would be computing against the cash.
**[6:19]** We'll transfer z^1, z^2, z^3.
**[6:25]** Here you pass backwards da^2 and da^1.
**[6:32]** This could compute da^0,
**[6:34]** but we won't use that so you can just discard that.
**[6:37]** This is how you implement forward prop and back prop for
**[6:40]** a three-layer neural network.
**[6:43]** There's this one last detail that I didn't talk
**[6:46]** about which is for the forward recursion,
**[6:48]** we will initialize it with the input data x.
**[6:52]** How about the backward recursion?
**[6:54]** Well it turns out that
**[6:55]** da of l when you're using logistic regression,
**[7:01]** when you're doing binary classification
**[7:02]** is equal to y over
**[7:04]** a plus 1 minus y over 1 minus a.
**[7:09]** It turns out that the derivative
**[7:11]** of the loss function respect to
**[7:13]** the output with respect to
**[7:14]** y-hat can be shown to be what it is.
**[7:17]** If you're familiar with calculus,
**[7:19]** if you look up the loss function l and
**[7:21]** take derivatives with respect to y-hat with respect to a,
**[7:24]** you can show that you get that formula.
**[7:26]** This is the formula you should use for da,
**[7:29]** for the final layer,
**[7:30]** capital L. Of course if you
**[7:33]** were to have a vectorized implementation,
**[7:35]** then you initialize
**[7:36]** the backward recursion, not with this,
**[7:39]** but with da capital A for
**[7:42]** the layer L which is going to be
**[7:44]** the same thing for the different examples.
**[7:48]** Over a for the first train example plus 1 minus
**[7:53]** y for the first train example over
**[7:55]** 1 minus A for the first train example,
**[7:58]** dot-dot-dot down to the nth train example.
**[8:02]** So 1 minus a of M. That's how
**[8:06]** you'd implement the vectorized version.
**[8:09]** That's how you initialize
**[8:10]** the vectorized version of back propagation.
**[8:13]** We've now seen the basic building blocks of
**[8:15]** both forward propagation as well as back propagation.
**[8:19]** Now if you implement these equations,
**[8:22]** you will get the correct implementation of
**[8:24]** forward prop and backprop to
**[8:25]** get you the derivatives you need.
**[8:27]** You might be thinking, well those are a lot of equations.
**[8:29]** I'm slightly confused. I'm not quite sure I see
**[8:31]** how this works and if you're feeling that way,
**[8:33]** my advice is when you
**[8:35]** get to this week's programming assignment,
**[8:37]** you will be able to implement these for
**[8:39]** yourself and they will be much more concrete.
**[8:42]** I know those are a lot of equations,
**[8:43]** and maybe some of the equations
**[8:45]** didn't make complete sense,
**[8:46]** but if you work through
**[8:48]** the calculus and the linear algebra which is not easy,
**[8:50]** so feel free to try,
**[8:52]** but that's actually one of the more
**[8:53]** difficult derivations in machine learning.
**[8:56]** It turns out the equations we wrote down are
**[8:58]** just the calculus equations
**[8:59]** for computing the derivatives,
**[9:01]** especially in backprop, but once again,
**[9:03]** if this feels a little bit abstract,
**[9:04]** a little bit mysterious to you,
**[9:06]** my advice is when you've done the programming exercise,
**[9:09]** it will feel a bit more concrete to you.
**[9:11]** Although I have to say, even
**[9:13]** today when I implement a learning algorithm,
**[9:15]** sometimes even I'm surprised when
**[9:17]** my learning algorithm implementation
**[9:19]** works and it's because
**[9:20]** a lot of the complexity of
**[9:22]** machine learning comes from
**[9:23]** the data rather than from the lines of codes.
**[9:25]** Sometimes you feel like
**[9:27]** you implement a few lines of code,
**[9:28]** not quite sure what it did,
**[9:30]** but it almost magically works,
**[9:31]** and it's because a lot of magic is actually not in
**[9:33]** the piece of code you write which is often not too long.
**[9:37]** It's not exactly simple,
**[9:38]** but it's not 10,000,
**[9:40]** 100,000 lines of code,
**[9:42]** but you feed it so much data that
**[9:44]** sometimes even though I've
**[9:45]** worked with machine learning for a long time,
**[9:46]** sometimes it still surprises
**[9:48]** me a bit when my learning algorithm works,
**[9:50]** because a lot of the complexity of
**[9:52]** your learning algorithm comes from the data
**[9:55]** rather than necessarily from you
**[9:57]** writing thousands and thousands of lines of code.
**[10:01]** That's how you implement deep neural networks.
**[10:05]** Again this will become more
**[10:07]** concrete when you've done the programming exercising.
**[10:09]** Before moving on, in the next video,
**[10:14]** I want to discuss hyper-parameters and parameters.
**[10:17]** It turns out that when you're training deep nets,
**[10:19]** being able to organize your hyper-parameters well
**[10:22]** will help you be more efficient
**[10:23]** in developing your networks.
**[10:25]** In the next video, let's talk
**[10:26]** about exactly what that means.
