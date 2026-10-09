---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 1
section: Train the model with gradient descent
item_title: Running gradient descent
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/349Ay/running-gradient-descent
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Running gradient descent — Transcript

**[0:02]** Let's see what happens when you run gradient descent for linear regression.
**[0:06]** Let's go see the algorithm in action.
**[0:08]** Here's a plot of the model and data on the upper left and
**[0:12]** a contour plot of the cost function on the upper right and
**[0:17]** at the bottom is the surface plot of the same cost function.
**[0:23]** Often w and b will both be initialized to 0, but for
**[0:28]** this demonstration, lets initialized w = -0.1 and b = 900.
**[0:35]** So this corresponds to f(x) = -0.1x + 900.
**[0:44]** Now, if we take one step using gradient descent,
**[0:48]** we ended up going from this point of the cost function out
**[0:53]** here to this point just down and to the right and
**[0:57]** notice that the straight line fit is also changed a bit.
**[1:04]** Let's take another step.
**[1:06]** The cost function has now moved to this third and
**[1:10]** again the function f(x) has also changed a bit.
**[1:15]** As you take more of these steps, the cost is decreasing at each update.
**[1:21]** So the parameters w and b are following this trajectory.
**[1:28]** And if you look on the left, you get this corresponding straight line
**[1:33]** fit that fits the data better and better until we've reached the global minimum.
**[1:40]** The global minimum corresponds to this straight line fit,
**[1:44]** which is a relatively good fit to the data.
**[1:47]** I mean, isn't that cool.
**[1:50]** And so that's gradient descent and
**[1:53]** we're going to use this to fit a model to the holding data.
**[1:58]** And you can now use this f(x) model to predict the price
**[2:02]** of your clients house or anyone else's house.
**[2:06]** For instance, if your friend's house size is 1250 square feet,
**[2:12]** you can now read off the value and predict that maybe they could get,
**[2:17]** I don't know, $250,000 for the house.
**[2:21]** To be more precise, this gradient descent process is called batch gradient descent.
**[2:27]** The term batch gradient descent refers to the fact that on every step of
**[2:31]** gradient descent, we're looking at all of the training examples,
**[2:36]** instead of just a subset of the training data.
**[2:41]** So in computing grading descent, when computing derivatives,
**[2:46]** when computing the sum from i =1 to m.
**[2:50]** And bash gradient descent is looking at the entire batch of
**[2:55]** training examples at each update.
**[2:58]** I know that bash grading percent may not be the most intuitive name, but
**[3:02]** this is what people in the machine learning community call it.
**[3:06]** If you've heard of the newsletter The Batch,
**[3:09]** that's published by DeepLearning.AI.
**[3:12]** The newsletter The batch was also named for this concept in machine learning.
**[3:18]** And then it turns out that there are other versions of gradient descent that do not
**[3:22]** look at the entire training set, but
**[3:24]** instead looks at smaller subsets of the training data at each update step.
**[3:29]** But we'll use batch gradient descent for linear regression.
**[3:34]** So that's it for linear regression.
**[3:36]** Congratulations on getting through your first machine learning model.
**[3:40]** I hope you go and celebrate or I don't know maybe take a nap in your hammock.
**[3:45]** In the optional lab that follows this video.
**[3:48]** You'll see a review of the gradient descent algorithm as was how to implement
**[3:53]** it in code.
**[3:54]** You'll also see a plot that shows how the cost decreases as you continue
**[3:58]** training more iterations.
**[4:01]** And you'll also see a contour plot,
**[4:03]** seeing how the cost gets closer to the global minimum as gradient
**[4:08]** descent finds better and better values for the parameters w and b.
**[4:13]** So remember that to do the optional lab.
**[4:16]** You just need to read and run this code.
**[4:19]** You will need to write any code yourself and
**[4:22]** I hope you take a few moments to do that.
**[4:24]** And also become familiar with the gradient descent code because this will
**[4:29]** help you to implement this and similar algorithms in the future yourself.
**[4:36]** Thanks for sticking with me through the end of this last video for
**[4:39]** the first week and congratulations for making it all the way here.
**[4:43]** You're on your way to becoming a machine learning person.
**[4:47]** In addition to the optional labs, if you haven't done so yet.
**[4:50]** I hope you also check out the practice quizzes, which are a nice way that
**[4:54]** you can double check your own understanding of the concepts.
**[4:58]** It's also totally fine, if you don't get them all right the first time.
**[5:02]** And you can also take the quizzes multiple times until you get the score that
**[5:06]** you want.
**[5:07]** You now know how to implement linear regression with one variable and
**[5:12]** that brings us to the close of this week.
**[5:15]** Next week, we'll learn to make linear regression much more powerful instead of
**[5:20]** one feature like size of a house,
**[5:22]** you learn how to get it to work with lots of features.
**[5:26]** You'll also learn how to get it to fit nonlinear curves.
**[5:29]** These improvements will make the algorithm much more useful and valuable.
**[5:34]** Lastly, we'll also go over some practical tips that will really hope for
**[5:38]** getting linear regression to work on practical applications.
**[5:43]** I'm really happy to have you here with me in this class and
**[5:45]** I look forward to seeing you next week.
