---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Face Recognition
item_title: Siamese Network
duration: 5 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/bjhmj/siamese-network
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Siamese Network — Transcript

**[0:00]** The job of the function d, which you learned about in the last video,
**[0:04]** is to input two faces and tell you how similar or how different they are.
**[0:08]** A good way to do this is to use a Siamese network.
**[0:12]** Let's take a look.
**[0:15]** You're used to seeing pictures of confidence like these where you input
**[0:19]** an image, let's say x1.
**[0:20]** And through a sequence of convolutional and pulling and
**[0:24]** fully connected layers, end up with a feature vector like that.
**[0:30]** And sometimes this is fed to a softmax unit to make a classification.
**[0:35]** We're not going to use that in this video.
**[0:39]** Instead, we're going to focus on this vector of let's say 128
**[0:44]** numbers computed by some fully connected layer that is deeper in the network.
**[0:50]** And I'm going to give this list of 128 numbers a name.
**[0:54]** I'm going to call this f of x1,
**[1:00]** and you should think of f of x1 as an encoding of the input image x1.
**[1:07]** So it's taken the input image, here this picture of Kian,
**[1:12]** and is re-representing it as a vector of 128 numbers.
**[1:17]** The way you can build a face recognition system is then that if you want to compare
**[1:22]** two pictures, let's say this first picture with this second picture here.
**[1:27]** What you can do is feed this second picture to the same neural network with
**[1:31]** the same parameters and get a different vector of 128 numbers,
**[1:37]** which encodes this second picture.
**[1:41]** So I'm going to call this second picture.
**[1:44]** So I'm going to call this encoding of this second picture f of x2, and
**[1:50]** here I'm using x1 and x2 just to denote two input images.
**[1:55]** They don't necessarily have to be the first and
**[1:58]** second examples in your training sets.
**[2:00]** It can be any two pictures.
**[2:02]** Finally, if you believe that these encodings are a good representation
**[2:07]** of these two images, what you can do is then define the image d
**[2:12]** of distance between x1 and
**[2:16]** x2 as the norm of the difference
**[2:21]** between the encodings of these two images.
**[2:26]** So this idea of running two identical,
**[2:29]** convolutional neural networks on two different inputs and then comparing them,
**[2:34]** sometimes that's called a Siamese neural network architecture.
**[2:39]** And many of the ideas I'm presenting here came from
**[2:43]** a paper due to Yaniv Taigman, Ming Yang, Marc'Aurelio Ranzato, and
**[2:47]** Lior Wolf in the research system that they developed called DeepFace.
**[2:52]** So how do you train this Siamese neural network?
**[2:56]** Remember that these two neural networks have the same parameters.
**[3:00]** So what you want to do is really train the neural network so
**[3:04]** that the encoding that it computes results in a function d
**[3:08]** that tells you when two pictures are of the same person.
**[3:12]** So more formally, the parameters of the neural network define an encoding f of xi.
**[3:18]** So given any input image xi,
**[3:20]** the neural network outputs this 128 dimensional encoding f of xi.
**[3:26]** So more formally, what you want to do is learn parameters so
**[3:30]** that if two pictures, xi and xj, are of the same person,
**[3:35]** then you want that distance between their encodings to be small.
**[3:40]** And in the previous slide, l was using x1 and x2, but
**[3:44]** it's really any pair xi and xj from your training set.
**[3:48]** And in contrast, if xi and xj are of different persons,
**[3:53]** then you want that distance between their encodings to be large.
**[3:57]** So as you vary the parameters in all of these layers of the neural network,
**[4:02]** you end up with different encodings.
**[4:05]** And what you can do is use back propagation
**[4:08]** to vary all those parameters in order to make sure these conditions are satisfied.
**[4:13]** So you've learned about the Siamese network architecture and
**[4:17]** have a sense of what you want the neural network to output for
**[4:21]** you in terms of what would make a good encoding.
**[4:23]** But how do you actually define an objective function
**[4:27]** to make a neural network learn to do what we just discussed here?
**[4:31]** Let's see how you can do that in the next video using the triplet loss function.
