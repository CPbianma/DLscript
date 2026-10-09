---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Explanation for Vectorized Implementation
duration: 8 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/Y20qP/explanation-for-vectorized-implementation
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Explanation for Vectorized Implementation — Transcript

**[0:00]** In the previous video,
**[0:01]** we saw how with your training examples stacked up horizontally in the matrix x,
**[0:06]** you can derive a vectorized implementation for propagation through your neural network.
**[0:11]** Let's give a bit more justification for why the equations we wrote
**[0:14]** down is a correct implementation of vectorizing across multiple examples.
**[0:19]** So let's go through part of the forward propagation calculation for the few examples.
**[0:25]** Let's say that for the first training example,
**[0:27]** you end up computing
**[0:29]** this x1 plus b1 and then for the second training example,
**[0:38]** you end up computing this x2 plus b1 and
**[0:49]** then for the third training example,
**[0:50]** you end up computing this 3 plus b1.
**[0:56]** So, just to simplify the explanation on this slide, I'm going to ignore b.
**[1:00]** So let's just say, to simplify this justification a little bit that b is equal to zero.
**[1:08]** But the argument we're going to lay out will work with
**[1:11]** just a little bit of a change even when b is non-zero.
**[1:14]** It does just simplify the description on the slide a bit.
**[1:17]** Now, w1 is going to be some matrix, right?
**[1:21]** So I have some number of rows in this matrix.
**[1:25]** So if you look at this calculation x1,
**[1:28]** what you have is
**[1:30]** that w1 times x1 gives you some column vector which you must draw like this.
**[1:40]** And similarly, if you look at this vector x2,
**[1:47]** you have that w1 times
**[1:54]** x2 gives some other column vector, right?
**[2:00]** And that's gives you this z12.
**[2:03]** And finally, if you look at x3,
**[2:06]** you have w1 times x3,
**[2:12]** gives you some third column vector, that's this z13.
**[2:19]** So now, if you consider the training set capital X,
**[2:25]** which we form by stacking together all of our training examples.
**[2:31]** So the matrix capital X is formed by taking the vector x1 and
**[2:37]** stacking it vertically with x2 and then also x3.
**[2:43]** This is if we have only three training examples.
**[2:46]** If you have more, you know, they'll keep stacking horizontally like that.
**[2:50]** But if you now take this matrix x and multiply it by w then you end up with,
**[2:57]** if you think about how matrix multiplication works,
**[3:00]** you end up with the first column being
**[3:02]** these same values that I had drawn up there in purple.
**[3:06]** The second column will be those same four values.
**[3:10]** And the third column will be those orange values,
**[3:16]** what they turn out to be.
**[3:19]** But of course this is just equal to z11 expressed as
**[3:27]** a column vector followed by z12 expressed as a column vector followed by z13,
**[3:37]** also expressed as a column vector.
**[3:39]** And this is if you have three training examples.
**[3:41]** You get more examples then there'd be more columns.
**[3:44]** And so, this is just our matrix capital Z1.
**[3:51]** So I hope this gives a justification for why we had
**[3:55]** previously w1 times xi equals
**[4:02]** z1i when we're looking at single training example at the time.
**[4:08]** When you took the different training examples and stacked them up in different columns,
**[4:12]** then the corresponding result is that you end up
**[4:15]** with the z's also stacked at the columns.
**[4:18]** And I won't show but you can convince yourself if you want that with Python broadcasting,
**[4:24]** if you add back in,
**[4:26]** these values of b to the values are still correct.
**[4:30]** And what actually ends up happening is you end up with Python broadcasting,
**[4:34]** you end up having bi individually to each of the columns of this matrix.
**[4:41]** So on this slide, I've only justified that z1 equals
**[4:48]** w1x plus b1 is
**[4:51]** a correct vectorization of
**[4:54]** the first step of the four steps we have in the previous slide,
**[4:57]** but it turns out that a similar analysis allows you to
**[4:59]** show that the other steps also work on using
**[5:02]** a very similar logic where if you stack the inputs in columns then after the equation,
**[5:08]** you get the corresponding outputs also stacked up in columns.
**[5:11]** Finally, let's just recap everything we talked about in this video.
**[5:14]** If this is your neural network,
**[5:16]** we said that this is what you need to do if you were to implement for propagation,
**[5:21]** one training example at a time going from i equals 1 through m. And then we said,
**[5:27]** let's stack up the training examples in columns like so and for each of these values z1,
**[5:34]** a1, z2, a2, let's stack up the corresponding columns as follows.
**[5:38]** So this is an example for a1 but this is true for z1,
**[5:43]** a1, z2, and a2.
**[5:46]** Then what we show on the previous slide was that
**[5:51]** this line allows you to vectorize this across all m examples at the same time.
**[5:58]** And it turns out with the similar reasoning,
**[6:00]** you can show that all of the other lines are
**[6:03]** correct vectorizations of all four of these lines of code.
**[6:08]** And just as a reminder,
**[6:10]** because x is also equal to a0 because remember that
**[6:18]** the input feature vector x was equal to a0, so xi equals a0i.
**[6:27]** Then there's actually a certain symmetry to
**[6:30]** these equations where this first equation can also be
**[6:34]** written z1 = w1 a0 + b1.
**[6:41]** And so, you see that this pair of equations and this pair of
**[6:45]** equations actually look very similar but just of all of the indices advance by one.
**[6:51]** So this kind of shows that the different layers of a neural network are
**[6:55]** roughly doing the same thing or just doing the same computation over and over.
**[7:00]** And here we have two-layer neural network where we go to
**[7:04]** a much deeper neural network in next week's videos.
**[7:08]** You see that even deeper neural networks are basically taking
**[7:11]** these two steps and just doing them even more times than you're seeing here.
**[7:16]** So that's how you can vectorize your neural network across multiple training examples.
**[7:21]** Next, we've so far been using the sigmoid functions throughout our neural networks.
**[7:25]** It turns out that's actually not the best choice.
**[7:27]** In the next video, let's dive a little bit
**[7:29]** further into how you can use different, what's called,
**[7:32]** activation functions of which the sigmoid function is just one possible choice.
