---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Non-max Suppression
duration: 8 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/dvrjH/non-max-suppression
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Non-max Suppression — Transcript

**[0:00]** One of the problems of Object Detection as you've learned about this so far,
**[0:03]** is that your algorithm may find multiple detections of the same objects.
**[0:09]** Rather than detecting an object just once,
**[0:11]** it might detect it multiple times.
**[0:13]** Non-max suppression is a way for you to make
**[0:16]** sure that your algorithm detects each object only once.
**[0:19]** Let's go through an example.
**[0:21]** Let's say you want to detect pedestrians,
**[0:23]** cars, and motorcycles in this image.
**[0:26]** You might place a grid over this,
**[0:29]** and this is a 19 by 19 grid.
**[0:33]** Now, while technically this car has just one midpoint,
**[0:36]** so it should be assigned just one grid cell.
**[0:39]** And the car on the left also has just one midpoint,
**[0:43]** so technically only one of those grid cells should predict that there is a car.
**[0:48]** In practice, you're running
**[0:50]** an object classification and localization algorithm for every one of these split cells.
**[0:56]** So it's quite possible that
**[0:57]** this split cell might think that the center of a car is in it,
**[1:01]** and so might this,
**[1:02]** and so might this, and for the car on the left as well.
**[1:05]** Maybe not only this box,
**[1:07]** if this is a test image you've seen before,
**[1:09]** not only that box might decide things that's on the car,
**[1:14]** maybe this box, and this box and maybe others as
**[1:16]** well will also think that they've found the car.
**[1:19]** Let's step through an example of how non-max suppression will work.
**[1:24]** So, because you're running
**[1:26]** the image classification and localization algorithm on every grid cell,
**[1:31]** on 361 grid cells,
**[1:34]** it's possible that many of them will raise their hand and say,
**[1:38]** "My Pc, my chance of thinking I have an object in it is large."
**[1:43]** Rather than just having two of the grid cells out of the
**[1:47]** 19 squared or 361 think they have detected an object.
**[1:51]** So, when you run your algorithm,
**[1:52]** you might end up with multiple detections of each object.
**[1:58]** So, what non-max suppression does,
**[1:59]** is it cleans up these detections.
**[2:02]** So they end up with just one detection per car,
**[2:06]** rather than multiple detections per car.
**[2:09]** So concretely, what it does,
**[2:12]** is it first looks at the probabilities associated with each of these detections.
**[2:16]** Canada Pcs, although there are
**[2:18]** some details you'll learn about in this week's problem exercises,
**[2:21]** is actually Pc times C1,
**[2:23]** or C2, or C3.
**[2:24]** But for now, let's just say is Pc with the probability of a detection.
**[2:29]** And it first takes the largest one,
**[2:32]** which in this case is 0.9 and says,
**[2:35]** "That's my most confident detection,
**[2:37]** so let's highlight that and just say I found the car there."
**[2:41]** Having done that the non-max suppression part then looks at all of
**[2:45]** the remaining rectangles and all the ones with a high overlap,
**[2:49]** with a high IOU,
**[2:51]** with this one that you've just output will get suppressed.
**[2:54]** So those two rectangles with the 0.6 and the 0.7.
**[2:58]** Both of those overlap a lot with the light blue rectangle.
**[3:02]** So those, you are going to suppress
**[3:03]** and darken them to show that they are being suppressed.
**[3:07]** Next, you then go through the remaining rectangles
**[3:09]** and find the one with the highest probability,
**[3:11]** the highest Pc, which in this case is this one with 0.8.
**[3:15]** So let's commit to that and just say,
**[3:17]** "Oh, I've detected a car there."
**[3:18]** And then, the non-max suppression part is to
**[3:21]** then get rid of any other ones with a high IOU.
**[3:25]** So now, every rectangle has been either highlighted or darkened.
**[3:30]** And if you just get rid of the darkened rectangles,
**[3:33]** you are left with just the highlighted ones,
**[3:35]** and these are your two final predictions.
**[3:39]** So, this is non-max suppression.
**[3:41]** And non-max means that you're going to output
**[3:44]** your maximal probabilities classifications
**[3:48]** but suppress the close-by ones that are non-maximal.
**[3:52]** Hence the name, non-max suppression.
**[3:55]** Let's go through the details of the algorithm.
**[3:58]** First, on this 19 by 19 grid,
**[4:00]** you're going to get a 19 by 19 by eight output volume.
**[4:07]** Although, for this example,
**[4:09]** I'm going to simplify it to say that you only doing car detection.
**[4:13]** So, let me get rid of the C1, C2,
**[4:16]** C3, and pretend for this line,
**[4:18]** that each output for each of the 19 by 19,
**[4:21]** so for each of the 361,
**[4:23]** which is 19 squared,
**[4:25]** for each of the 361 positions,
**[4:26]** you get an output prediction of the following.
**[4:29]** Which is the chance there's an object,
**[4:31]** and then the bounding box.
**[4:32]** And if you have only one object,
**[4:34]** there's no C1, C2, C3 prediction.
**[4:38]** The details of what happens,
**[4:40]** you have multiple objects,
**[4:41]** I'll leave to the programming exercise,
**[4:43]** which you'll work on towards the end of this week.
**[4:47]** Now, to intimate non-max suppression,
**[4:50]** the first thing you can do is discard all the boxes,
**[4:54]** discard all the predictions of the bounding boxes with
**[4:57]** Pc less than or equal to some threshold, let's say 0.6.
**[5:01]** So we're going to say that unless you think there's at least a
**[5:04]** 0.6 chance it is an object there, let's just get rid of it.
**[5:08]** This has caused all of the low probability output boxes.
**[5:13]** The way to think about this is for each of the 361 positions,
**[5:19]** you output a bounding box together
**[5:23]** with a probability of that bounding box being a good one.
**[5:28]** So we're just going to discard
**[5:29]** all the bounding boxes that were assigned a low probability.
**[5:33]** Next, while there are
**[5:35]** any remaining bounding boxes that you've not yet discarded or processed,
**[5:41]** you're going to repeatedly pick the box with the highest probability,
**[5:45]** with the highest Pc,
**[5:47]** and then output that as a prediction.
**[5:50]** So this is a process on a previous slide of taking one of the bounding boxes,
**[5:54]** and making it lighter in color.
**[5:56]** So you commit to outputting that as a prediction for that there is a car there.
**[6:02]** Next, you then discard any remaining box.
**[6:05]** Any box that you have not output as a prediction,
**[6:08]** and that was not previously discarded.
**[6:10]** So discard any remaining box with a high overlap,
**[6:14]** with a high IOU,
**[6:15]** with the box that you just output in the previous step.
**[6:20]** This second step in the while loop was when on the previous slide you would
**[6:25]** darken any remaining bounding box that had
**[6:28]** a high overlap with the bounding box that we just made lighter,
**[6:32]** that we just highlighted.
**[6:34]** And so, you keep doing this while there's
**[6:36]** still any remaining boxes that you've not yet processed,
**[6:40]** until you've taken each of the boxes and either output it as a prediction,
**[6:45]** or discarded it as having too high an overlap,
**[6:48]** or too high an IOU,
**[6:50]** with one of the boxes that you have just output as
**[6:53]** your predicted position for one of the detected objects.
**[7:00]** I've described the algorithm using just a single object on this slide.
**[7:06]** If you actually tried to detect three objects say pedestrians,
**[7:10]** cars, and motorcycles, then the output vector will have three additional components.
**[7:16]** And it turns out, the right thing to do is to
**[7:18]** independently carry out non-max suppression three times,
**[7:22]** one on each of the outputs classes.
**[7:26]** But the details of that, I'll leave to
**[7:29]** this week's program exercise where you get to implement that yourself,
**[7:33]** where you get to implement non-max suppression yourself on multiple object classes.
**[7:38]** So that's it for non-max suppression,
**[7:41]** and if you implement the Object Detection algorithm we've described,
**[7:45]** you actually get pretty decent results.
**[7:48]** But before wrapping up our discussion of the YOLO algorithm,
**[7:51]** there's just one last idea I want to share with you,
**[7:54]** which makes the algorithm work much better,
**[7:57]** which is the idea of using anchor boxes.
**[8:00]** Let's go on to the next video.
