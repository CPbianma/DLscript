---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 3
section: Cost function for logistic regression
item_title: Simplified Cost Function for Logistic Regression
duration: 6 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/Zjj2j/simplified-cost-function-for-logistic-regression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Simplified Cost Function for Logistic Regression — Transcript

**[0:00]** In the last video you saw the loss function and
**[0:04]** the cost function for logistic regression.
**[0:07]** In this video you'll see
**[0:09]** a slightly simpler way to write
**[0:11]** out the loss and cost functions,
**[0:13]** so that the implementation
**[0:15]** can be a bit simpler when we get to
**[0:17]** gradient descent for fitting
**[0:18]** the parameters of a logistic regression model.
**[0:22]** Let's take a look. As a reminder,
**[0:24]** here is the loss function that we had defined
**[0:27]** in the previous video for logistic regression.
**[0:30]** Because we're still working on
**[0:33]** a binary classification problem,
**[0:34]** y is either zero or one.
**[0:37]** Because y is either zero or
**[0:41]** one and cannot take on any value other than zero or one,
**[0:45]** we'll be able to come up with a simpler way
**[0:47]** to write this loss function.
**[0:50]** You can write the loss function as follows.
**[0:53]** Given a prediction f of x and the target label y,
**[0:57]** the loss equals negative y times log of f minus
**[1:04]** 1 minus y times log of
**[1:07]** 1 minus f. It turns out this equation,
**[1:12]** which we just wrote in one line,
**[1:14]** is completely equivalent to
**[1:17]** this more complex formula up here.
**[1:20]** Let's see why this is the case.
**[1:23]** Remember, y can only take on
**[1:26]** the values of either one or zero.
**[1:31]** In the first case,
**[1:33]** let's say y equals 1.
**[1:35]** This first y over here is
**[1:38]** one and this 1 minus y is 1 minus 1,
**[1:43]** which is therefore equal to 0.
**[1:46]** So the loss becomes negative 1 times log
**[1:50]** of f of x minus 0 times a bunch of stuff.
**[1:54]** That becomes zero and goes away.
**[1:58]** When y is equal to 1,
**[2:00]** the loss is indeed the first term on top,
**[2:04]** negative log of f of x.
**[2:07]** Let's look at the second case,
**[2:09]** when y is equal to 0.
**[2:13]** In this case, this y here is equal to 0,
**[2:18]** so this first term goes away,
**[2:21]** and the second term is
**[2:23]** 1 minus 0 times that logarithmic term.
**[2:29]** The loss becomes this negative 1 times log
**[2:36]** of 1 minus f of x.
**[2:38]** That's just equal to this second term up here.
**[2:43]** In the case of y equals 0,
**[2:47]** we also get back
**[2:49]** the original loss function as defined above.
**[2:52]** What you see is that whether y is one or zero,
**[2:57]** this single expression here is
**[2:59]** equivalent to the more complex expression up here,
**[3:03]** which is why this gives us
**[3:04]** a simpler way to write the loss with
**[3:06]** just one equation without separating
**[3:09]** out these two cases, like we did on top.
**[3:13]** Using this simplified loss function,
**[3:16]** let's go back and write out
**[3:17]** the cost function for logistic regression.
**[3:21]** Here again is the simplified loss function.
**[3:26]** Recall that the cost J is just the average loss,
**[3:31]** average across the entire training set of m examples.
**[3:35]** So it's 1 over
**[3:37]** n times the sum of the loss from i equals 1
**[3:41]** to m. If you
**[3:43]** plug in the definition for
**[3:44]** the simplified loss from above,
**[3:46]** then it looks like this,
**[3:48]** 1 over m times the sum of this term above.
**[3:52]** If you bring the negative signs and move them outside,
**[3:57]** then you end up with this expression over here,
**[4:00]** and this is the cost function.
**[4:02]** The cost function that pretty much everyone
**[4:05]** uses to train logistic regression.
**[4:08]** You might be wondering,
**[4:10]** why do we choose this particular function when
**[4:13]** there could be tons of
**[4:15]** other costs functions we could have chosen?
**[4:17]** Although we won't have time to go into
**[4:19]** great detail on this in this class,
**[4:22]** I'd just like to mention that
**[4:24]** this particular cost function is derived from
**[4:27]** statistics using a statistical principle
**[4:30]** called maximum likelihood estimation,
**[4:33]** which is an idea from statistics on how to
**[4:36]** efficiently find parameters for different models.
**[4:40]** This cost function has
**[4:43]** the nice property that it is convex.
**[4:46]** But don't worry about learning
**[4:48]** the details of maximum likelihood.
**[4:50]** It's just a deeper rationale and
**[4:52]** justification behind this particular cost function.
**[4:57]** The upcoming optional lab will show you how
**[5:01]** the logistic cost function is implemented in code.
**[5:04]** I recommend taking a look at it,
**[5:07]** because you implement this later
**[5:09]** into practice lab at the end of the week.
**[5:13]** This upcoming optional lab also shows you how
**[5:17]** two different choices of the parameters
**[5:19]** will lead to different cost calculations.
**[5:22]** You can see in the plot that
**[5:25]** the better fitting blue decision boundary has
**[5:28]** a lower cost relative to the magenta decision boundary.
**[5:33]** So with the simplified cost function,
**[5:36]** we're now ready to jump into applying
**[5:38]** gradient descent to logistic regression.
**[5:41]** Let's go see that in the next video.
