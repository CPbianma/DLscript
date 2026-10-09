---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 1
section: Regularizing your Neural Network
item_title: Regularization
duration: 10 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/Srsrc/regularization
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Regularization — Transcript

**[0:00]** If you suspect your neural network is over fitting your data,
**[0:03]** that is, you have a high variance problem,
**[0:05]** one of the first things you should try is probably regularization.
**[0:09]** The other way to address high variance
**[0:11]** is to get more training data that's also quite reliable.
**[0:13]** But you can't always get more training data, or
**[0:15]** it could be expensive to get more data.
**[0:17]** But adding regularization will often help to prevent overfitting, or
**[0:21]** to reduce variance in your network.
**[0:23]** So let's see how regularization works.
**[0:26]** Let's develop these ideas using logistic regression.
**[0:28]** Recall that for logistic regression, you try to minimize the cost function J,
**[0:33]** which is defined as this cost function.
**[0:37]** Some of your training examples of the losses of the individual predictions in
**[0:41]** the different examples, where you recall that w and
**[0:45]** b in the logistic regression, are the parameters.
**[0:48]** So w is an x-dimensional parameter vector, and b is a real number.
**[0:54]** And so, to add regularization to logistic regression, what you do is add to
**[0:58]** it, this thing, lambda, which is called the regularization parameter.
**[1:03]** I'll say more about that in a second.
**[1:04]** But lambda over 2m times the norm of w squared.
**[1:10]** So here, the norm of w squared, is just equal to
**[1:15]** sum from j equals 1 to nx of wj squared, or this can also be written w,
**[1:22]** transpose w, it's just a square Euclidean norm of the prime to vector w.
**[1:27]** And this is called L2 regularization.
**[1:33]** Because here, you're using the Euclidean norm, also it's
**[1:36]** called the L2 norm with the parameter vector w.
**[1:38]** Now, why do you regularize just the parameter w?
**[1:41]** Why don't we add something here, you know, about b as well?
**[1:47]** In practice, you could do this, but I usually just omit this.
**[1:51]** Because if you look at your parameters, w is usually a pretty high dimensional
**[1:56]** parameter vector, especially with a high variance problem.
**[2:00]** Maybe w just has a lot of parameters, so
**[2:02]** you aren't fitting all the parameters well, whereas b is just a single number.
**[2:06]** So almost all the parameters are in w rather than b.
**[2:10]** And if you add this last term, in practice,
**[2:12]** it won't make much of a difference,
**[2:14]** because b is just one parameter over a very large number of parameters.
**[2:17]** In practice, I usually just don't bother to include it.
**[2:21]** But you can if you want.
**[2:22]** So L2 regularization is the most common type of regularization.
**[2:27]** You might have also heard of some people talk about L1 regularization.
**[2:32]** And that's when you add, instead of this L2 norm,
**[2:38]** you instead add a term that is lambda over m of sum over, of this.
**[2:45]** And this is also called the L1 norm of the parameter vector w,
**[2:49]** so the little subscript 1 down there, right?
**[2:52]** And I guess whether you put m or 2m in the denominator, is just a scaling constant.
**[2:58]** If you use L1 regularization, then w will end up being sparse.
**[3:03]** And what that means is that the w vector will have a lot of zeros in it.
**[3:08]** And some people say that this can help with compressing the model, because
**[3:11]** the set of parameters are zero, then you need less memory to store the model.
**[3:16]** Although, I find that, in practice, L1 regularization, to make your model sparse,
**[3:19]** helps only a little bit.
**[3:20]** So I don't think it's used that much, at least not for
**[3:23]** the purpose of compressing your model.
**[3:26]** And when people train your networks,
**[3:28]** L2 regularization is just used much, much more often.
**[3:31]** (Sorry, just fixing up some of the notation here).
**[3:34]** So, one last detail.
**[3:35]** Lambda here is called the regularization parameter.
**[3:45]** And usually, you set this using your development set, or
**[3:48]** using hold-out cross validation.
**[3:50]** When you try a variety of values and see what does the best,
**[3:53]** in terms of trading off between doing well in your training set versus also
**[3:57]** setting that two normal of your parameters to be small,
**[4:01]** which helps prevent over fitting.
**[4:03]** So lambda is another hyper parameter that you might have to tune.
**[4:07]** And by the way, for the programming exercises,
**[4:09]** lambda is a reserved keyword in the Python programming language.
**[4:14]** So in the programming exercise, we will have l-a-m-b-d,
**[4:19]** without the a, so as not to clash with the reserved keyword in Python.
**[4:23]** So we use l-a-m-b-d to represent the lambda regularization parameter.
**[4:29]** So this is how you implement L2 regularization for logistic regression.
**[4:33]** How about a neural network?
**[4:35]** In a neural network, you have a cost function that's a function of
**[4:39]** all of your parameters, w[1], b[1] through w[capital L], b[capital L],
**[4:44]** where capital L is the number of layers in your neural network.
**[4:48]** And so the cost function is this, sum of the losses,
**[4:54]** sum over your m training examples.
**[4:58]** And so to add regularization, you add lambda over
**[5:03]** 2m, of sum over all of your parameters w, your parameter matrix is w,
**[5:10]** of their, that's called the squared norm.
**[5:14]** Where, this norm of a matrix, really the squared
**[5:19]** norm, is defined as the sum of i, sum of j,
**[5:23]** of each of the elements of that matrix, squared.
**[5:29]** And if you want the indices of this summation,
**[5:31]** this is sum from i=1 through n[l minus 1].
**[5:35]** Sum from j=1 through n[l],
**[5:38]** because w is a n[l] by n[l minus 1] dimensional matrix,
**[5:44]** where these are the number of hidden units or number of units in layers [l minus 1] in layer l.
**[5:51]** So this matrix norm, it turns out is called the Frobenius
**[5:57]** norm of the matrix, denoted with a F in the subscript.
**[6:03]** So for arcane linear algebra technical reasons,
**[6:07]** this is not called the, you know, l2 norm of a matrix.
**[6:10]** Instead, it's called the Frobenius norm of a matrix.
**[6:14]** I know it sounds like it would be more natural to just call the l2 norm of
**[6:16]** the matrix, but for really arcane reasons that you don't need to know,
**[6:21]** by convention, this is called the Frobenius norm.
**[6:24]** It just means the sum of square of elements of a matrix.
**[6:27]** So how do you implement gradient descent with this?
**[6:30]** Previously, we would complete dw, you know, using backprop,
**[6:35]** where backprop would give us the partial derivative
**[6:40]** of J with respect to w, or really w for any given [l].
**[6:46]** And then you update w[l], as w[l] minus the learning rate, times d.
**[6:52]** So this is before we added this extra regularization term to the objective.
**[6:57]** Now that we've added this regularization term to the objective,
**[7:02]** what you do is you take dw and you add to it, lambda over m times w.
**[7:07]** And then you just compute this update, same as before.
**[7:10]** And it turns out that with this new definition of dw[l],
**[7:14]** this is still, you know, this new dw[l] is still a correct definition of the derivative
**[7:19]** of your cost function, with respect to your parameters,
**[7:23]** now that you've added the extra regularization term at the end.
**[7:29]** And it's for this reason that L2 regularization is sometimes also
**[7:33]** called weight decay.
**[7:36]** So if I take this definition of dw[l] and just plug it in here,
**[7:42]** then you see that the update is w[l] gets updated as w[l] times
**[7:47]** the learning rate alpha times, you know, the thing from backprop,
**[7:54]** plus lambda over m, times w[l].
**[8:02]** Let's move the minus sign there.
**[8:04]** And so this is equal to w[l] minus alpha,
**[8:09]** lambda over m times w[l], minus alpha times,
**[8:14]** you know, the thing you got from backprop.
**[8:18]** And so this term shows that whatever the matrix w[l] is,
**[8:22]** you're going to make it a little bit smaller, right?
**[8:25]** This is actually as if you're taking the matrix w and
**[8:28]** you're multiplying it by 1 minus alpha lambda over m.
**[8:33]** You're really taking the matrix w and subtracting alpha lambda over m times this.
**[8:38]** Like you're multiplying the matrix w by this number,
**[8:41]** which is going to be a little bit less than 1.
**[8:43]** So this is why L2 norm regularization is also called weight decay.
**[8:48]** Because it's just like the ordinary gradient descent, where you update
**[8:53]** w by subtracting alpha, times the original gradient you got from backprop.
**[8:59]** But now you're also, you know, multiplying w by this thing,
**[9:04]** which is a little bit less than 1.
**[9:08]** So the alternative name for L2 regularization is weight decay.
**[9:11]** I'm not really going to use that name, but the intuition for why
**[9:15]** it's called weight decay is that this first term here, is equal to this.
**[9:21]** So you're just multiplying the weight matrix by a number slightly less than 1.
**[9:25]** So that's how you implement L2 regularization in a neural network.
**[9:29]** Now, one question that peer centers ask me is, you know, "Hey, Andrew,
**[9:32]** why does regularization prevent over-fitting?"
**[9:35]** Let's take a quick look at the next video,
**[9:37]** and gain some intuition for how regularization prevents over-fitting.
