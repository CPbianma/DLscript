---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 2
section: Gradient descent in practice
item_title: Polynomial regression
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/OnGhN/polynomial-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Polynomial regression — Transcript

**[0:02]** So far we've just been
**[0:05]** fitting straight lines to our data.
**[0:07]** Let's take the ideas of multiple linear regression and
**[0:10]** feature engineering to come up with
**[0:12]** a new algorithm called polynomial regression,
**[0:15]** which will let you fit curves,
**[0:16]** non-linear functions, to your data.
**[0:18]** Let's say you have a housing
**[0:20]** data-set that looks like this,
**[0:22]** where feature x is the size in square feet.
**[0:25]** It doesn't look like a straight line
**[0:27]** fits this data-set very well.
**[0:29]** Maybe you want to fit a curve,
**[0:32]** maybe a quadratic function to the data like
**[0:35]** this which includes a size x and also x squared,
**[0:41]** which is the size raised to the power of two.
**[0:44]** Maybe that will give you a better fit to the data.
**[0:47]** But then you may decide that
**[0:49]** your quadratic model doesn't really make sense
**[0:51]** because a quadratic function eventually comes back down.
**[0:55]** Well, we wouldn't really expect
**[0:56]** housing prices to go down when the size increases.
**[1:00]** Big houses seem like they should usually cost more.
**[1:04]** Then you may choose a cubic function where we
**[1:07]** now have not only x squared, but x cubed.
**[1:12]** Maybe this model produces this curve here,
**[1:16]** which is a somewhat better fit to
**[1:17]** the data because the size
**[1:19]** does eventually come back up as the size increases.
**[1:23]** These are both examples of polynomial regression,
**[1:26]** because you took your optional feature x,
**[1:29]** and raised it to the power of
**[1:31]** two or three or any other power.
**[1:34]** In the case of the cubic function,
**[1:36]** the first feature is the size,
**[1:38]** the second feature is the size squared,
**[1:40]** and the third feature is the size cubed.
**[1:43]** I just want to point out one more thing,
**[1:46]** which is that if you create features that are
**[1:49]** these powers like the square
**[1:51]** of the original features like this,
**[1:53]** then feature scaling becomes increasingly important.
**[1:57]** If the size of the house ranges from say,
**[2:00]** 1-1,000 square feet,
**[2:02]** then the second feature,
**[2:04]** which is a size squared,
**[2:06]** will range from one to a million,
**[2:08]** and the third feature,
**[2:10]** which is size cubed,
**[2:11]** ranges from one to a billion.
**[2:14]** These two features, x squared and x cubed,
**[2:18]** take on very different ranges of
**[2:20]** values compared to the original feature x.
**[2:23]** If you're using gradient descent,
**[2:25]** it's important to apply feature scaling to get
**[2:28]** your features into comparable ranges of values.
**[2:31]** Finally, just one last example of how you
**[2:35]** really have a wide range of choices of features to use.
**[2:38]** Another reasonable alternative to
**[2:40]** taking the size squared and
**[2:42]** size cubed is to say use the square root of x.
**[2:46]** Your model may look like w_1 times
**[2:50]** x plus w_2 times the square root of x plus b.
**[2:55]** The square root function looks like this,
**[2:57]** and it becomes a bit less steep as x increases,
**[3:01]** but it doesn't ever completely flatten out,
**[3:04]** and it certainly never ever comes back down.
**[3:07]** This would be another choice of features that
**[3:09]** might work well for this data-set as well.
**[3:12]** You may ask yourself,
**[3:14]** how do I decide what features to use?
**[3:17]** Later in the second course in this specialization,
**[3:20]** you see how you can choose different features and
**[3:23]** different models that include
**[3:25]** or don't include these features,
**[3:26]** and you have a process for measuring how well
**[3:30]** these different models perform to help you
**[3:32]** decide which features to include or not include.
**[3:35]** For now, I just want you to be aware
**[3:37]** that you have a choice in what features you use.
**[3:40]** By using feature engineering and polynomial functions,
**[3:44]** you can potentially get
**[3:45]** a much better model for your data.
**[3:48]** In the optional lab that follows this video,
**[3:51]** you will see some code that implements
**[3:53]** polynomial regression using features like x,
**[3:56]** x squared, and x cubed.
**[3:58]** Please take a look and run the code and see how it works.
**[4:02]** There's also another optional lab
**[4:05]** after that one that shows how to
**[4:07]** use a popular open source toolkit
**[4:09]** that implements linear regression.
**[4:12]** Scikit-learn is
**[4:14]** a very widely used open source machine learning library
**[4:18]** that is used by many practitioners
**[4:20]** in many of the top AI,
**[4:21]** internet, machine learning companies in the world.
**[4:26]** If either now or in the future
**[4:28]** you're using machine learning in your job,
**[4:30]** there's a very good chance you'll be using
**[4:32]** tools like Scikit-learn to train your models.
**[4:37]** Working through that optional lab will give you
**[4:40]** a chance to not only better understand linear regression,
**[4:43]** but also see how this can be done in
**[4:46]** just a few lines of code using
**[4:47]** a library like Scikit-learn.
**[4:50]** For you to have a solid understanding
**[4:53]** of these algorithms,
**[4:54]** and be able to apply them,
**[4:55]** I do think is important that you
**[4:57]** know how to implement linear regression
**[4:59]** yourself and not just call
**[5:01]** some scikit-learn function that is a black-box.
**[5:04]** But scikit-learn also has
**[5:06]** an important role in a way
**[5:08]** machine learning is done in practice today.
**[5:11]** We're just about at the end of this week.
**[5:14]** Congratulations on finishing all of this week's videos.
**[5:18]** Please do take a look at the practice
**[5:19]** quizzes and also the practice lab,
**[5:22]** which I hope will let you try out and
**[5:24]** practice ideas that we've discussed.
**[5:27]** In this week's practice lab,
**[5:29]** you implement linear regression.
**[5:31]** I hope you have a lot of fun getting
**[5:33]** this learning algorithm to work for yourself.
**[5:35]** Best of luck with that.
**[5:37]** I also look forward to seeing you in next week's videos,
**[5:41]** where we'll go beyond regression,
**[5:43]** that is predicting numbers,
**[5:44]** to talk about our first classification algorithm,
**[5:47]** which can predict categories.
**[5:49]** I'll see you next week.
