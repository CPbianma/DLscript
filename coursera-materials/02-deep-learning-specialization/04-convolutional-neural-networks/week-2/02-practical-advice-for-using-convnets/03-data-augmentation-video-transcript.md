---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Practical Advice for Using ConvNets
item_title: Data Augmentation
duration: 10 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/AYzbX/data-augmentation
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Data Augmentation — Transcript

**[0:00]** Most computer vision task could use more data.
**[0:03]** And so data augmentation is one of the techniques that is
**[0:07]** often used to improve the performance of computer vision systems.
**[0:11]** I think that computer vision is a pretty complicated task.
**[0:15]** You have to input this image,
**[0:16]** all these pixels and then figure out what is in this picture.
**[0:21]** And it seems like you need to learn the decently complicated function to do that.
**[0:26]** And in practice, there almost all competing visions task having more data will help.
**[0:32]** This is unlike some other domains where sometimes you can get enough data,
**[0:36]** they don't feel as much pressure to get even more data.
**[0:39]** But I think today, this data computer vision is that,
**[0:42]** for the majority of computer vision problems,
**[0:44]** we feel like we just can't get enough data.
**[0:47]** And this is not true for all applications of machine learning,
**[0:50]** but it does feel like it's true for computer vision.
**[0:53]** So, what that means is that when you're training in computer vision model,
**[0:57]** often data augmentation will help.
**[0:59]** And this is true whether you're using transfer learning or
**[1:02]** using someone else's pre-trained ways to start,
**[1:05]** or whether you're trying to train something yourself from scratch.
**[1:09]** Let's take a look at the common data augmentation that is in computer vision.
**[1:13]** Perhaps the simplest data augmentation method is mirroring on the vertical axis,
**[1:19]** where if you have this example in your training set,
**[1:22]** you flip it horizontally to get that image on the right.
**[1:27]** And for most computer vision task,
**[1:29]** if the left picture is a cat then mirroring it is though a cat.
**[1:33]** And if the mirroring operation
**[1:35]** preserves whatever you're trying to recognize in the picture,
**[1:38]** this would be a good data augmentation technique to use.
**[1:43]** Another commonly used technique is random cropping.
**[1:47]** So given this dataset,
**[1:48]** let's pick a few random crops.
**[1:50]** So you might pick that,
**[1:51]** and take that crop or you might take that, to that crop,
**[1:56]** take this, take that crop and so this
**[1:59]** gives you different examples to feed in your training sample,
**[2:02]** sort of different random crops of your datasets.
**[2:04]** So random cropping isn't a perfect data augmentation.
**[2:08]** What if you randomly end up taking that crop which will look much like
**[2:14]** a cat but in practice and worthwhile so long as
**[2:18]** your random crops are reasonably large subsets of the actual image.
**[2:21]** So, mirroring and random cropping are frequently used and in theory,
**[2:26]** you could also use things like rotation,
**[2:29]** shearing of the image,
**[2:31]** so that's if you do this to the image,
**[2:34]** distort it that way,
**[2:35]** introduce various forms of local warping and so on.
**[2:39]** And there's really no harm with trying all of these things as well,
**[2:42]** although in practice they seem to be used a bit less,
**[2:45]** or perhaps because of their complexity.
**[2:48]** The second type of data augmentation that is commonly used is color shifting.
**[2:58]** So, given a picture like this,
**[3:01]** let's say you add to the R,
**[3:04]** G and B channels different distortions.
**[3:09]** In this example, we are adding to
**[3:12]** the red and blue channels and subtracting from the green channel.
**[3:16]** So, red and blue make purple.
**[3:20]** So, this makes the whole image a bit more purpley and that
**[3:23]** creates a distorted image for training set.
**[3:27]** For illustration purposes, I'm making
**[3:29]** somewhat dramatic changes to the colors and practice,
**[3:32]** you draw R, G and B from some distribution that could be quite small as well.
**[3:39]** But what you do is take different values of R,
**[3:43]** G, and B and use them to distort the color channels.
**[3:46]** So, in the second example,
**[3:48]** we are making a less red,
**[3:50]** and more green and more blue,
**[3:52]** so that turns our image a bit more yellowish.
**[3:57]** And here, we are making it much more blue,
**[4:01]** just a tiny little bit longer.
**[4:03]** But in practice, the values R,
**[4:04]** G and B, are drawn from some probability distribution.
**[4:09]** And the motivation for this is that if maybe the sunlight was
**[4:15]** a bit yellow or maybe the in-goal illumination was a bit more yellow,
**[4:20]** that could easily change the color of an image,
**[4:23]** but the identity of the cat or the identity of the content,
**[4:27]** the label y, just still stay the same.
**[4:30]** And so introducing these color distortions or by doing color shifting,
**[4:35]** this makes your learning algorithm more robust to changes in the colors of your images.
**[4:46]** Just a comment for the advanced learners in this course,
**[4:54]** that is okay if you don't understand what I'm about to say when using red.
**[4:59]** There are different ways to sample R, G, and B.
**[5:04]** One of the ways to implement color distortion uses an algorithm called PCA.
**[5:08]** This is called Principles Component Analysis,
**[5:11]** which I talked about in the
**[5:14]** ml-class.org Machine Learning Course on Coursera.
**[5:22]** But the details of this are actually given in the AlexNet paper,
**[5:29]** and sometimes called PCA Color Augmentation.
**[5:36]** But the rough idea at the time PCA Color Augmentation is for example,
**[5:41]** if your image is mainly purple,
**[5:44]** if it mainly has red and blue tints,
**[5:47]** and very little green,
**[5:49]** then PCA Color Augmentation,
**[5:52]** will add and subtract a lot to red and blue,
**[5:55]** where it balance [inaudible] all the greens,
**[5:56]** so kind of keeps the overall color of the tint the same.
**[6:01]** If you didn't understand any of this, don't worry about it.
**[6:05]** But if you can search online for that,
**[6:09]** you can and if you want to read about the details of it in the AlexNet paper,
**[6:13]** and you can also find some open-source implementations of the PCA Color Augmentation,
**[6:18]** and just use that.
**[6:21]** So, you might have your training data stored in a hard disk and uses symbol,
**[6:30]** this round bucket symbol to represent your hard disk.
**[6:33]** And if you have a small training set,
**[6:36]** you can do almost anything and you'll be okay.
**[6:38]** But the very last training set and this is how people will often implement it,
**[6:42]** which is you might have a CPU thread that is constantly loading images of your hard disk.
**[6:52]** So, you have this stream of images coming in from your hard disk.
**[7:00]** And what you can do is use maybe a CPU thread to implement the distortions,
**[7:08]** yet the random cropping,
**[7:11]** or the color shifting, or the mirroring,
**[7:13]** but for each image,
**[7:16]** you might then end up with some distorted version of it.
**[7:21]** So, let's see this image,
**[7:22]** I'm going to mirror it and if you also implement colors distortion and so on.
**[7:28]** And if this image ends up being color shifted,
**[7:35]** so you end up with some different colored cat.
**[7:41]** And so your CPU thread is constantly loading data as well as implementing
**[7:48]** whether the distortions are needed to form a batch or really many batches of data.
**[7:56]** And this data is then constantly passed to some other thread or some other process for
**[8:05]** implementing training and this could be done on the CPU or really
**[8:08]** increasingly on the GPU if you have a large neural network to train.
**[8:14]** And so, a pretty common way of implementing
**[8:17]** data augmentation is to really have one thread,
**[8:22]** almost four threads, that is
**[8:26]** responsible for loading the data and implementing distortions,
**[8:30]** and then passing that to some other thread or
**[8:32]** some other process that then does the training.
**[8:35]** And often, this and this,
**[8:38]** can run in parallel.
**[8:39]** So, that's it for data augmentation.
**[8:46]** And similar to other parts of training a deep neural network,
**[8:49]** the data augmentation process also has a few hyperparameters such as how much
**[8:55]** color shifting do you implement and exactly what parameters you use for random cropping?
**[9:00]** So, similar to elsewhere in computer vision,
**[9:03]** a good place to get started might be to use
**[9:06]** someone else's open-source implementation for how they use data augmentation.
**[9:10]** But of course, if you want to capture more in variances,
**[9:15]** then you think someone else's open-source implementation isn't,
**[9:19]** it might be reasonable also to use hyperparameters yourself.
**[9:24]** So with that, I hope that you're going to use data augmentation,
**[9:27]** to get your computer vision applications to work better.
