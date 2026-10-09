---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Neural networks intuition
item_title: Demand Prediction
duration: 16 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/MsbrF/demand-prediction
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Demand Prediction — Transcript

**[0:00]** To illustrate how neural networks work,
**[0:03]** let's start with an example.
**[0:04]** We'll use an example from
**[0:06]** demand prediction in which you
**[0:08]** look at the product and try to predict,
**[0:10]** will this product be a top seller or not?
**[0:12]** Let's take a look.
**[0:14]** In this example, you're selling T-shirts
**[0:17]** and you would like to know if
**[0:19]** a particular T-shirt will be a top seller,
**[0:22]** yes or no, and you have collected data
**[0:25]** of different t-shirts that were sold at different prices,
**[0:28]** as well as which ones became a top seller.
**[0:31]** This type of application is used
**[0:33]** by retailers today in order
**[0:35]** to plan better inventory levels
**[0:38]** as well as marketing campaigns.
**[0:40]** If you know what's likely to be
**[0:41]** a top seller, you would plan,
**[0:42]** for example, to just
**[0:44]** purchase more of that stock in advance.
**[0:47]** In this example, the input feature
**[0:50]** x is the price of the T-shirt,
**[0:53]** and so that's the input to the learning algorithm.
**[0:56]** If you apply logistic regression to
**[0:59]** fit a sigmoid function to
**[1:01]** the data that might look like that then
**[1:04]** the outputs of your prediction might look like this,
**[1:07]** 1/1 plus e to the negative wx plus b.
**[1:11]** Previously, we had written this as
**[1:14]** f of x as the output of the learning algorithm.
**[1:17]** In order to set us up to build a neural network,
**[1:20]** I'm going to switch the terminology a little
**[1:22]** bit and use the alphabet
**[1:24]** a to denote the output
**[1:26]** of this logistic regression algorithm.
**[1:28]** The term a stands for activation,
**[1:31]** and it's actually a term from neuroscience,
**[1:34]** and it refers to how much a neuron is sending
**[1:37]** a high output to other neurons downstream from it.
**[1:42]** It turns out that
**[1:43]** this logistic regression units
**[1:46]** or this little logistic regression algorithm,
**[1:48]** can be thought of as
**[1:49]** a very simplified model of a single neuron in the brain.
**[1:54]** Where what the neuron does
**[1:56]** is it takes us input the price x,
**[2:00]** and then it computes this formula on top,
**[2:03]** and it outputs the number a,
**[2:05]** which is computed by this formula,
**[2:08]** and it outputs the probability
**[2:10]** of this T-shirt being a top seller.
**[2:12]** Another way to think of a neuron is as
**[2:15]** a tiny little computer
**[2:18]** whose only job is to input one number or a few numbers,
**[2:22]** such as a price, and then to output one number or
**[2:26]** maybe a few other numbers which in
**[2:29]** this case is the probability
**[2:30]** of the T-shirt being a top seller.
**[2:33]** As I alluded in the previous video,
**[2:36]** a logistic regression algorithm is much simpler
**[2:40]** than what any biological
**[2:42]** neuron in your brain or mine does.
**[2:44]** Which is why the artificial neural network is
**[2:46]** such a vastly oversimplified model of the human brain.
**[2:50]** Even though in practice, as you know,
**[2:52]** deep learning algorithms do work very well.
**[2:55]** Given this description of a single neuron,
**[2:58]** building a neural network now it
**[3:00]** just requires taking a bunch of
**[3:02]** these neurons and wiring them
**[3:04]** together or putting them together.
**[3:06]** Let's now look at a more complex example
**[3:08]** of demand prediction.
**[3:10]** In this example, we're going to have four features
**[3:13]** to predict whether or not a T-shirt is a top seller.
**[3:17]** The features are the price of the T-shirt,
**[3:19]** the shipping costs, the amounts
**[3:21]** of marketing of that particular T-shirt,
**[3:24]** as well as the material quality,
**[3:26]** is this a high-quality,
**[3:27]** thick cotton versus maybe a lower quality material?
**[3:32]** Now, you might suspect that whether or not
**[3:35]** a T-shirt becomes a top seller
**[3:37]** actually depends on a few factors.
**[3:39]** First, one is the affordability of this T-shirt.
**[3:43]** Second is, what's the degree of
**[3:45]** awareness of this T-shirt that potential buyers have?
**[3:49]** Third is perceived quality to
**[3:51]** bias or potential bias
**[3:53]** saying this is a high-quality T-shirt.
**[3:56]** What I'm going to do is create one artificial neuron to
**[4:02]** try to estimate the probability that
**[4:04]** this T-shirt is perceive as highly affordable.
**[4:07]** Affordability is mainly a function of price and shipping
**[4:11]** costs because the total amount of
**[4:13]** the pay is some of the price plus the shipping costs.
**[4:15]** We're going to use a little neuron here,
**[4:18]** a logistic regression unit to input price and shipping
**[4:21]** costs and predict do people think this is affordable?
**[4:25]** Second, I'm going to create
**[4:27]** another artificial neuron here to estimate,
**[4:30]** is there high awareness of this?
**[4:32]** Awareness in this case is
**[4:34]** mainly a function of the marketing of the T-shirt.
**[4:37]** Finally, going to create another neuron to
**[4:41]** estimate do people perceive this to be of high quality,
**[4:45]** and that may mainly be a function of
**[4:48]** the price of the T-shirt and of the material quality.
**[4:51]** Price is a factor here
**[4:53]** because fortunately or unfortunately,
**[4:56]** if there's a very high priced T-shirt,
**[4:58]** people will sometimes perceive
**[5:00]** that to be of high quality because it is
**[5:02]** very expensive than maybe
**[5:04]** people think it's going to be of high-quality.
**[5:06]** Given these estimates of affordability, awareness,
**[5:09]** and perceived quality we then wire the outputs of
**[5:13]** these three neurons to another neuron here on the right,
**[5:17]** that then there's another logistic regression unit.
**[5:19]** That finally inputs those three numbers and
**[5:23]** outputs the probability of
**[5:24]** this t-shirt being a top seller.
**[5:27]** In the terminology of neural networks,
**[5:29]** we're going to group
**[5:31]** these three neurons together into what's called a layer.
**[5:36]** A layer is a grouping of neurons which
**[5:40]** takes as input the same or similar features,
**[5:43]** and that in turn outputs a few numbers together.
**[5:47]** These three neurons on
**[5:48]** the left form one layer
**[5:50]** which is why I drew them on top of each other,
**[5:52]** and this single neuron on the right is also one layer.
**[5:57]** The layer on the left has three neurons,
**[5:59]** so a layer can have multiple neurons or it can also have
**[6:03]** a single neuron as in
**[6:04]** the case of this layer on the right.
**[6:07]** This layer on the right is also called
**[6:09]** the output layer because the outputs
**[6:12]** of this final neuron is
**[6:15]** the output probability predicted by the neural network.
**[6:18]** In the terminology of
**[6:20]** neural networks we're also going to call
**[6:23]** affordability awareness and perceive
**[6:25]** quality to be activations.
**[6:28]** The term activations comes from biological neurons,
**[6:31]** and it refers to the degree
**[6:32]** that the biological neuron is sending
**[6:34]** a high output value or sending
**[6:36]** many electrical impulses to
**[6:38]** other neurons to the downstream from it.
**[6:41]** These numbers on affordability, awareness,
**[6:43]** and perceived quality are
**[6:45]** the activations of these three neurons in this layer,
**[6:49]** and also this output probability is
**[6:53]** the activation of this neuron shown here on the right.
**[6:58]** This particular neural network
**[7:00]** therefore carries out computations as follows.
**[7:03]** It inputs four numbers then
**[7:05]** this layer of the neural network uses
**[7:07]** those four numbers to compute
**[7:10]** the new numbers also called activation values.
**[7:13]** Then the final layer,
**[7:15]** the output layer of the neural network used
**[7:18]** those three numbers to compute one number.
**[7:22]** In a neural network this list of
**[7:25]** four numbers is also called the input layer,
**[7:30]** and that's just a list of four numbers.
**[7:32]** Now, there's one simplification
**[7:36]** I'd like make to this neural network.
**[7:39]** The way I've described it so far,
**[7:41]** we had to go through the neurons one at a time and
**[7:44]** decide what inputs it would take from the previous layer.
**[7:48]** For example, we said affordability is a function of
**[7:51]** just price and shipping costs and awareness is
**[7:53]** a function of just marketing and so on,
**[7:56]** but if you're building a large neural network
**[7:58]** it'd be a lot of work to go through and
**[8:00]** manually decide which neurons
**[8:02]** should take which features as inputs.
**[8:05]** The way a neural network is implemented in
**[8:07]** practice each neuron in a certain layer;
**[8:11]** say this layer in the middle,
**[8:12]** will have access to every feature,
**[8:16]** to every value from the previous layer,
**[8:18]** from the input layer which is why I'm now drawing arrows
**[8:24]** from every input feature to every one
**[8:26]** of these neurons shown here in the middle.
**[8:29]** You can imagine that if you're trying to predict
**[8:32]** affordability and it knows
**[8:35]** what's the price shipping cost marketing and material,
**[8:37]** may be you'll learn to ignore
**[8:39]** marketing and material and just figure
**[8:41]** out through setting the parameters appropriately to only
**[8:45]** focus on the subset of features that are
**[8:47]** most relevant to affordability.
**[8:50]** To further simplify the notation and
**[8:53]** the description of this neural network I'm going
**[8:56]** to take these four input features
**[8:58]** and write them as a vector x,
**[9:02]** and we're going to view the neural network as having
**[9:05]** four features that comprise this feature vector x.
**[9:10]** This feature vector is fed to this layer in
**[9:14]** the middle which then computes three activation values.
**[9:18]** That is these numbers and
**[9:21]** these three activation values
**[9:24]** in turn becomes another vector which
**[9:27]** is fed to this final output layer that
**[9:31]** finally outputs the probability
**[9:34]** of this t-shirt to being a top seller.
**[9:37]** That's all a neural network is.
**[9:39]** It has a few layers where each layer inputs
**[9:43]** a vector and outputs another vector of numbers.
**[9:48]** For example, this layer in the middle inputs
**[9:51]** four numbers x and
**[9:53]** outputs three numbers corresponding to affordability,
**[9:56]** awareness, and perceived quality.
**[9:58]** To add a little bit more terminology,
**[10:01]** you've seen that this layer is called the output
**[10:05]** layer and this layer is called the input layer.
**[10:09]** To give the layer in the middle a name as well,
**[10:12]** this layer in the middle is called a hidden layer.
**[10:16]** I know that this is maybe not the best or
**[10:19]** the most intuitive name but
**[10:21]** that terminology comes from
**[10:23]** that's when you have a training set.
**[10:25]** In a training set,
**[10:26]** you get to observe both x and y.
**[10:29]** Your data set tells you what is x and what is y,
**[10:32]** and so you get data that tells
**[10:34]** you what are the correct inputs and the correct outputs.
**[10:37]** But your dataset doesn't tell you what
**[10:40]** are the correct values for affordability,
**[10:43]** awareness, and perceived quality.
**[10:45]** The correct values for those are hidden.
**[10:47]** You don't see them in the training set,
**[10:48]** which is why this layer in
**[10:50]** the middle is called a hidden layer.
**[10:52]** I'd like to share with you another way of thinking
**[10:56]** about neural networks that I've found
**[10:58]** useful for building my intuition about it.
**[11:00]** Just let me cover up the left half of this diagram,
**[11:03]** and see what we're left with.
**[11:05]** What you see here is that there is
**[11:08]** a logistic regression algorithm or
**[11:10]** logistic regression unit that is taking as input,
**[11:13]** affordability,
**[11:15]** awareness, and perceived quality of a t-shirt,
**[11:17]** and using these three features to estimate
**[11:20]** the probability of the t-shirt being a top seller.
**[11:24]** This is just logistic regression.
**[11:27]** But the cool thing about this
**[11:30]** is rather than using the original features,
**[11:33]** price, shipping cost, marketing, and so on,
**[11:35]** is using maybe better set
**[11:37]** of features, affordability, awareness,
**[11:39]** and perceived quality, that are hopefully more
**[11:42]** predictive of whether or
**[11:43]** not this t-shirt will be a top seller.
**[11:46]** One way to think of this neural network
**[11:48]** is, just logistic regression.
**[11:51]** But as a version of logistic regression,
**[11:54]** they can learn its own features that
**[11:57]** makes it easier to make accurate predictions.
**[12:00]** In fact, you might remember from the previous course,
**[12:04]** this housing example where we said
**[12:06]** that if you want to predict the price of the house,
**[12:09]** you might take the frontage or
**[12:11]** the width of lots and multiply that
**[12:13]** by the depth of a lot to construct
**[12:15]** a more complex feature,
**[12:17]** x_1 times x_2,
**[12:18]** which was the size of the lawn.
**[12:20]** There we were doing manual feature engineering
**[12:23]** where we had to look at the features x_1
**[12:25]** and x_2 and decide by hand how to combine
**[12:28]** them together to come up with better features.
**[12:30]** What the neural network does is instead of you
**[12:33]** needing to manually engineer the features,
**[12:36]** it can learn, as you'll see later,
**[12:39]** its own features to make
**[12:41]** the learning problem easier for itself.
**[12:43]** This is what makes
**[12:46]** neural networks one of
**[12:47]** the most powerful learning algorithms in the world today.
**[12:50]** To summarize, a neural network,
**[12:52]** does this, the input layer has a vector of features,
**[12:56]** four numbers in this example,
**[12:58]** it is input to the hidden layer,
**[13:01]** which outputs three numbers.
**[13:03]** I'm going to use a vector to denote
**[13:07]** this vector of activations
**[13:09]** that this hidden layer outputs.
**[13:11]** Then the output layer takes its input to
**[13:14]** three numbers and outputs one number,
**[13:18]** which would be the final activation,
**[13:20]** or the final prediction of the neural network.
**[13:23]** One note, even though I previously
**[13:26]** described this neural network as computing affordability,
**[13:29]** awareness, and perceived quality,
**[13:31]** one of the really nice properties of a neural network
**[13:33]** is when you train it from data,
**[13:36]** you don't need to go in to
**[13:38]** explicitly decide what other features,
**[13:40]** such as affordability and so on,
**[13:42]** that the neural network should
**[13:43]** compute instead or figure out all by
**[13:46]** itself what are the features it
**[13:48]** wants to use in this hidden layer.
**[13:51]** That's what makes it such a powerful learning algorithm.
**[13:54]** You've seen here one example of a neural network and
**[13:57]** this neural network has
**[13:59]** a single layer that is a hidden layer.
**[14:01]** Let's take a look at some other examples
**[14:03]** of neural networks, specifically,
**[14:05]** examples with more than one hidden layer.
**[14:09]** Here's an example.
**[14:11]** This neural network has
**[14:13]** an input feature vector X
**[14:16]** that is fed to one hidden layer.
**[14:19]** I'm going to call this the first hidden layer.
**[14:21]** If this hidden layer has three neurons,
**[14:24]** it will then output a vector of three activation values.
**[14:29]** These three numbers can then be
**[14:32]** input to the second hidden layer.
**[14:35]** If the second hidden layer has
**[14:37]** two neurons to logistic units,
**[14:40]** then this second hidden there will
**[14:42]** output another vector of now
**[14:44]** two activation values that maybe goes to
**[14:47]** the output layer that then
**[14:48]** outputs the neural network's final prediction.
**[14:51]** Here's another example.
**[14:53]** Here's a neural network
**[14:54]** that it's input goes to the first hidden layer,
**[14:58]** the output of the first hidden layer
**[15:00]** goes to the second hidden layer,
**[15:01]** goes to the third hidden layer,
**[15:03]** and then finally to the output layer.
**[15:05]** When you're building your own neural network,
**[15:08]** one of the decisions you need to make
**[15:10]** is how many hidden layers do you
**[15:11]** want and how many neurons do
**[15:14]** you want each hidden layer to have.
**[15:16]** This question of how many hidden layers and
**[15:20]** how many neurons per hidden layer is
**[15:22]** a question of the architecture of the neural network.
**[15:25]** You'll learn later in this course some tips for
**[15:29]** choosing an appropriate architecture
**[15:31]** for a neural network.
**[15:32]** But choosing the right number of
**[15:33]** hidden layers and number of
**[15:36]** hidden units per layer can have
**[15:38]** an impact on the performance
**[15:39]** of a learning algorithm as well.
**[15:41]** Later in this course, you'll learn how to choose
**[15:44]** a good architecture for your neural network as well.
**[15:46]** By the way, in some of the literature,
**[15:49]** you see this type of neural network with
**[15:51]** multiple layers like this called a multilayer perceptron.
**[15:54]** If you see that, that just refers to a neural network
**[15:57]** that looks like what you're seeing here on the slide.
**[16:00]** That's a neural network.
**[16:03]** I know we went through a lot in this video.
**[16:05]** Thank you for sticking with me.
**[16:07]** But you now know how a neural network works.
**[16:10]** In the next video,
**[16:11]** let's take a look at how these ideas
**[16:13]** can be applied to other applications as well.
**[16:16]** In particular, we'll take a look at
**[16:17]** the computer vision application of face recognition.
**[16:21]** Let's go on to the next video.
