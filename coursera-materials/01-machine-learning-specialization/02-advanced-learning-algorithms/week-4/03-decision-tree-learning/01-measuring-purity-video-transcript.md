---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 4
section: Decision tree learning
item_title: Measuring purity
duration: 8 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/6jL2z/measuring-purity
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Measuring purity — Transcript

**[0:01]** In this video, we'll look at the way of measuring
**[0:04]** the purity of a set of examples.
**[0:07]** If the examples are all cats
**[0:09]** of a single class then that's very pure,
**[0:11]** if it's all not cats that's also very pure,
**[0:15]** but if it's somewhere in between how do you
**[0:17]** quantify how pure is the set of examples?
**[0:20]** Let's take a look at the definition of entropy,
**[0:23]** which is a measure of the impurity of a set of data.
**[0:27]** Given a set of six examples like this,
**[0:30]** we have three cats and three dogs,
**[0:32]** let's define p_1 to be
**[0:35]** the fraction of examples that are cats,
**[0:38]** that is, the fraction of examples with label one,
**[0:41]** that's what the subscript one indicates.
**[0:44]** p_1 in this example is equal to 3/6.
**[0:48]** We're going to measure the impurity of a set of examples
**[0:54]** using a function called
**[0:57]** the entropy which looks like this.
**[1:01]** The entropy function is conventionally
**[1:03]** denoted as capital H of
**[1:08]** this number p_1 and
**[1:11]** the function looks like this curve
**[1:14]** over here where the horizontal axis is p_1,
**[1:16]** the fraction of cats in the sample,
**[1:20]** and the vertical axis is the value of the entropy.
**[1:23]** In this example where p_1 is 3/6 or 0.5,
**[1:28]** the value of the entropy of p_1 would be equal to one.
**[1:33]** You notice that this curve is
**[1:36]** highest when your set of examples is 50-50,
**[1:40]** so it's most impure as an impurity of one or
**[1:44]** with an entropy of one
**[1:45]** when your set of examples is 50-50,
**[1:48]** whereas in contrast if your set of examples was
**[1:52]** either all cats or not cats then the entropy is zero.
**[1:57]** Let's just go through a few more examples to gain
**[2:00]** further intuition about entropy and how it works.
**[2:03]** Here's a different set of examples
**[2:06]** with five cats and one dog,
**[2:09]** so p_1 the fraction of positive examples,
**[2:12]** a fraction of examples labeled one is 5/6
**[2:16]** and so p_1 is about 0.83.
**[2:22]** If you read off that value at about 0.83 we find
**[2:27]** that the entropy of p_1 is about 0.65.
**[2:31]** And here I'm writing it only to two significant digits.
**[2:34]** Here's one more example.
**[2:36]** This sample of six images has
**[2:39]** all cats so p_1 is six out of
**[2:42]** six because all six are cats and the entropy of
**[2:45]** p_1 is this point over here which is zero.
**[2:50]** We see that as you go from 3/6 to six out of six cats,
**[2:54]** the impurity decreases from
**[2:57]** one to zero or in other words,
**[2:59]** the purity increases as you go
**[3:02]** from a 50-50 mix of cats and dogs to all cats.
**[3:06]** Let's look at a few more examples.
**[3:09]** Here's another sample with two cats and four dogs,
**[3:13]** so p_1 here is 2/6 which is 1/3,
**[3:17]** and if you read off the entropy at
**[3:22]** 0.33 it turns out to be about 0.92.
**[3:27]** This is actually quite impure and in particular
**[3:32]** this set is more
**[3:35]** impure than this set because it's closer to a 50-50 mix,
**[3:40]** which is why the impurity here is
**[3:42]** 0.92 as opposed to 0.65.
**[3:46]** Finally, one last example,
**[3:49]** if we have a set of all six dogs then
**[3:52]** p_1 is equal to 0 and the entropy of p_1 is
**[3:56]** just this number down here which is equal to 0 so there's
**[4:01]** zero impurity or this would be
**[4:03]** a completely pure set of all not cats or all dogs.
**[4:07]** Now, let's look at the actual equation for
**[4:10]** the entropy function H(p_1).
**[4:14]** Recall that p_1 is the fraction
**[4:17]** of examples that are equal to
**[4:19]** cats so if you have a sample that
**[4:23]** is 2/3 cats then that sample must have 1/3 not cats.
**[4:28]** Let me define p_0 to be equal to the fraction of examples
**[4:33]** that are not cats to be just equal to 1 minus p_1.
**[4:37]** The entropy function is then defined
**[4:40]** as negative p_1log_2 (p_1),
**[4:45]** and by convention when
**[4:46]** computing entropy we take
**[4:49]** logs to base two rather than to base e,
**[4:53]** and then minus p_0log_2(p_0).
**[5:00]** Alternatively, this is also
**[5:02]** equal to negative p_1log_2(p_1)
**[5:06]** minus 1 minus p_1 log_2(1 minus p_1).
**[5:14]** If you were to plot
**[5:16]** this function in a computer you will find
**[5:18]** that it will be exactly this function on the left.
**[5:21]** We take log_2 just
**[5:24]** to make the peak of this curve equal to one,
**[5:27]** if we were to take log_e or
**[5:28]** the base of natural logarithms,
**[5:31]** then that just vertically scales this function,
**[5:35]** and it will still work but
**[5:37]** the numbers become a bit hard to interpret because
**[5:39]** the peak of the function isn't
**[5:41]** a nice round number like one anymore.
**[5:44]** One note on computing this function,
**[5:49]** if p_1 or p_0 is equal to 0
**[5:53]** then an expression like this will look like 0log(0),
**[6:00]** and log(0) is technically undefined,
**[6:03]** it's actually negative infinity.
**[6:05]** But by convention for the purposes of computing entropy,
**[6:10]** we'll take 0log(0) to be equal
**[6:12]** to 0 and that will correctly
**[6:14]** compute the entropy as zero
**[6:16]** or as one to be equal to zero.
**[6:19]** If you're thinking that
**[6:21]** this definition of entropy looks a little bit
**[6:24]** like the definition of
**[6:25]** the logistic loss that
**[6:27]** we learned about in the last course,
**[6:28]** there is actually a mathematical rationale
**[6:31]** for why these two formulas look so similar.
**[6:34]** But you don't have to worry about it and we
**[6:36]** won't get into it in this class.
**[6:38]** But applying this formula for entropy should
**[6:41]** work just fine when you're building a decision tree.
**[6:44]** To summarize, the entropy function is
**[6:46]** a measure of the impurity of a set of data.
**[6:50]** It starts from zero, goes up to one,
**[6:52]** and then comes back down to zero as a function of
**[6:55]** the fraction of positive examples in your sample.
**[6:58]** There are other functions that look like this,
**[7:00]** they go from zero up to one and then back down.
**[7:03]** For example, if you look in open source packages you
**[7:06]** may also hear about something called the Gini criteria,
**[7:08]** which is another function that looks a
**[7:10]** lot like the entropy function,
**[7:12]** and that will work well as
**[7:14]** well for building decision trees.
**[7:15]** But for the sake of simplicity,
**[7:17]** in these videos I'm going to focus on using
**[7:20]** the entropy criteria which
**[7:22]** will usually work just fine for most applications.
**[7:26]** Now that we have this definition of entropy,
**[7:29]** in the next video let's take
**[7:30]** a look at how you can actually use it to make
**[7:33]** decisions as to what feature to split
**[7:35]** on in the nodes of a decision tree.
