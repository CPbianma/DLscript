---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 2
section: Python and Vectorization
item_title: Vectorizing Logistic Regression
duration: 8 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/moUlO/vectorizing-logistic-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Vectorizing Logistic Regression — Transcript

**[0:00]** We have talked about how vectorization lets you speed up your code significantly.
**[0:05]** In this video, we'll talk about how you can vectorize
**[0:08]** the implementation of logistic regression,
**[0:10]** so they can process an entire training set,
**[0:12]** that is implement a single elevation of grading descent with respect to
**[0:15]** an entire training set without using even a single explicit for loop.
**[0:22]** I'm super excited about this technique,
**[0:24]** and when we talk about neural networks later without
**[0:26]** using even a single explicit for loop.
**[0:30]** Let's get started. Let's first examine the four propagation steps of logistic regression.
**[0:35]** So, if you have M training examples,
**[0:37]** then to make a prediction on the first example,
**[0:40]** you need to compute that,
**[0:42]** compute Z. I'm using this familiar formula,
**[0:45]** then compute the activations,
**[0:47]** you compute y hat in the first example.
**[0:49]** Then to make a prediction on the second training example,
**[0:52]** you need to compute that.
**[0:54]** Then, to make a prediction on the third example,
**[0:57]** you need to compute that, and so on.
**[0:59]** And you might need to do this M times,
**[1:01]** if you have M training examples.
**[1:03]** So, it turns out, that in order to carry out the four propagation step,
**[1:08]** that is to compute these predictions on our M training examples,
**[1:13]** there is a way to do so,
**[1:14]** without needing an explicit for loop.
**[1:17]** Let's see how you can do it.
**[1:20]** First, remember that we defined a matrix capital X to be your training inputs,
**[1:26]** stacked together in different columns like this.
**[1:30]** So, this is a matrix,
**[1:33]** that is a NX by M matrix.
**[1:38]** So, I'm writing this as a Python numpy shape,
**[1:41]** this just means that X is a NX by M dimensional matrix.
**[1:50]** Now, the first thing I want to do is show how you can compute Z1, Z2,
**[1:54]** Z3 and so on,
**[1:56]** all in one step,
**[1:58]** in fact, with one line of code.
**[2:01]** So, I'm going to construct a 1
**[2:06]** by M matrix that's really a row vector while I'm going to compute Z1,
**[2:13]** Z2, and so on,
**[2:15]** down to ZM, all at the same time.
**[2:18]** It turns out that this can be expressed as
**[2:22]** W transpose to capital matrix X plus and then this vector B,
**[2:29]** B and so on.
**[2:31]** B, where this thing,
**[2:33]** this B, B, B, B,
**[2:34]** B thing is a 1xM vector or
**[2:38]** 1xM matrix or that is as a M dimensional row vector.
**[2:46]** So hopefully there you are with matrix multiplication.
**[2:50]** You might see that W transpose X1,
**[2:56]** X2 and so on to XM,
**[2:58]** that W transpose can be a row vector.
**[3:05]** So this W transpose will be a row vector like that.
**[3:10]** And so this first term will evaluate to W transpose X1,
**[3:18]** W transpose X2 and so on, dot, dot, dot,
**[3:22]** W transpose XM, and then we add this second term B,
**[3:29]** B, B, and so on,
**[3:30]** you end up adding B to each element.
**[3:33]** So you end up with another 1xM vector.
**[3:37]** Well that's the first element,
**[3:38]** that's the second element and so on,
**[3:40]** and that's the nth element.
**[3:42]** And if you refer to the definitions above,
**[3:45]** this first element is exactly the definition of Z1.
**[3:51]** The second element is exactly the definition of Z2 and so on.
**[3:57]** So just as X was once obtained,
**[4:00]** when you took your training examples and
**[4:02]** stacked them next to each other, stacked them horizontally.
**[4:07]** I'm going to define capital Z to be this where
**[4:11]** you take the lowercase Z's and stack them horizontally.
**[4:16]** So when you stack the lower case X's corresponding to a different training examples,
**[4:21]** horizontally you get this variable capital X and
**[4:24]** the same way when you take these lowercase Z variables,
**[4:27]** and stack them horizontally,
**[4:28]** you get this variable capital Z.
**[4:34]** And it turns out, that in order to implement this,
**[4:37]** the non-pie command is capital Z equals NP dot W dot T,
**[4:45]** that's W transpose X and then plus B.
**[4:51]** Now there is a subtlety in Python,
**[4:53]** which is at here B is a real number or if you want to say you know 1x1 matrix,
**[4:59]** is just a normal real number.
**[5:01]** But, when you add this vector to this real number,
**[5:06]** Python automatically takes this real number B and expands it out to this 1XM row vector.
**[5:13]** So in case this operation seems a little bit mysterious,
**[5:16]** this is called broadcasting in Python,
**[5:20]** and you don't have to worry about it for now,
**[5:22]** we'll talk about it some more in the next video.
**[5:25]** But the takeaway is that with just one line of code, with this line of code,
**[5:29]** you can calculate capital Z and capital Z is
**[5:33]** going to be a 1XM matrix that contains all of the lower cases Z's.
**[5:37]** Lowercase Z1 through lower case ZM.
**[5:41]** So that was Z, how about these values A.
**[5:46]** What we like to do next,
**[5:48]** is find a way to compute A1,
**[5:52]** A2 and so on to AM,
**[5:57]** all at the same time,
**[5:58]** and just as stacking lowercase X's resulted in
**[6:03]** capital X and stacking horizontally lowercase Z's resulted in capital Z,
**[6:08]** stacking lower case A,
**[6:10]** is going to result in a new variable,
**[6:12]** which we are going to define as capital A.
**[6:15]** And in the program assignment,
**[6:18]** you see how to implement a vector valued sigmoid function,
**[6:22]** so that the sigmoid function,
**[6:24]** inputs this capital Z as a variable and very efficiently outputs capital A.
**[6:32]** So you see the details of that in the programming assignment.
**[6:36]** So just to recap,
**[6:38]** what we've seen on this slide is that instead of needing to loop over
**[6:42]** M training examples to compute lowercase Z and lowercase A,
**[6:47]** one of the time, you can implement this one line of code,
**[6:52]** to compute all these Z's at the same time.
**[6:54]** And then, this one line of code,
**[6:57]** with appropriate implementation of
**[6:59]** lowercase Sigma to compute all the lowercase A's all at the same time.
**[7:04]** So this is how you implement
**[7:05]** a vectorize implementation of
**[7:07]** the four propagation for all M training examples at the same time.
**[7:11]** So to summarize, you've just seen how you can use
**[7:13]** vectorization to very efficiently compute all of the activations,
**[7:18]** all the lowercase A's at the same time.
**[7:21]** Next, it turns out, you can also use vectorization very
**[7:24]** efficiently to compute the backward propagation,
**[7:27]** to compute the gradients.
**[7:29]** Let's see how you can do that, in the next video.
