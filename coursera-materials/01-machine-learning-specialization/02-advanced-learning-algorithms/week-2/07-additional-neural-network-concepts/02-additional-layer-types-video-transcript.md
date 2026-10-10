---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 2
section: Additional Neural Network Concepts
item_title: Additional Layer Types
duration: 9 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/L0aFK/additional-layer-types
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Additional Layer Types — Transcript

**[0:03]** All the neural network layers with you so
**[0:05]** far have been the dense layer type in which every neuron in the layer gets
**[0:10]** its inputs all the activations from the previous layer.
**[0:15]** And it turns out that just using the dense layer type,
**[0:18]** you can actually build some pretty powerful learning algorithms.
**[0:22]** And to help you build further intuition about what neural networks can do.
**[0:27]** It turns out that there's some other types of layers as well with other properties.
**[0:32]** In this video I'd like to briefly touch on this and
**[0:35]** give you an example of a different type of neural network layer.
**[0:39]** Let's take a look to recap in the dense layer that we've been
**[0:44]** using the activation of a neuron in say the second hidden layer Is
**[0:50]** a function of every single activation value from the previous layer of a one.
**[0:57]** But it turns out that for some applications,
**[1:00]** someone designing a neural network may choose to use a different type of layer.
**[1:07]** One other layer type that you may see in some work is called a convolutional layer.
**[1:13]** Let me illustrate this with an example.
**[1:15]** So what I'm showing on the left is the input X.
**[1:19]** Which is a handwritten digit nine.
**[1:22]** And what I'm going to do is construct a hidden layer which
**[1:26]** will compute different activations as functions of this input image X.
**[1:31]** But here's something I can do for the first hidden unit, which I've drawn in
**[1:36]** blue rather than saying this neuron can look at all the pixels in this image.
**[1:42]** I might say this neuron can only look at the pixels in this little
**[1:46]** rectangular region.
**[1:48]** Second neuron, which I'm going to illustrate in magenta is also not
**[1:53]** going to look at the entire input image X instead,
**[1:56]** it's only going to look at the pixels in a limited region of the image.
**[2:01]** And so on for the third neuron and the 4th neuron and so on and so forth.
**[2:07]** Down to the last neuron which may be looking only at that region of the image.
**[2:14]** So why might you want to do this?
**[2:16]** Why won't you let every neuron look at all the pixels but
**[2:19]** instead look at only some of the pixels?
**[2:22]** Well, some of the benefits are first, it speeds up computation.
**[2:27]** And second advantage is that a neural network that uses this type of
**[2:32]** layer called a convolutional layer can need less training data or
**[2:37]** alternatively, it can also be less prone to overfitting.
**[2:41]** You heard me talk a bit about overfitting in their previous course but
**[2:45]** this is something that will dive into greater detail on next week as well.
**[2:50]** When we talk about practical tips for using learning algorithms and
**[2:55]** this is the type of layer where each neuron only looks at
**[3:00]** a region of the input image is called a convolutional layer.
**[3:06]** It was a researcher John Macoun who had figured out a lot of the details
**[3:10]** of how to get convolutional layers to work and popularized their use.
**[3:15]** Let me illustrate in more detail a convolutional layer.
**[3:19]** And if you have multiple convolutional layers in a neural network
**[3:24]** sometimes that's called a convolutional neural network.
**[3:28]** To illustrate the convolutional layer of convolutional neural
**[3:32]** network on this slide I'm going to use instead of a two D image input.
**[3:37]** I'm going to use a one dimensional input and the motivating example
**[3:42]** I'm going to use is classification of E K G signals or electrocardiograms.
**[3:49]** So if you put two electrodes on your chest you will record the voltages that look
**[3:53]** like this that correspond to your heartbeat.
**[3:57]** This is actually something that my stanford research group did research on.
**[4:01]** We were actually reading E K G signals that actually look like this to try to
**[4:06]** diagnose if patients may have a heart issue.
**[4:10]** So an E K G signal and electoral cardia graham E C G in some places E K G.
**[4:15]** In some places there's just a list of numbers corresponding
**[4:19]** to the height of the surface at different points in time.
**[4:23]** So you may have say 100 numbers corresponding to the height of this
**[4:28]** curve at 100 different points of time.
**[4:32]** And the learning tosses given this time series,
**[4:36]** given this E K G signal to classify say whether this patient
**[4:40]** has a heart disease or some diagnosable heart conditions.
**[4:46]** Here's what the convolutional neural network might do.
**[4:49]** So I'm going to take the E K G signal and rotated 90 degrees to lay it on the side.
**[4:54]** And so we have here 100 inputs X one X two all the way through X 100.
**[4:59]** Like. So and when I construct the first hidden
**[5:03]** layer Instead of having the first hidden unit take us input all 100 numbers.
**[5:10]** Let me have the first hidden unit.
**[5:12]** Look at only X one through X 20.
**[5:16]** So that corresponds to looking at just a small window of this E K G signal.
**[5:21]** The second hidden unit shown in a different color here.
**[5:25]** Well look at X 11 through X 30, so
**[5:28]** looks at a different window in this E K G signal.
**[5:32]** And the third hidden there looks at another window X21 through X 40 and so on.
**[5:37]** And the final hidden units in this example.
**[5:40]** Well Look at X 81 through X100.
**[5:43]** So it looks like a small window towards the end of this EKG time series.
**[5:49]** So this is a convolutional layer because these units in this layer looks at
**[5:54]** only a limited window of the input.
**[5:57]** Now this layer of the neural network has nine units.
**[6:03]** The next layer can also be a convolutional layer.
**[6:08]** So in the second hidden layer let me architect my first unit not
**[6:13]** to look at all nine activations from the previous layer, but
**[6:18]** to look at say just the first 5 activations from the previous layer.
**[6:25]** And then my second unit In this second hidden there may
**[6:29]** look at just another five numbers, say A3-A7.
**[6:34]** And the third and
**[6:35]** final hidden unit in this layer will only look at A5 through A9.
**[6:41]** And then maybe finally these activations.
**[6:45]** A2 gets inputs to a sigmoid unit that does look at all three of
**[6:49]** these values of A2 in order to make a binary classification
**[6:54]** regarding the presence or absence of heart disease.
**[6:59]** So this is the example of a neural network with the first hidden layer
**[7:03]** being a convolutional layer.
**[7:05]** The second hidden layer also being a convolutional layer and
**[7:09]** then the output layer being a sigmoid layer.
**[7:12]** And it turns out that with convolutional layers you have many architecture choices
**[7:17]** such as how big is the window of inputs that a single neuron should look at and
**[7:22]** how many neurons should layer have.
**[7:25]** And by choosing those architectural parameters effectively,
**[7:29]** you can build new versions of neural networks that can be even more effective
**[7:33]** than the dense layer for some applications.
**[7:36]** To recap, that's it for the convolutional layer and convolutional neural networks.
**[7:42]** I'm not going to go deeper into convolutional networks in this class and
**[7:46]** you don't need to know anything about them to do the homework and
**[7:49]** finish this class successfully.
**[7:52]** But I hope that you find this additional intuition that
**[7:55]** neural networks can have other types of layers as well to be useful.
**[8:00]** And in fact, if you sometimes hear about the latest cutting edge
**[8:04]** architectures like a transformer model or an LS TM or an attention model.
**[8:10]** A lot of this research in neural networks even today pertains to researchers trying
**[8:15]** to invent new types of layers for neural networks.
**[8:18]** And plugging these different types of layers together as building blocks to
**[8:22]** form even more complex and hopefully more powerful neural networks.
**[8:27]** So that's it for the required videos for this week.
**[8:30]** Thank you and congrats on sticking with me all the way through this.
**[8:34]** And I look forward to seeing you next week also where we'll start to talk
**[8:39]** about practical advice for how you can build machine learning systems.
**[8:44]** I hope that the tips you learn next week will help you become much more effective
**[8:49]** at building useful machine learning systems.
**[8:52]** So I look forward also to see you next week.
