---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 2
section: Gradient descent in practice
item_title: Checking gradient descent for convergence
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/rOTkB/checking-gradient-descent-for-convergence
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Checking gradient descent for convergence — Transcript

**[0:00]** When running gradient descent,
**[0:03]** how can you tell if it is converging?
**[0:05]** That is, whether it's helping you to find
**[0:07]** parameters close to the global minimum
**[0:10]** of the cost function.
**[0:11]** By learning to recognize what
**[0:13]** a well-running implementation of
**[0:15]** gradient descent looks like,
**[0:16]** we will also, in a later video,
**[0:18]** be better able to choose a good learning rate Alpha.
**[0:22]** Let's take a look. As a reminder,
**[0:24]** here's the gradient descent rule.
**[0:26]** One of the key choices is
**[0:29]** the choice of the learning rate Alpha.
**[0:32]** Here's something that I often do to make
**[0:34]** sure that gradient descent is working well.
**[0:37]** Recall that the job of
**[0:39]** gradient descent is to find parameters w
**[0:41]** and b that hopefully minimize the cost function J.
**[0:46]** What I'll often do is plot the cost function J,
**[0:49]** which is calculated on the training set,
**[0:52]** and I plot the value of J at
**[0:55]** each iteration of gradient descent.
**[0:58]** Remember that each iteration means after
**[1:01]** each simultaneous update of the parameters w and b.
**[1:07]** In this plot, the horizontal axis is
**[1:11]** the number of iterations of
**[1:13]** gradient descent that you've run so far.
**[1:16]** You may get a curve that looks like this.
**[1:20]** Notice that the horizontal axis
**[1:22]** is the number of iterations of
**[1:24]** gradient descent and not a parameter like w or b.
**[1:29]** This differs from previous graphs you've
**[1:32]** seen where the vertical axis was cost
**[1:35]** J and the horizontal axis was
**[1:38]** a single parameter like w or b.
**[1:42]** This curve is also called a learning curve.
**[1:46]** Note that there are
**[1:47]** a few different types of learning
**[1:49]** curves used in machine learning,
**[1:51]** and you see some of the types
**[1:53]** later in this course as well.
**[1:55]** Concretely, if you look here at this point on the curve,
**[1:59]** this means that after you've run
**[2:02]** gradient descent for 100 iterations,
**[2:04]** meaning 100 simultaneous updates of the parameters,
**[2:08]** you have some learned values for w and b.
**[2:12]** If you compute the cost J, w,
**[2:16]** b for those values of w and b,
**[2:19]** the ones you got after 100 iterations,
**[2:21]** you get this value for the cost J.
**[2:25]** That is this point on the vertical axis.
**[2:29]** This point here corresponds to the value of J for
**[2:34]** the parameters that you got after
**[2:36]** 200 iterations of gradient descent.
**[2:39]** Looking at this graph helps you to see
**[2:42]** how your cost J changes
**[2:44]** after each iteration of gradient descent.
**[2:47]** If gradient descent is working properly,
**[2:50]** then the cost J should
**[2:51]** decrease after every single iteration.
**[2:54]** If J ever increases after one iteration,
**[2:58]** that means either Alpha is chosen poorly,
**[3:02]** and it usually means Alpha is too large,
**[3:05]** or there could be a bug in the code.
**[3:07]** Another useful thing that this part can tell
**[3:10]** you is that if you look at this curve,
**[3:12]** by the time you reach maybe 300 iterations also,
**[3:16]** the cost J is leveling
**[3:19]** off and is no longer decreasing much.
**[3:22]** By 400 iterations,
**[3:24]** it looks like the curve has flattened out.
**[3:27]** This means that gradient descent has more or less
**[3:31]** converged because the curve is no longer decreasing.
**[3:36]** Looking at this learning curve,
**[3:38]** you can try to spot whether or not
**[3:41]** gradient descent is converging.
**[3:44]** By the way, the number
**[3:46]** of iterations that gradient descent
**[3:48]** takes a conversion can vary
**[3:49]** a lot between different applications.
**[3:52]** In one application, it may
**[3:53]** converge after just 30 iterations.
**[3:56]** For a different application,
**[3:58]** it could take 1,000 or 100,000 iterations.
**[4:02]** It turns out to be very difficult to tell in
**[4:06]** advance how many iterations
**[4:08]** gradient descent needs to converge,
**[4:10]** which is why you can create
**[4:12]** a graph like this, a learning curve.
**[4:15]** Try to find out when you can start
**[4:17]** training your particular model.
**[4:20]** Another way to decide when your model is done training
**[4:23]** is with an automatic convergence test.
**[4:29]** Here is the Greek alphabet epsilon.
**[4:33]** Let's let epsilon be a
**[4:35]** variable representing a small number,
**[4:37]** such as 0.001 or 10^-3.
**[4:43]** If the cost J decreases by less
**[4:45]** than this number epsilon on one iteration,
**[4:48]** then you're likely on this flattened part of
**[4:51]** the curve that you see on
**[4:53]** the left and you can declare convergence.
**[4:56]** Remember, convergence,
**[4:58]** hopefully in the case that you found parameters
**[5:00]** w and b that are close to the minimum possible value of
**[5:04]** J. I usually find
**[5:06]** that choosing the right threshold
**[5:08]** epsilon is pretty difficult.
**[5:10]** I actually tend to look at graphs
**[5:12]** like this one on the left,
**[5:13]** rather than rely on automatic convergence tests.
**[5:16]** Looking at the solid figure can tell you,
**[5:19]** I'll give you at some advanced warning if
**[5:22]** maybe gradient descent is not working correctly as well.
**[5:26]** You've now seen what the learning curve
**[5:29]** should look like when gradient descent is running well.
**[5:32]** Let's take these insights and in the next video,
**[5:35]** take a look at how to
**[5:36]** choose an appropriate learning rate.
