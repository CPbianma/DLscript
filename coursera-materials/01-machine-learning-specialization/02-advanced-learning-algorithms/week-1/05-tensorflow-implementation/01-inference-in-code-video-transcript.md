---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: TensorFlow implementation
item_title: Inference in Code
duration: 7 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/rJMKC/inference-in-code
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Inference in Code — Transcript

**[0:00]** TensorFlow is one of
**[0:02]** the leading frameworks to
**[0:03]** implementing deep learning algorithms.
**[0:05]** When I'm building projects,
**[0:07]** TensorFlow is actually a tool that I use the most often.
**[0:10]** The other popular tool is PyTorch.
**[0:13]** But we're going to focus in
**[0:15]** this specialization on TensorFlow.
**[0:17]** In this video, let's take a look at how you can implement
**[0:21]** inferencing code using TensorFlow. Let's dive in.
**[0:24]** One of the remarkable things about neural networks is
**[0:28]** the same algorithm can be applied
**[0:30]** to so many different applications.
**[0:33]** For this video and in some of the labs for you
**[0:37]** to see what the neural network is doing,
**[0:40]** I'm going to use another example to illustrate inference.
**[0:45]** Sometimes I do like to roast coffee beans myself at home.
**[0:49]** My favorite is actually Colombian coffee beans.
**[0:53]** Can the learning algorithm help optimize
**[0:56]** the quality of the beans you get
**[0:58]** from a roasting process like this?
**[1:00]** When you're roasting coffee,
**[1:02]** two parameters you get to control are
**[1:04]** the temperature at which you're heating up
**[1:07]** the raw coffee beans to turn
**[1:09]** them into nicely roasted coffee beans,
**[1:12]** as well as the duration or how
**[1:14]** long are you going to roast the beans.
**[1:16]** In this slightly simplified example,
**[1:19]** we've created the datasets of
**[1:21]** different temperatures and different durations,
**[1:24]** as well as labels showing whether
**[1:27]** the coffee you roasted is good-tasting coffee.
**[1:32]** Where cross here,
**[1:33]** the positive cross y equals 1 corresponds to good coffee,
**[1:37]** and all the negative cross corresponds to bad coffee.
**[1:41]** It looks like a reasonable way to think of
**[1:45]** this dataset is if you cook it at too lower temperature,
**[1:50]** it doesn't get roasted and it ends up undercooked.
**[1:53]** If you cook it, not for long enough,
**[1:56]** the duration is too short,
**[1:58]** it's also not a nicely roasted set of beans.
**[2:01]** Finally, if you were to cook it
**[2:03]** either for too long or for too higher temperature,
**[2:06]** then you end up with overcooked beans.
**[2:08]** They're a little bit burnt beans.
**[2:10]** There's not good coffee either.
**[2:12]** It's only points within
**[2:14]** this little triangle here
**[2:16]** that corresponds to good coffee.
**[2:18]** This example is simplified a
**[2:20]** bit from actual coffee roasting.
**[2:23]** Even though this example is
**[2:25]** a simplified one for the purpose of illustration,
**[2:29]** there have actually been serious projects
**[2:31]** using machine learning to
**[2:32]** optimize coffee roasting as well.
**[2:35]** The task is given
**[2:36]** a feature vector x with both temperature and duration,
**[2:41]** say 200 degrees Celsius for 17 minutes,
**[2:45]** how can we do inference in
**[2:48]** a neural network to get it to tell us
**[2:50]** whether or not this temperature and duration setting
**[2:54]** will result in good coffee or not?
**[2:56]** It looks like this.
**[2:58]** We're going to set x to be an array of two numbers.
**[3:05]** The input features 200 degrees celsius and 17 minutes.
**[3:11]** Then you create Layer 1
**[3:14]** as this first hidden layer, the neural network,
**[3:17]** as dense open parenthesis units 3,
**[3:21]** that means three units or three hidden units in
**[3:24]** this layer using as
**[3:26]** the activation function, the sigmoid function.
**[3:29]** Dense is another name for
**[3:32]** the layers of a neural network
**[3:34]** that we've learned about so far.
**[3:35]** As you learn more about neural networks,
**[3:38]** you learn about other types of layers as well.
**[3:41]** But for now, we'll just use the dense layer,
**[3:43]** which is the layer type you've learned about in
**[3:45]** the last few videos for all of our examples.
**[3:49]** Next, you compute a1 by taking Layer 1,
**[3:54]** which is actually a function,
**[3:56]** and applying this function Layer 1 to the values of x.
**[3:59]** That's how you get a1,
**[4:01]** which is going to be a list of three numbers
**[4:04]** because Layer 1 had three units.
**[4:07]** So a1 here may,
**[4:08]** just for the sake of illustration,
**[4:10]** be 0.2, 0.7, 0.3.
**[4:12]** Next, for the second hidden layer,
**[4:15]** Layer 2, would be dense.
**[4:18]** Now this time it has one unit and
**[4:20]** again to sigmoid activation function,
**[4:22]** and you can then compute a2 by applying
**[4:25]** this Layer 2 function to
**[4:27]** the activation values from Layer 1 to a1.
**[4:31]** That will give you the value of a2,
**[4:33]** which for the sake of illustration is maybe 0.8.
**[4:37]** Finally, if you wish to threshold it at 0.5,
**[4:41]** then you can just test if a2
**[4:43]** is greater and equal to 0.5 and
**[4:46]** set y-hat equals to
**[4:47]** one or zero positive or negative cross accordingly.
**[4:51]** That's how you do inference in
**[4:53]** the neural network using TensorFlow.
**[4:55]** There are some additional details
**[4:57]** that I didn't go over here,
**[4:59]** such as how to load
**[5:00]** the TensorFlow library and how to also
**[5:03]** load the parameters w and b of the neural network.
**[5:07]** But we'll go over that in the lab.
**[5:09]** Please be sure to take a look at the lab.
**[5:11]** But these are the key steps for forward propagation in
**[5:16]** how you compute a1 and a2 and optionally threshold a2.
**[5:20]** Let's look at one more example
**[5:22]** and we're going to go back to
**[5:24]** the handwritten digit classification problem.
**[5:28]** In this example, x is
**[5:30]** a list of the pixel intensity values.
**[5:33]** So x is equal to
**[5:34]** a numpy array of this list of pixel intensity values.
**[5:38]** Then to initialize and
**[5:40]** carry out one step of forward propagation,
**[5:43]** Layer 1 is a dense layer
**[5:46]** with 25 units and the sigmoid activation function.
**[5:50]** You then compute a1
**[5:51]** equals the Layer 1 function applied to x.
**[5:54]** To build and carry out
**[5:56]** inference through the second layer, similarly,
**[6:00]** you set up Layer 2 as follows,
**[6:03]** and then computes a2 as Layer 2 applied to a1.
**[6:08]** Then finally, Layer 3 is the third and final dense layer.
**[6:13]** Then finally, you can optionally threshold
**[6:16]** a3 to come up with a binary prediction for y-hat.
**[6:20]** That's the syntax for carrying
**[6:22]** out inference in TensorFlow.
**[6:25]** One thing I briefly alluded to is
**[6:27]** the structure of the numpy arrays.
**[6:30]** TensorFlow treats data in
**[6:32]** a certain way that is important to get right.
**[6:35]** In the next video,
**[6:36]** let's take a look at how TensorFlow handles data.
