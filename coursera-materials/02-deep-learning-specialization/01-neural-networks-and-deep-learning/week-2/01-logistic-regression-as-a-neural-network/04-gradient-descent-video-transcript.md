---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Logistic Regression as a Neural Network
item_title: Gradient Descent
duration: 11 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/A0tBd/gradient-descent
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Gradient Descent — Transcript

**[0:00]** You've seen the logistic regression model, you've seen the loss function that
**[0:04]** measures how well you're doing on the single training example.
**[0:08]** You've also seen the cost function that measures how well your parameters W and
**[0:13]** B are doing on your entire training set.
**[0:16]** Now let's talk about how you can use the gradient descent algorithm to train or
**[0:22]** to learn the parameters W on your training set.
**[0:25]** To recap here is the familiar logistic regression algorithm and
**[0:30]** we have on the second line the cost function J,
**[0:34]** which is a function of your parameters W and B.
**[0:37]** And that's defined as the average is one over m times has some of
**[0:42]** this loss function.
**[0:44]** And so the loss function measures how well your algorithms outputs.
**[0:49]** Y hat I on each of the training examples stacks up compares to the boundary
**[0:54]** lables Y I on each of the training examples. The
**[0:57]** full formula is expanded out on the right.
**[1:00]** So the cost function measures how well your parameters w and
**[1:04]** b are doing on the training set.
**[1:06]** So in order to learn a set of parameters w and b,
**[1:10]** it seems natural that we want to find w and b.
**[1:13]** That make the cost function J of w, b as small as possible.
**[1:17]** So, here's an illustration of gradient descent.
**[1:21]** In this diagram, the horizontal axes represent your space of parameters w and
**[1:26]** b in practice w can be much higher dimensional, but for the purposes of
**[1:32]** plotting, let's illustrate w as a singular number and b as a singular number.
**[1:38]** The cost function J of w,
**[1:40]** b is then some surface above these horizontal axes w and b.
**[1:45]** So the height of the surface represents the value of J, b at a certain point.
**[1:50]** And what we want to do really is to find the value of w and
**[1:55]** b that corresponds to the minimum of the cost function J.
**[2:00]** It turns out that this particular cost function J is a convex function.
**[2:05]** So it's just a single big bowl, so this is a convex function and
**[2:10]** this is as opposed to functions that look like this,
**[2:13]** which are non convex and has lots of different local optimal.
**[2:18]** So the fact that our cost function J of w, b as defined here is convex,
**[2:22]** is one of the huge reasons why we use this particular cost function J for
**[2:27]** logistic regression.
**[2:29]** So to find a good value for the parameters,
**[2:33]** what we'll do is initialize w and
**[2:37]** b to some initial value may be denoted by that little red dot.
**[2:43]** And for logistic regression, almost any initialization method works.
**[2:47]** Usually you Initialize the values of 0.
**[2:50]** Random initialization also works, but people don't usually do that for
**[2:54]** logistic regression.
**[2:55]** But because this function is convex, no matter where you initialize,
**[2:59]** you should get to the same point or roughly the same point.
**[3:02]** And what gradient descent does is it starts at that initial point and
**[3:06]** then takes a step in the steepest downhill direction.
**[3:10]** So after one step of gradient descent, you might end up there because it's
**[3:14]** trying to take a step downhill in the direction of steepest descent or
**[3:19]** as quickly down who as possible.
**[3:21]** So that's one iteration of gradient descent.
**[3:23]** And after iterations of gradient descent,
**[3:26]** you might stop there, three iterations and so on.
**[3:28]** I guess this is not hidden by the back of the plot until eventually, hopefully you
**[3:33]** converge to this global optimum or get to something close to the global optimum.
**[3:38]** So this picture illustrates the gradient descent algorithm.
**[3:42]** Let's write a little bit more of the details for the purpose of illustration,
**[3:46]** let's say that there's some function J of w that you want to minimize and
**[3:49]** maybe that function looks like this to make this easier to draw.
**[3:53]** I'm going to ignore b for
**[3:54]** now just to make this one dimensional plot instead of a higher dimensional plot.
**[3:59]** So gradient descent does this.
**[4:01]** We're going to repeatedly carry out the following update.
**[4:06]** We'll take the value of w and update it.
**[4:09]** Going to use colon equals to represent updating w.
**[4:12]** So set w to w minus alpha times and
**[4:17]** this is a derivative d of J w d w.
**[4:22]** And we repeatedly do that until the algorithm converges.
**[4:26]** So a couple of points in the notation alpha here is the learning rate and
**[4:30]** controls how big a step we take on each iteration are gradient descent,
**[4:35]** we'll talk later about some ways for choosing the learning rate,
**[4:40]** alpha and second this quantity here, this is a derivative.
**[4:44]** This is basically the update of the change you want to make to the parameters w,
**[4:49]** when we start to write code to implement gradient descent,
**[4:53]** we're going to use the convention that the variable name in our code,
**[4:58]** d w will be used to represent this derivative term.
**[5:02]** So when you write code, you write something like w equals or
**[5:07]** cold equals w minus alpha time's d w.
**[5:10]** So we use d w to be the variable name to represent this derivative term.
**[5:14]** Now, let's just make sure that this gradient descent update makes sense.
**[5:19]** Let's say that w was over here.
**[5:21]** So you're at this point on the cost function J of w.
**[5:26]** Remember that the definition of a derivative is the slope
**[5:29]** of a function at the point.
**[5:31]** So the slope of the function is really,
**[5:33]** the height divided by the width right of the lower triangle.
**[5:37]** Here, in this tension to J of w at that point.
**[5:40]** And so here the derivative is positive.
**[5:43]** W gets updated as w minus a learning rate times the derivative,
**[5:48]** the derivative is positive.
**[5:50]** And so you end up subtracting from w.
**[5:53]** So you end up taking a step to the left and so gradient descent with,
**[5:57]** make your algorithm slowly decrease the parameter.
**[6:00]** If you had started off with this large value of w.
**[6:04]** As another example, if w was over here,
**[6:08]** then at this point the slope here or dJ detail, you will be negative.
**[6:16]** And so they driven to send update with subtract alpha times a negative number.
**[6:22]** And so end up slowly increasing w.
**[6:25]** So you end up you're making w bigger and
**[6:27]** bigger with successive generations of gradient descent.
**[6:31]** So that hopefully whether you initialize on the left, wonder right,
**[6:35]** create into central move you towards this global minimum here.
**[6:38]** If you're not familiar with derivatives of calculus and
**[6:44]** what this term d J of w d w means.
**[6:47]** Don't worry too much about it.
**[6:49]** We'll talk some more about derivatives in the next video.
**[6:53]** If you have a deep knowledge of calculus,
**[6:56]** you might be able to have a deeper intuitions about how neural networks work.
**[7:02]** But even if you're not that familiar with calculus in the next few videos
**[7:06]** will give you enough intuitions about derivatives and
**[7:10]** about calculus that you'll be able to effectively use neural networks.
**[7:14]** But the overall intuition for
**[7:17]** now is that this term represents the slope of the function and we want to
**[7:22]** know the slope of the function at the current setting of the parameters so
**[7:27]** that we can take these steps of steepest descent so that we know what
**[7:31]** direction to step in in order to go downhill on the cost function J.
**[7:36]** So we wrote our gradient descent for J of w.
**[7:40]** If only w was your parameter in logistic regression.
**[7:43]** Your cost function is a function above w and b.
**[7:47]** In that case the inner loop of gradient descent,
**[7:49]** that is this thing here the thing you have to repeat becomes as follows.
**[7:53]** You end up updating w as w minus the learning rate
**[7:58]** times the derivative of J of wb respect to w and
**[8:02]** you update b as b minus the learning rate times
**[8:07]** the derivative of the cost function respect to b.
**[8:12]** So these two equations at the bottom of the actual update you implement as in
**[8:16]** the side, I just want to mention one notation, all convention and calculus.
**[8:21]** That is a bit confusing to some people.
**[8:24]** I don't think it's super important that you understand calculus but
**[8:28]** in case you see this, I want to make sure that you don't think too much of this.
**[8:32]** Which is that in calculus this term here we actually write as follows,
**[8:38]** that funny squiggle symbol.
**[8:40]** So this symbol, this is actually just the lower
**[8:45]** case d in a fancy font, in a stylized font.
**[8:49]** But when you see this expression, all this means is this is the of J of w,
**[8:54]** b or really the slope of the function J of w,
**[8:57]** b how much that function slopes in the w direction.
**[9:01]** And the rule of the notation and calculus, which I think is in total logical.
**[9:06]** But the rule in the notation for calculus, which I think just makes things
**[9:11]** much more complicated than you need to be is that if J is a function of two or
**[9:16]** more variables, then instead of using lower case d.
**[9:20]** You use this funny symbol.
**[9:21]** This is called a partial derivative symbol, but don't worry about this.
**[9:25]** And if J is a function of only one variable, then you use lower case d.
**[9:31]** So the only difference between whether you use this funny partial derivative symbol
**[9:35]** or lower case d.
**[9:36]** As we did on top is whether J is a function of two or more variables.
**[9:41]** In which case use this symbol, the partial derivative symbol or
**[9:46]** J is only a function of one variable.
**[9:48]** Then you use lower case d.
**[9:51]** This is one of those funny rules of notation and
**[9:53]** calculus that I think just make things more complicated than they need to be.
**[9:58]** But if you see this partial derivative symbol,
**[10:01]** all it means is you're measuring the slope of the function with
**[10:06]** respect to one of the variables, and similarly to adhere to the,
**[10:10]** formally correct mathematical notation calculus because here J has two inputs.
**[10:16]** Not just one.
**[10:18]** This thing on the bottom should be written with this partial derivative simple,
**[10:23]** but it really means the same thing as, almost the same thing as lowercase d.
**[10:28]** Finally, when you implement this in code,
**[10:31]** we're going to use the convention that this quantity really the amount
**[10:37]** I wish you update w will denote as the variable d w in your code.
**[10:41]** And this quantity, right, the amount by which you want
**[10:46]** to update b with the note by the variable db in your code.
**[10:51]** All right. So
**[10:52]** that's how you can implement gradient descent.
**[10:55]** Now if you haven't seen calculus for a few years, I know that that might seem like
**[10:59]** a lot more derivatives and calculus than you might be comfortable with so far.
**[11:03]** But if you're feeling that way, don't worry about it.
**[11:06]** In the next video will give you better intuition about derivatives.
**[11:09]** And even without the deep mathematical understanding of calculus,
**[11:13]** with just an intuitive understanding of calculus,
**[11:16]** you will be able to make your networks work effectively so
**[11:19]** that let's go into the next video, we'll talk a little bit more about derivatives.
