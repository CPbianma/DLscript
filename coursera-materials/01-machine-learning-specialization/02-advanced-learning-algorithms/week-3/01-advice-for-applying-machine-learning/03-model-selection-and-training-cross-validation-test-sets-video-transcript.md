---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Advice for applying machine learning
item_title: Model selection and training/cross validation/test sets
duration: 14 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/zqXm6/model-selection-and-training-cross-validation-test-sets
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Model selection and training/cross validation/test sets — Transcript

**[0:00]** In the last video, you saw how to use
**[0:03]** the test set to evaluate the performance of a model.
**[0:07]** Let's make one further refinement
**[0:08]** to that idea in this video,
**[0:10]** which allow you to use the technique,
**[0:13]** to automatically choose a good model
**[0:15]** for your machine learning algorithm.
**[0:16]** One thing we've seen is that once
**[0:19]** the model's parameters w and
**[0:21]** b have been fit to the training set.
**[0:23]** The training error may not be
**[0:25]** a good indicator of how well the algorithm will
**[0:28]** do or how well it will generalize to
**[0:31]** new examples that were not in the training set,
**[0:34]** and in particular, for this example,
**[0:37]** the training error will be pretty much zero.
**[0:39]** That's likely much lower than
**[0:42]** the actual generalization error,
**[0:44]** and by that I mean the average error
**[0:46]** on new examples that were not in the training set.
**[0:51]** What you saw on the last video is that
**[0:53]** J test the performance of the algorithm on examples,
**[0:56]** is not trained on,
**[0:57]** that will be a better indicator of
**[0:59]** how well the model will likely do on new data.
**[1:02]** By that I mean other data that's not in the training set.
**[1:07]** Let's take a look at how this affects,
**[1:09]** how we might use a test set to
**[1:12]** choose a model for a given machine learning application.
**[1:16]** If a fitting a function to
**[1:18]** predict housing prices or some other regression problem,
**[1:21]** one model you might consider
**[1:23]** is to fit a linear model like this.
**[1:25]** This is a first-order polynomial and
**[1:28]** we're going to use d equals 1 on
**[1:30]** this slide to denote
**[1:31]** fitting a one or first-order polynomial.
**[1:35]** If you were to fit
**[1:36]** a model like this to your training set,
**[1:38]** you get some parameters, w and b,
**[1:41]** and you can then compute
**[1:42]** J tests to estimate
**[1:45]** how well does this generalize to new data?
**[1:47]** On this slide, I'm going to use w^1,
**[1:51]** b^1 to denote that these are the parameters you
**[1:55]** get if you were to fit a first order polynomial,
**[1:58]** a degree one, d equals 1 polynomial.
**[2:01]** Now, you might also consider
**[2:05]** fitting a second-order polynomial or quadratic model,
**[2:08]** so this is the model.
**[2:11]** If you were to fit this to your training set,
**[2:14]** you would get some parameters, w^2, b^2,
**[2:18]** and you can then similarly evaluate
**[2:22]** those parameters on your test set and get J test w^2,
**[2:26]** b^2, and this will give you a sense of how
**[2:29]** well the second-order polynomial does.
**[2:31]** You can go on to try d equals 3,
**[2:33]** that's a third order or
**[2:35]** a degree three polynomial that looks like this,
**[2:38]** and fit parameters and similarly get J test.
**[2:43]** You might keep doing this until,
**[2:45]** say you try up to a 10th order polynomial and you
**[2:48]** end up with J test of w^10, b^10.
**[2:52]** That gives you a sense of how well
**[2:54]** the 10th order polynomial is doing.
**[2:57]** One procedure you could try,
**[2:59]** this turns out not to be the best procedure,
**[3:02]** but one thing you could try is,
**[3:04]** look at all of these J tests,
**[3:07]** and see which one gives you the lowest value.
**[3:11]** Say, you find that,
**[3:13]** J test for the fifth order polynomial for w^5,
**[3:18]** b^5 turns out to be the lowest.
**[3:21]** If that's the case, then you might decide that
**[3:24]** the fifth order polynomial d equals 5 does best,
**[3:27]** and choose that model for your application.
**[3:31]** If you want to estimate how well this model performs,
**[3:34]** one thing you could do,
**[3:35]** but this turns out to be a slightly flawed procedure,
**[3:38]** is to report the test set error,
**[3:40]** J test w^5, b^5.
**[3:44]** The reason this procedure is flawed is J test of w^5,
**[3:50]** b^5 is likely to be
**[3:51]** an optimistic estimate of the generalization error.
**[3:54]** In other words, it is likely to be
**[3:57]** lower than the actual generalization error,
**[4:01]** and the reason is,
**[4:03]** in the procedure we talked about on this slide
**[4:05]** with basic fits, one extra parameter,
**[4:08]** which is d, the degree of polynomial,
**[4:12]** and we chose this parameter using the test set.
**[4:16]** On the previous slide, we saw that if you were to fit w,
**[4:19]** b to the training data,
**[4:21]** then the training data would be
**[4:24]** an overly optimistic estimate of generalization error.
**[4:28]** It turns out too, that if you want to choose the
**[4:31]** parameter d using the test set,
**[4:33]** then the test set J test is now an overly optimistic,
**[4:37]** that is lower than actual estimate
**[4:39]** of the generalization error.
**[4:41]** The procedure on this particular slide is
**[4:44]** flawed and I don't recommend using this.
**[4:46]** Instead, if you want to automatically choose a model,
**[4:50]** such as decide what degree polynomial to use.
**[4:53]** Here's how you modify the training and
**[4:56]** testing procedure in order to carry out model selection.
**[5:00]** Whereby model selection, I
**[5:01]** mean choosing amongst different models,
**[5:04]** such as these 10 different models that you might
**[5:07]** contemplate using for your machine learning application.
**[5:10]** The way we'll modify the procedure is instead
**[5:14]** of splitting your data into just two subsets,
**[5:16]** the training set and the test set,
**[5:18]** we're going to split your data
**[5:19]** into three different subsets,
**[5:21]** which we're going to call the training set,
**[5:23]** the cross-validation set, and then also the test set.
**[5:28]** Using our example from before
**[5:31]** of these 10 training examples,
**[5:34]** we might split it into
**[5:36]** putting 60 percent of the data into
**[5:39]** the training set and so
**[5:43]** the notation we'll use for
**[5:45]** the training set portion will be the same as before,
**[5:47]** except that now M train,
**[5:50]** the number of training examples will be six
**[5:53]** and we might put 20 percent of the data
**[5:56]** into the cross-validation set
**[5:59]** and a notation I'm going to use is x_cv of one,
**[6:04]** y_cv of one for the first cross-validation example.
**[6:08]** So cv stands for cross-validation,
**[6:10]** all the way down to x_cv of m_cv and y_cv of m_cv.
**[6:17]** Where here, m_cv equals 2 in this example,
**[6:19]** is the number of cross-validation examples.
**[6:22]** Then finally we have the test set same as before,
**[6:26]** so x1 through x m tests and y1 through y m,
**[6:33]** where m tests equal to 2.
**[6:36]** This is the number of test examples.
**[6:37]** We'll see you on the next slide how to
**[6:39]** use the cross-validation set.
**[6:42]** The way we'll modify the procedure
**[6:44]** is you've already seen the training set and
**[6:48]** the test set and we're going to introduce
**[6:51]** a new subset of the data called the cross-validation set.
**[6:56]** The name cross-validation refers to
**[6:59]** that this is an extra dataset that we're going to use
**[7:02]** to check or cross check
**[7:04]** the validity or really the accuracy of different models.
**[7:08]** I don t think it's a great name,
**[7:09]** but that is what people in machine learning
**[7:11]** have gotten to call this extra dataset.
**[7:15]** You may also hear people call
**[7:17]** this the validation set for short,
**[7:19]** it's just fewer syllables than
**[7:21]** cross-validation or in some applications,
**[7:24]** people also call this the development set.
**[7:27]** Means basically the same thing or for short.
**[7:29]** Sometimes you hear people call this the dev set,
**[7:32]** but all of these terms mean
**[7:33]** the same thing as cross-validation set.
**[7:36]** I personally use the term dev
**[7:38]** set the most often because it's the shortest,
**[7:41]** fastest way to say it but cross-validation is pretty
**[7:44]** used a little bit more often
**[7:45]** by machine learning practitioners.
**[7:47]** Onto these three subsets of the data training set,
**[7:51]** cross-validation set, and test set,
**[7:53]** you can then compute
**[7:55]** the training error, the cross-validation error,
**[7:57]** and the test error using these three formulas.
**[8:01]** Whereas usual, none of these terms include
**[8:04]** the regularization term that is
**[8:05]** included in the training objective,
**[8:08]** and this new term in the middle,
**[8:09]** the cross-validation error is just the average over
**[8:12]** your m_cv cross-validation examples
**[8:15]** of the average say, squared error.
**[8:18]** This term,
**[8:20]** in addition to being called cross-validation error,
**[8:23]** is also commonly called the validation error for short,
**[8:26]** or even the development set error, or the dev error.
**[8:30]** Armed with these three measures
**[8:33]** of learning algorithm performance,
**[8:35]** this is how you can then go
**[8:36]** about carrying out model selection.
**[8:39]** You can, with the 10 models,
**[8:42]** same as earlier on this slide,
**[8:44]** with d equals 1, d equals 2,
**[8:47]** all the way up to
**[8:48]** a 10th degree or the 10th order polynomial,
**[8:51]** you can then fit the parameters w_1, b_1.
**[8:56]** But instead of evaluating this on your test set,
**[8:59]** you will instead evaluate these parameters on
**[9:02]** your cross-validation sets and compute J_cv of w1,
**[9:06]** b1, and similarly,
**[9:08]** for the second model,
**[9:10]** we get J_cv of w2, v2,
**[9:13]** and all the way down to J_cv of w10, b10.
**[9:18]** Then, in order to choose a model,
**[9:22]** you will look at which model has
**[9:24]** the lowest cross-validation error,
**[9:27]** and concretely, let's say that J_cv of w4,
**[9:33]** b4 as low as,
**[9:35]** then what that means is you pick
**[9:37]** this fourth-order polynomial as
**[9:39]** the model you will use for this application.
**[9:41]** Finally, if you want to report out an estimate of
**[9:46]** the generalization error of how
**[9:48]** well this model will do on new data.
**[9:50]** You will do so using that third subset of your data,
**[9:55]** the test set and you report out Jtest of w4,b4.
**[10:00]** You notice that throughout this entire procedure,
**[10:03]** you had fit these parameters using the training set.
**[10:07]** You then chose the parameter d or chose the degree of
**[10:11]** polynomial using the cross-validation set
**[10:14]** and so up until this point,
**[10:15]** you've not fit any parameters,
**[10:17]** either w or b or d to
**[10:19]** the test set and that's why Jtest in this example will
**[10:24]** be fair estimate of
**[10:26]** the generalization error of
**[10:28]** this model thus parameters w4,b4.
**[10:32]** This gives a better procedure
**[10:35]** for model selection and it lets you
**[10:38]** automatically make a decision like what order
**[10:40]** polynomial to choose for your linear regression model.
**[10:44]** This model selection procedure also works
**[10:47]** for choosing among other types of models.
**[10:50]** For example, choosing a neural network architecture.
**[10:53]** If you are fitting
**[10:54]** a model for handwritten digit recognition,
**[10:58]** you might consider three models like this,
**[11:01]** maybe even a larger set of models than just me but
**[11:04]** here are a few different neural networks of small,
**[11:07]** somewhat larger, and then even larger.
**[11:09]** To help you decide how many layers do
**[11:13]** the neural network have and
**[11:14]** how many hidden units per layer should you have,
**[11:17]** you can then train all three of these models and
**[11:20]** end up with parameters w1,
**[11:25]** b1 for the first model, w2,
**[11:28]** b2 for the second model,
**[11:30]** and w3,b3 for the third model.
**[11:33]** You can then evaluate
**[11:35]** the neural networks performance using Jcv,
**[11:39]** using your cross-validation set
**[11:42]** Since this is a classification problem,
**[11:44]** Jcv the most common choice would be to compute this as
**[11:48]** the fraction of cross-validation examples
**[11:51]** that the algorithm has misclassified.
**[11:53]** You would compute this using
**[11:56]** all three models and then
**[11:59]** pick the model with the lowest cross validation error.
**[12:03]** If in this example,
**[12:05]** this has the lowest cross validation error,
**[12:08]** you will then pick the second neural network and use
**[12:13]** parameters trained on this model and finally,
**[12:17]** if you want to report out
**[12:19]** an estimate of the generalization error,
**[12:21]** you then use the test set to
**[12:23]** estimate how well the neural network
**[12:25]** that you just chose will do.
**[12:27]** It's considered best practice in machine learning
**[12:30]** that if you have to make decisions about your model,
**[12:34]** such as fitting parameters or
**[12:35]** choosing the model architecture,
**[12:37]** such as neural network architecture or degree of
**[12:39]** polynomial if you're fitting a linear regression,
**[12:42]** to make all those decisions only using
**[12:45]** your training set and your cross-validation set,
**[12:49]** and to not look at the test set at all while you're still
**[12:51]** making decisions regarding your learning algorithm.
**[12:54]** It's only after you've come up with
**[12:57]** one model as your final model to only then
**[13:00]** evaluate it on the test set and
**[13:03]** because you haven't made any
**[13:04]** decisions using the test set,
**[13:06]** that ensures that your test set is
**[13:08]** a fair and not overly optimistic estimate
**[13:12]** of how well your model will generalize to new data.
**[13:16]** That's model selection and this is
**[13:18]** actually a very widely used procedure.
**[13:21]** I use this all the time to automatically
**[13:23]** choose what model to use
**[13:25]** for a given machine learning application.
**[13:28]** Earlier this week, I mentioned running diagnostics to
**[13:32]** decide how to improve
**[13:34]** the performance of a learning algorithm.
**[13:36]** Now that you have a way to evaluate
**[13:38]** learning algorithms and even
**[13:40]** automatically choose a model,
**[13:41]** let's dive more deeply into examples of some diagnostics.
**[13:45]** The most powerful diagnostic
**[13:47]** that I know of and that I used for a lot of
**[13:49]** machine learning applications is one
**[13:51]** called bias and variance.
**[13:53]** Let's take a look at what that means in the next video.
