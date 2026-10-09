---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Advice for applying machine learning
item_title: Evaluating a model
duration: 10 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/26yGi/evaluating-a-model
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Evaluating a model — Transcript

**[0:01]** Let's see, you've trained a machine learning model.
**[0:04]** How do you evaluate that model's performance?
**[0:06]** You find that having a systematic way to evaluate performance will also hope paint
**[0:11]** a clearer path for how to improve its performance.
**[0:14]** So let's take a look at how to evaluate the model.
**[0:17]** Let's take the example of learning to predict housing prices as
**[0:22]** a function of the size.
**[0:24]** Let's say you've trained the model to predict housing prices as
**[0:29]** a function of the size x.
**[0:31]** And for the model that is a fourth order polynomial.
**[0:35]** So features x, x squared, execute and x to the 4.
**[0:39]** Because we fit 1/4 order polynomial to a training set with five data points,
**[0:45]** this fits the training data really well.
**[0:50]** But, we don't like this model very much because even though
**[0:54]** the model fits the training data well,
**[0:56]** we think it will fail to generalize to new examples that aren't in the training set.
**[1:03]** So, when you are predicting prices, just a single feature at the size of the house,
**[1:09]** you could plot the model like this and we could see that the curve is very wiggly so
**[1:14]** we know this is probably isn't a good model.
**[1:17]** But if you were fitting this model with even more features,
**[1:21]** say we had x1 the size of house, number of bedrooms,
**[1:25]** the number of floors of the house, also the age of the home in years, then it
**[1:31]** becomes much harder to plot f because f is now a function of x1 through x4.
**[1:36]** And how do you plot a four dimensional function?
**[1:42]** So in order to tell if your model is doing well, especially for applications where
**[1:47]** you have more than one or two features, which makes it difficult to plot f of x.
**[1:52]** We need some more systematic way to evaluate how well your model is doing.
**[1:58]** Here's a technique that you can use.
**[2:00]** If you have a training set and this is a small training set with just 10 examples
**[2:05]** listed here, rather than taking all your data to train the parameters w and
**[2:10]** p of the model, you can instead split the training set into two subsets.
**[2:15]** I'm going to draw a line here, and let's put 70% of the data into
**[2:21]** the first part and I'm going to call that the training set.
**[2:26]** And the second part of the data, let's say 30% of the data,
**[2:31]** I'm going to put into it a test set.
**[2:35]** And what we're going to do is train the models,
**[2:38]** parameters on the training set on this first 70% or so of the data, and
**[2:43]** then we'll test its performance on this test set.
**[2:47]** In notation, I'm going to use x1, y1?
**[2:53]** Same as before, to denote the training examples through xm,
**[3:00]** ym, except that now to make explicit.
**[3:06]** So in this little example we would have seven training example.
**[3:10]** And to introduce one new piece of notation,
**[3:13]** I'm going to use m subscript train.
**[3:16]** M train is a number of training examples which in this small dataset is 7.
**[3:22]** So the subscript train just emphasizes if we're looking at
**[3:26]** the training set portion of the data.
**[3:29]** And for the test set, I'm going to use the notation x1 subscript test comma y1,
**[3:36]** subscript test to denote the first test example, and
**[3:41]** this goes all the way to x mtest subscript tests,
**[3:46]** y mtest subscript tests
**[3:50]** and m tests is the number of test examples, which in this case is 3.
**[3:55]** And it's not uncommon to split your dataset according to maybe a 70,
**[4:00]** 30 split or 80, 20 split with most of your data going into the training set,
**[4:05]** and then a smaller fraction going into the test set.
**[4:10]** So, in order to train a model and evaluated it, this is what it would
**[4:15]** look like if you're using linear regression with a squared error cost.
**[4:21]** Start off by fitting the parameters by minimizing the cost function j of w,b.
**[4:26]** So this is the usual cost function minimize over w,b of
**[4:31]** this square error cost, plus regularization term
**[4:35]** lambda over 2m times some of the w,j squared.
**[4:41]** And then to tell how well this model is doing, you would compute J test of w,b,
**[4:48]** which is equal to the average error on the test set,
**[4:53]** and that's just equal to 1/2 times m test.
**[4:57]** That's the number of test examples.
**[5:00]** And then of some overall the examples from r equals 1, to the number
**[5:05]** of test examples of the squared era on each of the test examples like so.
**[5:10]** So it's a prediction on the i'th test example input minus
**[5:15]** the actual price of the house on the test example squared.
**[5:19]** And notice that the test error formula J test,
**[5:22]** it does not include that regularization term.
**[5:26]** And this will give you a sense of how well your learning algorithm is doing.
**[5:32]** One of the quantity that's often useful to computer as well as
**[5:37]** the training error, which is a measure of how well you're
**[5:41]** learning algorithm is doing on the training set.
**[5:46]** So let me define J train of w,b to be equal to the average over
**[5:50]** the training set.
**[5:52]** 1 over to 2m, or 1/2 m subscript train of
**[5:55]** some over your training set of this squared error term.
**[6:00]** And once again, this does not include the regularization term unlike the cost
**[6:04]** function that you are minimizing to fit the parameters.
**[6:08]** So, in the model like what we saw earlier in this video,
**[6:14]** J train of w,b will be low because the average era on your
**[6:19]** training examples will be zero or very close to zero.
**[6:24]** So J train will be very close to zero.
**[6:27]** But if you have a few additional examples in your test set that the album had
**[6:32]** not trained on, then those test examples, might look like these.
**[6:36]** And there's a large gap between what the album is predicting as the estimated
**[6:41]** housing price, and the actual value of those housing prices.
**[6:45]** And so, J tests will be high.
**[6:48]** So seeing that J test is high on this model, gives you a way to realize that
**[6:53]** even though it does great on the training set, is actually not so good at
**[6:58]** generalizing to new examples to new data points that were not in the training set.
**[7:04]** So, that was regression with squared error cost.
**[7:08]** Now, let's take a look at how you apply this procedure to a classification
**[7:12]** problem.
**[7:13]** For example, if you are classifying between handwritten digits
**[7:17]** that are either 0 or 1,, so same as before,
**[7:20]** you fit the parameters by minimizing the cost function to find the parameters w,b.
**[7:25]** For example, if you were training logistic regression,
**[7:30]** then this would be the cost function J of w,b, where this is the usual
**[7:35]** logistic loss function, and then plus also the regularization term.
**[7:41]** And to compute the test error, J test is then the average over your
**[7:46]** test examples, that's that 30% of your data that wasn't
**[7:51]** in the training set of the logistic loss on your test set.
**[7:56]** And the training error you can also compute using this formula,
**[8:01]** is the average logistic loss on your training data that
**[8:05]** the album was using to minimize the cost function J of w, b.
**[8:11]** Well, when I described here will work, okay, for figuring out if your learning
**[8:16]** algorithm is doing well, by seeing how I was doing in terms of test error.
**[8:21]** When applying machine learning to classification problems,
**[8:25]** there's actually one other definition of J tests and
**[8:28]** J train that is maybe even more commonly used.
**[8:31]** Which is instead of using the logistic loss to compute the test error and
**[8:36]** the training error to instead measure what the fraction of the test set,
**[8:40]** and the fraction of the training set that the algorithm has misclassified.
**[8:46]** So specifically on the test set, you can have the algorithm
**[8:52]** make a prediction 1 or 0 on every test example.
**[8:57]** So, recall y_hat we would predict us 1 if f of x is greater than equal 4.5,
**[9:03]** and zero if it's less than 0.5.
**[9:06]** And you can then count up in the test set the fraction of examples
**[9:11]** where y_hat is not equal to the actual ground truth label while in the test set.
**[9:17]** So concretely, if you are classifying handwritten digits 0,
**[9:22]** 1 binary classification loss, then J tests would be the fraction of that test set,
**[9:28]** where 0 was classified as 1 of 1, classified as 0.
**[9:32]** And similarly,
**[9:33]** J train is a fraction of the training set that has been misclassified.
**[9:38]** Taking a dataset and splitting it into a training set and a separate test set gives
**[9:43]** you a way to systematically evaluate how well your learning algorithm is doing.
**[9:47]** By computing both J tests and J train,
**[9:50]** you can now measure how was doing on the test set and on the training set.
**[9:55]** This procedure is one step to what you'll be able to automatically choose what
**[9:59]** model to use for a given machine learning application.
**[10:03]** For example, if you're trying to predict housing prices,
**[10:06]** should you fit a straight line to your data, or
**[10:09]** fit a second order polynomial, or third order fourth order polynomial?
**[10:12]** It turns out that with one further refinement to the idea you saw in this
**[10:16]** video, you'll be able to have an algorithm help you to automatically make that type
**[10:20]** of decision well.
**[10:21]** Let's take a look at how to do that in the next video.
