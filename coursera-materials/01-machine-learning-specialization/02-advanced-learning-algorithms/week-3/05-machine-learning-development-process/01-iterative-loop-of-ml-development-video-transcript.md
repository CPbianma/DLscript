---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Machine learning development process
item_title: Iterative loop of ML development
duration: 8 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/uOXJM/iterative-loop-of-ml-development
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Iterative loop of ML development — Transcript

**[0:01]** In the next few videos,
**[0:03]** I'd like to share with you what is like
**[0:05]** to go through the process of
**[0:07]** developing a machine learning system
**[0:09]** so that when you are doing so yourself,
**[0:12]** hopefully, you'd be in a position
**[0:13]** to make great decisions at
**[0:15]** many stages of the machine learning development process.
**[0:19]** Let's take a look first at
**[0:20]** the iterative loop of machine learning development.
**[0:24]** This is what developing
**[0:25]** a machine learning model will often feel like.
**[0:28]** First, you decide on what
**[0:30]** is the overall architecture of your system.
**[0:33]** That means choosing your machine learning model
**[0:36]** as well as deciding what data to use,
**[0:38]** maybe picking the hyperparameters, and so on.
**[0:41]** Then, given those decisions,
**[0:44]** you would implement and train a model.
**[0:47]** As I've mentioned before,
**[0:49]** when you train a model for the first time,
**[0:51]** it will almost never work as well as you want it to.
**[0:55]** The next step that I recommend then is
**[0:58]** to implement or to look at a few diagnostics,
**[1:01]** such as looking at the bias and
**[1:03]** variance of your algorithm as well as
**[1:05]** something we'll see in
**[1:06]** the next video called error analysis.
**[1:09]** Based on the insights from the diagnostics,
**[1:12]** you can then make decisions
**[1:14]** like do want to make your neural network
**[1:16]** bigger or change the Lambda regularization parameter,
**[1:21]** or maybe add more data
**[1:23]** or add more features or subtract features.
**[1:26]** Then you go around this loop
**[1:27]** again with your new choice of architecture,
**[1:31]** and it will often take multiple iterations through
**[1:33]** this loop until you get to the performance that you want.
**[1:37]** Let's look at an example of building
**[1:39]** an email spam classifier.
**[1:42]** I think many of us passionately hate
**[1:44]** email spam and this is a problem that I
**[1:47]** worked on years ago and also was involved in
**[1:51]** starting an anti-spam conference once years ago.
**[1:55]** The example on the left is what
**[1:56]** a highly spammy email might look like.
**[1:59]** Deal of the week, by now, Rolex watches.
**[2:02]** Spammers will sometimes deliberately
**[2:05]** misspell words like these,
**[2:07]** watches, medicine, and mortgages
**[2:10]** in order to try to trip up a spam recognizer.
**[2:13]** In contrast, this email on
**[2:15]** the right is an actual email I once
**[2:17]** got from my younger brother Alfred
**[2:19]** about getting together for Christmas.
**[2:21]** How do you build a classifier
**[2:25]** to recognize spam versus non-spam emails?
**[2:29]** One way to do so would be to train
**[2:32]** a supervised learning algorithm
**[2:34]** where the input features x
**[2:37]** will be the features of
**[2:38]** an email and the output label y will
**[2:41]** be one or zero
**[2:43]** depending on whether it's spam or non-spam.
**[2:47]** This application is an example
**[2:51]** of text classification because you're
**[2:53]** taking a text document that is an email
**[2:56]** and trying to classify it as either spam or non-spam.
**[2:59]** One way to construct
**[3:01]** the features of the email would be to say,
**[3:03]** take the top 10,000 words in the English language or in
**[3:07]** some other dictionary and use them to define
**[3:11]** features x_1, x_2 through x_10,000.
**[3:15]** For example, given this email on the right,
**[3:19]** if the list of words we have is a,
**[3:22]** Andrew buy deal discount and so on.
**[3:30]** Then given the email on the right,
**[3:32]** we would set these features to be, say,
**[3:35]** 0 or 1, depending on whether or not that word appears.
**[3:39]** The word a does not appear.
**[3:41]** The word Andrew does appear.
**[3:43]** The word buy does appear, deal does,
**[3:47]** discount does not, and so on,
**[3:49]** and so you can construct 10,000 features of this email.
**[3:54]** There are many ways to construct a feature vector.
**[3:57]** Another way would be to
**[3:59]** let these numbers not just be 1 or 0,
**[4:02]** but actually, count the number of
**[4:03]** times a given word appears in the email.
**[4:06]** If buy appears twice,
**[4:08]** maybe you want to set this to 2,
**[4:10]** but setting into just 1 or 0.
**[4:12]** It actually works decently well.
**[4:15]** Given these features, you can then train
**[4:18]** a classification algorithm such as
**[4:21]** a logistic regression model or a neural network to
**[4:24]** predict y given these features x.
**[4:28]** After you've trained your initial model,
**[4:31]** if it doesn't work as well as you wish,
**[4:34]** you will quite likely have
**[4:36]** multiple ideas for improving
**[4:37]** the learning algorithm's performance.
**[4:39]** For example, is always tempting to collect more data.
**[4:43]** In fact, I have friends that have worked on
**[4:45]** very large-scale honeypot projects.
**[4:48]** These are projects that create a large number
**[4:50]** of fake email addresses and tries to
**[4:53]** deliberately to get these fake email addresses
**[4:56]** into the hands of spammers so that when they send
**[4:59]** spam email to these fake emails well we know these are
**[5:02]** spam email messages and so this is a way
**[5:04]** to get a lot of spam data.
**[5:06]** Or you might decide to work on developing
**[5:09]** more sophisticated features based on the email routing.
**[5:13]** Email routing refers to the sequence of compute service.
**[5:19]** Sometimes around the world that the email has
**[5:21]** gone through all this way to reach
**[5:23]** you and emails actually
**[5:25]** have what's called email header information.
**[5:28]** That is information that keeps track of how
**[5:31]** the email has traveled across different servers,
**[5:33]** across different networks to find its way to you.
**[5:36]** Sometimes the path that an email has traveled
**[5:40]** can help tell you if it was sent by a spammer or not.
**[5:44]** Or you might work on coming up with
**[5:47]** more sophisticated features from
**[5:49]** the email body that is the text of the email.
**[5:52]** In the features I talked about last time,
**[5:55]** discounting and discount may
**[5:57]** be treated as different words,
**[5:59]** and maybe they should be treated as the same words.
**[6:03]** Or you might decide to come up with algorithms
**[6:07]** to detect misspellings or
**[6:08]** deliberate misspellings like watches,
**[6:10]** medicine, and mortgage and this
**[6:12]** too could help you decide if an email is spammy.
**[6:16]** Given all of these and possibly even more ideas,
**[6:19]** how can you decide which of
**[6:21]** these ideas are more promising to work on?
**[6:24]** Because choosing the more promising path
**[6:26]** forward can speed up your project
**[6:29]** easily 10 times compared to if you were to
**[6:31]** somehow choose some of the less promising directions.
**[6:35]** For example, we've already seen that if
**[6:38]** your algorithm has high bias rather than high variance,
**[6:40]** then spending months and months on
**[6:42]** a honeypot project may
**[6:44]** not be the most fruitful direction.
**[6:46]** But if your algorithm has high variance,
**[6:48]** then collecting more data could help a lot.
**[6:50]** Doing the iterative loop of machinery and development,
**[6:53]** you may have many ideas for how to
**[6:55]** modify the model or the data,
**[6:58]** and it will be coming up with
**[6:59]** different diagnostics that could give you a lot
**[7:02]** of guidance on what choices for the model or data,
**[7:05]** or other parts of
**[7:07]** the architecture could be most promising to try.
**[7:10]** In the last several videos,
**[7:12]** we've already talked about bias and variance.
**[7:15]** In the next video, I'd like to start
**[7:19]** describing to you the error analysis process,
**[7:22]** which has a second key set of ideas for gaining
**[7:25]** insight about
**[7:26]** what architecture choices might be fruitful.
**[7:30]** That's the iterative loop of machine learning
**[7:33]** development and using the example
**[7:35]** of building a spam classifier.
**[7:37]** Let's take a look at what error analysis looks like.
**[7:40]** Let's do that in the next video.
