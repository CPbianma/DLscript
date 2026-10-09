---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 2
section: Gradient descent in practice
item_title: Feature engineering
duration: 3 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/dgZYR/feature-engineering
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Feature engineering — Transcript

**[0:00]** The choice of features can have
**[0:03]** a huge impact on your learning algorithm's performance.
**[0:06]** In fact, for many practical applications,
**[0:08]** choosing or entering the right features is
**[0:11]** a critical step to making the algorithm work well.
**[0:14]** In this video, let's take a look at how you can choose or
**[0:17]** engineer the most appropriate features
**[0:19]** for your learning algorithm.
**[0:21]** Let's take a look at feature engineering by revisiting
**[0:24]** the example of predicting the price of a house.
**[0:27]** Say you have two features for each house.
**[0:31]** X_1 is the width of the lot size
**[0:33]** of the plots of land that the house is built on.
**[0:37]** This in real state is also
**[0:39]** called the frontage of the lot,
**[0:42]** and the second feature,
**[0:44]** x_2, is the depth of the lot size of,
**[0:47]** lets assume the rectangular plot
**[0:49]** of land that the house was built on.
**[0:51]** Given these two features, x_1 and x_2,
**[0:54]** you might build a model like this where f of x
**[0:57]** is w_1x_1 plus w_2x_2 plus b,
**[1:02]** where x_1 is the frontage or width,
**[1:04]** and x_2 is the depth.
**[1:07]** This model might work okay.
**[1:10]** But here's another option for how
**[1:12]** you might choose a different way to
**[1:13]** use these features in the model
**[1:15]** that could be even more effective.
**[1:17]** You might notice that the area of
**[1:18]** the land can be calculated
**[1:20]** as the frontage or width times the depth.
**[1:24]** You may have an intuition that
**[1:27]** the area of the land is more predictive of the price,
**[1:30]** than the frontage and depth as separate features.
**[1:33]** You might define a new feature,
**[1:36]** x_3, as x_1 times x_2.
**[1:39]** This new feature x_3 is
**[1:41]** equal to the area of the plot of land.
**[1:44]** With this feature, you can then have a model f_w,
**[1:48]** b of x equals w_1x_1 plus w_2x_2
**[1:53]** plus w_3x_3 plus b
**[1:56]** so that the model can now choose parameters w_1,
**[1:59]** w_2, and w_3,
**[2:01]** depending on whether the data shows that
**[2:03]** the frontage or the depth or the area
**[2:06]** x_3 of the lot turns out to be
**[2:08]** the most important thing for
**[2:10]** predicting the price of the house.
**[2:12]** What we just did, creating a new feature
**[2:15]** is an example of what's called feature engineering,
**[2:19]** in which you might use your knowledge or
**[2:21]** intuition about the problem to design new features
**[2:24]** usually by transforming or
**[2:26]** combining the original features of
**[2:28]** the problem in order to make it
**[2:29]** easier for the learning algorithm
**[2:31]** to make accurate predictions.
**[2:33]** Depending on what insights you
**[2:35]** may have into the application,
**[2:37]** rather than just taking
**[2:38]** the features that you happen to have
**[2:40]** started off with sometimes by defining new features,
**[2:43]** you might be able to get a much better model.
**[2:47]** That's feature engineering.
**[2:50]** It turns out that this one flavor of feature engineering,
**[2:54]** that allow you to fit not just straight lines,
**[2:56]** but curves, non-linear functions to your data.
**[3:00]** Let's take a look in the next video
**[3:02]** at how you can do that.
