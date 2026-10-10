---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 3
section: Shallow Neural Network
item_title: Neural Networks Overview
duration: 4 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/qg83v/neural-networks-overview
language: en
extracted_at: 2026-10-08T22:15:52+08:00
status: success
---

# Neural Networks Overview — Transcript

**[0:00]** Welcome back. In this week,
**[0:02]** you learned to implement a neural network.
**[0:04]** Before diving into the technical details,
**[0:06]** I want in this video,
**[0:08]** to give you a quick overview of what you'll be seeing in this week's videos.
**[0:12]** So, if you don't follow all the details in this video,
**[0:14]** don't worry about it, we'll delve into the technical details in the next few videos.
**[0:18]** But for now, let's give a quick overview of how you implement a neural network.
**[0:23]** Last week, we had talked about logistic regression,
**[0:26]** and we saw how this model corresponds to the following computation draft,
**[0:31]** where you then put the features x and parameters
**[0:35]** w and b that allows you to compute z which is then used to computes a,
**[0:40]** and we were using a interchangeably with
**[0:43]** this output y hat and then you can compute the loss function,
**[0:48]** L. A neural network looks like this.
**[0:51]** As I'd already previously alluded,
**[0:53]** you can form a neural network by stacking together a lot of little sigmoid units.
**[0:58]** Whereas previously, this node corresponds to two steps to calculations.
**[1:03]** The first is compute the z-value,
**[1:05]** second is it computes this a value.
**[1:08]** In this neural network,
**[1:10]** this stack of notes will correspond to a z-like calculation like this,
**[1:16]** as well as, an a-like calculation like that.
**[1:20]** Then, that node will correspond to another z and another a like calculation.
**[1:26]** So the notation which we will introduce later will look like this.
**[1:30]** First, we'll inputs the features, x,
**[1:33]** together with some parameters w and b,
**[1:36]** and this will allow you to compute z one.
**[1:39]** So, new notation that we'll introduce is that we'll use
**[1:43]** superscript square bracket one to refer to
**[1:47]** quantities associated with this stack of nodes, it's called a layer.
**[1:51]** Then later, we'll use superscript square bracket
**[1:54]** two to refer to quantities associated with that node.
**[1:58]** That's called another layer of the neural network.
**[2:01]** The superscript square brackets,
**[2:03]** like we have here,
**[2:05]** are not to be confused with
**[2:06]** the superscript round brackets which we use to refer to individual training examples.
**[2:12]** So, whereas x superscript round bracket I refer to the ith training example,
**[2:17]** superscript square bracket one and two refer to these different layers;
**[2:23]** layer one and layer two in this neural network.
**[2:27]** But so going on, after computing z_1 similar to logistic regression,
**[2:33]** there'll be a computation to compute a_1,
**[2:37]** and that's just sigmoid of z_1,
**[2:40]** and then you compute z_2 using another linear equation and then compute a_2.
**[2:51]** A_2 is the final output
**[2:55]** of the neural network and will also be used interchangeably with y-hat.
**[2:59]** So, I know that was a lot of details but the key intuition to
**[3:02]** take away is that whereas for logistic regression,
**[3:05]** we had this z followed by a calculation.
**[3:09]** In this neural network,
**[3:10]** here we just do it multiple times,
**[3:12]** as a z followed by a calculation,
**[3:14]** and a z followed by a calculation,
**[3:17]** and then you finally compute the loss at the end.
**[3:21]** You remember that for logistic regression,
**[3:24]** we had this backward calculation in order
**[3:27]** to compute derivatives or as you're computing your d a,
**[3:32]** d z and so on.
**[3:33]** So, in the same way,
**[3:34]** a neural network will end up doing a backward calculation that looks like
**[3:38]** this in which you end up computing da_2,
**[3:47]** dz_2, that allows you to compute dw_2,
**[3:51]** db_2, and so on.
**[3:56]** This right to left backward calculation that is denoting with the red arrows.
**[4:04]** So, that gives you a quick overview of what a neural network looks like.
**[4:08]** It's basically taken logistic regression and repeating it twice.
**[4:12]** I know there was a lot of new notation laws,
**[4:14]** new details, don't worry about saving them,
**[4:16]** follow everything, we'll go into the details most probably in the next few videos.
**[4:21]** So, let's go on to the next video.
**[4:23]** We'll start to talk about the neural network representation.
