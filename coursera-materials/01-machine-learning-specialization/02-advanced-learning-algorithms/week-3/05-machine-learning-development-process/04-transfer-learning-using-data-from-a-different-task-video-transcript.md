---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 3
section: Machine learning development process
item_title: "Transfer learning: using data from a different task"
duration: 12 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/ycgS5/transfer-learning-using-data-from-a-different-task
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Transfer learning: using data from a different task — Transcript

**[0:01]** For an application where you don't have that much data,
**[0:05]** transfer learning is
**[0:07]** a wonderful technique that lets you use
**[0:08]** data from a different task to help on your application.
**[0:12]** This is one of those techniques that
**[0:14]** I use very frequently.
**[0:16]** Let's take a look at how transfer learning works.
**[0:19]** Here's how transfer learning works.
**[0:22]** Let's say you want to recognize
**[0:24]** the handwritten digits from
**[0:27]** zero through nine but you don't have
**[0:29]** that much labeled data of these handwritten digits.
**[0:32]** Here's what you can do. Say you
**[0:35]** find a very large datasets
**[0:36]** of one million images of pictures of cats,
**[0:40]** dogs, cars, people, and so on, a thousand classes.
**[0:44]** You can then start by training
**[0:46]** a neural network on this large dataset of
**[0:49]** a million images with a thousand different classes
**[0:52]** and train the algorithm to take as input an image X,
**[0:55]** and learn to recognize any of
**[0:58]** these 1,000 different classes.
**[1:00]** In this process, you end up
**[1:02]** learning parameters for the first layer
**[1:04]** of the neural network W^1, b^1,
**[1:06]** for the second layer W^2, b^2,
**[1:08]** and so on, W^3,
**[1:11]** b^3, W^4, b^4, and W^5, b^5 for the output layer.
**[1:15]** To apply transfer learning,
**[1:17]** what you do is then make a copy of
**[1:19]** this neural network where you
**[1:22]** would keep the parameters W^1,
**[1:25]** b^1, W^2, b^2, W^3, b^3,
**[1:27]** and W^4, b^4.
**[1:30]** But for the last layer,
**[1:32]** you would eliminate the output layer and replace it with
**[1:37]** a much smaller output layer with just 10 rather
**[1:40]** than 1,000 output units.
**[1:43]** These 10 output units will
**[1:45]** correspond to the classes zero,
**[1:47]** one, through nine that
**[1:48]** you want your neural network to recognize.
**[1:51]** Notice that the parameters W^5,
**[1:53]** b^5 they can't be copied over
**[1:56]** because the dimension of this layer has changed,
**[1:58]** so you need to come up with new parameters W^5,
**[2:03]** b^5 that you need to train from
**[2:05]** scratch rather than just copy
**[2:07]** it from the previous neural network.
**[2:11]** In transfer learning,
**[2:12]** what you can do is use
**[2:14]** the parameters from the first four layers,
**[2:19]** really all the layers except the final output layer
**[2:21]** as a starting point for the parameters and then run
**[2:24]** an optimization algorithm such as gradient descent or
**[2:27]** the Adam optimization algorithm with the parameters
**[2:30]** initialized using the values
**[2:32]** from this neural network up on top.
**[2:34]** In detail, there are two options for how you can
**[2:37]** train this neural networks parameters.
**[2:40]** Option 1 is you only train the output layers parameters.
**[2:44]** You would take the parameters W^1, b^1, W^2,
**[2:48]** b^2 through W^4,
**[2:50]** b^4 as the values from on top and
**[2:52]** just hold them fix and don't even bother to change them,
**[2:54]** and use an algorithm like Stochastic gradient descent or
**[2:57]** the Adam optimization algorithm to only update W^5,
**[3:02]** b^5 to lower the usual cost function
**[3:06]** that you use for learning to
**[3:08]** recognize these digits zero
**[3:09]** to nine from a small training set of
**[3:11]** these digits zero to nine, so this is Option 1.
**[3:14]** Option 2 would be to train all the parameters in
**[3:17]** the network including W^1, b^1, W^2,
**[3:20]** b^2 all the way through W^5,
**[3:22]** b^5 but the first four layers parameters would be
**[3:25]** initialized using the values that you had trained on top.
**[3:29]** If you have a very small training
**[3:32]** set then Option 1 might work a little bit better,
**[3:36]** but if you have a training set that's a little bit
**[3:39]** larger then Option 2 might work a little bit better.
**[3:42]** This algorithm is called transfer learning
**[3:45]** because the intuition is by learning to recognize cats,
**[3:50]** dogs, cows, people, and so on.
**[3:51]** It will hopefully, have learned
**[3:53]** some plausible sets of parameters
**[3:55]** for the earlier layers for processing image inputs.
**[3:59]** Then by transferring these parameters
**[4:02]** to the new neural network,
**[4:03]** the new neural network starts off with the parameters in
**[4:07]** a much better place so
**[4:09]** that we have just a little bit of further learning.
**[4:11]** Hopefully, it can end up at a pretty good model.
**[4:14]** These two steps of first training on
**[4:16]** a large dataset and then tuning
**[4:20]** the parameters further on
**[4:21]** a smaller dataset go by the name
**[4:23]** of supervised pre-training for this step on top.
**[4:27]** That's when you train the neural network on
**[4:29]** a very large dataset of say
**[4:31]** a million images of not quite the related task.
**[4:34]** Then the second step is called
**[4:36]** fine tuning where you take the parameters that you
**[4:40]** had initialized or gotten from
**[4:42]** supervised pre-training and then
**[4:44]** run gradient descent further to
**[4:46]** fine tune the weights to suit
**[4:48]** the specific application of
**[4:50]** handwritten digit recognition that you may have.
**[4:53]** If you have a small dataset,
**[4:55]** even tens or hundreds or thousands or
**[4:57]** just tens of thousands of
**[4:59]** images of the handwritten digits,
**[5:00]** being able to learn from these million images of
**[5:04]** a not quite related task can actually help
**[5:07]** your learning algorithm's performance a lot.
**[5:09]** One nice thing about transfer learning as well
**[5:13]** is maybe you don't need to be the
**[5:16]** one to carry out supervised pre-training.
**[5:18]** For a lot of neural networks,
**[5:19]** there will already be researchers they have
**[5:21]** already trained a neural network on a large image
**[5:24]** and will have posted
**[5:27]** a trained neural networks on the Internet,
**[5:31]** freely licensed for anyone to download and use.
**[5:33]** What that means is rather
**[5:35]** than carrying out the first step yourself,
**[5:37]** you can just download
**[5:39]** the neural network that someone else may have spent
**[5:41]** weeks training and then replace the output layer
**[5:44]** with your own output layer
**[5:46]** and carry out either Option 1 or
**[5:48]** Option 2 to fine tune a neural network
**[5:51]** that someone else has already carried
**[5:53]** out supervised pre-training on,
**[5:55]** and just do a little bit of fine tuning to quickly
**[5:58]** be able to get a neural network
**[5:59]** that performs well on your task.
**[6:01]** Downloading a pre-trained model that
**[6:03]** someone else has trained and provided for
**[6:06]** free is one of those techniques where by building on
**[6:10]** each other's work on machine learning
**[6:11]** community we can all get much better results.
**[6:14]** By the generosity of other researchers that have
**[6:17]** pre-trained and posted their neural networks online.
**[6:20]** But why does transfer learning even work?
**[6:23]** How can you possibly take parameters
**[6:25]** obtained by recognizing cats, dogs, cars,
**[6:27]** and people and use that to help you
**[6:30]** recognize something as different as handwritten digits?
**[6:33]** Here's some intuition behind it.
**[6:37]** If you are training a neural network to detect, say,
**[6:41]** different objects from images,
**[6:44]** then the first layer of
**[6:46]** a neural network may learn to detect edges in the image.
**[6:50]** We think of these as somewhat low-level features
**[6:53]** in the image which is to detect edges.
**[6:56]** Each of these squares is
**[6:57]** a visualization of what a single neuron has learned to
**[7:00]** detect as learn to group together
**[7:02]** pixels to find edges in an image.
**[7:05]** The next layer of the neural network then learns to
**[7:08]** group together edges to detect corners.
**[7:12]** Each of these is a visualization of
**[7:15]** what one neuron may have learned to detect,
**[7:17]** must learn to technical,
**[7:19]** simple shapes like corner like shapes like this.
**[7:22]** The next layer of the neural network may have
**[7:25]** learned to detect some are more complex,
**[7:27]** but still generic shapes like
**[7:29]** basic curves or smaller shapes like these.
**[7:33]** That's why by learning
**[7:35]** on detecting lots of different images,
**[7:38]** you're teaching the neural network to detect edges,
**[7:41]** corners, and basic shapes.
**[7:42]** That's why by training
**[7:44]** a neural network to detect things as diverse as cats,
**[7:47]** dogs, cars and people,
**[7:48]** you're helping it to learn to detect
**[7:51]** these pretty generic features of
**[7:54]** images and finding edges,
**[7:57]** corners, curves, basic shapes.
**[7:59]** This is useful for many other computer vision tasks,
**[8:02]** such as recognizing handwritten digits.
**[8:06]** One restriction of pre-training though,
**[8:08]** is that the image type x has
**[8:11]** to be the same for
**[8:12]** the pre-training and fine-tuning steps.
**[8:15]** If the final task you want to
**[8:17]** solve is a computer vision tasks,
**[8:19]** then the pre-training step also has been
**[8:22]** a neural network trained on the same type of input,
**[8:24]** namely an image of the desired dimensions.
**[8:28]** Conversely, if your goal is to
**[8:31]** build a speech recognition system to process audio,
**[8:34]** then a neural network pre-trained on
**[8:36]** images probably won't do much good on audio.
**[8:38]** Instead, you want a neural network
**[8:40]** pre-trained on audio data,
**[8:42]** there you then fine tune on
**[8:43]** your own audio dataset and the
**[8:45]** same for other types of applications.
**[8:47]** You can pre-train a neural network on text data and
**[8:51]** If your application has
**[8:52]** a save feature input x of text data,
**[8:55]** then you can fine tune that neural
**[8:56]** network on your own data.
**[8:58]** To summarize, these are
**[9:00]** the two steps for transfer learning.
**[9:02]** Step 1 is download neural network with parameters
**[9:07]** that have been pre-trained on a large dataset with
**[9:10]** the same input type as your application.
**[9:13]** That input type could be images, audio, texts,
**[9:15]** or something else, or if
**[9:17]** you don't want to download the neural network,
**[9:18]** maybe you can train your own.
**[9:20]** But in practice, if you're using images,
**[9:24]** say, is much more common to
**[9:25]** download someone else's pre-trained neural network.
**[9:27]** Then further train or
**[9:31]** fine tune the network on your own data.
**[9:34]** I found that if you can get
**[9:36]** a neural network pre-trained on large dataset,
**[9:38]** say a million images,
**[9:40]** then sometimes you can use a much smaller dataset,
**[9:43]** maybe a thousand images,
**[9:45]** maybe even smaller, to fine tune
**[9:48]** the neural network on your own data
**[9:49]** and get pretty good results.
**[9:52]** I'd sometimes train neural networks on
**[9:54]** as few as 50 images
**[9:56]** that were quite well using this technique,
**[9:58]** when it has already been pre-trained
**[10:00]** on a much larger dataset.
**[10:02]** This technique isn't panacea.,
**[10:04]** you can't get every application
**[10:06]** to work just on 50 images,
**[10:08]** but it does help a lot when the dataset
**[10:10]** you have for your application isn't that large.
**[10:14]** By the way, if you've heard of
**[10:16]** advanced techniques in the news like
**[10:18]** GPT-3 or BERTs or
**[10:20]** neural networks pre-trained on ImageNet,
**[10:23]** those are actually examples
**[10:25]** of neural networks that they have someone
**[10:27]** else's pre-trained on a very large image datasets
**[10:30]** or text dataset,
**[10:32]** they can then be fine tuned on other applications.
**[10:34]** If you haven't heard of GPT-3,
**[10:36]** or BERTs, or ImageNet, don't
**[10:37]** worry about it, whether you have.
**[10:39]** Those have been successful applications
**[10:41]** of pre-training in the machine learning literature.
**[10:43]** One of the things I like about
**[10:44]** transfer learning is just that one of
**[10:46]** the ways that the machine learning community
**[10:49]** has shared ideas,
**[10:50]** and code, and even parameters,
**[10:52]** with each other because thanks to
**[10:54]** the researchers that have pre-trained
**[10:56]** large neural networks and posted the parameters on
**[10:59]** the internet freely for anyone else to download and use.
**[11:02]** This empowers anyone to take models,
**[11:05]** their pre-trained, to fine tune on
**[11:07]** potentially much smaller dataset.
**[11:09]** In machine learning, all of
**[11:11]** us end up often building on the work of
**[11:13]** each other and that open sharing of ideas, of codes,
**[11:18]** of trained parameters is one
**[11:20]** of the ways that the machine learning community,
**[11:22]** all of us collectively manage to do
**[11:25]** much better work than
**[11:26]** any single person by themselves can.
**[11:29]** I hope that you
**[11:30]** joining the machine learning community will
**[11:32]** someday maybe find a way to
**[11:33]** contribute back to this community as well.
**[11:36]** That's it for pre-training.
**[11:39]** I hope you find this technique useful.
**[11:41]** In the next video,
**[11:43]** I'd like to share with you some thoughts on
**[11:46]** the full cycle of a machine learning project.
**[11:49]** When building a machine learning system,
**[11:51]** whether all the steps that are worth thinking about.
**[11:54]** Let's take a look at that in the next video.
