---
type: video-transcript
specialization: Machine Learning Specialization
course: Supervised Machine Learning: Regression and Classification
week: 3
section: Classification with logistic regression
item_title: Motivations
duration: 10 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/aoMt6/motivations
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Motivations — Transcript

**[0:00]** Welcome to the third week of this course.
**[0:03]** By the end of this week,
**[0:04]** you have completed the first course of this specialization.
**[0:07]** So let's jump in.
**[0:09]** Last week you learned about linear regression, which predicts a number.
**[0:14]** This week, you learn about classification where your output variable y can
**[0:19]** take on only one of a small handful of possible values instead of any number in
**[0:24]** an infinite range of numbers.
**[0:26]** It turns out that linear regression is not a good algorithm for
**[0:30]** classification problems.
**[0:32]** Let's take a look at why and
**[0:33]** this will lead us into a different algorithm called logistic regression.
**[0:39]** Which is one of the most popular and most widely used learning algorithms today.
**[0:43]** Here are some examples of classification problems recall
**[0:47]** the example of trying to figure out whether an email is spam.
**[0:51]** So the answer you want to output is going to be either a no or a yes.
**[0:57]** Another example would be figuring out if an online financial
**[1:01]** transaction is fraudulent.
**[1:04]** Fighting online financial fraud is something I once worked on and
**[1:07]** it was strangely exhilarating.
**[1:09]** Because I knew there were forces out there trying to steal money and
**[1:14]** my team's job was to stop them.
**[1:16]** So the problem is given a financial transaction.
**[1:20]** Can your learning algorithm figure out is this transaction fraudulent,
**[1:26]** such as what this credit card stolen?
**[1:28]** Another example we've touched on before was trying
**[1:33]** to classify a tumor as malignant versus not.
**[1:37]** In each of these problems the variable that you want to predict can
**[1:41]** only be one of two possible values.
**[1:44]** No or yes.
**[1:46]** This type of classification problem where there are only two possible outputs is
**[1:50]** called binary classification.
**[1:52]** Where the word binary refers to there being only
**[1:56]** two possible classes or two possible categories.
**[2:01]** In these problems I will use the terms class and
**[2:05]** category relatively interchangeably.
**[2:09]** They mean basically the same thing.
**[2:11]** By convention we can refer to these two classes or
**[2:15]** categories in a few common ways.
**[2:18]** We often designate clauses as no or yes or
**[2:22]** sometimes equivalently false or true or
**[2:26]** very commonly using the numbers zero or one.
**[2:31]** Following the common convention in computer science with zero
**[2:35]** denoting falls and one denoting true.
**[2:38]** I'm usually going to use the numbers zero and one to represent the answer y.
**[2:44]** Because that will fit in most easily with the types of learning algorithms we
**[2:48]** want to implement.
**[2:50]** But when we talk about it will often say no or yes or false or true as well.
**[2:56]** One of the technologies commonly used is to call the false or zero class.
**[3:01]** The negative class and the true or the one class, the positive class.
**[3:09]** For example, for spam classification,
**[3:12]** an email that is not spam may be referred to as a negative example.
**[3:16]** Because the output to the question of is a spam.
**[3:19]** The output is no or zero.
**[3:22]** In contrast,
**[3:24]** an email that has spam might be referred to as a positive training example.
**[3:30]** Because the answer to is it spam is yes or
**[3:33]** true or one to be clear, negative and positive.
**[3:38]** Do not necessarily mean bad versus good or evil versus good.
**[3:42]** It's just that negative and
**[3:44]** positive examples are used to convey the concepts of absence or zero or
**[3:48]** false vs the presence or true or one of something you might be looking for.
**[3:53]** Such as the absence or presence of the spam illness or
**[3:57]** the spam property of an email or the absence of presence of broadening
**[4:02]** activity or absence of presence of malignancy of the tumor.
**[4:07]** Between non spam and spam emails.
**[4:10]** Which one you call false or zero and which one you call true or
**[4:14]** one is a little bit arbitrary.
**[4:17]** Often either choice could work.
**[4:20]** So, different engineer might actually swap it around and have the positive class B.
**[4:24]** The presence of a good email or the possible causes be the presence
**[4:29]** of a real financial transaction or a healthy patient.
**[4:33]** So how do you build a classification algorithm?
**[4:38]** Here's the example of a training set for classifying if the tumor is malignant.
**[4:43]** A class one, positive class, yes class or
**[4:47]** benign, class zero or negative class.
**[4:51]** I plotted both the tumor size on the horizontal axis
**[4:55]** as well as the label Y on the vertical axis.
**[4:59]** By the way, in week one, when we first talked about classification.
**[5:03]** This is how we previously visualized it on the number line except that now we're
**[5:08]** calling the classes zero.
**[5:09]** And one and plotting them on the vertical axis.
**[5:14]** Now, one thing you could try on this training set is to apply the album you
**[5:19]** already know.
**[5:20]** Linear regression and try to fit a straight line to the data.
**[5:24]** If you do that, maybe the straight line looks like this, right?
**[5:28]** And that's your F effects.
**[5:31]** Linear regression predicts not just the values zero and one.
**[5:35]** But all numbers between zero and one or even less than zero or greater than one.
**[5:41]** But here we want to predict categories.
**[5:45]** One thing you could try is to pick a threshold of say 0.5.
**[5:51]** So that if the model outputs a value below 0.5,
**[5:56]** then you predict why equal zero or not malignant.
**[6:00]** And if the model outputs a number equal to or
**[6:04]** greater than 0.5, then predict Y equals one or malignant.
**[6:09]** Notice that this threshold value of 0.5 intersects
**[6:14]** the best fit straight line at this point.
**[6:17]** So if you draw this vertical line here,
**[6:20]** everything to the left ends up with a prediction of y equals zero.
**[6:25]** And everything on the right ends up with the prediction of y equals one.
**[6:31]** Now, for this particular data set it looks like linear
**[6:34]** regression could do something reasonable.
**[6:37]** But now let's see what happens if your dataset has one more training example.
**[6:42]** This one way over here on the right.
**[6:46]** Let's also extend the horizontal axis.
**[6:49]** Notice that this training example shouldn't really change how you classify
**[6:53]** the data points.
**[6:54]** This vertical dividing line that we drew just now still makes sense as the cut off
**[6:59]** where tumors smaller than this should be classified as zero.
**[7:02]** And tumors greater than this should be classified as one.
**[7:07]** But once you've added this extra training example on the right.
**[7:10]** The best fit line for linear regression will shift over like this.
**[7:15]** And if you continue using the threshold of 0.5, you now notice
**[7:20]** that everything to the left of this point is predicted at zero non malignant.
**[7:27]** And everything to the right of this point is predicted to be one or malignant.
**[7:32]** This isn't what we want because adding that example way to the right shouldn't
**[7:38]** change any of our conclusions about how to classify malignant versus benign tumors.
**[7:44]** But if you try to do this with linear regression,
**[7:47]** adding this one example which feels like it shouldn't be changing anything.
**[7:51]** It ends up with us learning a much worse function for this classification problem.
**[7:57]** Clearly, when the tumor is large, we want the algorithm to classify it as malignant.
**[8:03]** So what we just saw was linear regression causes the best fit line.
**[8:08]** When we added one more example to the right to shift over.
**[8:13]** And does the dividing line also called the decision
**[8:17]** boundary to shift over to the right.
**[8:20]** You learn more about the decision boundary in the next video,
**[8:24]** you also learn about an algorithm called logistic regression.
**[8:29]** Where the output value of the outcome will always be between zero and one.
**[8:34]** And the average will avoid these problems that we're seeing on this slide.
**[8:38]** By the way one thing confusing about the name logistic regression is that even
**[8:43]** though it has the word of regression in it is actually used for classification.
**[8:49]** Don't be confused by the name which was given for historical reasons.
**[8:53]** It's actually used to solve binary classification problems
**[8:58]** with output label y is either zero or one.
**[9:01]** In the upcoming optional lab you also get to take a look at what happens
**[9:06]** when you try to use linear regression for classification.
**[9:10]** Sometimes you get lucky and it may work but often it will not work well.
**[9:16]** Which is why I don't use linear regression myself for classification.
**[9:21]** In the optional lab,
**[9:22]** you see an interactive plot that attempts to classify between two categories.
**[9:27]** And hopefully notice how this often doesn't work very well.
**[9:32]** Which is okay because that motivates the need for
**[9:35]** a different model to do classification talks.
**[9:37]** So please check out this optional lab and after that we're
**[9:41]** going to the next video to look at logistic regression for classification.
