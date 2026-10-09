---
type: video-transcript
specialization: Deep Learning Specialization
course: "Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization"
week: 3
section: Introduction to Programming Frameworks
item_title: Deep Learning Frameworks
duration: 4 min
source_url: https://www.coursera.org/learn/deep-neural-network/lecture/NpLFp/deep-learning-frameworks
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Deep Learning Frameworks — Transcript

**[0:00]** You've learned to implement deep learning algorithms more or
**[0:03]** less from scratch using Python and NumPY.
**[0:06]** And I'm glad you did that because I wanted you to
**[0:08]** understand what these deep learning algorithms are really doing.
**[0:11]** But you find unless you implement more complex models,
**[0:14]** such as convolutional neural networks or recurring neural networks,
**[0:18]** or as you start to implement very large models that is increasingly not practical,
**[0:23]** at least for most people, is not practical to implement everything yourself from scratch.
**[0:28]** Fortunately, there are now
**[0:29]** many good deep learning software frameworks that can help you implement these models.
**[0:34]** To make an analogy,
**[0:36]** I think that hopefully you understand how to do
**[0:38]** a matrix multiplication and you should be able to implement how to code,
**[0:43]** to multiply two matrices yourself.
**[0:45]** But as you build very large applications,
**[0:47]** you'll probably not want to implement your own matrix multiplication function but
**[0:51]** instead you want to call
**[0:53]** a numerical linear algebra library that could do it more efficiently for you.
**[0:57]** But this still helps that you understand how multiplying two matrices work.
**[1:01]** So I think deep learning has now matured to that point where it's actually more
**[1:05]** practical you'll be more efficient doing
**[1:07]** some things with some of the deep learning frameworks.
**[1:10]** So let's take a look at the frameworks out there.
**[1:13]** Today, there are many deep learning frameworks
**[1:16]** that makes it easy for you to implement neural networks,
**[1:19]** and here are some of the leading ones.
**[1:22]** Each of these frameworks has a dedicated user and developer community
**[1:27]** and I think each of these frameworks is
**[1:29]** a credible choice for some subset of applications.
**[1:33]** There are lot of people writing articles comparing
**[1:36]** these deep learning frameworks and how well these deep learning frameworks changes.
**[1:41]** And because these frameworks are often evolving and getting better month to month,
**[1:46]** I'll leave you to do a few internet searches yourself,
**[1:49]** if you want to see the arguments on the pros and cons of some of these frameworks.
**[1:54]** But I think many of these frameworks are evolving and getting better very rapidly.
**[1:59]** So rather than too strongly endorsing any of these frameworks I want to share
**[2:04]** with you the criteria I would recommend you use to choose frameworks.
**[2:10]** One important criteria is the ease of programming,
**[2:13]** and that means both developing the neural network and
**[2:15]** iterating on it as well as deploying it for production,
**[2:19]** for actual use, by thousands or millions or maybe hundreds of millions of users,
**[2:25]** depending on what you're trying to do.
**[2:27]** A second important criteria is running speeds,
**[2:30]** especially training on large data sets,
**[2:32]** some frameworks will let you run and train
**[2:35]** your neural network more efficiently than others.
**[2:38]** And then, one criteria that people don't often talk about but I think
**[2:42]** is important is whether or not the framework is truly open.
**[2:46]** And for a framework to be truly open,
**[2:49]** it needs not only to be open source but I think it needs good governance as well.
**[2:54]** Unfortunately, in the software industry some companies have a history of
**[2:58]** open sourcing software but maintaining single corporation control of the software.
**[3:04]** And then over some number of years,
**[3:06]** as people start to use the software,
**[3:08]** some companies have a history of gradually closing off what was open source,
**[3:14]** or perhaps moving functionality into their own proprietary cloud services.
**[3:19]** So one thing I pay a bit of attention to is how
**[3:22]** much you trust that the framework will remain
**[3:25]** open source for a long time rather than just being under the control of a single company,
**[3:31]** which for whatever reason may choose to close it off in
**[3:35]** the future even if the software is currently released under open source.
**[3:40]** But at least in the short term depending on your preferences of language,
**[3:44]** whether you prefer Python or Java or C++ or something else,
**[3:49]** and depending on what application you're working on,
**[3:51]** whether this can be division or natural language processing
**[3:54]** or online advertising or something else,
**[3:57]** I think multiple of these frameworks could be a good choice.
**[4:01]** So that said on programming frameworks by providing
**[4:05]** a higher level of abstraction than just a numerical linear algebra library,
**[4:09]** any of these program frameworks can make you more
**[4:11]** efficient as you develop machine learning applications.
