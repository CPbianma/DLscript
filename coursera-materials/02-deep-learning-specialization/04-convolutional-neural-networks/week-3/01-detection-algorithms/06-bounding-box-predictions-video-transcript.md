---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Bounding Box Predictions
duration: 14 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/9EcTO/bounding-box-predictions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Bounding Box Predictions — Transcript

**[0:00]** In the last video, you learned how to use
**[0:02]** a convolutional implementation of sliding windows,
**[0:06]** and that's more computationally efficient,
**[0:08]** but it still has a problem of not quite
**[0:11]** outputting the most accurate bounding boxes.
**[0:14]** In this video, let's see how you can get
**[0:16]** your bounding box predictions to be more accurate.
**[0:19]** With sliding windows, you take this, um,
**[0:22]** discrete set of locations and run the classifier through it.
**[0:25]** And in this case,
**[0:27]** none of the boxes really match up perfectly with the position of the car.
**[0:32]** So maybe that box was the best match.
**[0:35]** And also, it looks like in the ground truth,
**[0:38]** the perfect bounding box isn't even quite square.
**[0:41]** It's actually, you know, has a slightly wider,
**[0:44]** um, rectangle, a slightly horizontal aspect ratio.
**[0:48]** So is there a way to get this algorithm to output more accurate bounding boxes?
**[0:53]** A good way to get this output more accurate bounding boxes is
**[0:57]** with the YOLO algorithm.
**[0:59]** YOLO stands for You Only Look Once,
**[1:03]** and is an algorithm due to Joseph Redman,
**[1:06]** Santosh Devala, Raj Gershwik, and Ali Fakhadi.
**[1:09]** Here's what you do. Let's say you have an input image that 100 by 100.
**[1:14]** You're going to place down a grid on this image.
**[1:16]** And for the purposes of illustration,
**[1:19]** I'm going to use a 3 by 3 grid.
**[1:21]** Although in an actual implementation,
**[1:23]** you'd use a finer one,
**[1:24]** like maybe a 19 by 19 grid.
**[1:27]** And basic idea is you're going to take
**[1:29]** the image classification and localization algorithm that you
**[1:32]** saw in the first video of this week,
**[1:36]** and apply that to each of the nine grid cells of this image.
**[1:41]** So to be more concrete,
**[1:42]** here's how you define the labels you use for training.
**[1:46]** So for each of the nine grid cells,
**[1:48]** you specify a label Y,
**[1:51]** where the label Y is this eight-dimensional vector,
**[1:57]** same as you saw previously.
**[1:59]** You'll first output PC01,
**[2:01]** depending on whether or not there's an image in that grid cell,
**[2:05]** and then BX, BY, BH,
**[2:10]** BW to specify the bounding box if there is an image,
**[2:13]** if there is an object associated that grid cell.
**[2:16]** And then say C1, C2, C3,
**[2:19]** if you're trying to recognize three classes,
**[2:22]** not counting the background class.
**[2:23]** So if you're trying to recognize pedestrians, cars,
**[2:26]** motorcycles, and the background class,
**[2:28]** then C1, C2, C3 can be the pedestrian,
**[2:30]** car, and motorcycle classes.
**[2:33]** So in this image,
**[2:35]** we have nine grid cells.
**[2:37]** So you'd have a vector like this for each of the grid cells.
**[2:41]** So let's start to the upper left grid cell,
**[2:45]** this one up here.
**[2:47]** For that one, there is no object.
**[2:49]** So the label vector Y for the upper left grid cell would be 0,
**[2:55]** and then don't cares for the rest of these.
**[2:59]** And the output label Y would be the same for this grid cell,
**[3:04]** and this grid cell,
**[3:05]** and all the grid cells with nothing,
**[3:07]** with no interesting object in them.
**[3:10]** Now, how about this grid cell?
**[3:12]** To give a bit more detail,
**[3:14]** this image has two objects.
**[3:16]** And what the YOLO algorithm does is it takes
**[3:18]** the midpoint of each of the two objects and then
**[3:21]** assigns the object to the grid cell containing the midpoint.
**[3:25]** So the left car is assigned to this grid cell,
**[3:29]** and the car on the right,
**[3:31]** which has this midpoint,
**[3:32]** is assigned to this grid cell.
**[3:36]** And so even though the central grid cell has, you know,
**[3:40]** some parts of both cars will
**[3:42]** pretend the central grid cell has no interesting object.
**[3:45]** So for the central grid cell,
**[3:47]** the class label Y also looks like this vector with no object,
**[3:51]** and it's the first component PC,
**[3:53]** and then the rest are don't cares.
**[3:55]** Whereas for this cell,
**[3:57]** this cell that I've circled in green on the left,
**[4:00]** the target label Y would be as follows.
**[4:03]** There is an object,
**[4:04]** and then you write BX,
**[4:06]** BY, BH, BW to specify the position of this bounding box.
**[4:12]** And then you have, let's see,
**[4:14]** if class 1 was a pedestrian,
**[4:17]** then that was 0, class 2 is a car,
**[4:19]** that's 1, class 3 was a motorcycle, that's 0.
**[4:23]** And then similarly, for the grid cell on the right,
**[4:26]** because that does have an object in it, you know,
**[4:28]** it will also have some vector like this,
**[4:33]** as the target label corresponding to the grid cell on the right.
**[4:37]** So for each of these nine grid cells,
**[4:40]** you end up with a eight-dimensional output vector.
**[4:44]** And because you have 3 by 3 grid cells,
**[4:48]** you have nine grid cells,
**[4:49]** the total volume of the output is going to be 3 by 3 by 8.
**[4:57]** So the target output is going to be 3 by 3 by 8,
**[5:01]** because you have 3 by 3 grid cells,
**[5:04]** and for each of the 3 by 3 grid cells,
**[5:07]** you have a eight-dimensional Y vector.
**[5:12]** So the target output volume is 3 by 3 by 8,
**[5:16]** where for example, this 1 by 1 by 8 volume in the upper left,
**[5:21]** corresponds to the target output vector for
**[5:24]** the upper left of the nine grid cells.
**[5:27]** And so for each of the 3 by 3 positions,
**[5:30]** for each of these nine grid cells,
**[5:32]** there's a corresponding eight-dimensional target vector Y that you want in the output,
**[5:38]** some of which could be don't cares if there's no object there.
**[5:40]** And that's why the total target output,
**[5:43]** the output label for this image is now itself a 3 by 3 by 8 volume.
**[5:48]** So now to train your neural network,
**[5:51]** the input is a 100 by 100 by 3.
**[5:56]** Now that's the input image.
**[5:58]** And then you have a usual conf net with conf layers,
**[6:03]** max pool layers, and so on.
**[6:07]** So that in the end, you would have this,
**[6:10]** should choose the conf layers and the max pool layers and so on,
**[6:15]** so that this eventually maps to a 3 by 3 by 8 output volume.
**[6:21]** And so what you do is you have an input X,
**[6:24]** which is the input image like that,
**[6:26]** and you have these target labels Y,
**[6:28]** which are 3 by 3 by 8,
**[6:29]** and you use backpropagation to train the neural network to map from
**[6:34]** any input X to this type of output volume Y.
**[6:38]** So the advantage of this algorithm is that the neural network
**[6:42]** outputs precise bounding boxes as follows.
**[6:46]** So at test time, what you do is you feed in
**[6:49]** an input image X and run for a prop until you get this output Y.
**[6:53]** And then for each of the nine outputs,
**[6:56]** for each of the 3 by 3 positions in which the output,
**[6:59]** you can then just read off one or zero.
**[7:02]** Is there an object associated with that one of the nine positions?
**[7:06]** And if there is an object,
**[7:08]** what object it is,
**[7:09]** and what is the bounding box for the objects in that grid cell?
**[7:15]** And so long as you don't have more than one object in each grid cell,
**[7:19]** this algorithm should work okay.
**[7:21]** And the problem of having multiple objects within
**[7:23]** a grid cell is something we'll address later.
**[7:26]** But in practice, I've used a relatively small 3 by 3 grid.
**[7:31]** In practice, you might use a much finer grid,
**[7:34]** maybe 19 by 19.
**[7:36]** So you end up with 19 by 19 by 8.
**[7:38]** And that also makes your grid much finer and
**[7:42]** reduces the chance that there are multiple objects assigned to the same grid cell.
**[7:46]** And just as a reminder,
**[7:48]** the way you assign an object to grid cell is you look at the midpoint of an object,
**[7:53]** and then you assign that object to
**[7:56]** whichever one grid cell contains the midpoint of the object.
**[7:59]** So each object, even if the object spans multiple grid cells,
**[8:03]** that object is assigned only to one of the nine grid cells or
**[8:07]** one of the 3 by 3 or one of the 19 by 19 grid cells.
**[8:11]** And with a 19 by 19 grid,
**[8:13]** the chance of a object of two midpoints of
**[8:16]** objects appearing in the same grid cell is just a bit smaller.
**[8:20]** So notice two things.
**[8:23]** First, this is a lot like
**[8:24]** the image classification and localization algorithm that we
**[8:28]** talked about in the first video of this week,
**[8:31]** in that it outputs the bounding box coordinates explicitly.
**[8:35]** And so this allows the neural network to output bounding boxes of, you know,
**[8:39]** any aspect ratio, um,
**[8:41]** as well as output much more precise coordinates that aren't just
**[8:45]** dictated by the stride size of your sliding windows classifier.
**[8:49]** And second, this is a convolutional implementation, right?
**[8:54]** You're not implementing this algorithm nine times,
**[8:58]** on the 3 by 3 grid,
**[8:59]** or if you're using a 19 by 19 grid,
**[9:03]** 19 squared is 361.
**[9:05]** So you're not running the same algorithm,
**[9:07]** you know, 361 times or 19 squared times.
**[9:10]** Instead, this is one single convolutional implementation where you use
**[9:14]** one conf net with a lot of shared computation between
**[9:19]** all the computations needed for all of your, you know,
**[9:22]** 3 by 3 or all your 9 by- all of your 19 by 19 grid cells.
**[9:26]** So this is a pretty efficient algorithm.
**[9:28]** And in fact, uh, one nice thing about the YOLO algorithm,
**[9:32]** which- which accounts for its popularity,
**[9:34]** is because this is a convolutional implementation,
**[9:37]** it actually runs very fast.
**[9:38]** So this works even for real-time object detection.
**[9:42]** Now, before wrapping up,
**[9:43]** there's one more detail I want to share with you,
**[9:46]** which is how do you encode these bounding boxes,
**[9:50]** BX, BY, BH, BW?
**[9:52]** Let's discuss that on the next slide.
**[9:55]** So given these two cars,
**[9:58]** remember we have the 3 by 3 grid.
**[10:01]** Let's take the example of the car on the right.
**[10:04]** So in this grid cell,
**[10:07]** there is an object and so the target label Y will be 1,
**[10:12]** that was PC is equal to 1,
**[10:14]** and then BX, BY, BH, BW, and then 0, 1, 0.
**[10:20]** So how do you specify the bounding box?
**[10:23]** In the YOLO algorithm, relative to this square,
**[10:28]** we're going to take the convention that
**[10:29]** the upper left point here is 0, 0,
**[10:32]** and this lower right point is 1, 1.
**[10:35]** So to specify the position of that midpoint,
**[10:38]** that orange dot, BX might be- let's see,
**[10:43]** X looks like it's about 0.4,
**[10:46]** since it's maybe about 0.4 of the way to the right,
**[10:49]** and then Y looks like that's maybe 0.3.
**[10:55]** And then the height of the bounding box is specified as
**[10:59]** a fraction of the overall width of this box.
**[11:03]** So the width of this red box is maybe 90 percent of that blue line.
**[11:10]** And so BH, 0.5.
**[11:14]** And the height of this is maybe one-half of
**[11:18]** the overall height of the grid cell.
**[11:21]** So in that case, BW would be, let's say, 0.9.
**[11:26]** So in other words, this BX, BY,
**[11:28]** BH, BW are specified relative to the grid cell.
**[11:33]** And so BX and BY,
**[11:35]** this has to be between 0 and 1, right?
**[11:38]** Because pretty much by definition,
**[11:40]** that orange dot is within the bounds of that grid cell it's assigned to.
**[11:44]** If it wasn't between 0 and 1,
**[11:46]** if it was outside the square,
**[11:48]** then it would have been assigned to a different grid cell.
**[11:51]** But these could be greater than 1.
**[11:54]** In particular, if you had a car where the bounding box was that,
**[11:58]** then the height and width of a bounding box,
**[12:00]** this could be greater than 1.
**[12:03]** So there are multiple ways of specifying the bounding boxes.
**[12:06]** But this would be one convention that's quite reasonable.
**[12:10]** Although if you read the YOLO research papers,
**[12:13]** there are other parametrizations that work even a little bit better.
**[12:16]** But I hope this gives one reasonable convention that should work okay.
**[12:22]** Although there are some more complicated parametrizations
**[12:25]** involving sigmoid functions to make sure this is between 0 and 1,
**[12:29]** and using an exponential parametrization to make sure that these are non-negative.
**[12:34]** Since 0.9, 0.5, this has to be greater than or equal to 0.
**[12:38]** There are some other more advanced parametrizations
**[12:41]** that work even a little bit better.
**[12:43]** But the one you saw here should work okay.
**[12:46]** So that's it for the YOLO or the You Only Look Once algorithm.
**[12:51]** In the next few videos,
**[12:52]** I'll show you a few other ideas that will help make this algorithm even better.
**[12:57]** In the meantime, if you want,
**[12:59]** you can take a look at the YOLO paper reference at
**[13:03]** the bottom of these past couple of slides I used.
**[13:06]** Although just one warning if you take a look at these papers,
**[13:09]** which is the YOLO paper is one of the harder papers to read.
**[13:13]** I remember when I was reading this paper for the first time,
**[13:16]** I had a really hard time figuring out what was going on,
**[13:19]** and I wound up asking a couple of my friends,
**[13:22]** very good researchers to help me figure it out,
**[13:25]** and even they had a hard time understanding some of the details of the paper.
**[13:29]** So if you look at the paper,
**[13:31]** just it's okay if you have a hard time figuring it out.
**[13:35]** I wish it was more uncommon,
**[13:37]** but it's not that uncommon sadly for even senior researchers to read
**[13:41]** research papers and have a hard time figuring out the details,
**[13:45]** and have to look at open source code,
**[13:47]** or contact the authors,
**[13:48]** or something else to figure out the details of these algorithms.
**[13:51]** But don't let me stop you from taking a look at the paper yourself though if you wish,
**[13:56]** but this is one of the harder ones.
**[13:57]** So with that though, you now understand the basics of the YOLO algorithm.
**[14:02]** Let's go on to some additional pieces that will make this algorithm work even better.
