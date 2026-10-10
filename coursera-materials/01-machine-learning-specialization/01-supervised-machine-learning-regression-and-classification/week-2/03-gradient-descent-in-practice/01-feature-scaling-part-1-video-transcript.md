---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 2
section: Gradient descent in practice
item_title: Feature scaling part 1
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/KMDV3/feature-scaling-part-1
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Feature scaling part 1 — Transcript

**[0:02]** So welcome back.
**[0:04]** Let's take a look at some techniques that make great inter sense work much better.
**[0:08]** In this video you see a technique called feature scaling that will enable
**[0:13]** gradient descent to run much faster.
**[0:15]** Let's start by taking a look at the relationship between the size of
**[0:20]** a feature that is how big are the numbers for that feature and
**[0:23]** the size of its associated parameter.
**[0:26]** As a concrete example, let's predict the price of a house using two
**[0:31]** features x1 the size of the house and x2 the number of bedrooms.
**[0:37]** Let's say that x1 typically ranges from 300 to 2000 square feet.
**[0:42]** And x2 in the data set ranges from 0 to 5 bedrooms.
**[0:48]** So for this example, x1 takes on a relatively large range of values and
**[0:53]** x2 takes on a relatively small range of values.
**[0:58]** Now let's take an example of a house that has a size of 2000 square
**[1:03]** feet has five bedrooms and a price of 500k or $500,000.
**[1:08]** For this one training example, what do you think
**[1:13]** are reasonable values for the size of parameters w1 and w2?
**[1:20]** Well, let's look at one possible set of parameters.
**[1:23]** Say w1 is 50 and w2 is 0.1 and
**[1:27]** b is 50 for the purposes of discussion.
**[1:34]** So in this case the estimated price in thousands
**[1:39]** of dollars is 100,000k here plus 0.5 k plus 50 k.
**[1:46]** Which is slightly over 100 million dollars.
**[1:50]** So that's clearly very far from the actual price of $500,000.
**[1:57]** And so this is not a very good set of parameter choices for w1 and w2.
**[2:03]** Now let's take a look at another possibility.
**[2:07]** Say w1 and w2 were the other way around.
**[2:11]** W1 is 0.1 and w2 is 50 and b is still also 50.
**[2:15]** In this choice of w1 and w2, w1 is relatively small and
**[2:21]** w2 is relatively large, 50 is much bigger than 0.1.
**[2:28]** So here the predicted price is 0.1 times
**[2:33]** 2000 plus 50 times five plus 50.
**[2:38]** The first term becomes 200k, the second term becomes 250k, and the plus 50.
**[2:45]** So this version of the model predicts a price of $500,000 which is a much more
**[2:50]** reasonable estimate and happens to be the same price as the true price of the house.
**[2:56]** So hopefully you might notice that when a possible range of values of a feature
**[3:01]** is large, like the size and square feet which goes all the way up to 2000.
**[3:06]** It's more likely that a good model will learn to choose a relatively small
**[3:11]** parameter value, like 0.1.
**[3:14]** Likewise, when the possible values of the feature are small,
**[3:18]** like the number of bedrooms, then a reasonable value for
**[3:22]** its parameters will be relatively large like 50.
**[3:26]** So how does this relate to grading descent?
**[3:30]** Well, let's take a look at the scatter plot of the features
**[3:35]** where the size square feet is the horizontal axis x1 and
**[3:39]** the number of bedrooms exudes is on the vertical axis.
**[3:44]** If you plot the training data, you notice that the horizontal axis is on a much
**[3:49]** larger scale or much larger range of values compared to the vertical axis.
**[3:55]** Next let's look at how the cost function might look in a contour plot.
**[4:00]** You might see a contour plot where the horizontal axis has a much narrower range,
**[4:06]** say between zero and one, whereas the vertical axis takes on much
**[4:11]** larger values, say between 10 and 100.
**[4:15]** So the contours form ovals or ellipses and
**[4:19]** they're short on one side and longer on the other.
**[4:23]** And this is because a very small change to w1 can have a very large impact
**[4:29]** on the estimated price and that's a very large impact on the cost J.
**[4:34]** Because w1 tends to be multiplied by a very large number,
**[4:38]** the size and square feet.
**[4:41]** In contrast,
**[4:42]** it takes a much larger change in w2 in order to change the predictions much.
**[4:47]** And thus small changes to w2, don't change the cost function nearly as much.
**[4:54]** So where does this leave us?
**[4:56]** This is what might end up happening if you were to run great in dissent,
**[5:01]** if you were to use your training data as is.
**[5:04]** Because the contours are so tall and
**[5:07]** skinny gradient descent may end up bouncing back and forth for
**[5:11]** a long time before it can finally find its way to the global minimum.
**[5:17]** In situations like this, a useful thing to do is to scale the features.
**[5:22]** This means performing some transformation of your training data so
**[5:28]** that x1 say might now range from 0 to 1 and x2 might also range from 0 to 1.
**[5:34]** So the data points now look more like this and you might notice that the scale of
**[5:39]** the plot on the bottom is now quite different than the one on top.
**[5:45]** The key point is that the re scale x1 and
**[5:48]** x2 are both now taking comparable ranges of values to each other.
**[5:54]** And if you run gradient descent on a cost function to find on this,
**[5:58]** re scaled x1 and x2 using this transformed data, then the contours
**[6:03]** will look more like this more like circles and less tall and skinny.
**[6:08]** And gradient descent can find a much more direct path to the global minimum.
**[6:14]** So to recap, when you have different features that take on very different
**[6:18]** ranges of values, it can cause gradient descent to run slowly but
**[6:22]** re scaling the different features so they all take on comparable range of values.
**[6:27]** because speed, upgrade and dissent significantly.
**[6:30]** How do you actually do this?
**[6:31]** Let's take a look at that in the next video.
