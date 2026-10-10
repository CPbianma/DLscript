---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Intersection Over Union
duration: 4 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/p9gxz/intersection-over-union
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Intersection Over Union — Transcript

**[0:00]** So how do you tell if your object detection algorithm is working well?
**[0:05]** In this video, you'll learn about a function called, "Intersection Over Union".
**[0:10]** And as we use both for evaluating your object detection algorithm,
**[0:14]** as well as in the next video,
**[0:16]** using it to add another component to your object detection algorithm,
**[0:20]** to make it work even better.
**[0:22]** Let's get started. In the object detection task,
**[0:25]** you expected to localize the object as well.
**[0:28]** So if that's the ground-truth bounding box,
**[0:31]** and if your algorithm outputs this bounding box in purple,
**[0:35]** is this a good outcome or a bad one?
**[0:38]** So what the intersection over union function does,
**[0:44]** or IoU does, is it computes the intersection over union of these two bounding boxes.
**[0:53]** So, the union of these two bounding boxes is this area,
**[0:59]** is really the area that is contained in either bounding boxes,
**[1:06]** whereas the intersection is this smaller region here.
**[1:11]** So what the intersection of a union does is it computes the size of the intersection.
**[1:18]** So that orange shaded area,
**[1:22]** and divided by the size of the union,
**[1:27]** which is that green shaded area.
**[1:30]** And by convention, the low compute division task will
**[1:34]** judge that your answer is correct if the IoU is greater than 0.5.
**[1:39]** And if the predicted and the ground-truth bounding boxes overlapped perfectly,
**[1:45]** the IoU would be one,
**[1:47]** because the intersection would equal to the union.
**[1:50]** But in general, so long as the IoU is greater than or equal to 0.5,
**[1:55]** then the answer will look okay, look pretty decent.
**[1:59]** And by convention, very often 0.5 is used as
**[2:03]** a threshold to judge as whether the predicted bounding box is correct or not.
**[2:10]** This is just a convention.
**[2:11]** If you want to be more stringent,
**[2:12]** you can judge an answer as correct,
**[2:14]** only if the IoU is greater than equal to 0.6 or some other number.
**[2:19]** But the higher the IoUs,
**[2:21]** the more accurate the bounding the box.
**[2:24]** And so, this is one way to map localization,
**[2:27]** to accuracy where you just count up the number of times an algorithm correctly
**[2:32]** detects and localizes an object where you could use a definition like this,
**[2:37]** of whether or not the object is correctly localized.
**[2:42]** And again 0.5 is just a human chosen convention.
**[2:46]** There's no particularly deep theoretical reason for it.
**[2:49]** You can also choose some other threshold like 0.6 if you want to be more stringent.
**[2:54]** I sometimes see people use more stringent criteria like 0.6 or maybe 0.7.
**[3:00]** I rarely see people drop the threshold below 0.5.
**[3:04]** Now, what motivates the definition of IoU,
**[3:08]** as a way to evaluate whether or not
**[3:10]** your object localization algorithm is accurate or not.
**[3:14]** But more generally, IoU is a measure of the overlap between two bounding boxes.
**[3:20]** Where if you have two boxes,
**[3:22]** you can compute the intersection,
**[3:23]** compute the union, and take the ratio of the two areas.
**[3:29]** And so this is also a way of measuring how similar two boxes are to each other.
**[3:34]** And we'll see this use again this way
**[3:37]** in the next video when we talk about non-max suppression.
**[3:40]** So that's it for IoU or Intersection over Union.
**[3:46]** Not to be confused with the promissory note concept in IoU,
**[3:50]** where if you lend someone money they write you a note that says,
**[3:53]** " Oh I owe you this much money," so that's also called an IoU.
**[3:55]** It's totally a different concept,
**[3:58]** that maybe it's cool that these two things have a similar name.
**[4:03]** So now, onto this definition of IoU, Intersection of Union.
**[4:07]** In the next video,
**[4:09]** I want to discuss with you non-max suppression,
**[4:12]** which is a tool you can use to make the outputs of YOLO work even better.
**[4:16]** So let's go on to the next video.
