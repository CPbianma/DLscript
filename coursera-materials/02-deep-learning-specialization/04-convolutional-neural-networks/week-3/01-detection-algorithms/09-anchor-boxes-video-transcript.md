---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Anchor Boxes
duration: 10 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/yNwO0/anchor-boxes
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Anchor Boxes — Transcript

**[0:00]** One of the problems with object detection as you have seen it so far is
**[0:04]** that each of the grid cells can detect only one object.
**[0:08]** What if a grid cell wants to detect multiple objects?
**[0:12]** Here is what you can do.
**[0:14]** You can use the idea of anchor boxes.
**[0:16]** Let's start with an example.
**[0:17]** Let's say you have an image like this.
**[0:20]** And for this example,
**[0:22]** I am going to continue to use a 3 by 3 grid.
**[0:26]** Notice that the midpoint of the pedestrian and the midpoint of the car are
**[0:31]** in almost the same place and both of them fall into the same grid cell.
**[0:37]** So, for that grid cell,
**[0:38]** if Y outputs this vector where you are detecting three causes,
**[0:44]** pedestrians, cars and motorcycles,
**[0:48]** it won't be able to output two detections.
**[0:51]** So I have to pick one of the two detections to output.
**[0:55]** With the idea of anchor boxes,
**[0:57]** what you are going to do,
**[0:59]** is pre-define two different shapes called, anchor boxes or anchor box shapes.
**[1:03]** And what you are going to do is now,
**[1:08]** be able to associate two predictions with the two anchor boxes.
**[1:13]** And in general, you might use more anchor boxes,
**[1:15]** maybe five or even more.
**[1:17]** But for this video, I am just going to use
**[1:20]** two anchor boxes just to make the description easier.
**[1:23]** So what you do is you define the cross label to be,
**[1:27]** instead of this vector on the left,
**[1:30]** you basically repeat this twice.
**[1:33]** S, you will have PC, PX, PY,
**[1:35]** PH, PW, C1, C2, C3,
**[1:39]** and these are the eight outputs associated with anchor box 1.
**[1:46]** And then you repeat that PC,
**[1:50]** PX and so on down to C1,
**[1:51]** C2, C3, and other eight outputs associated with anchor box 2.
**[1:59]** So, because the shape of
**[2:01]** the pedestrian is more similar to the shape of anchor box 1 and anchor box 2,
**[2:06]** you can use these eight numbers to encode that PC as one,
**[2:13]** yes there is a pedestrian.
**[2:15]** Use this to encode the bounding box around the pedestrian,
**[2:20]** and then use this to encode that that object is a pedestrian.
**[2:26]** And then because the box
**[2:29]** around the car is more similar to the shape of anchor box 2 than anchor box 1,
**[2:32]** you can then use this to encode that the second object here is the car,
**[2:40]** and have the bounding box and so
**[2:42]** on be all the parameters associated with the detected car.
**[2:45]** So to summarize, previously,
**[2:50]** before you are using anchor boxes,
**[2:51]** you did the following,
**[2:53]** which is for each object in the training set and the training set image,
**[2:57]** it was assigned to the grid cell that corresponds to that object's midpoint.
**[3:03]** And so the output Y was 3 by 3 by 8 because you have a 3 by 3 grid.
**[3:11]** And for each grid position,
**[3:13]** we had that output vector which is PC, then the bounding box, and C1, C2, C3.
**[3:18]** With the anchor box,
**[3:19]** you now do that following.
**[3:21]** Now, each object is assigned to the same grid cell as before,
**[3:27]** assigned to the grid cell that contains the object's midpoint,
**[3:29]** but it is assigned to a grid cell and
**[3:33]** anchor box with the highest IoU with the object's shape.
**[3:41]** So, you have two anchor boxes,
**[3:43]** you will take an object and see.
**[3:45]** So if you have an object with this shape,
**[3:50]** what you do is take your two anchor boxes.
**[3:53]** Maybe one anchor box is this this shape that's anchor box 1,
**[3:55]** maybe anchor box 2 is this shape,
**[3:58]** and then you see which of the two anchor boxes has a higher IoU,
**[4:01]** will be drawn through bounding box.
**[4:04]** And whichever it is,
**[4:05]** that object then gets assigned not just to a grid cell but to a pair.
**[4:11]** It gets assigned to grid cell comma anchor box pair.
**[4:18]** And that's how that object gets encoded in the target label.
**[4:22]** And so now, the output Y is going to be 3 by 3 by 16.
**[4:31]** Because as you saw on the previous slide,
**[4:34]** Y is now 16 dimensional.
**[4:36]** Or if you want,
**[4:37]** you can also view this as 3 by 3 by 2 by 8
**[4:42]** ,because there are now two anchor boxes and Y is eight dimensional.
**[4:48]** And dimension of Y being eight was because we have three objects causes
**[4:54]** ; if you have more objects than the dimension of Y would be even higher.
**[5:01]** So let's go through a complete example.
**[5:04]** For this grid cell,
**[5:09]** let's specify what is Y.
**[5:12]** So the pedestrian is more similar to the shape of anchor box 1.
**[5:21]** So for the pedestrian,
**[5:22]** we're going to assign it to the top half of this vector.
**[5:25]** So yes, there is an object,
**[5:27]** there will be some bounding box associated at the pedestrian.
**[5:31]** And I guess if a pedestrian is cos one,
**[5:33]** then we see one as one, and then zero, zero.
**[5:36]** And then the shape of the car is more similar to anchor box 2.
**[5:41]** And so the rest of this vector will be
**[5:43]** one and then the bounding box associated with the car,
**[5:47]** and then the car is C2,
**[5:51]** so there's zero, one, zero.
**[5:53]** And so that's the label Y for
**[5:56]** that lower middle grid cell that this arrow was pointing to.
**[6:02]** Now, what if this grid cell only had a car and had no pedestrian?
**[6:09]** If it only had a car,
**[6:11]** then assuming that the shape of the bounding box around
**[6:14]** the car is still more similar to anchor box 2,
**[6:18]** then the target label Y,
**[6:20]** if there was just a car there and the pedestrian had gone away,
**[6:24]** it will still be the same for the anchor box 2 component.
**[6:30]** Remember that this is a part of the vector corresponding to anchor box 2.
**[6:37]** And for the part of the vector corresponding to anchor box 1,
**[6:42]** what you do is you just say there is no object there.
**[6:46]** So PC is zero,
**[6:47]** and then the rest of these will be don't cares.
**[6:52]** Now, just some additional details.
**[6:55]** What if you have two anchor boxes but three objects in the same grid cell?
**[6:59]** That's one case that this algorithm doesn't handle well.
**[7:04]** Hopefully, it won't happen.
**[7:06]** But if it does, this algorithm doesn't have a great way of handling it.
**[7:11]** I will just influence some default tiebreaker for that case.
**[7:15]** Or what if you have two objects associated with the same grid cell,
**[7:17]** but both of them have the same anchor box shape?
**[7:21]** Again, that's another case that this algorithm doesn't handle well.
**[7:24]** If you influence some default way of tiebreaking if that happens,
**[7:28]** hopefully this won't happen with your data set,
**[7:31]** it won't happen much at all.
**[7:32]** And so, it shouldn't affect performance as much.
**[7:35]** So, that's it for anchor boxes.
**[7:38]** And even though I'd motivated anchor boxes as a way to
**[7:42]** deal with what happens if two objects appear in the same grid cell,
**[7:46]** in practice, that happens quite rarely,
**[7:49]** especially if you use a 19 by 19 rather than a 3 by 3 grid.
**[7:54]** The chance of two objects having the same midpoint rather these 361 cells,
**[7:59]** it does happen, but it doesn't happen that often.
**[8:02]** Maybe even better motivation or even better results that
**[8:06]** anchor boxes gives you is it allows your learning algorithm to specialize better.
**[8:12]** In particular, if your data set has some tall,
**[8:15]** skinny objects like pedestrians,
**[8:17]** and some white objects like cars,
**[8:20]** then this allows your learning algorithm to specialize so
**[8:23]** that some of the outputs can specialize in detecting white,
**[8:27]** fat objects like cars,
**[8:28]** and some of the output units can specialize in detecting tall,
**[8:32]** skinny objects like pedestrians.
**[8:34]** So finally, how do you choose the anchor boxes?
**[8:38]** And people used to just choose them by hand or choose maybe five or 10 anchor box
**[8:43]** shapes that spans a variety of shapes that seems
**[8:46]** to cover the types of objects you seem to detect.
**[8:49]** As a much more advanced version,
**[8:51]** just in the advance common for those of who have other knowledge in machine learning,
**[8:55]** and even better way to do this in one of the later YOLO research papers,
**[9:00]** is to use a K-means algorithm,
**[9:02]** to group together two types of objects shapes you tend to get.
**[9:05]** And then to use that to select a set of anchor boxes that
**[9:09]** this most stereotypically representative of the maybe multiple,
**[9:13]** of the maybe dozens of object causes you're trying to detect.
**[9:16]** But that's a more advanced way to automatically choose the anchor boxes.
**[9:20]** And if you just choose by hand a variety of shapes
**[9:24]** that reasonably expands the set of object shapes,
**[9:27]** you expect to detect some tall,
**[9:29]** skinny ones, some fat, white ones.
**[9:31]** That should work with these as well.
**[9:33]** So that's it for anchor boxes.
**[9:34]** In the next video,
**[9:37]** let's take everything we've seen and tie it back together into the YOLO algorithm.
