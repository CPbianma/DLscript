---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Multiclass Classification
item_title: Classification with multiple outputs (Optional)
duration: 4 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/pjIk0/classification-with-multiple-outputs-optional
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Classification with multiple outputs (Optional) — Transcript

**[0:01]** You've learned about multi-class classification,
**[0:05]** where the output label Y can be any one of
**[0:09]** two or potentially many more
**[0:11]** than two possible categories.
**[0:13]** There's a different type of
**[0:15]** classification problem called a
**[0:17]** multi-label classification problem,
**[0:19]** which is where associate of each image,
**[0:23]** they could be multiple labels.
**[0:25]** Let me show you what I mean by that.
**[0:27]** If you're building a self-driving car or
**[0:30]** maybe a driver assistance system,
**[0:32]** then given a picture of what's in front of your car,
**[0:36]** you may want to ask a question like,
**[0:39]** is there a car or at least one car?
**[0:41]** Or is there a bus,
**[0:42]** or is there a pedestrian or are there any pedestrians?
**[0:46]** In this case, there is a car,
**[0:50]** there is no bus,
**[0:51]** and there is at least one pedestrian
**[0:54]** or in this second image, no cars,
**[0:57]** no buses and yes to pedestrians and yes car,
**[1:01]** yes bus and no pedestrians.
**[1:04]** These are examples of
**[1:06]** multi-label classification problems because
**[1:10]** associated with a single input,
**[1:13]** image X are three different labels
**[1:18]** corresponding to whether or not there are any cars,
**[1:20]** buses, or pedestrians in the image.
**[1:23]** In this case, the target of the Y is
**[1:26]** actually a vector of three numbers,
**[1:31]** and this is as distinct from
**[1:33]** multi-class classification, where for,
**[1:36]** say handwritten digit classification,
**[1:38]** Y was just a single number,
**[1:40]** even if that number could take on
**[1:42]** 10 different possible values.
**[1:44]** How do you build a neural network for
**[1:47]** multi-label classification?
**[1:49]** One way to go about it is to just treat this as
**[1:52]** three completely separate machine learning problems.
**[1:55]** You could build one neural network
**[1:57]** to decide, are there any cars?
**[1:59]** The second one to detect buses and
**[2:01]** the third one to detect pedestrians.
**[2:03]** That's actually not an unreasonable approach.
**[2:07]** Here's the first neural network to detect cars,
**[2:10]** second one to detect buses,
**[2:12]** third one to detect pedestrians.
**[2:14]** But there's another way to do this,
**[2:16]** which is to train a single neural network to
**[2:19]** simultaneously detect all three of cars,
**[2:23]** buses, and pedestrians, which is,
**[2:25]** if your neural network architecture,
**[2:27]** looks like this, there's input X.
**[2:30]** First hidden layer offers a^1,
**[2:32]** second hidden layer offers a^2,
**[2:35]** and then the final output layer, in this case,
**[2:38]** we'll have three output neurals and we'll output a^3,
**[2:43]** which is going to be a vector of three numbers.
**[2:47]** Because we're solving
**[2:48]** three binary classification problems, so is there a car?
**[2:52]** Is there a bus? Is there a pedestrian?
**[2:53]** You can use a sigmoid activation function for each of
**[2:56]** these three nodes in the output layer,
**[2:59]** and so a^3 in this case will be a_1^3,
**[3:03]** a_2^3, and a_3^3,
**[3:04]** corresponding to whether or not the learning
**[3:07]** [inaudible] as a car and no bus,
**[3:09]** and no pedestrians in the image.
**[3:12]** Multi-class classification and multi-label classification
**[3:16]** are sometimes confused with each other,
**[3:18]** and that's why in this video I want to share with you
**[3:20]** just a definition of
**[3:22]** multi-label classification problems as well,
**[3:25]** so that depending on your application,
**[3:27]** you could choose the right one
**[3:28]** for the job you want to do.
**[3:30]** So that's it for multi-label classification.
**[3:34]** I find that sometimes multi-class classification
**[3:37]** and multi-label classification are confused with other,
**[3:41]** which is why I wanted to expressively,
**[3:43]** in this video, share with you what
**[3:45]** is multi-label classification,
**[3:48]** so that depending on your application you
**[3:50]** can choose to write to for the job that you want to do.
**[3:53]** And that wraps up the section on
**[3:55]** multi-class and multi-label classification.
**[3:59]** In the next video, we'll start to look at
**[4:02]** some more advanced neural network concepts,
**[4:05]** including an optimization algorithm
**[4:07]** that is even better than gradient descent.
**[4:10]** Let's take a look at that algorithm in the next video,
**[4:13]** because it'll help you to get
**[4:14]** your learning algorithms to learn much faster.
**[4:17]** Let's go on to the next video.
