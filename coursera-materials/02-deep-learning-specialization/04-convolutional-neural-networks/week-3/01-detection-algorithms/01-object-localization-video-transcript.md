---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Object Localization
duration: 12 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/nEeJM/object-localization
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Object Localization — Transcript

**[0:01]** Hello and welcome back.
**[0:02]** This week you learn about object detection.
**[0:05]** This is one of the areas of computer vision that's just exploding and
**[0:08]** is working so much better than just a couple of years ago.
**[0:12]** In order to build up to object detection, you first learn about object localization.
**[0:18]** Let's start by defining what that means.
**[0:20]** You're already familiar with the image classification task where an algorithm
**[0:25]** looks at this picture and might be responsible for saying this is a car.
**[0:30]** So that was classification.
**[0:34]** The problem you learn to build in your network to address later on this video is
**[0:38]** classification with localization.
**[0:41]** Which means not only do you have to label this as say a car but
**[0:45]** the algorithm also is responsible for putting a bounding box,
**[0:49]** or drawing a red rectangle around the position of the car in the image.
**[0:55]** So that's called the classification with localization problem.
**[0:59]** Where the term localization refers to figuring out where in the picture
**[1:03]** is the car you've detective.
**[1:05]** Later this week, you then learn about the detection problem
**[1:09]** where now there might be multiple objects in the picture and
**[1:13]** ,you have to detect them all and and localized them all.
**[1:17]** And if you're doing this for an autonomous driving application,
**[1:21]** then you might need to detect not just other cars,
**[1:24]** but maybe other pedestrians and motorcycles and maybe even other objects.
**[1:29]** So you'll see that later this week.
**[1:31]** So in the terminology we'll use this week, the classification and
**[1:36]** the classification of localization problems usually have one object.
**[1:42]** Usually one big object in the middle of the image that you're trying to recognize
**[1:45]** or recognize and localize.
**[1:47]** In contrast, in the detection problem there can be multiple objects.
**[1:53]** And in fact, maybe even multiple objects of different categories
**[1:57]** within a single image.
**[1:59]** So the ideas you've learned about for image classification will be useful for
**[2:03]** classification with localization.
**[2:04]** And that the ideas you learn for
**[2:06]** localization will then turn out to be useful for detection.
**[2:10]** So let's start by talking about classification with localization.
**[2:15]** You're already familiar with the image classification problem, in which you might
**[2:20]** input a picture into a ConfNet with multiple layers so that's our ConfNet.
**[2:26]** And this results in a vector features that is fed
**[2:31]** to maybe a softmax unit that outputs the predicted clause.
**[2:38]** So if you are building a self driving car,
**[2:41]** maybe your object categories are the following.
**[2:44]** Where you might have a pedestrian, or a car, or a motorcycle, or a background.
**[2:49]** This means none of the above.
**[2:51]** So if there's no pedestrian,
**[2:53]** no car, no motorcycle, then you might have an output background.
**[2:57]** So these are your classes, they have a softmax with four possible outputs.
**[3:03]** So this is the standard classification pipeline.
**[3:07]** How about if you want to localize the car in the image as well.
**[3:12]** To do that, you can change your neural network to have
**[3:17]** a few more output units that output a bounding box.
**[3:21]** So, in particular, you can have the neural network output four
**[3:25]** more numbers, and I'm going to call them bx, by, bh, and bw.
**[3:32]** And these four numbers parameterized the bounding box of the detected object.
**[3:40]** So in these videos, I am going to use the notational convention that the upper
**[3:44]** left of the image, I'm going to denote as the coordinate (0,0),
**[3:49]** and at the lower right is (1,1).
**[3:52]** So, specifying the bounding box,
**[3:55]** the red rectangle requires specifying the midpoint.
**[4:00]** So that’s the point bx,
**[4:03]** by as well as the height, that would be bh,
**[4:08]** as well as the width, bw of this bounding box.
**[4:14]** So now if your training set contains not just the object class label,
**[4:19]** which a neural network is trying to predict up here, but
**[4:23]** it also contains four additional numbers.
**[4:26]** Giving the bounding box then you can use supervised learning to make your algorithm
**[4:31]** outputs not just a class label but also the four parameters
**[4:35]** to tell you where is the bounding box of the object you detected.
**[4:39]** So in this example the ideal bx might
**[4:42]** be about 0.5 because this is about halfway to the right to the image.
**[4:47]** by might be about 0.7 since it's about maybe 70% to the way down to the image.
**[4:55]** bh might be about 0.3 because the height of this red square is
**[5:02]** about 30% of the overall height of the image.
**[5:04]** And bw might be about 0.4 let's say because the width
**[5:10]** of the red box is about 0.4 of the overall width of the entire image.
**[5:15]** So let's formalize this a bit more in terms of how we define the target label
**[5:20]** y for this as a supervised learning task.
**[5:24]** So just as a reminder these are our four classes, and
**[5:29]** the neural network now outputs those four numbers as well as a class label,
**[5:36]** or maybe probabilities of the class labels.
**[5:40]** So, let's define the target label y as follows.
**[5:47]** Is going to be a vector where the first component pc is going to be,
**[5:53]** is there an object?
**[5:55]** So, if the object is, classes 1, 2 or 3, pc will be equal to 1.
**[6:02]** And if it's the background class, so
**[6:04]** if it's none of the objects you're trying to detect, then pc will be 0.
**[6:09]** And pc you can think of that as standing for
**[6:11]** the probability that there's an object.
**[6:15]** Probability that one of the classes you're trying to detect is there.
**[6:19]** So something other than the background class.
**[6:22]** Next if there is an object, then you wanted to output bx,
**[6:28]** by, bh and bw, the bounding box for the object you detected.
**[6:35]** And finally if there is an object, so if pc is equal to 1,
**[6:40]** you wanted to also output c1, c2 and
**[6:44]** c3 which tells us is it the class 1, class 2 or class 3.
**[6:49]** So is it a pedestrian, a car or a motorcycle.
**[6:53]** And remember in the problem we're addressing
**[6:56]** we assume that your image has only one object.
**[6:59]** So at most, one of these objects appears in the picture,
**[7:03]** in this classification with localization problem.
**[7:06]** So let's go through a couple of examples.
**[7:09]** If this is a training set image, so if that is x, then y will be
**[7:16]** the first component pc will be equal to 1 because there is an object, then bx, by,
**[7:22]** by, bh and bw will specify the bounding box.
**[7:27]** So your labeled training set will need bounding boxes in the labels.
**[7:32]** And then finally this is a car, so it's class 2.
**[7:35]** So c1 will be 0 because it's not a pedestrian,
**[7:38]** c2 will be 1 because it is car, c3 will be 0 since it is not a motorcycle.
**[7:44]** So among c1, c2 and c3 at most one of them should be equal to 1.
**[7:50]** So that's if there's an object in the image.
**[7:54]** What if there's no object in the image?
**[7:55]** What if we have a training example where x is equal to that?
**[7:59]** In this case, pc would be equal to 0, and
**[8:06]** the rest of the elements of this, will be don't cares,
**[8:10]** so I'm going to write question marks in all of them.
**[8:13]** So this is a don't care, because if there is no object in this image,
**[8:18]** then you don't care what bounding box the neural network outputs as well as
**[8:23]** which of the three objects, c1, c2, c3 it thinks it is.
**[8:27]** So given a set of label training examples, this is how you will construct x,
**[8:33]** the input image as well as y, the cost label both for
**[8:38]** images where there is an object and for images where there is no object.
**[8:42]** And the set of this will then define your training set.
**[8:47]** Finally, next let's describe the loss function
**[8:51]** you use to train the neural network.
**[8:53]** So the ground true label was y and the neural network outputs some yhat.
**[8:59]** What should be the loss be?
**[9:01]** Well if you're using squared error
**[9:05]** then the loss can be (y1 hat- y1)
**[9:10]** squared + (y2 hat- y2) squared +
**[9:15]** ...+( y8 hat- y8) squared.
**[9:19]** Notice that y here has eight components.
**[9:23]** So that goes from sum of the squares of the difference of the elements.
**[9:28]** And that's the loss if y1=1.
**[9:33]** So that's the case where there is an object.
**[9:36]** So y1= pc.
**[9:39]** So, pc = 1, that if there is an object in the image
**[9:43]** then the loss can be the sum of squares of all the different elements.
**[9:48]** The other case is if y1=0,
**[9:53]** so that's if this pc = 0.
**[9:57]** In that case the loss can be just (y1 hat-y1) squared,
**[10:04]** because in that second case, all of the rest of the components are don't care us.
**[10:11]** And so all you care about is how accurately is the neural
**[10:16]** network ourputting pc in that case.
**[10:19]** So just a recap, if y1 = 1, that's this case,
**[10:23]** then you can use squared error to penalize square deviation from
**[10:28]** the predicted, and the actual output of all eight components.
**[10:33]** Whereas if y1 = 0, then the second to the eighth components I don't care.
**[10:39]** So all you care about is how accurately is your neural network
**[10:42]** estimating y1, which is equal to pc.
**[10:48]** Just as a side comment for those of you that want to know all the details,
**[10:53]** I've used the squared error just to simplify the description here.
**[10:57]** In practice you could probably use a log like feature loss for
**[11:02]** the c1, c2, c3 to the softmax output.
**[11:06]** One of those elements usually you can use squared error or
**[11:10]** something like squared error for the bounding box coordinates and
**[11:14]** if a pc you could use something like the logistics regression loss.
**[11:19]** Although even if you use squared error it'll probably work okay.
**[11:22]** So that's how you get a neural network to not just classify an object but
**[11:27]** also to localize it.
**[11:29]** The idea of having a neural network output a bunch of real numbers
**[11:33]** to tell you where things are in a picture turns out to be a very powerful idea.
**[11:38]** In the next video I want to share with you some other places where this idea of
**[11:42]** having a neural network output a set of real numbers, almost as a regression task,
**[11:48]** can be very powerful to use elsewhere in computer vision as well.
**[11:51]** So let's go on to the next video.
