---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Semantic Segmentation with U-Net
duration: 7 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/rEYzz/semantic-segmentation-with-u-net
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Semantic Segmentation with U-Net — Transcript

**[0:03]** Hi and welcome back.
**[0:05]** In this course, you've learned about object recognition,
**[0:09]** where the goal is to input a picture
**[0:11]** and figure out what is in the picture,
**[0:14]** such as is this a cat or not.
**[0:15]** You've learned about object detection,
**[0:18]** where the goal is to further put
**[0:20]** a bounding box around the object is found.
**[0:23]** In this video, you learn about a set
**[0:26]** of algorithms that's even one step more sophisticated,
**[0:29]** which is semantic segmentation,
**[0:31]** where the goal is to draw
**[0:33]** a careful outline around the object that is
**[0:36]** detected so that you know exactly which
**[0:39]** pixels belong to the object and which pixels don't.
**[0:42]** This type of algorithm,
**[0:44]** semantic segmentation is useful for
**[0:47]** many commercial applications as well
**[0:48]** today. Let's dive in.
**[0:51]** What is semantic segmentation?
**[0:53]** Let's say you're building a self-driving car and you see
**[0:57]** an input image like this and
**[0:59]** you'd like to detect the position of the other cars.
**[1:02]** If you use an object detection algorithm,
**[1:05]** the goal may be to draw
**[1:06]** bounding boxes like these around the other vehicles.
**[1:09]** This might be good enough for self-driving car,
**[1:12]** but if you want your learning algorithm to figure
**[1:14]** out what is every single pixel in this image,
**[1:17]** then you may use
**[1:19]** a semantic segmentation algorithm
**[1:21]** whose goal is to output this.
**[1:24]** Where, for example, rather than detecting
**[1:27]** the road and trying to draw
**[1:29]** a bounding box around the roads,
**[1:31]** which isn't going to be that useful,
**[1:32]** with semantic segmentation the algorithm attempts to
**[1:36]** label every single pixel
**[1:38]** as is this drivable roads or not,
**[1:41]** indicated by the dark green there.
**[1:43]** One of the uses of semantic segmentation
**[1:47]** is that it is used by some self-driving car teams to
**[1:51]** figure out exactly which pixels are
**[1:54]** safe to drive over because they
**[1:56]** represent a drivable surface.
**[1:58]** Let's look at some other applications.
**[2:00]** These are a couple of images from
**[2:03]** research papers by Novikov et al and by Dong et al.
**[2:08]** In medical imaging, given a chest X-ray,
**[2:11]** you may want to diagnose
**[2:12]** if someone has a certain condition,
**[2:14]** but what may be even more helpful to doctors,
**[2:17]** is if you can segment out in the image,
**[2:19]** exactly which pixels correspond
**[2:22]** to certain parts of the patient's anatomy.
**[2:25]** In the image on the left,
**[2:27]** the lungs, the heart,
**[2:29]** and the clavicle, so
**[2:31]** the collarbones are segmented out using different colors.
**[2:35]** This segmentation can make it
**[2:37]** easier to spot irregularities and diagnose
**[2:40]** serious diseases and also help
**[2:43]** surgeons with planning out surgeries.
**[2:47]** In this example,
**[2:49]** a brain MRI scan is used for brain tumor detection.
**[2:55]** Manually segmenting out this tumor
**[2:58]** is very time-consuming and laborious,
**[3:01]** but if a learning algorithm can segment
**[3:04]** out the tumor automatically; this
**[3:07]** saves radiologists a lot of time and this is
**[3:10]** a useful input as well for surgical planning.
**[3:13]** The algorithm used to generate
**[3:15]** this result is an algorithm called unit,
**[3:18]** which you'll learn about in the remainder of this video.
**[3:22]** Let's dig into what semantic segmentation actually does.
**[3:26]** For the sake of simplicity,
**[3:28]** let's use the example of
**[3:30]** segmenting out a car from some background.
**[3:34]** Let's say for now that the only thing you care
**[3:37]** about is segmenting out the car in this image.
**[3:40]** In that case, you may decide to have two cause labels.
**[3:45]** One for a car and zero for not car.
**[3:50]** In this case, the job of
**[3:52]** the segmentation algorithm of
**[3:53]** the unit algorithm will be to output,
**[3:56]** either one or zero for every single pixel in this image,
**[4:00]** where a pixel should be labeled one,
**[4:03]** if it is part of the car and label
**[4:05]** zero if it's not part of the car.
**[4:07]** Alternatively, if you want to segment this image,
**[4:11]** looking more finely you may decide
**[4:14]** that you want to label the car one.
**[4:17]** Maybe you also want to know where the buildings are.
**[4:19]** In which case you would have a second class,
**[4:22]** class two the building and then
**[4:25]** finally the ground or the roads,
**[4:28]** class three, in which case the job the learning algorithm
**[4:32]** would be to label every pixel as follows instead.
**[4:36]** Taking the per-pixel labels and shifting it to the right,
**[4:40]** this is the output
**[4:43]** that we would like to train a unit table to give.
**[4:47]** This is a lot of outputs,
**[4:49]** instead of just giving
**[4:51]** a single class label or maybe a class label and
**[4:55]** coordinates needed to specify bounding box
**[4:57]** the neural network unit in this case,
**[5:00]** has to generate a whole matrix of labels.
**[5:03]** What's the right neural network architecture to do that?
**[5:07]** Let's start with the object recognition
**[5:11]** neural network architecture that you're
**[5:13]** familiar with and let's figure how to modify
**[5:16]** this in order to make this new network output,
**[5:20]** a whole matrix of class labels.
**[5:22]** Here's a familiar
**[5:24]** convolutional neural network architecture,
**[5:27]** where you input an image which is fed forward
**[5:31]** through multiple layers in order
**[5:32]** to generate a class label y hat.
**[5:35]** In order to change this architecture into
**[5:38]** a semantic segmentation architecture,
**[5:41]** let's get rid of the last few layers and
**[5:44]** one key step of semantic segmentation is that,
**[5:48]** whereas the dimensions of the image have
**[5:51]** been generally getting smaller
**[5:53]** as we go from left to right,
**[5:55]** it now needs to get bigger so they can gradually
**[5:58]** blow it back up to a full-size image,
**[6:02]** which is a size you want for the output.
**[6:04]** Specifically,
**[6:06]** this is what a unit architecture looks like.
**[6:09]** As we go deeper into the unit,
**[6:11]** the height and width will go back
**[6:14]** up while the number of channels will decrease
**[6:17]** so the unit architecture looks like this until
**[6:21]** eventually, you get your segmentation map of the cat.
**[6:25]** One operation we have not yet
**[6:27]** covered is what does this look like?
**[6:30]** To make the image bigger.
**[6:32]** To explain how that works,
**[6:35]** you have to know how to
**[6:37]** implement a transpose convolution.
**[6:40]** That's semantic segmentation, a very
**[6:43]** useful algorithm for many computer vision applications
**[6:46]** where the key idea is you have to
**[6:48]** take every single pixel and
**[6:50]** label every single pixel
**[6:51]** individually with the appropriate class label.
**[6:54]** As you've seen in this video,
**[6:56]** a key step to do that is to take a small set of
**[6:59]** activations and to blow it
**[7:01]** up to a bigger set of activations.
**[7:04]** In order to do that,
**[7:05]** you have to implement something
**[7:06]** called the transpose convolution,
**[7:09]** which is important operation that is used
**[7:11]** multiple times in the unit architecture.
**[7:14]** Let's go on to the next video where you learn
**[7:16]** about the transpose convolution.
**[7:19]** I'll see you in the next video.
