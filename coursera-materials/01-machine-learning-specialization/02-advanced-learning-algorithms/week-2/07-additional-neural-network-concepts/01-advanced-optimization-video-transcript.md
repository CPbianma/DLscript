---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Additional Neural Network Concepts
item_title: Advanced Optimization
duration: 6 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/5Qt9E/advanced-optimization
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Advanced Optimization — Transcript

**[0:01]** Gradient descent is an optimization algorithm
**[0:05]** that is widely used in machine learning,
**[0:08]** and was the foundation of many algorithms like
**[0:11]** linear regression and logistic regression
**[0:14]** and early implementations of neural networks.
**[0:17]** But it turns out that there are now
**[0:19]** some other optimization algorithms
**[0:22]** for minimizing the cost function,
**[0:24]** that are even better than gradient descent.
**[0:26]** In this video, we'll take
**[0:28]** a look at an algorithm that can help
**[0:30]** you train your neural network
**[0:32]** much faster than gradient descent.
**[0:34]** Recall that this is
**[0:36]** the expression for one step of gradient descent.
**[0:39]** A parameter w_j is updated as w_j
**[0:42]** minus the learning rate Alpha times
**[0:45]** this partial derivative term.
**[0:47]** How can we make this work even better?
**[0:50]** In this example, I've plotted the cost function J
**[0:54]** using a contour plot comprising these ellipsis,
**[0:58]** and the minimum of this cost function
**[1:00]** is at the center of this ellipsis down here.
**[1:04]** Now, if you were to start gradient descent down here,
**[1:09]** one step of gradient descent,
**[1:11]** if Alpha is small,
**[1:12]** may take you a little bit in that direction.
**[1:14]** Then another step, then another step,
**[1:17]** then another step, then another step,
**[1:19]** and you notice that every single step of
**[1:21]** gradient descent is pretty much
**[1:23]** going in the same direction,
**[1:24]** and if you see this to be the case,
**[1:27]** you might wonder, well,
**[1:28]** why don't we make Alpha bigger,
**[1:30]** can we have an algorithm to automatically increase Alpha?
**[1:34]** They just make it take bigger steps and
**[1:36]** get to the minimum faster.
**[1:38]** There's an algorithm called
**[1:41]** the Adam algorithm that can do that.
**[1:44]** If it sees that the learning rate is too small,
**[1:47]** and we are just taking
**[1:48]** tiny little steps in a similar direction over and over,
**[1:51]** we should just make the learning rate Alpha bigger.
**[1:55]** In contrast, here again,
**[1:58]** is the same cost function if we were
**[2:01]** starting here and have
**[2:02]** a relatively big learning rate Alpha,
**[2:05]** then maybe one step of gradient descent takes us here,
**[2:07]** in the second step takes us here,
**[2:09]** third step, and the fourth step,
**[2:11]** and the fifth step, and the sixth step,
**[2:13]** and if you see gradient descent doing this,
**[2:16]** is oscillating back and forth.
**[2:18]** You'd be tempted to say, well,
**[2:19]** why don't we make the learning rates smaller?
**[2:22]** The Adam algorithm can also do that automatically,
**[2:25]** and with a smaller learning rate,
**[2:27]** you can then take a more smooth path
**[2:29]** toward the minimum of the cost function.
**[2:32]** Depending on how gradient descent is proceeding,
**[2:36]** sometimes you wish you had a bigger learning rate Alpha,
**[2:39]** and sometimes you wish you had
**[2:40]** a smaller learning rate Alpha.
**[2:43]** The Adam algorithm can
**[2:45]** adjust the learning rate automatically.
**[2:47]** Adam stands for Adaptive Moment Estimation,
**[2:51]** or A-D-A-M, and
**[2:54]** don't worry too much about what this name means,
**[2:56]** it's just what the authors had called this algorithm.
**[2:59]** But interestingly, the Adam algorithm
**[3:02]** doesn't use a single global learning rate Alpha.
**[3:05]** It uses a different learning rates
**[3:07]** for every single parameter of your model.
**[3:10]** If you have parameters w_1 through w_10, as was b,
**[3:14]** then it actually has
**[3:15]** 11 learning rate parameters, Alpha_1,
**[3:18]** Alpha_2, all the way through Alpha_10 for w_1 to w_10,
**[3:23]** as well as I'll call it Alpha_11 for the parameter b.
**[3:28]** The intuition behind the Adam algorithm is,
**[3:32]** if a parameter w_j,
**[3:34]** or b seems to keep on
**[3:36]** moving in roughly the same direction.
**[3:38]** This is what we saw on
**[3:40]** the first example on the previous slide.
**[3:42]** But if it seems to keep on moving
**[3:44]** in roughly the same direction,
**[3:45]** let's increase the learning rate for that parameter.
**[3:48]** Let's go faster in that direction.
**[3:50]** Conversely, if a parameter
**[3:52]** keeps oscillating back and forth,
**[3:54]** this is what you saw in
**[3:56]** the second example on the previous slide.
**[3:58]** Then let's not have it keep on
**[4:00]** oscillating or bouncing back and forth.
**[4:02]** Let's reduce Alpha_j for that parameter a little bit.
**[4:07]** The details of how Adam does this are a
**[4:10]** bit complicated and beyond the scope of this course,
**[4:13]** but if you take some more
**[4:15]** advanced deep learning courses later,
**[4:16]** you may learn more about the details
**[4:18]** of this Adam algorithm,
**[4:20]** but in codes this is how you implement it.
**[4:23]** The model is exactly the same as before,
**[4:26]** and the way you compile
**[4:29]** the model is very similar to what we had before,
**[4:32]** except that we now add
**[4:33]** one extra argument to the compile function,
**[4:37]** which is that we specify that the optimizer you want to
**[4:40]** use is tf.keras.optimizers.Adam optimizer.
**[4:46]** The Adam optimization algorithm does need
**[4:49]** some default initial learning rate Alpha,
**[4:52]** and in this example,
**[4:53]** I've set that initial learning rate to be 10^ negative 3.
**[4:59]** But when you're using the Adam algorithm in practice,
**[5:02]** it's worth trying a few values for
**[5:04]** this default global learning rate.
**[5:07]** Try some large and some smaller values to
**[5:10]** see what gives you the fastest learning performance.
**[5:13]** Compared to the original gradient descent algorithm
**[5:16]** that you had learned in the previous course though,
**[5:20]** the Adam algorithm,
**[5:22]** because it can adapt the learning rate
**[5:24]** a bit automatically,
**[5:25]** it is more robust to
**[5:26]** the exact choice of learning rate that you pick.
**[5:29]** Though there's still way tuning
**[5:31]** this parameter little bit to see
**[5:33]** if you can get somewhat faster learning.
**[5:35]** That's it for the Adam optimization algorithm.
**[5:38]** It typically works much faster than gradient descent,
**[5:42]** and it's become a de facto standard
**[5:45]** in how practitioners train their neural networks.
**[5:48]** If you're trying to decide
**[5:49]** what learning algorithm to use,
**[5:51]** what optimization algorithm to
**[5:52]** use to train your neural network.
**[5:54]** A safe choice would be to just
**[5:56]** use the Adam optimization algorithm,
**[5:59]** and most practitioners today will use Adam
**[6:02]** rather than the optional gradient descent algorithm,
**[6:04]** and with this, I hope that
**[6:06]** your learning algorithms will be
**[6:08]** able to learn much more quickly.
**[6:11]** Now, in the next couple of videos,
**[6:14]** I'd like to touch on
**[6:15]** some more advanced concepts for neural networks,
**[6:19]** and in particular, in the next video,
**[6:21]** let's take a look at some alternative layer types.
