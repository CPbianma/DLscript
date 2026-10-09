---
type: video-transcript
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: Learning from Multiple Tasks
item_title: Multi-task Learning
duration: 13 min
source_url: https://www.coursera.org/learn/machine-learning-projects/lecture/l9zia/multi-task-learning
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Multi-task Learning — Transcript

**[0:00]** So whereas in transfer learning, you have a sequential process
**[0:03]** where you learn from task A and then transfer that to task B.
**[0:07]** In multi-task learning, you start off simultaneously,
**[0:10]** trying to have one neural network do several things at the same time.
**[0:13]** And then each of these task helps hopefully all of the other task.
**[0:17]** Let's look at an example.
**[0:20]** Let's say you're building an autonomous vehicle, building a self driving car.
**[0:24]** Then your self driving car would need to detect several different things such as pedestrians,
**[0:28]** detect other cars, detect stop signs.
**[0:37]** And also detect traffic lights and also other things.
**[0:43]** So for example, in this example on the left, there is a stop sign in this image
**[0:47]** and there is a car in this image but there aren't any pedestrians or traffic lights.
**[0:53]** So if this image is an input for an example, x(i),
**[0:58]** then Instead of having one label y(i), you would actually a four labels.
**[1:02]** In this example, there are no pedestrians, there is a car,
**[1:05]** there is a stop sign and there are no traffic lights.
**[1:08]** And if you try and detect other things,
**[1:10]** there may be y(i) has even more dimensions.
**[1:12]** But for now let's stick with these four.
**[1:14]** So y(i) is a 4 by 1 vector.
**[1:18]** And if you look at the training test labels as a whole,
**[1:22]** then similar to before, we'll stack the training data's
**[1:27]** labels horizontally as follows, y(1) up to y(m).
**[1:32]** Except that now y(i) is a 4 by 1 vector so each of these is a tall column vector.
**[1:39]** And so this matrix Y is now a 4 by m matrix, whereas previously,
**[1:45]** when y was single real number, this would have been a 1 by m matrix.
**[1:49]** So what you can do is now train a neural network to predict these values of y.
**[1:55]** So you can have a neural network input x and output
**[1:57]** now a four dimensional value for y.
**[2:00]** Notice here for the output there I've drawn four nodes.
**[2:04]** And so the first node when we try to predict is there a pedestrian
**[2:09]** in this picture.
**[2:10]** The second output will predict is there a car here,
**[2:13]** predict is there a stop sign and this will predict maybe is there a traffic light.
**[2:20]** So y hat here is four dimensional.
**[2:26]** So to train this neural network, you now need to define the loss for
**[2:29]** the neural network.
**[2:32]** And so given a predicted output y hat i which is 4 by 1 dimensional.
**[2:39]** The loss averaged over your entire training set
**[2:43]** would be 1 over m sum from i = 1 through m,
**[2:48]** sum from j = 1 through 4 of the losses of the individual predictions.
**[2:59]** So it's just summing over at the four components of pedestrian, car, stop sign,
**[3:03]** traffic lights.
**[3:04]** And this script L is the usual logistic loss.
**[3:14]** So just to write this out,
**[3:15]** this is -yj i log y hat ji- 1- y
**[3:24]** log 1- y hat.
**[3:31]** And the main difference compared to the earlier binding classification examples is
**[3:36]** that you're now summing over j equals 1 through 4.
**[3:40]** And the main difference between this and softmax regression, is that unlike softmax
**[3:45]** regression, which assigned a single label to single example.
**[3:50]** This one image can have multiple labels.
**[3:55]** So you're not saying that each image is either
**[4:00]** a picture of a pedestrian, or a picture of car, a picture of a stop sign, picture of a traffic light.
**[4:04]** You're asking for each picture, does it have a pedestrian, or a car a stop sign or
**[4:09]** traffic light, and multiple objects could appear in the same image.
**[4:11]** In fact, in the example on the previous slide, we had both a car and
**[4:16]** a stop sign in that image, but no pedestrians and traffic lights.
**[4:19]** So you're not assigning a single label to an image,
**[4:22]** you're going through the different classes and asking for
**[4:25]** each of the classes does that class, does that type of object appear in the image?
**[4:31]** So that's why I'm saying that with this setting, one image can have
**[4:34]** multiple labels.
**[4:37]** If you train a neural network to minimize this cost function,
**[4:42]** you are carrying out multi-task learning.
**[4:45]** Because what you're doing is building a single neural network that is looking at
**[4:50]** each image and basically solving four problems.
**[4:53]** It's trying to tell you does each image have each of these four objects in it.
**[5:00]** And one other thing you could have done is just train four separate neural networks,
**[5:03]** instead of train one network to do four things.
**[5:06]** But if some of the earlier features in neural network can be shared between these
**[5:11]** different types of objects, then you find that
**[5:13]** training one neural network to do four things results in better performance than
**[5:17]** training four completely separate neural networks to do the four tasks separately.
**[5:23]** So that's the power of multi-task learning.
**[5:26]** And one other detail,
**[5:28]** so far I've described this algorithm as if every image had every single label.
**[5:33]** It turns out that multi-task learning also works even if some of the images we'll
**[5:37]** label only some of the objects.
**[5:39]** So the first training example, let's say someone, your labeler had told you there's
**[5:43]** a pedestrian, there's no car, but they didn't bother to label whether or
**[5:46]** not there's a stop sign or whether or not there's a traffic light.
**[5:49]** And maybe for the second example, there is a pedestrian, there is a car, but
**[5:52]** again the labeler, when they looked at that image, they just didn't label it,
**[5:56]** whether it had a stop sign or whether it had a traffic light, and so on.
**[5:59]** And maybe some examples are fully labeled, and maybe some examples,
**[6:03]** they were just labeling for the presence and absence of cars so
**[6:06]** there's some question marks, and so on.
**[6:08]** So with a data set like this, you can still train your learning algorithm
**[6:13]** to do four tasks at the same time, even when some images have
**[6:16]** only a subset of the labels and others are sort of question marks or don't cares.
**[6:21]** And the way you train your algorithm, even when some of these labels are question marks
**[6:24]** or really unlabeled is that in this sum over
**[6:29]** j from 1 to 4, you would sum only over
**[6:34]** values of j with a 0 or 1 label.
**[6:41]** So whenever there's a question mark, you just omit that term from summation but
**[6:46]** just sum over only the values where there is a label.
**[6:51]** And so that allows you to use datasets like this as well.
**[6:54]** So when does multi-task learning makes sense?
**[6:57]** So when does multi-task learning make sense?
**[6:59]** I'll say it makes sense usually when three things are true.
**[7:03]** One is if your training on a set of tasks that could benefit from
**[7:06]** having shared low-level features.
**[7:08]** So for the autonomous driving example, it makes sense that recognizing traffic
**[7:13]** lights and cars and pedestrians, those should have similar features that
**[7:16]** could also help you recognize stop signs, because these are all features of roads.
**[7:23]** Second, this is less of a hard and fast rule, so this isn't always true.
**[7:28]** But what I see from a lot of successful multi-task learning settings is that
**[7:31]** the amount of data you have for each task is quite similar.
**[7:35]** So if you recall from transfer learning, you learn from some task A and
**[7:39]** transfer it to some task B.
**[7:41]** So if you have a million examples for task A then and
**[7:46]** 1,000 examples for task B, then all the knowledge you learned from that million examples could really
**[7:51]** help augment the much smaller data set you have for task B.
**[7:56]** Well how about multi-task learning?
**[7:58]** In multi-task learning you usually have a lot more tasks than just two.
**[8:01]** So maybe you have, previously we had 4 tasks but let's say you have 100 tasks.
**[8:07]** And you're going to do multi-task learning to try to recognize 100 different types of
**[8:11]** objects at the same time.
**[8:12]** So what you may find is that you may have 1,000 examples per task
**[8:17]** and so if you focus on the performance of just one task,
**[8:20]** let's focus on the performance on the 100th task, you can call A100.
**[8:25]** If you are trying to do this final task in isolation,
**[8:28]** you would have had just a thousand examples to train this one task,
**[8:32]** this one of the 100 tasks that by training on these 99 other tasks.
**[8:37]** These in aggregate have 99,000 training examples which
**[8:42]** could be a big boost, could give a lot of knowledge to argument this otherwise,
**[8:46]** relatively small 1,000 example training set that you have for task A100.
**[8:52]** And symmetrically every one of the other 99 tasks can provide some data or provide
**[8:57]** some knowledge that help every one of the other tasks in this list of 100 tasks.
**[9:02]** So the second bullet isn't a hard and fast rule but what I tend to look at is
**[9:07]** if you focus on any one task, for that to get a big boost for multi-task learning,
**[9:13]** the other tasks in aggregate need to have quite a lot more data than for
**[9:17]** that one task.
**[9:18]** And so one way to satisfy that is if a lot of tasks like we have in this example on
**[9:22]** the right, and if the amount of data you have in each task is quite similar.
**[9:27]** But the key really is that if you already have 1,000 examples for 1 task,
**[9:31]** then for all of the other tasks you better have a lot more than 1,000 examples if
**[9:36]** those other other task are meant to help you do better on this final task.
**[9:40]** And finally multi-task learning tends to make more sense when you can train a big
**[9:44]** enough neural network to do well on all the tasks.
**[9:47]** So the alternative to multi-task learning would be
**[9:50]** to train a separate neural network for each task.
**[9:52]** So rather than training one neural network for pedestrian, car, stop sign, and
**[9:56]** traffic light detection, you could have trained one neural network for
**[9:59]** pedestrian detection, one neural network for car detection, one neural network for
**[10:02]** stop sign detection, and one neural network for traffic light detection.
**[10:06]** So what a researcher, Rich Carona, found many years ago was that the only times
**[10:10]** multi-task learning hurts performance compared to training
**[10:14]** separate neural networks is if your neural network isn't big enough.
**[10:18]** But if you can train a big enough neural network, then multi-task learning
**[10:22]** certainly should not or should very rarely hurt performance.
**[10:26]** And hopefully it will actually help performance compared to if you
**[10:29]** were training neural networks to do these different tasks in isolation.
**[10:33]** So that's it for multi-task learning.
**[10:35]** In practice, multi-task learning is used much less often than transfer learning.
**[10:40]** I see a lot of applications of transfer learning where you
**[10:43]** have a problem you want to solve with a small amount of data.
**[10:46]** So you find a related problem with a lot of data to learn something and
**[10:49]** transfer that to this new problem.
**[10:51]** But multi-task learning is just more rare that you have a huge set of tasks you want
**[10:56]** to use that you want to do well on,
**[10:57]** you can train all of those tasks at the same time.
**[11:00]** Maybe the one example is computer vision.
**[11:02]** In object detection I see more applications of
**[11:05]** multi-task learning where one neural network trying to detect a whole bunch of objects at the same
**[11:09]** time works better than different neural networks trained separately to detect objects.
**[11:13]** But I would say that on average transfer learning is used much more today
**[11:17]** than multi-task learning, but both are useful tools to have in your arsenal.
**[11:22]** So to summarize,
**[11:23]** multi-task learning enables you to train one neural network to do many tasks and
**[11:28]** this can give you better performance than if you were to do the tasks in isolation.
**[11:32]** Now one note of caution, in practice I see that transfer learning is used
**[11:37]** much more often than multi-task learning.
**[11:39]** So I do see a lot of tasks where if you want to solve a machine learning problem
**[11:43]** but you have a relatively small data set, then transfer learning can really help.
**[11:47]** Where if you find a related problem but you have a much bigger data set,
**[11:50]** you can train in your neural network from there and
**[11:52]** then transfer it to the problem where we have very low data.
**[11:54]** So transfer learning is used a lot today.
**[11:57]** There are some applications of transfer multi-task learning as well, but
**[12:01]** multi-task learning I think is used much less often than transfer learning.
**[12:05]** And maybe the one exception is computer vision object detection,
**[12:09]** where I do see a lot of applications of training a neural network
**[12:12]** to detect lots of different objects.
**[12:13]** And that works better than training separate neural networks and
**[12:16]** detecting the visual objects.
**[12:18]** But on average I think that even though transfer learning and
**[12:21]** multi-task learning often you're presented in a similar way, in practice I've
**[12:26]** seen a lot more applications of transfer learning than of multi-task learning.
**[12:30]** I think because often it's just difficult to set up or to find so many different
**[12:34]** tasks that you would actually want to train a single neural network for.
**[12:37]** Again, with some sort of computer vision,
**[12:39]** object detection examples being the most notable exception.
**[12:43]** So that's it for multi-task learning.
**[12:45]** Multi-task learning and
**[12:46]** transfer learning are both important tools to have in your tool bag.
**[12:50]** And finally, I'd like to move on to discuss end-to-end deep learning.
**[12:54]** So let's go onto the next video to discuss end-to-end learning.
