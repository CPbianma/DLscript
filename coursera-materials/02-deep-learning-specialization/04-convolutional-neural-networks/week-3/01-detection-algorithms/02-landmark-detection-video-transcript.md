---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Landmark Detection
duration: 6 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/OkD3X/landmark-detection
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Landmark Detection — Transcript

**[0:00]** In the previous video,
**[0:01]** you saw how you can get a neural network to output four numbers of bx,
**[0:06]** by, bh, and bw to specify
**[0:08]** the bounding box of an object you want a neural network to localize.
**[0:12]** In more general cases,
**[0:14]** you can have a neural network just output X and
**[0:17]** Y coordinates of important points and image,
**[0:20]** sometimes called landmarks, that you want the neural networks to recognize.
**[0:24]** Let me show you a few examples.
**[0:26]** Let's say you're building a face recognition application and for some reason,
**[0:31]** you want the algorithm to tell you where is the corner of someone's eye.
**[0:36]** So that point has an X and Y coordinate,
**[0:40]** so you can just have a neural network have
**[0:43]** its final layer and have it just output two more numbers which
**[0:48]** I'm going to call our lx and ly
**[0:51]** to just tell you the coordinates of that corner of the person's eye.
**[0:56]** Now, what if you want it to tell you all four corners of the eye,
**[1:01]** really of both eyes.
**[1:03]** So, if we call the points, the first, second,
**[1:06]** third and fourth points going from left to right,
**[1:08]** then you could modify the neural network now to output l1x,
**[1:13]** l1y for the first point and l2x,
**[1:17]** l2y for the second point and so on,
**[1:22]** so that the neural network can output
**[1:25]** the estimated position of all those four points of the person's face.
**[1:29]** But what if you don't want just those four points?
**[1:31]** What do you want to output this point,
**[1:33]** and this point and this point and this point along the eye?
**[1:36]** Maybe I'll put some key points along the mouth,
**[1:39]** so you can extract the mouth shape and tell if the person is smiling or frowning,
**[1:44]** maybe extract a few key points along the edges
**[1:47]** of the nose but you could define some number,
**[1:50]** for the sake of argument, let's say 64 points or 64 landmarks on the face.
**[1:57]** Maybe even some points that help you define the edge of the face,
**[2:02]** defines the jaw line but by selecting a number of landmarks
**[2:06]** and generating a label training sets that contains all of these landmarks,
**[2:11]** you can then have the neural network to tell you where are
**[2:14]** all the key positions or the key landmarks on a face.
**[2:19]** So what you do is you have this image,
**[2:21]** a person's face as input,
**[2:23]** have it go through a convnet and have a convnet,
**[2:28]** then have some set of features,
**[2:32]** maybe have it output 0 or 1,
**[2:34]** like zero face changes or not and then have it also output l1x,
**[2:40]** l1y and so on down to l64x, l64y.
**[2:48]** And here I'm using l to stand for a landmark.
**[2:52]** So this example would have 129 output units,
**[2:59]** one for is your face or not?
**[3:02]** And then if you have 64 landmarks,
**[3:04]** that's sixty-four times two,
**[3:05]** so 128 plus one output units and
**[3:09]** this can tell you if there's a face as well as where all the key landmarks on the face.
**[3:14]** So, this is a basic building block for recognizing
**[3:19]** emotions from faces and if you played with the Snapchat and the other entertainment,
**[3:25]** also AR augmented reality filters like
**[3:28]** the Snapchat photos can draw a crown on the face and have other special effects.
**[3:33]** Being able to detect these landmarks on the face,
**[3:36]** there's also a key building block for the computer graphics effects that warp
**[3:41]** the face or drawing various special effects like putting a crown or a hat on the person.
**[3:48]** Of course, in order to treat a network like this,
**[3:50]** you will need a label training set.
**[3:52]** We have a set of images as well as labels Y where people,
**[3:57]** where someone will have had to go through and
**[4:00]** laboriously annotate all of these landmarks.
**[4:04]** One last example, if you are interested in people pose detection,
**[4:11]** you could also define a few key positions like the midpoint of the chest,
**[4:17]** the left shoulder, left elbow, the wrist,
**[4:21]** and so on, and just have a neural network to annotate
**[4:24]** key positions in the person's pose as well and by having a neural network output,
**[4:34]** all of those points I'm annotating,
**[4:36]** you could also have the neural network output the pose of the person.
**[4:42]** And of course, to do that you also need to specify on
**[4:47]** these key landmarks like maybe l1x and l1y
**[4:50]** is the midpoint of the chest down to maybe l32x,
**[4:55]** l32y, if you use 32 coordinates to specify the pose of the person.
**[5:01]** So, this idea might seem quite simple of just adding a bunch of output units
**[5:06]** to output the X,Y coordinates of different landmarks you want to recognize.
**[5:12]** To be clear, the identity of landmark one must be
**[5:16]** consistent across different images like maybe
**[5:18]** landmark one is always this corner of the eye,
**[5:21]** landmark two is always this corner of the eye,
**[5:23]** landmark three, landmark four, and so on.
**[5:25]** So, the labels have to be consistent across different images.
**[5:29]** But if you can hire labelers or label yourself a big enough data set to do this,
**[5:34]** then a neural network can output all of these landmarks which is going to
**[5:38]** used to carry out other interesting effect such as with the pose of the person,
**[5:43]** maybe try to recognize someone's emotion from a picture, and so on.
**[5:47]** So that's it for landmark detection.
**[5:50]** Next, let's take these building blocks and use
**[5:53]** it to start building up towards object detection.
