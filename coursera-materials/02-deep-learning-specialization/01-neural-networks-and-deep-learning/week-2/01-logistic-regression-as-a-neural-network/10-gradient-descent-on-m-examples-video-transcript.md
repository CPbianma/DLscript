---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Logistic Regression as a Neural Network
item_title: Gradient Descent on m Examples
duration: 8 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/udiAq/gradient-descent-on-m-examples
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Gradient Descent on m Examples — Transcript

**[0:00]** In a previous video, you saw how to compute derivatives and implement
**[0:03]** gradient descent with respect to just one training example for logistic regression.
**[0:08]** Now, we want to do it for m training examples.
**[0:11]** To get started, let's remind ourselves of the definition of the cost function
**[0:15]** J. Cost- function w,b,which you care about is this average,
**[0:19]** one over m sum from i equals one through m of
**[0:23]** the loss when you algorithm output a_i on the example y,
**[0:28]** where a_i is the prediction on the ith training example which is sigma of z_i,
**[0:36]** which is equal to sigma of w transpose x_i plus b.
**[0:45]** So, what we show in the previous slide is for any single training example,
**[0:49]** how to compute the derivatives when you have just one training example.
**[0:57]** So dw_1, dw_2 and d_b,
**[1:02]** with now the superscript i to denote
**[1:04]** the corresponding values you get if you were doing what we did on the previous slide,
**[1:09]** but just using the one training example,
**[1:12]** x_i y_i, excuse me,
**[1:15]** missing an i there as well.
**[1:16]** So, now you notice the overall cost functions as a sum was really average,
**[1:22]** because the one over m term of the individual losses.
**[1:25]** So, it turns out that the derivative,
**[1:28]** respect to w_1 of the overall cost function is also going to be
**[1:35]** the average of derivatives respect to w_1 of the individual loss terms.
**[1:45]** But previously, we have already shown how to compute this term as dw_1_i,
**[1:52]** which we, on the previous slide,
**[1:55]** show how to compute this on a single training example.
**[1:58]** So, what you need to do is really compute
**[2:00]** these derivatives as we showed on the previous training example and average them,
**[2:06]** and this will give you
**[2:07]** the overall gradient that you can use to implement the gradient descent.
**[2:12]** So, I know that was a lot of details,
**[2:14]** but let's take all of this up and wrap this up into
**[2:17]** a concrete algorithm until when you should
**[2:19]** implement logistic regression with gradient descent working.
**[2:23]** So, here's what you can do: let's initialize j equals zero,
**[2:29]** dw_1 equals zero, dw_2 equals zero, d_b equals zero.
**[2:38]** What we're going to do is use a for loop over the training set,
**[2:43]** and compute the derivative with respect to each training example and then add them up.
**[2:47]** So, here's how we do it, for i equals one through m,
**[2:50]** so m is the number of training examples,
**[2:52]** we compute z_i equals w transpose x_i plus b.
**[2:56]** The prediction a_i is equal to sigma of z_i,
**[3:00]** and then let's add up J,
**[3:03]** J plus equals y_i log a_i plus one minus y_i log one minus a_i,
**[3:11]** and then put the negative sign in front of the whole thing,
**[3:14]** and then as we saw earlier,
**[3:15]** we have dz_i, that's equal to a_i minus y_i,
**[3:20]** and d_w gets plus equals x1_i dz_i,
**[3:25]** dw_2 plus equals xi_2 dz_i,
**[3:32]** and I'm doing this calculation assuming that you have just two features,
**[3:36]** so that n equals to two otherwise,
**[3:38]** you do this for dw_1,
**[3:39]** dw_2, dw_3 and so on,
**[3:41]** and then db plus equals dz_i,
**[3:44]** and I guess that's the end of the for loop.
**[3:47]** Then finally, having done this for all m training examples,
**[3:50]** you will still need to divide by m because we're computing averages.
**[3:55]** So, dw_1 divide equals m,
**[3:58]** dw_2 divides equals m,
**[4:01]** db divide equals m,
**[4:03]** in order to compute averages.
**[4:05]** So, with all of these calculations,
**[4:08]** you've just computed the derivatives of the cost function J with respect
**[4:11]** to each your parameters w_1, w_2 and b.
**[4:15]** Just a couple of details about what we're doing,
**[4:17]** we're using dw_1 and dw_2 and db as accumulators,
**[4:24]** so that after this computation,
**[4:26]** dw_1 is equal to the derivative of
**[4:30]** your overall cost function with respect to w_1 and similarly for dw_2 and db.
**[4:36]** So, notice that dw_1 and dw_2 do not have a superscript i,
**[4:39]** because we're using them in this code as
**[4:41]** accumulators to sum over the entire training set.
**[4:44]** Whereas in contrast, dz_i here,
**[4:46]** this was dz with respect to just one single training example.
**[4:51]** So, that's why that had a superscript i to refer to the one training example,
**[4:55]** i that is computerised.
**[4:56]** So, having finished all these calculations,
**[4:59]** to implement one step of gradient descent,
**[5:02]** you will implement w_1,
**[5:03]** gets updated as w_1 minus the learning rate times dw_1,
**[5:08]** w_2, ends up this as w_2 minus learning rate times dw_2,
**[5:12]** and b gets updated as b minus the learning rate times db,
**[5:17]** where dw_1, dw_2 and db were as computed.
**[5:22]** Finally, J here will also be a correct value for your cost function.
**[5:27]** So, everything on the slide implements just one single step of gradient descent,
**[5:32]** and so you have to repeat everything on this slide
**[5:35]** multiple times in order to take multiple steps of gradient descent.
**[5:38]** In case these details seem too complicated, again,
**[5:42]** don't worry too much about it for now,
**[5:44]** hopefully all this will be clearer when you
**[5:47]** go and implement this in the programming assignments.
**[5:49]** But it turns out there are two weaknesses
**[5:53]** with the calculation as we've implemented it here,
**[5:57]** which is that, to implement logistic regression this way,
**[6:01]** you need to write two for loops.
**[6:03]** The first for loop is this for loop over the m training examples,
**[6:06]** and the second for loop is a for loop over all the features over here.
**[6:11]** So, in this example,
**[6:12]** we just had two features; so,
**[6:14]** n is equal to two and x equals two,
**[6:16]** but maybe we have more features,
**[6:18]** you end up writing here dw_1 dw_2,
**[6:20]** and you similar computations for dw_t,
**[6:23]** and so on delta dw_n.
**[6:25]** So, it seems like you need to have a for loop over the features, over n features.
**[6:31]** When you're implementing deep learning algorithms,
**[6:34]** you find that having explicit for loops in
**[6:37]** your code makes your algorithm run less efficiency.
**[6:41]** So, in the deep learning era,
**[6:43]** we would move to a bigger and bigger datasets,
**[6:46]** and so being able to implement your algorithms without using explicit
**[6:50]** for loops is really important and will help you to scale to much bigger datasets.
**[6:54]** So, it turns out that there are a set of techniques called vectorization
**[6:58]** techniques that allow you to get rid of these explicit for-loops in your code.
**[7:03]** I think in the pre-deep learning era,
**[7:06]** that's before the rise of deep learning,
**[7:08]** vectorization was a nice to have,
**[7:10]** so you could sometimes do it to speed up your code and sometimes not.
**[7:14]** But in the deep learning era, vectorization,
**[7:17]** that is getting rid of for loops,
**[7:19]** like this and like this,
**[7:20]** has become really important,
**[7:22]** because we're more and more training on very large datasets,
**[7:26]** and so you really need your code to be very efficient.
**[7:28]** So, in the next few videos,
**[7:30]** we'll talk about vectorization and how to
**[7:33]** implement all this without using even a single for loop.
**[7:38]** So, with this, I hope you have a sense of how to
**[7:41]** implement logistic regression or gradient descent for logistic regression.
**[7:45]** Things will be clearer when you implement the programming exercise.
**[7:48]** But before actually doing the programming exercise,
**[7:51]** let's first talk about vectorization so that you can implement this whole thing,
**[7:55]** implement a single iteration of gradient descent without using any for loops.
