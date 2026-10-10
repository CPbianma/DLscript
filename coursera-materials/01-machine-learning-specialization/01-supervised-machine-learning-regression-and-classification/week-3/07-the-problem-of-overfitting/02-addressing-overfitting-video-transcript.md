---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 3
section: The problem of overfitting
item_title: Addressing overfitting
duration: 8 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/HvDkF/addressing-overfitting
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Addressing overfitting — Transcript

**[0:01]** Later in this specialization,
**[0:04]** we'll talk about debugging and
**[0:05]** diagnosing things that can go
**[0:07]** wrong with learning algorithms.
**[0:09]** You'll also learn about specific tools to
**[0:11]** recognize when overfitting and
**[0:13]** underfitting may be occurring.
**[0:16]** But for now, when you think overfitting has occurred,
**[0:19]** lets talk about what you can do to address it.
**[0:21]** Let's say you fit a model
**[0:24]** and it has high variance, is overfit.
**[0:27]** Here's our overfit house price prediction model.
**[0:31]** One way to address this problem is to
**[0:34]** collect more training data, that's one option.
**[0:38]** If you're able to get more data,
**[0:40]** that is more training examples
**[0:42]** on sizes and prices of houses,
**[0:45]** then with the larger training set,
**[0:48]** the learning algorithm will learn to
**[0:50]** fit a function that is less wiggly.
**[0:53]** You can continue to fit
**[0:55]** a high order polynomial
**[0:57]** or some of the function with a lot of features,
**[0:59]** and if you have enough training examples,
**[1:02]** it will still do okay.
**[1:04]** To summarize, the number one tool you can
**[1:08]** use against overfitting is to get more training data.
**[1:11]** Now, getting more data isn't always an option.
**[1:14]** Maybe only so many houses have
**[1:16]** been sold in this location,
**[1:18]** so maybe there just isn't more data to be add.
**[1:21]** But when the data is available,
**[1:22]** this can work really well.
**[1:24]** A second option for addressing
**[1:26]** overfitting is to see if you can use fewer features.
**[1:30]** In the previous video,
**[1:33]** our models features included the size x,
**[1:36]** as well as the size squared, and this x squared,
**[1:39]** and x cubed and x^4 and so on.
**[1:43]** These were a lot of polynomial features.
**[1:47]** In that case, one way to reduce overfitting is to
**[1:51]** just not use so many of these polynomial features.
**[1:55]** But now let's look at a different example.
**[1:57]** Maybe you have a lot of different features of
**[2:00]** a house of which to try to predict its price,
**[2:02]** ranging from the size, number of bedrooms,
**[2:05]** number of floors, the age,
**[2:06]** average income of the neighborhood,
**[2:08]** and so on and so forth,
**[2:10]** total distance to the nearest coffee shop.
**[2:12]** It turns out that if you have a lot of features like
**[2:16]** these but don't have enough training data,
**[2:19]** then your learning algorithm may
**[2:21]** also overfit to your training set.
**[2:23]** Now instead of using all 100 features,
**[2:26]** if we were to pick just a subset of the most useful ones,
**[2:30]** maybe size, bedrooms,
**[2:33]** and the age of the house.
**[2:35]** If you think those are the most relevant features,
**[2:38]** then using just that smallest subset of features,
**[2:41]** you may find that your model no longer overfits as badly.
**[2:45]** Choosing the most appropriate set of features to
**[2:48]** use is sometimes also called feature selection.
**[2:52]** One way you could do so is to use
**[2:54]** your intuition to choose what you
**[2:56]** think is the best set of features,
**[2:58]** what's most relevant for predicting the price.
**[3:01]** Now, one disadvantage of feature selection
**[3:04]** is that by using only a subset of the features,
**[3:08]** the algorithm is throwing away some of
**[3:10]** the information that you have about the houses.
**[3:12]** For example, maybe all of these features,
**[3:15]** all 100 of them are actually
**[3:17]** useful for predicting the price of a house.
**[3:20]** Maybe you don't want to throw away some of
**[3:22]** the information by throwing away some of the features.
**[3:25]** Later in Course 2,
**[3:27]** you'll also see some algorithms for automatically
**[3:30]** choosing the most appropriate set of
**[3:32]** features to use for our prediction task.
**[3:35]** Now, this takes us to
**[3:36]** the third option for reducing overfitting.
**[3:39]** This technique, which we'll look at in even greater depth
**[3:42]** in the next video is called regularization.
**[3:46]** If you look at an overfit model,
**[3:50]** here's a model using polynomial features: x,
**[3:53]** x squared, x cubed, and so on.
**[3:55]** You find that the parameters are often relatively large.
**[3:59]** Now if you were to
**[4:01]** eliminate some of these features, say,
**[4:04]** if you were to eliminate the feature x4,
**[4:07]** that corresponds to setting this parameter to 0.
**[4:12]** So setting a parameter to 0
**[4:15]** is equivalent to eliminating a feature,
**[4:17]** which is what we saw on the previous slide.
**[4:20]** It turns out that regularization
**[4:22]** is a way to more gently reduce
**[4:25]** the impacts of some of the features without
**[4:28]** doing something as harsh as eliminating it outright.
**[4:31]** What regularization does is encourage
**[4:34]** the learning algorithm to shrink the values of
**[4:37]** the parameters without necessarily
**[4:39]** demanding that the parameter is set to exactly 0.
**[4:43]** It turns out that even if you fit
**[4:45]** a higher order polynomial like this,
**[4:48]** so long as you can get the algorithm to use
**[4:50]** smaller parameter values: w1,
**[4:53]** w2, w3, w4.
**[4:55]** You end up with a curve that ends up fitting
**[4:57]** the training data much better.
**[5:00]** So what regularization does,
**[5:02]** is it lets you keep all of your features,
**[5:04]** but they just prevents the features from
**[5:07]** having an overly large effect,
**[5:09]** which is what sometimes can cause overfitting.
**[5:13]** By the way, by convention,
**[5:15]** we normally just reduce the size of the wj parameters,
**[5:20]** that is w1 through wn.
**[5:23]** It doesn't make a huge difference whether you
**[5:25]** regularize the parameter b as well,
**[5:28]** you could do so if you want or not if you don't.
**[5:31]** I usually don't and it's just
**[5:33]** fine to regularize w1, w2,
**[5:35]** all the way to wn,
**[5:37]** but not really encourage b to become smaller.
**[5:41]** In practice, it should make very little difference
**[5:43]** whether you also regularize b or not.
**[5:47]** To recap, these are
**[5:49]** the three ways you saw in
**[5:51]** this video for addressing overfitting.
**[5:54]** One, collect more data.
**[5:56]** If you can get more data,
**[5:58]** this can really help reduce overfitting.
**[6:01]** Sometimes that's not possible.
**[6:03]** In which case, some of the options are, two,
**[6:07]** try selecting and using only a subset of the features.
**[6:11]** You'll learn more about feature selection in Course 2.
**[6:16]** Three would be to
**[6:19]** reduce the size of the parameters using regularization.
**[6:23]** This will be the subject of the next video as well.
**[6:26]** Just for myself, I use regularization all the time.
**[6:29]** So this is a very useful technique
**[6:31]** for training learning algorithms,
**[6:33]** including neural networks specifically,
**[6:35]** which you'll see later in this specialization as well.
**[6:38]** I hope you'll also check out
**[6:40]** the optional lab on overfitting.
**[6:43]** In the lab, you'll be able to see different examples of
**[6:47]** overfitting and adjust those examples
**[6:50]** by clicking on options in the plots.
**[6:52]** You'll also be able to add
**[6:54]** your own data points by clicking on
**[6:56]** the plot and see how that changes the curve that is fit.
**[7:00]** You can also try examples for both regression and
**[7:04]** classification and you will
**[7:07]** change the degree of the polynomial to be x,
**[7:10]** x squared, x cubed, and so on.
**[7:13]** The lab also lets you play with
**[7:15]** two different options for addressing overfitting.
**[7:18]** You can add additional training data to
**[7:21]** reduce overfitting and you can also select which
**[7:24]** features to include or to exclude
**[7:27]** as another way to try to reduce overfitting.
**[7:30]** Please take a look at a lab,
**[7:32]** which I hope will help you build your intuition about
**[7:35]** overfitting as well as some methods for addressing it.
**[7:39]** In this video, you also saw the idea of
**[7:42]** regularization at a relatively high level.
**[7:45]** I realize that all of these details on
**[7:48]** regularization may not fully make sense to you yet.
**[7:51]** But in the next video,
**[7:53]** we'll start to formulate exactly how to apply
**[7:55]** regularization and exactly what regularization means.
**[7:59]** Then we'll start to figure out how to make this work with
**[8:03]** our learning algorithms to make
**[8:05]** linear regression and logistic regression,
**[8:08]** and in the future, other algorithms
**[8:09]** as well avoid overfitting.
**[8:11]** Let's take a look at that in the next video.
