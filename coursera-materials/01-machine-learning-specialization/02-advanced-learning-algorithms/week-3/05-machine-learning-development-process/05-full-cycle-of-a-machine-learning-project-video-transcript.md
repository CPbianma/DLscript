---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Machine learning development process
item_title: Full cycle of a machine learning project
duration: 9 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/D1N6k/full-cycle-of-a-machine-learning-project
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Full cycle of a machine learning project — Transcript

**[0:01]** So far we've talked a lot about how
**[0:04]** to train a model and also talked
**[0:06]** a bit about how to get
**[0:07]** data for your machine learning application.
**[0:10]** But when I'm building a machine learning system I
**[0:13]** find that training a model is just part of the puzzle.
**[0:17]** In this video I'd like to share with you what I think of
**[0:20]** as the full cycle of a machine learning project.
**[0:23]** That is, when you're
**[0:24]** building a valuable machine learning system,
**[0:27]** what are the steps to think about and plan for?
**[0:30]** Let's take a look, let me use speech recognition as
**[0:33]** an example to illustrate
**[0:35]** the full cycle of a machine learning project.
**[0:37]** The first step of machine learning project
**[0:40]** is to scope the project.
**[0:41]** In other words, decide what is
**[0:42]** the project and what you want to work on.
**[0:45]** For example, I once decided to work
**[0:48]** on speech recognition for voice search.
**[0:50]** That is to do web search using
**[0:53]** speaking to your mobile phone
**[0:54]** rather than typing into your mobile phone.
**[0:57]** This project scoping.
**[0:59]** After deciding what to work on you have to collect data.
**[1:02]** Decide what data you need
**[1:05]** to train your machine learning system and go and do
**[1:07]** the work to get the audio and get
**[1:09]** the transcripts of the labels for your dataset.
**[1:12]** That's data collection.
**[1:14]** After you have your initial data collection
**[1:17]** you can then start to train the model.
**[1:20]** Here you would train a speech recognition system and
**[1:24]** carry out error analysis and
**[1:25]** iteratively improve your model.
**[1:28]** Is not at all uncommon.
**[1:31]** After you've started training
**[1:32]** the model for error analysis
**[1:36]** or for a bias-variance analysis to tell you
**[1:38]** that you might want to go back to collect more data.
**[1:41]** Maybe collect more data of everything or
**[1:43]** just collect more data of a specific type
**[1:46]** where your error analysis tells you you want to
**[1:48]** improve the performance of your learning algorithm.
**[1:51]** For example, once when working on speech I realized that
**[1:55]** my model was doing particularly poorly
**[1:57]** when there was car noise in the background.
**[2:00]** That sounded like someone was speaking in a car.
**[2:03]** My speech system perform poorly decided to get more data,
**[2:07]** actually using data augmentation
**[2:08]** to get more speech data that
**[2:11]** sounds like it was a car in order to
**[2:13]** improve the performance of my learning algorithm.
**[2:16]** You go around this loop a few times, train the model,
**[2:20]** error analysis, go back to collect more data,
**[2:22]** maybe do this for a while until eventually you say
**[2:26]** the model is good enough to then
**[2:27]** deploy in a production environment.
**[2:29]** What that means is you make it
**[2:31]** available for users to use.
**[2:34]** When you deploy a system you have
**[2:36]** to also make sure that you continue to
**[2:38]** monitor the performance of the system and
**[2:41]** to maintain the system in case the performance
**[2:43]** gets worse to bring us performance back up instead
**[2:46]** of just hosting your machine learning model on a server.
**[2:50]** I'll say a little bit more about why you need to
**[2:52]** maintain these machine learning
**[2:54]** systems on the next slide.
**[2:55]** But after this deployment,
**[2:57]** sometimes you realize that
**[2:59]** is not working as well as you hoped and you go
**[3:02]** back to train the model to improve it again
**[3:04]** or even go back and get more data.
**[3:07]** In fact, if users and if you have
**[3:10]** permission to use data from your production deployment,
**[3:14]** sometimes that data from
**[3:16]** your working speech system can give you
**[3:19]** access to even more data with which
**[3:21]** to keep on improving the performance of your system.
**[3:24]** Now, I think you have a sense of what
**[3:26]** scoping a project means and we've talked
**[3:28]** a bunch about collecting data and
**[3:29]** training models in this course.
**[3:32]** But let me share with you a little bit more detail
**[3:34]** about what deploying in production might look like.
**[3:38]** After you've trained
**[3:40]** a high performing machine learning model,
**[3:43]** say a speech recognition model,
**[3:45]** a common way to deploy the model would be to take
**[3:50]** your machine learning model and implement it in a server,
**[3:55]** which I'm going to call an inference server,
**[3:58]** whose job it is to call your machine learning model,
**[4:01]** your trained model,
**[4:02]** in order to make predictions.
**[4:04]** Then if your team has implemented a mobile app,
**[4:09]** say a search application,
**[4:11]** then when a user talks to the mobile app,
**[4:14]** the mobile app can then make an API call to
**[4:17]** pass to your inference server the audio clip that was
**[4:21]** recorded and the inference server's
**[4:24]** job is supply the machine learning model to
**[4:26]** it and then return to it the prediction of your model,
**[4:31]** which in this case would be
**[4:32]** the text transcripts of what was said.
**[4:36]** This would be a common way of implementing
**[4:39]** an application that calls via
**[4:42]** the API and inference server that has
**[4:45]** your model repeatedly make predictions
**[4:47]** based on the input, x.
**[4:49]** This were common pattern where
**[4:52]** depend on the application does implemented.
**[4:54]** You have an API call to
**[4:56]** give your learning algorithm the input, x,
**[4:58]** and your machine learning model within
**[5:01]** output to prediction, say y hat.
**[5:04]** To implement this some software engineering
**[5:08]** may be needed to write
**[5:10]** all the code that does all of these things.
**[5:13]** Depending on whether your application
**[5:16]** needs to serve just a few handful of
**[5:17]** users or millions of users
**[5:20]** the amounts of software engineer
**[5:21]** needed can be quite different.
**[5:23]** I've build software that serve
**[5:26]** just a handful of users on my laptop and I've also
**[5:29]** built software that serves
**[5:30]** hundreds of millions of users requiring
**[5:32]** significant data center resources.
**[5:36]** Depending on scale application needed,
**[5:39]** software engineering may be needed to make sure
**[5:41]** that your inference server is able to
**[5:44]** make reliable and efficient predictions
**[5:47]** hopefully not too high of computational cost.
**[5:50]** Software engineering may be needed to manage
**[5:52]** scaling to a large number of users.
**[5:54]** You often want to log the data you're
**[5:56]** getting both the inputs,
**[5:58]** x, as well as the predictions,
**[5:59]** y hat, assuming that
**[6:01]** user privacy and consent allows you to store this data.
**[6:05]** This data, if you can access to it,
**[6:08]** is also very useful for system monitoring.
**[6:12]** For example, I once built a speech recognition system on
**[6:15]** a certain dataset that I had but when there
**[6:19]** were new celebrities that suddenly
**[6:21]** became well-known or elections cause
**[6:23]** new politicians to become
**[6:25]** elected and people will search for
**[6:27]** these new names that were not
**[6:29]** in the training set and then my system did poorly on.
**[6:32]** It was because we were monitoring
**[6:34]** the system allowed us to figure
**[6:36]** out when the data was
**[6:38]** shifting and the algorithm was becoming less accurate.
**[6:41]** This allowed us to retrain
**[6:43]** the model and then to carry out
**[6:45]** a model update to replace the old model with a new one.
**[6:52]** The deployment process can
**[6:54]** require some amounts of software engineering.
**[6:57]** For some applications,
**[6:59]** if you're just running it on
**[7:00]** a laptop or on a one or two servers,
**[7:02]** maybe not that much software engineering is needed.
**[7:05]** Depending on the team you're working on,
**[7:08]** it is possible that you built
**[7:10]** the machine learning model but there could be
**[7:14]** a different team responsible for deploying it.
**[7:17]** But there is a growing field
**[7:20]** in machine learning called MLOps.
**[7:22]** This stands for Machine Learning Operations.
**[7:25]** This refers to the practice of how to
**[7:30]** systematically build and deploy
**[7:33]** and maintain machine learning systems.
**[7:35]** To do all of these things to make sure that
**[7:38]** your machine learning model is reliable, scales well,
**[7:42]** has good laws, is monitored,
**[7:44]** and then you have the opportunity to make updates to
**[7:47]** the model as appropriate to keep it running well.
**[7:50]** For example, if you are deploying
**[7:52]** your system to millions of people you may
**[7:54]** want to make sure you have a
**[7:55]** highly optimized implementations so
**[7:58]** that the compute cost of
**[8:00]** serving millions of people is not too expensive.
**[8:03]** In this and the last class I spent
**[8:06]** a lot of time talking about how to train
**[8:08]** a machine learning model and got
**[8:09]** this absolutely the critical piece to
**[8:12]** making sure you have a high performance system.
**[8:15]** If you ever have to deploy system to millions of people,
**[8:20]** these are some additional steps
**[8:22]** that you probably have to address.
**[8:24]** Think about the [inaudible] at that point as well.
**[8:26]** Before moving on from the topic of
**[8:29]** the machine learning development process,
**[8:32]** there's one more set of
**[8:33]** ideas that I want to share with you
**[8:35]** that relates to the ethics
**[8:36]** of building machine learning systems.
**[8:38]** This is a crucial topic for
**[8:40]** many applications so let's
**[8:42]** take a look at this in the next video.
