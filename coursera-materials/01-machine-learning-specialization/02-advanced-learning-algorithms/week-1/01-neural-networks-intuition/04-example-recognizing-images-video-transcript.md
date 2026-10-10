---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Neural networks intuition
item_title: "Example: Recognizing Images"
duration: 7 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/RCpEW/example-recognizing-images
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Example: Recognizing Images — Transcript

**[0:00]** In the last video, you saw how
**[0:03]** a neural network works in a demand prediction example.
**[0:06]** Let's take a look at how you can apply a similar type of
**[0:09]** idea to computer vision application. Let's dive in.
**[0:13]** If you're building a face recognition application,
**[0:15]** you might want to train
**[0:17]** a neural network that takes as input a picture like
**[0:19]** this and outputs the identity
**[0:22]** of the person in the picture.
**[0:24]** This image is 1,000 by 1,000 pixels.
**[0:29]** Its representation in the computer is
**[0:32]** actually as 1,000 by 1,000 grid,
**[0:36]** or also called 1,000 by 1,000
**[0:38]** matrix of pixel intensity values.
**[0:42]** In this example, my pixel intensity values
**[0:45]** or pixel brightness values,
**[0:46]** goes from 0-255 and so
**[0:50]** 197 here would be
**[0:53]** the brightness of the pixel
**[0:54]** in the very upper left of the image,
**[0:56]** 185 is brightness of the pixel, one pixel over,
**[1:00]** and so on down to
**[1:02]** 214 would be the lower right corner of this image.
**[1:06]** If you were to take
**[1:08]** these pixel intensity values
**[1:10]** and unroll them into a vector,
**[1:13]** you end up with a list or a vector
**[1:16]** of a million pixel intensity values.
**[1:20]** One million because 1,000 by
**[1:22]** 1,000 square gives you a million numbers.
**[1:24]** The face recognition problem is,
**[1:27]** can you train a neural network
**[1:29]** that takes as input a feature vector with
**[1:33]** a million pixel brightness values
**[1:35]** and outputs the identity of the person in the picture.
**[1:39]** This is how you might build
**[1:41]** a neural network to carry out this task.
**[1:45]** The input image X is fed to this layer of neurons.
**[1:50]** This is the first hidden layer,
**[1:52]** which then extract some features.
**[1:55]** The output of this first hidden layer is
**[1:58]** fed to a second hidden layer and
**[2:00]** that output is fed to
**[2:02]** a third layer and then finally to the output layer,
**[2:05]** which then estimates,
**[2:06]** say the probability of this being a particular person.
**[2:10]** One interesting thing would be if
**[2:13]** you look at a neural network that's been trained on
**[2:16]** a lot of images of faces and to try to
**[2:19]** visualize what are
**[2:20]** these hidden layers, trying to compute.
**[2:23]** It turns out that when you
**[2:25]** train a system like this on a lot of pictures
**[2:27]** of faces and you peer at
**[2:30]** the different neurons in the hidden layers
**[2:33]** to figure out what they may be
**[2:34]** computing this is what you might find.
**[2:37]** In the first hidden layer,
**[2:39]** you might find one neuron that is looking
**[2:42]** for the low vertical line or a vertical edge like that.
**[2:46]** A second neuron looking for
**[2:49]** a oriented line or oriented edge like that.
**[2:52]** The third neuron looking for a line
**[2:54]** at that orientation, and so on.
**[2:57]** In the earliest layers of a neural network,
**[3:00]** you might find that the neurons are looking for
**[3:02]** very short lines or very short edges in the image.
**[3:07]** If you look at the next hidden layer,
**[3:10]** you find that these neurons might learn to group together
**[3:16]** lots of little short lines and
**[3:18]** little short edge segments in
**[3:20]** order to look for parts of faces.
**[3:22]** For example, each of these little square boxes is
**[3:26]** a visualization of what that neuron is trying to detect.
**[3:30]** This first neuron looks like it's
**[3:32]** trying to detect the presence or
**[3:34]** absence of an eye in a certain position of the image.
**[3:38]** The second neuron, looks like it's trying
**[3:40]** to detect like a corner of
**[3:43]** a nose and maybe this neuron over
**[3:45]** here is trying to detect the bottom of an ear.
**[3:50]** Then as you look at the next hidden
**[3:52]** layer in this example,
**[3:54]** the neural network is aggregating
**[3:56]** different parts of faces to then
**[3:59]** try to detect presence or absence of
**[4:01]** larger, coarser face shapes.
**[4:05]** Then finally, detecting how much
**[4:07]** the face corresponds to different face shapes creates
**[4:12]** a rich set of features that then helps
**[4:14]** the output layer try to
**[4:16]** determine the identity of the person picture.
**[4:19]** A remarkable thing about
**[4:21]** the neural network is you can learn
**[4:22]** these feature detectors at
**[4:24]** the different hidden layers all by itself.
**[4:27]** In this example, no one ever told it to
**[4:29]** look for short little edges in the first layer,
**[4:32]** and eyes and noses and face parts in
**[4:34]** the second layer and then more
**[4:36]** complete face shapes at the third layer.
**[4:38]** The neural network is able to figure out these things
**[4:40]** all by itself from data.
**[4:42]** Just one note, in this visualization,
**[4:45]** the neurons in the first hidden layer
**[4:47]** are shown looking at
**[4:49]** relatively small windows to look for these edges.
**[4:53]** In the second hidden layer is looking at bigger window,
**[4:56]** and the third hidden layer is
**[4:57]** looking at even bigger window.
**[5:00]** These little neurons visualizations
**[5:03]** actually correspond to differently
**[5:04]** sized regions in the image.
**[5:07]** Just for fun, let's see what happens if you were to
**[5:09]** train this neural network on a different dataset,
**[5:13]** say on lots of pictures of cars,
**[5:16]** picture on the side.
**[5:18]** The same learning algorithm is asked to detect cars,
**[5:24]** will then learn edges in the first layer.
**[5:27]** Pretty similar but then they'll
**[5:29]** learn to detect parts of cars in
**[5:32]** the second hidden layer and then more
**[5:34]** complete car shapes in the third hidden layer.
**[5:37]** Just by feeding it different data,
**[5:42]** the neural network automatically learns to detect
**[5:44]** very different features so as to try to
**[5:48]** make the predictions of car detection or
**[5:52]** person recognition or whether there's a
**[5:54]** particular given task that is trained on.
**[5:57]** That's how a neural network works
**[5:59]** for computer vision application.
**[6:01]** In fact, later this week,
**[6:02]** you'll see how you can build
**[6:04]** a neural network yourself and apply
**[6:06]** it to a handwritten digit recognition application.
**[6:10]** So far we've been going over the description of
**[6:13]** intuitions of neural networks
**[6:15]** to give you a feel for how they work.
**[6:17]** In the next video,
**[6:19]** let's look more deeply into the concrete mathematics and
**[6:22]** a concrete implementation of details of how you
**[6:25]** actually build one or more layers of a neural network,
**[6:29]** and therefore how you can implement
**[6:31]** one of these things yourself.
**[6:32]** Let's go on to the next video.
