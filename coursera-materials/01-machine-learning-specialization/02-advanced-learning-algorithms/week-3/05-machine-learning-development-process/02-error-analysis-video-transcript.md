---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Machine learning development process
item_title: Error analysis
duration: 8 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/FaPgS/error-analysis
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Error analysis — Transcript

**[0:01]** In terms of the most important ways
**[0:04]** to help you run diagnostics
**[0:06]** to choose what to try next
**[0:07]** to improve your learning algorithm performance,
**[0:09]** I would say bias and variance is probably
**[0:12]** the most important idea and
**[0:14]** error analysis would probably be second on my list.
**[0:17]** Let's take a look at what this means.
**[0:19]** Concretely, let's say you have m_cv equals
**[0:23]** 500 cross validation examples and
**[0:27]** your algorithm misclassifies 100
**[0:29]** of these 500 cross validation examples.
**[0:32]** The error analysis process just
**[0:35]** refers to manually looking through
**[0:38]** these 100 examples and trying to
**[0:41]** gain insights into where the algorithm is going wrong.
**[0:45]** Specifically, what I will often do is find
**[0:48]** a set of examples that the algorithm has
**[0:51]** misclassified examples from the cross validation set and
**[0:56]** try to group them into
**[0:58]** common teams or common properties or common traits.
**[1:02]** For example, if you notice that quite a lot of
**[1:06]** the misclassified spam emails are pharmaceutical sales,
**[1:10]** trying to sell medicines or drugs then
**[1:13]** I will actually go through these examples and
**[1:15]** count up by hand how many emails that are misclassified are
**[1:20]** pharmaceutical spam and say there
**[1:22]** are 21 emails that are pharmaceutical spam.
**[1:25]** Or if you suspect
**[1:28]** that deliberate misspellings
**[1:30]** may be tripping over your spam
**[1:31]** classifier then I will also
**[1:33]** go through and just count up how many of
**[1:36]** these examples that it
**[1:38]** misclassified had a deliberate misspelling.
**[1:40]** Let's say I find three out of a 100.
**[1:43]** Or looking through the email
**[1:46]** routing info I find seven has
**[1:48]** unusual email routing and
**[1:51]** 18 emails trying to steal passwords or phishing emails.
**[1:57]** Spam is sometimes also,
**[1:59]** instead of writing the spam message in
**[2:01]** the email body they instead create
**[2:05]** an image and then writes to spam
**[2:07]** the message inside an image that appears in the email.
**[2:11]** This makes it a little bit harder for
**[2:12]** learning algorithm to figure out what's going on.
**[2:15]** Maybe some of those emails are these embedded image spam.
**[2:19]** If you end up with these counts then
**[2:23]** that tells you that pharmaceutical spam
**[2:27]** and emails trying to steal
**[2:29]** passwords or phishing emails seem to
**[2:32]** be huge problems whereas deliberate misspellings,
**[2:36]** well, it is a problem it is a smaller one.
**[2:39]** In particular, what this analysis tells you is
**[2:42]** that even if you were to build
**[2:44]** really sophisticated algorithms to
**[2:46]** find deliberate misspellings it will only
**[2:49]** solve three out of 100 of your misclassified examples.
**[2:54]** The net impact seems like it may not be that large.
**[2:58]** Doesn't mean it's not worth doing?
**[3:00]** But when you're prioritizing what to do,
**[3:02]** you might therefore decide not
**[3:04]** to prioritizes this as highly.
**[3:06]** By the way, I'm telling the story
**[3:08]** because I once actually spent a lot of time
**[3:11]** building algorithms to find deliberate misspellings and
**[3:14]** spam emails only much later to
**[3:16]** realize that the net impact was actually quite small.
**[3:19]** This is one example where I
**[3:21]** wish I'd done more careful error analysis
**[3:23]** before spending a lot of time
**[3:24]** myself trying to find these deliberate misspellings.
**[3:28]** Just a couple of notes on this process.
**[3:32]** These categories can be
**[3:34]** overlapping or in other words
**[3:36]** they're not mutually exclusive.
**[3:38]** For example, there can be
**[3:40]** a pharmaceutical spam email that also has unusual routing
**[3:44]** or a password that has deliberate misspellings
**[3:48]** and is also trying to carry out the phishing attack.
**[3:52]** One email can be counted in multiple categories.
**[3:56]** In this example, I had said that the algorithm
**[4:01]** misclassified as 100 examples and we'll look
**[4:03]** at all 100 examples manually.
**[4:05]** If you have a larger cross validation set,
**[4:08]** say we had 5,000
**[4:11]** cross validation examples and if the algorithm
**[4:13]** misclassified say 1,000 of them then you may not have
**[4:18]** the time depending on the team size
**[4:20]** and how much time you have to work on this project.
**[4:24]** You may not have the time to manually look at
**[4:26]** all 1,000 examples that the algorithm misclassifies.
**[4:30]** In that case, I will often sample
**[4:33]** randomly a subset of usually around a 100,
**[4:36]** maybe a couple 100 examples because that's
**[4:38]** the amount that you can look
**[4:39]** through in a reasonable amount of time.
**[4:41]** Hopefully looking through maybe around
**[4:44]** a 100 examples will give you enough statistics about
**[4:47]** whether the most common types of errors and
**[4:50]** therefore where maybe most
**[4:51]** fruitful to focus your attention.
**[4:54]** After this analysis, if you find that a lot of errors are
**[5:00]** pharmaceutical spam emails then this might give
**[5:04]** you some ideas or inspiration for things to do next.
**[5:08]** For example, you may decide to
**[5:11]** collect more data but not more data of everything,
**[5:15]** but just try to find more data
**[5:18]** of pharmaceutical spam emails so
**[5:20]** that the learning algorithm can do a better job
**[5:22]** recognizing these pharmaceutical spam.
**[5:25]** Or you may decide to come up with
**[5:27]** some new features that are related to say specific names
**[5:31]** of drugs or specific names of
**[5:33]** pharmaceutical products of
**[5:34]** the spammers are trying to sell
**[5:36]** in order to help your learning algorithm become
**[5:38]** better at recognizing this type of pharma spam.
**[5:42]** Then again this might inspire you to make
**[5:45]** specific changes to the algorithm
**[5:47]** relating to detecting phishing emails.
**[5:50]** For example, you might look
**[5:51]** at the URLs in the email and write
**[5:54]** special code to come with extra features to
**[5:56]** see if it's linking to suspicious URLs.
**[5:58]** Or again, you might decide to get
**[6:00]** more data of phishing emails
**[6:02]** specifically in order to help
**[6:04]** your learning algorithm do a
**[6:05]** better job of recognizing them.
**[6:07]** The point of this error analysis is by manually examining
**[6:12]** a set of examples that your algorithm
**[6:15]** is misclassifying or mislabeling.
**[6:17]** Often this will create
**[6:19]** inspiration for what might be useful to try next
**[6:23]** and sometimes it can also tell you that certain types of
**[6:28]** errors are sufficiently rare that they
**[6:30]** aren't worth as much of your time to try to fix.
**[6:33]** Returning to this list,
**[6:35]** a bias variance analysis should tell
**[6:38]** you if collecting more data is helpful or not.
**[6:42]** Based on our error analysis
**[6:44]** in the example we just went through,
**[6:45]** it looks like more sophisticated email features
**[6:47]** could help but only a bit whereas
**[6:50]** more sophisticated features to detect
**[6:52]** pharma spam or phishing emails could help a lot.
**[6:55]** These detecting misspellings would
**[6:58]** not help nearly as much.
**[7:00]** In general I found both the bias
**[7:02]** variance diagnostic as well as
**[7:03]** carrying out this form of error analysis
**[7:06]** to be really helpful to screening or to
**[7:08]** deciding which changes to
**[7:11]** the model are more promising to try on next.
**[7:14]** Now one limitation of error analysis is that it's
**[7:17]** much easier to do for problems that humans are good at.
**[7:21]** You can look at the email
**[7:22]** and say you think is a spam email,
**[7:24]** why did the algorithm get it wrong?
**[7:26]** Error analysis can be a bit harder
**[7:28]** for tasks that even humans aren't good at.
**[7:30]** For example, if you're trying to predict
**[7:33]** what ads someone will click on on the website.
**[7:35]** Well, I can't predict what someone will click on.
**[7:37]** Error analysis there actually tends to be more difficult.
**[7:41]** But when you apply error analysis
**[7:43]** to problems that you can it
**[7:45]** can be extremely helpful for
**[7:47]** focusing attention on the more promising things to try.
**[7:50]** That in turn can easily save
**[7:52]** you months of otherwise fruitless work.
**[7:55]** In the next video,
**[7:56]** I'd like to dive deeper into the problem of adding data.
**[8:01]** When you train a learning algorithm,
**[8:03]** sometimes you decide there's
**[8:05]** high variance and you want to get more data for it.
**[8:08]** Some techniques they can make how you
**[8:10]** add data much more efficient.
**[8:13]** Let's take a look at that
**[8:14]** so that hopefully you'll be armed with
**[8:16]** some good ways to get
**[8:18]** more data for your learning application.
