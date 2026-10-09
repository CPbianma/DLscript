---
type: video-transcript
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 2
section: Principal Component Analysis
item_title: Reducing the number of features (optional)
duration: 12 min
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/lecture/73zWO/reducing-the-number-of-features-optional
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Reducing the number of features (optional) — Transcript

**[0:00]** I hope you enjoyed the videos on how you
**[0:03]** can build your own recommender system.
**[0:06]** Before we wrap up this week in this and
**[0:08]** a few other optional videos I'd like to share with
**[0:11]** you an unsupervised learning algorithm
**[0:14]** called principal components analysis.
**[0:17]** This is an algorithm that is
**[0:18]** commonly used for visualization.
**[0:21]** Specifically, if you
**[0:22]** have a dataset with a lot of features,
**[0:24]** say 10 features or
**[0:26]** 50 features or even thousands of features,
**[0:28]** you can't plot 1,000 dimensional data.
**[0:32]** PCA, or principal components analysis
**[0:35]** is an algorithm that lets
**[0:36]** you take data with a lot of features, 50, 1,000,
**[0:40]** even more, and reduce
**[0:42]** the number of features to two features,
**[0:44]** maybe three features, so that you
**[0:46]** can plot it and visualize it.
**[0:48]** Is commonly used by
**[0:50]** data scientists to visualize the data,
**[0:52]** to figure out what might be going on.
**[0:54]** Let's take a look at how PCA,
**[0:56]** principal components analysis works.
**[0:59]** To describe PCA, I'm going to use as a running example,
**[1:03]** if you have data from a collection of passenger cars,
**[1:08]** and passenger cars can have a lot of features.
**[1:11]** You may know the length of
**[1:14]** the car or the width of the car,
**[1:17]** maybe the diameter of the wheel,
**[1:20]** or maybe the height of the car,
**[1:23]** and many other features of cars.
**[1:27]** If you want to reduce
**[1:29]** the number of features so you can visualize it,
**[1:32]** how can you use PCA to do so?
**[1:35]** For the first example,
**[1:38]** let's say you're given a dataset with two features.
**[1:41]** The feature x_1 is the length of the car,
**[1:45]** like so, and the second feature x_2,
**[1:50]** is the width of the car,
**[1:52]** which is measured like so.
**[1:55]** It turns out that in most countries,
**[1:58]** because of constraints about the width
**[2:00]** of the road the cars drive on,
**[2:03]** width of the car which has got to fit
**[2:05]** within the width of the road of a single lane,
**[2:08]** tends not to vary that much.
**[2:10]** For example, in the United States,
**[2:13]** most cars are,
**[2:14]** let's call it about 1.8 meters wide,
**[2:18]** that's just under six feet.
**[2:20]** If you were to have a collection of
**[2:23]** cars and the dataset of
**[2:25]** the length and width of the cars,
**[2:28]** you will find that the dataset might look like this,
**[2:32]** where x_1 varies quite a bit because some cars are really
**[2:36]** long and x_2 varies relatively little.
**[2:41]** If you want to reduce the number of features, well,
**[2:45]** one thing you could do is let us take x_1 because
**[2:48]** x_2 varies relatively little from car to car.
**[2:51]** It turns out that PCA is an algorithm
**[2:54]** that when applied to this data set will
**[2:57]** more or less automatically decide to just take x_1,
**[3:02]** but it can do much more than that.
**[3:04]** Let's look at a second example
**[3:07]** where here x_1 is again the length of the car,
**[3:11]** and let's say that in this dataset,
**[3:14]** x_2 is the diameter of the wheel.
**[3:18]** The diameter of the wheel does vary a little bit.
**[3:22]** If you were to plot the data,
**[3:24]** it might look like this.
**[3:25]** But again, if you want to
**[3:29]** simplify this dataset to just one feature,
**[3:32]** you might decide, let's just take x_1 and
**[3:35]** forget x_2 and PCA when applied to this dataset.
**[3:38]** Well, again, more or less,
**[3:40]** cause you to just check the feature x_1.
**[3:44]** In both the examples we saw,
**[3:46]** only one of the two features seemed
**[3:49]** to have a meaningful degree of variation.
**[3:52]** Here's a more complex example.
**[3:55]** Say the feature x_1 is the length of the car,
**[3:58]** so that varies quite a bit,
**[4:00]** and the feature x_2 here is the height of the car,
**[4:04]** which also varies quite a bit.
**[4:06]** Some cars are much taller than other cars.
**[4:08]** If you were to plot the data,
**[4:10]** you might get a dataset that looks like this,
**[4:13]** where some cars are bigger and
**[4:15]** they tend to be longer and taller,
**[4:17]** and some cars are a little bit smaller.
**[4:20]** They tend to be not as long and not as tall.
**[4:23]** If you wanted to reduce the number of
**[4:26]** features, what should you pick?
**[4:29]** You don't want to pick just x_1, the length,
**[4:31]** and ignore x_2 the height
**[4:33]** and you also don't want to pick just x_2,
**[4:35]** the height, and ignore x_1, the length.
**[4:38]** It seems as if both x_1 and x_2 have useful information.
**[4:42]** In this graph,
**[4:44]** x_1 and x_2 are the two axes of this plot.
**[4:49]** Instead of being limited to taking
**[4:52]** either the x_1 axis or the x_2 axis,
**[4:55]** what if we had a third axis.
**[4:58]** I'm going to call this new axis the z-axis.
**[5:02]** To be clear, this is not sticking out of this diagram.
**[5:05]** This is a combination of x_1 and x_2.
**[5:08]** This is not a z-axis
**[5:10]** that's sticking out in the third dimension.
**[5:13]** This z-axis lies flat within this plot.
**[5:17]** But why do we have the z-axis which
**[5:20]** corresponds to something about the size of the car?
**[5:25]** Given a car like this one over here, its coordinate,
**[5:29]** meaning the value on the x-axis tells
**[5:31]** us the length of the car and the coordinate is just,
**[5:34]** what is this distance?
**[5:36]** Similarly its coordinate, meaning,
**[5:39]** what is this distance on
**[5:41]** the x_2 axis tells us what is the height of the car.
**[5:46]** If we're now going to use the z-axis instead
**[5:48]** as one feature to capture what
**[5:52]** we know about this car then is coordinate on
**[5:55]** the z-axis, meaning this distance.
**[5:58]** That tells us roughly what is the size of the car.
**[6:03]** We'll formalize this in the next few videos.
**[6:07]** But the idea of PCA is to find one or more new axes,
**[6:13]** such as z so that when you
**[6:16]** measure your datas coordinates on the new axis,
**[6:20]** you end up still with
**[6:21]** very useful information about the car.
**[6:25]** But maybe now, instead of needing
**[6:28]** two numbers corresponding to
**[6:30]** the coordinates on X_1 and X_2 axes,
**[6:33]** the length and height.
**[6:34]** You now need a few numbers, in this case,
**[6:37]** only one number instead of two,
**[6:39]** to capture roughly the size of the car.
**[6:42]** In the example, we've used so far,
**[6:45]** we were trying to reduce the data from two numbers,
**[6:49]** X_1 and X_2 down to one number,
**[6:52]** the coordinate on the z-axis.
**[6:55]** In practice, PCA is usually used to
**[6:58]** reduce a very large number of features,
**[7:01]** say 10, 20,
**[7:02]** 50, even thousands of features,
**[7:05]** down to maybe two or three features so that you can
**[7:10]** visualize the data in a
**[7:12]** two-dimensional or in a three-dimensional plot.
**[7:16]** But for this video,
**[7:18]** because I could only draw on a two-dimensional screen.
**[7:22]** I'm going to use mainly
**[7:24]** two or three-dimensional data sets
**[7:27]** as my examples.
**[7:28]** Let's look at one more example.
**[7:31]** In this visualization, we have a three-dimensional data
**[7:35]** set and notice that I can rotate the data set here,
**[7:39]** so you can see it in 3D.
**[7:40]** But notice if I rotate the data set like this,
**[7:45]** well, most of this data,
**[7:47]** even though it is in 3D,
**[7:48]** it actually lives on a very thin surface.
**[7:53]** It's almost as if all the data lies
**[7:55]** on a two-dimensional pancake,
**[7:57]** even though the pancake
**[7:59]** lives in this three-dimensional space.
**[8:01]** A PCA, what you can do is,
**[8:04]** instead of having three features, x_1,
**[8:08]** x_2, x_3,
**[8:10]** reduce it to two numbers,
**[8:12]** which we're going to call Z_1 and Z_2.
**[8:16]** When you do that,
**[8:18]** you can then visualize the data on this Z_1,
**[8:22]** Z_2 axis and this becomes
**[8:25]** a convenient way to visualize this data if you had to,
**[8:29]** say print on a piece of paper.
**[8:31]** I couldn't dynamically rotate
**[8:33]** it like you'll seeing me do on the screen.
**[8:35]** Here's one more example.
**[8:37]** If you have data about
**[8:39]** the development status of many different countries,
**[8:42]** you might have for example
**[8:44]** data about different countries,
**[8:47]** GDP, and that's feature x_1.
**[8:50]** In addition, Let's say we also have
**[8:52]** the per capita GDP and also
**[8:56]** a measure of their Human Development Index.
**[8:59]** The Human Development Index was developed
**[9:03]** to measure the overall progress of how well
**[9:07]** people in a country might be
**[9:09]** doing based on things like the lifespan and
**[9:12]** education and so on
**[9:13]** or you might separately have a feature
**[9:16]** corresponding to the life expectancy
**[9:20]** in different countries and so on and so forth.
**[9:23]** If for each country you have 50 features,
**[9:28]** how can you visualize this data because you can't plot
**[9:31]** 50 dimensional data on
**[9:33]** a two-dimensional computer monitor.
**[9:35]** What PCLS will do is take
**[9:38]** these 50 features, X_1,X_2,X_3,X_4,
**[9:42]** and so on and compress it
**[9:45]** down to two features which I'm going to call
**[9:48]** Z_1 and Z_2 and you can then
**[9:51]** plot these different countries values of z_1 and z_2.
**[9:56]** You might find for example that Z_1 loosely corresponds
**[10:01]** to how big is the country and what is this total GDP?
**[10:05]** Because larger countries tend to have a higher GDP,
**[10:09]** because large countries have many people,
**[10:11]** tend to have a larger economy
**[10:14]** and perhaps you find that Z_2
**[10:18]** corresponds roughly to the per person GDP
**[10:22]** or the amount of economic activity per person.
**[10:26]** For example, the United States,
**[10:29]** which is a relatively large country and has
**[10:32]** relatively high per person economic activity
**[10:36]** may be somewhere up here to the up and right of
**[10:39]** this plot and a country like Singapore,
**[10:43]** where I live many years as well,
**[10:44]** is a smaller country but it has
**[10:47]** relatively high per person economic activity.
**[10:50]** Take on a lower value on the z_1 axis,
**[10:54]** but still a relatively high value on the z_2 axis.
**[10:58]** Whereas a country like this would be maybe
**[11:01]** a smaller country with
**[11:02]** lower per person economic activity.
**[11:04]** Whereas the country like this may be a large country with
**[11:08]** lower per person economic activity and a figure like
**[11:11]** this lets you take
**[11:13]** a large number of features, 50 features.
**[11:15]** Sometimes we also say that's 50 dimensional data.
**[11:18]** It just means we have 50 features and
**[11:21]** reduce that to two features or sometimes we say
**[11:24]** is two-dimensional data because you can then plot it on
**[11:27]** this two-dimensional plot like you're seeing here.
**[11:30]** Whenever I get a new data set,
**[11:32]** one of the things I'll often want to do is to visualize
**[11:35]** the data since that helps me
**[11:37]** understand what the data looks like,
**[11:39]** what do the countries look like,
**[11:40]** or what do the cars seem like in this data set
**[11:43]** or whatever data you may be examining.
**[11:47]** You find also that visualizing the data set will
**[11:50]** sometimes help you figure out
**[11:51]** something funny's going on in this datas.
**[11:54]** Something unexpected is happening.
**[11:56]** PCA is a powerful algorithm
**[11:58]** for taking data with a lot of features,
**[12:01]** with a lot of dimensions or high-dimensional data,
**[12:03]** and reducing it to two or three features to
**[12:07]** two or three dimensional data so you can plot
**[12:10]** it and visualize it and better
**[12:12]** understand what's in your data.
**[12:14]** That's what the PCA algorithm can do for you.
**[12:17]** In the next video,
**[12:18]** let's start to take a look at how
**[12:20]** exactly the PCA algorithm works.
