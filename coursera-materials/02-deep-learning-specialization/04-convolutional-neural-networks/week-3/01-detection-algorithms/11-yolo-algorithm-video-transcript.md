---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: YOLO Algorithm
duration: 7 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/fF3O0/yolo-algorithm
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# YOLO Algorithm — Transcript

**[0:00]** You've already seen most of the components of object detection.
**[0:03]** In this video, let's put all the components
**[0:06]** together to form the YOLO object detection algorithm.
**[0:10]** First, let's see how you construct your training set.
**[0:14]** Suppose you're trying to train an algorithm to detect
**[0:16]** three objects: pedestrians, cars, and motorcycles.
**[0:19]** And you will need to explicitly have the full background class,
**[0:23]** so just the class labels here.
**[0:25]** If you're using two anchor boxes,
**[0:28]** then the outputs y will be three by three because you are using three by three grid cell,
**[0:33]** by two, this is the number of anchors,
**[0:36]** by eight because that's the dimension of this.
**[0:39]** Eight is actually five which is plus the number of classes.
**[0:45]** So five because you have Pc and then the bounding boxes,
**[0:49]** that's five, and then C1, C2, C3.
**[0:53]** That dimension is equal to the number of classes.
**[0:56]** And you can either view this as three by three by two by eight,
**[0:59]** or by three by three by sixteen.
**[1:03]** So to construct the training set,
**[1:05]** you go through each of these nine grid cells and form the appropriate target vector y.
**[1:11]** So take this first grid cell,
**[1:13]** there's nothing worth detecting in that grid cell.
**[1:16]** None of the three classes pedestrian, car and motocycle,
**[1:19]** appear in the upper left grid cell and so,
**[1:22]** the target y corresponding to that grid cell would be equal to this.
**[1:27]** Where Pc for the first anchor box
**[1:31]** is zero because there's nothing associated for the first anchor box,
**[1:34]** and is also zero for the second anchor box and
**[1:37]** so on all of these other values are don't cares.
**[1:42]** Now, most of the grid cells have nothing in them,
**[1:45]** but for that box over there,
**[1:47]** you would have this target vector y.
**[1:53]** So assuming that your training set has a bounding box like this for the car,
**[1:58]** it's just a little bit wider than it is tall.
**[2:01]** And so, if your anchor boxes are that,
**[2:04]** this is a anchor box one,
**[2:05]** this is anchor box two,
**[2:07]** then the red box has just slightly higher IoU with anchor box two.
**[2:12]** And so, the car gets associated with this lower portion of the vector.
**[2:17]** So notice then that Pc associate anchor box one is zero.
**[2:22]** So you have don't cares all these components.
**[2:24]** Then you have this Pc is equal to one,
**[2:28]** then you should use these to specify the position of the red bounding box,
**[2:33]** and then specify that the correct object is class two.
**[2:38]** Right that it is a car.
**[2:41]** So you go through this and for each of
**[2:44]** your nine grid positions each of your three by three grid positions,
**[2:47]** you would come up with a vector like this.
**[2:50]** Come up with a 16 dimensional vector.
**[2:52]** And so, that's why the final output volume is going to be 3 by 3 by 16.
**[2:59]** Oh and as usual for simplicity on the slide I've used a 3 by 3 the grid.
**[3:04]** In practice it might be more like a 19 by 19 by 16.
**[3:09]** Or in fact if you use more anchor boxes,
**[3:12]** maybe 19 by 19 by 5 x 8 because five times eight is 40.
**[3:17]** So it will be 19 by 19 by 40.
**[3:20]** That's if you use five anchor boxes.
**[3:23]** So that's training and you train ConvNet that inputs an image,
**[3:30]** maybe 100 by 100 by 3,
**[3:32]** and your ConvNet would then finally output this output volume in our example,
**[3:39]** 3 by 3 by 16 or 3 by 3 by 2 by 8.
**[3:43]** Next, let's look at how your algorithm can make predictions.
**[3:47]** Given an image, your neural network will output this by 3 by 3 by 2 by 8 volume,
**[3:53]** where for each of the nine grid cells you get a vector like that.
**[3:57]** So for the grid cell here on the upper left,
**[4:00]** if there's no object there,
**[4:02]** hopefully, your neural network will output zero here,
**[4:06]** and zero here, and it will output some other values.
**[4:08]** Your neural network can't output a question mark,
**[4:11]** can't output a don't care.
**[4:12]** So I'll put some numbers for the rest.
**[4:15]** But these numbers will basically be ignored because
**[4:17]** the neural network is telling you that there's no object there.
**[4:20]** So it doesn't really matter whether the output is a bounding box or there's is a car.
**[4:23]** So basically just be some set of numbers, more or less noise.
**[4:28]** In contrast, for this box over here hopefully,
**[4:32]** the value of y to the output for that box at the bottom left,
**[4:37]** hopefully would be something like zero for bounding box one.
**[4:40]** And then just open a bunch of numbers, just noise.
**[4:43]** Hopefully, you'll also output a set of numbers that
**[4:47]** corresponds to specifying a pretty accurate bounding box for the car.
**[4:52]** So that's how the neural network will make predictions.
**[4:56]** Finally, you run this through non-max suppression.
**[5:00]** So just to make it interesting.
**[5:02]** Let's look at the new test set image.
**[5:04]** Here's how you would run non-max suppression.
**[5:08]** If you're using two anchor boxes,
**[5:10]** then for each of the non-grid cells,
**[5:12]** you get two predicted bounding boxes.
**[5:15]** Some of them will have very low probability,
**[5:17]** very low Pc, but you still get
**[5:20]** two predicted bounding boxes for each of the nine grid cells.
**[5:24]** So let's say, those are the bounding boxes you get.
**[5:27]** And notice that some of the bounding boxes can go
**[5:30]** outside the height and width of the grid cell that they came from.
**[5:34]** Next, you then get rid of the low probability predictions.
**[5:38]** So get rid of the ones that even the neural network says,
**[5:41]** gee this object probably isn't there.
**[5:44]** So get rid of those.
**[5:45]** And then finally if you have three classes you're trying to detect,
**[5:49]** you're trying to detect pedestrians, cars and motorcycles.
**[5:53]** What you do is, for each of the three classes,
**[5:56]** independently run non-max suppression for
**[5:59]** the objects that were predicted to come from that class.
**[6:03]** But use non-max suppression for the predictions of the pedestrians class,
**[6:07]** run non-max suppression for the car class,
**[6:10]** and non-max suppression for the motorcycle class.
**[6:13]** But run that basically three times to generate the final predictions.
**[6:17]** And so, the output of this is hopefully that you will have
**[6:20]** detected all the cars and all the pedestrians in this image.
**[6:25]** So that's it for the YOLO object detection algorithm.
**[6:29]** Which is really one of the most effective object detection algorithms,
**[6:33]** that also encompasses many of the best ideas across
**[6:35]** the entire computer vision literature that relate to object detection.
**[6:41]** And you get a chance to practice implementing many components of this yourself,
**[6:46]** in this week's problem exercise.
**[6:47]** So I hope you enjoy this week's problem exercise.
**[6:51]** There's also an optional video that follows this one
**[6:54]** which you can either watch or not watch as you please.
**[6:57]** But either way I also look forward to seeing you next week.
