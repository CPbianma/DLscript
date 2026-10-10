---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: Computer Vision
duration: 6 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/Ob1nR/computer-vision
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Computer Vision — Transcript

**[0:00]** Welcome to this course on Convolutional Networks.
**[0:03]** Computer vision is one of the areas that's been
**[0:05]** advancing rapidly thanks to deep learning.
**[0:08]** Deep learning computer vision is now helping self-driving cars
**[0:11]** figure out where the other cars and pedestrians around so as to avoid them.
**[0:15]** Is making face recognition work much better than ever before,
**[0:18]** so that perhaps some of you will soon, or perhaps already,
**[0:21]** be able to unlock a phone,
**[0:23]** unlock even a door using just your face.
**[0:25]** And if you look on your cell phone,
**[0:27]** I bet you have many apps that show you pictures of food,
**[0:29]** or pictures of a hotel, or just fun pictures of scenery.
**[0:32]** And some of the companies that build those apps are
**[0:34]** using deep learning to help show you the most attractive,
**[0:37]** the most beautiful, or the most relevant pictures.
**[0:40]** And I think deep learning is even enabling new types of art to be created.
**[0:45]** So, I think the two reasons I'm excited about
**[0:48]** deep learning for computer vision and why I think you might be too.
**[0:51]** First, rapid advances in computer vision are enabling brand new applications to view,
**[0:57]** though they just were impossible a few years ago.
**[0:59]** And by learning these tools,
**[1:01]** perhaps you will be able to invent some of these new products and applications.
**[1:06]** Second, even if you don't end up building computer vision systems per se,
**[1:09]** I found that because the computer vision research community has been so
**[1:13]** creative and so inventive in coming up
**[1:15]** with new neural network architectures and algorithms,
**[1:18]** is actually inspire that creates a lot cross-fertilization into other areas as well.
**[1:23]** For example, when I was working on speech recognition,
**[1:25]** I sometimes actually took inspiration from ideas
**[1:27]** from computer vision and borrowed them into the speech literature.
**[1:31]** So, even if you don't end up working on computer vision,
**[1:33]** I hope that you find some of the ideas you learn about in this course hopeful
**[1:37]** for some of your algorithms and your architectures.
**[1:41]** So with that, let's get started.
**[1:43]** Here are some examples of computer vision problems we'll study in this course.
**[1:48]** You've already seen image classifications,
**[1:50]** sometimes also called image recognition,
**[1:52]** where you might take as input say a 64 by 64 image and try to figure out,
**[1:56]** is that a cat?
**[1:58]** Another example of the computer vision problem is object detection.
**[2:02]** So, if you're building a self-driving car,
**[2:04]** maybe you don't just need to figure out that there are other cars in this image.
**[2:08]** But instead, you need to figure out the position of the other cars in this picture,
**[2:12]** so that your car can avoid them.
**[2:14]** In object detection, usually,
**[2:16]** we have to not just figure out that these other objects say cars and picture,
**[2:20]** but also draw boxes around them.
**[2:23]** We have some other way of recognizing where in the picture are these objects.
**[2:29]** And notice also, in this example,
**[2:30]** that they can be multiple cars in the same picture,
**[2:34]** or at least every one of them within a certain distance of your car.
**[2:38]** Here's another example, maybe a more fun one is neural style transfer.
**[2:42]** Let's say you have a picture,
**[2:44]** and you want this picture repainted in a different style.
**[2:49]** So neural style transfer,
**[2:50]** you have a content image,
**[2:52]** and you have a style image.
**[2:54]** The image on the right is actually a Picasso.
**[2:56]** And you can have a neural network put them together to
**[2:59]** repaint the content image (that is the image on the left),
**[3:02]** but in the style of the image on the right,
**[3:05]** and you end up with the image at the bottom.
**[3:08]** So, algorithms like these are enabling new types of artwork to be created.
**[3:12]** And in this course, you'll learn how to do this yourself as well.
**[3:15]** One of the challenges of computer vision problems is that the inputs can get really big.
**[3:21]** For example, in previous courses,
**[3:23]** you've worked with 64 by 64 images.
**[3:25]** And so that's 64 by 64 by 3 because there are three color channels.
**[3:29]** And if you multiply that out, that's 12288.
**[3:32]** So x the input features has dimension 12288.
**[3:37]** And that's not too bad.
**[3:38]** But 64 by 64 is actually a very small image.
**[3:42]** If you work with larger images,
**[3:44]** maybe this is a 1000 pixel by 1000 pixel image,
**[3:48]** and that's actually just one megapixel.
**[3:51]** But the dimension of the input features will be 1000 by 1000 by 3,
**[3:57]** because you have three RGB channels,
**[3:59]** and that's three million.
**[4:02]** If you are viewing this on a smaller screen,
**[4:04]** this might not be apparent,
**[4:05]** but this is actually a low res 64 by 64 image,
**[4:08]** and this is a higher res 1000 by 1000 image.
**[4:11]** But if you have three million input features,
**[4:14]** then this means that X here will be three million dimensional.
**[4:21]** And so, if in the first hidden layer maybe you have just a 1000 hidden units,
**[4:27]** then the total number of weights that is the matrix W1,
**[4:36]** if you use a standard or fully connected network like we have in courses one or two.
**[4:42]** This matrix will be a 1000 by 3 million dimensional matrix.
**[4:50]** Because X is now R by three million.
**[4:55]** 3m. I'm using to denote three million.
**[4:57]** And this means that this matrix here will have
**[5:00]** three billion parameters which is just very, very large.
**[5:05]** And with that many parameters,
**[5:06]** it's difficult to get enough data to prevent a neural network from overfitting.
**[5:12]** And also, the computational requirements and the memory requirements to train
**[5:16]** a neural network with three billion parameters is just a bit infeasible.
**[5:20]** But for computer vision applications,
**[5:22]** you don't want to be stuck using only tiny little images.
**[5:25]** You want to use large images.
**[5:27]** To do that, you need to better implement the convolution operation,
**[5:32]** which is one of the fundamental building blocks of convolutional neural networks.
**[5:35]** Let's see what this means,
**[5:37]** and how you can implement this, in the next video.
**[5:39]** And we'll illustrate convolutions,
**[5:40]** using the example of Edge Detection.
