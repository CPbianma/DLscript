---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: Mismatched Training and Dev/Test Set
item_title: Training and Testing on Different Distributions
duration: 11 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/Xs9IV/training-and-testing-on-different-distributions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Training and Testing on Different Distributions — Transcript

**[0:00]** Deep learning algorithms have a huge hunger for training data.
**[0:04]** They just often work best when you can find enough
**[0:06]** label training data to put into the training set.
**[0:10]** This has resulted in many teams sometimes taking whatever data you can find and
**[0:14]** just shoving it into the training set just to get it more training data.
**[0:18]** Even if some of this data, or even maybe a lot of this data,
**[0:21]** doesn't come from the same distribution as your dev and test data.
**[0:25]** So in a deep learning era, more and more teams are now training on data
**[0:30]** that comes from a different distribution than your dev and test sets.
**[0:34]** And there's some subtleties and some best practices for
**[0:37]** dealing with when you're training and test distributions differ from each other.
**[0:41]** Let's take a look.
**[0:43]** Let's say that you're building a mobile app where users will upload
**[0:48]** pictures taken from their cell phones, and you want to recognize whether the pictures
**[0:51]** that your users upload from the mobile app is a cat or not.
**[0:56]** So you can now get two sources of data.
**[0:59]** One which is the distribution of data you really care about, this data from a mobile
**[1:03]** app like that on the right, which tends to be less professionally shot,
**[1:07]** less well framed, maybe even blurrier because it's shot by amateur users.
**[1:12]** The other source of data you can get is you can crawl the web and just download
**[1:16]** a lot of, for the sake of this example, let's say you can download a lot of very
**[1:21]** professionally framed, high resolution, professionally taken images of cats.
**[1:27]** And let's say you don't have a lot of users yet for your mobile app.
**[1:29]** So maybe you've gotten 10,000 pictures uploaded from the mobile app.
**[1:35]** But by crawling the web you can download huge numbers of cat pictures, and
**[1:40]** maybe you have 200,000 pictures of cats downloaded off the Internet.
**[1:48]** So what you really care about is that your final system does well
**[1:53]** on the mobile app distribution of images, right?
**[1:58]** Because in the end, your users will be uploading pictures like those on
**[2:01]** the right and you need your classifier to do well on that.
**[2:04]** But you now have a bit of a dilemma because you have a relatively small
**[2:08]** dataset, just 10,000 examples drawn from that distribution.
**[2:12]** And you have a much bigger dataset that's drawn from a different distribution.
**[2:16]** There's a different appearance of image than the one you actually want.
**[2:19]** So you don't want to use just those 10,000 images because it ends up
**[2:24]** giving you a relatively small training set.
**[2:28]** And using those 200,000 images seems helpful, but
**[2:31]** the dilemma is this 200,000 images isn't from exactly the distribution you want.
**[2:37]** So what can you do?
**[2:38]** Well, here's one option.
**[2:43]** One thing you can do is put both of these data sets together so you now have
**[2:47]** 210,000 images.
**[2:50]** And you can then take the 210,000 images and randomly shuffle them
**[2:56]** into a train, dev, and test set.
**[3:03]** And let's say for the sake of argument that you've decided that your dev and
**[3:07]** test sets will be 2,500 examples each.
**[3:11]** So your training set will be 205,000 examples.
**[3:17]** Now so setting up your data this way has some advantages but also disadvantages.
**[3:23]** The advantage is that now you're training, dev and test sets will all come
**[3:26]** from the same distribution, so that makes it easier to manage.
**[3:30]** But the disadvantage, and this is a huge disadvantage,
**[3:33]** is that if you look at your dev set, of these 2,500 examples,
**[3:38]** a lot of it will come from the web page distribution of images, rather than
**[3:43]** what you actually care about, which is the mobile app distribution of images.
**[3:48]** So it turns out that of your total amount of data, 200,000, so
**[3:53]** I'll just abbreviate that 200k, out of 210,000,
**[3:57]** we'll write that as 210k, that comes from web pages.
**[4:01]** So all of these 2,500 examples on expectation,
**[4:06]** I think 2,381 of them will come from web pages.
**[4:13]** This is on expectation, the exact number will vary around depending on
**[4:17]** how the random shuttle operation went.
**[4:20]** But on average, only 119 will come from mobile app uploads.
**[4:27]** So remember that setting up your dev set is telling your team where to aim
**[4:32]** the target.
**[4:33]** And the way you're aiming your target,
**[4:35]** you're saying spend most of the time optimizing for
**[4:38]** the web page distribution of images, which is really not what you want.
**[4:42]** So I would recommend against option one,
**[4:45]** because this is setting up the dev set to tell your team to optimize for
**[4:50]** a different distribution of data than what you actually care about.
**[4:54]** So instead of doing this, I would recommend that you
**[4:56]** instead take another option, which is the following.
**[5:01]** The training set, let's say it's still 205,000 images, I would have the training set
**[5:08]** have all 200,000 images from the web.
**[5:15]** And then you can, if you want, add in 5,000 images from the mobile app.
**[5:21]** And then for your dev and test sets,
**[5:24]** I guess my data sets size aren't drawn to scale.
**[5:27]** Your dev and test sets would be all mobile app images.
**[5:38]** So the training set will include 200,000 images from the web and
**[5:44]** 5,000 from the mobile app.
**[5:46]** The dev set will be 2,500 images from the mobile app, and
**[5:51]** the test set will be 2,500 images also from the mobile app.
**[5:58]** The advantage of this way of splitting up your data into train, dev, and test,
**[6:03]** is that you're now aiming the target where you want it to be.
**[6:07]** You're telling your team, my dev set has data uploaded from the mobile app and
**[6:12]** that's the distribution of images you really care about, so
**[6:15]** let's try to build a machine learning system that does really well on
**[6:19]** the mobile app distribution of images.
**[6:21]** The disadvantage, of course, is that now your training
**[6:25]** distribution is different from your dev and test set distributions.
**[6:30]** But it turns out that this split of your data into train, dev and
**[6:34]** test will get you better performance over the long term.
**[6:38]** And we'll discuss later some specific techniques for dealing with your
**[6:42]** training sets coming from different distribution than your dev and test sets.
**[6:47]** Let's look at another example.
**[6:49]** Let's say you're building a brand new product, a speech activated
**[6:53]** rearview mirror for a car.
**[6:58]** So this is a real product in China.
**[7:01]** It's making its way into other countries but you can build a rearview mirror to
**[7:05]** replace this little thing there, so that you can now talk to the rearview mirror
**[7:10]** and basically say, dear rearview mirror, please help me find
**[7:13]** navigational directions to the nearest gas station and it'll deal with it.
**[7:19]** So this is actually a real product, and let's say you're trying to build this for
**[7:22]** your own country.
**[7:27]** So how can you get data to train up a speech recognition system for
**[7:31]** this product?
**[7:32]** Well, maybe you've worked on speech recognition for a long time so
**[7:36]** you have a lot of data from other speech recognition applications,
**[7:39]** just not from a speech activated rearview mirror.
**[7:43]** Here's how you could split up your training and your dev and test sets.
**[7:47]** So for your training, you can take all the speech data you have that
**[7:50]** you've accumulated from working on other speech problems, such as
**[7:54]** data you purchased over the years from various speech recognition data vendors.
**[7:59]** And today you can actually buy data from vendors of x, y pairs,
**[8:03]** where x is an audio clip and y is a transcript.
**[8:06]** Or maybe you've worked on smart speakers, smart voice activated speakers, so
**[8:10]** you have some data from that.
**[8:12]** Maybe you've worked on voice activated keyboards and so on.
**[8:17]** And for the sake of argument, maybe you have 500,000
**[8:21]** utterences from all of these sources.
**[8:25]** And for your dev and test set, maybe you have a much smaller data set that
**[8:30]** actually came from a speech activated rearview mirror.
**[8:34]** Because users are asking for navigational
**[8:38]** queries or trying to find directions to various places.
**[8:41]** This data set will maybe have a lot more street addresses, right?
**[8:46]** Please help me navigate to this street address, or
**[8:49]** please help me navigate to this gas station.
**[8:51]** So this distribution of data will be very different than these on the left.
**[8:58]** But this is really the data you care about, because this is what you need your
**[9:01]** product to do well on, so this is what you set your dev and test set to be.
**[9:08]** So what you do in this example is set your training set to be
**[9:12]** the 500,000 utterances on the left, and
**[9:16]** then your dev and test sets which I'll abbreviate D and T,
**[9:21]** these could be maybe 10,000 utterances each.
**[9:26]** That's drawn from actual the speech activated rearview mirror.
**[9:31]** Or alternatively, if you think you don't need to put all 20,000 examples from
**[9:35]** your speech activated rearview mirror into the dev and
**[9:38]** test sets, maybe you can take half of that and put that in the training set.
**[9:43]** So then the training set could be 510,000 utterances,
**[9:49]** including all 500 from there and 10,000 from the rearview mirror.
**[9:58]** And then the dev and test sets could maybe be 5,000 utterances each.
**[10:04]** So of the 20,000 utterances, maybe 10k goes into the training set and
**[10:09]** 5k into the dev set and 5,000 into the test set.
**[10:14]** So this would be another reasonable way of splitting your data into train,
**[10:18]** dev, and test.
**[10:20]** And this gives you a much bigger training set, over 500,000 utterances, than if you
**[10:26]** were to only use speech activated rearview mirror data for your training set.
**[10:31]** So in this video, you've seen a couple examples of when allowing your training
**[10:35]** set data to come from a different distribution than your dev and
**[10:38]** test set allows you to have much more training data.
**[10:41]** And in these examples, it will cause your learning algorithm to perform better.
**[10:45]** Now one question you might ask is, should you always use all the data you have?
**[10:50]** The answer is subtle, it is not always yes.
**[10:52]** Let's look at a counter-example in the next video.
