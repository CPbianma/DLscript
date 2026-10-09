---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Neural Style Transfer
item_title: What are deep ConvNets learning?
duration: 8 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/GboGx/what-are-deep-convnets-learning
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# What are deep ConvNets learning? — Transcript

**[0:00]** What are deep ConvNets really learning?
**[0:03]** In this video, I want to share with you some visualizations that will help you
**[0:07]** hone your intuition about what the deeper layers of a ConvNet really are doing.
**[0:11]** And this will help us think through how you can implement
**[0:14]** neural style transfer as well.
**[0:17]** Let's start with an example.
**[0:18]** Lets say you've trained a ConvNet, this is an AlexNet like network,
**[0:23]** and you want to visualize what the hidden units in different layers are computing.
**[0:28]** Here's what you can do.
**[0:30]** Let's start with a hidden unit in layer 1.
**[0:33]** And suppose you scan through your training sets and find out what are the images or
**[0:38]** what are the image patches that maximize that unit's activation.
**[0:43]** So in other words pause your training set through your neural network, and figure
**[0:49]** out what is the image that maximizes that particular unit's activation.
**[0:55]** Now, notice that a hidden unit in layer 1,
**[0:58]** will see only a relatively small portion of the neural network.
**[1:02]** And so if you visualize, if you plot what activated unit's activation,
**[1:08]** it makes makes sense to plot just a small image patches,
**[1:11]** because all of the image that that particular unit sees.
**[1:15]** So if you pick one hidden unit and find the nine input images that maximizes
**[1:20]** that unit's activation, you might find nine image patches like this.
**[1:25]** So looks like that in the lower region of an image that this particular hidden unit sees,
**[1:30]** it's looking for an edge or a line that looks like that.
**[1:34]** So those are the nine image patches that maximally activate
**[1:39]** one hidden unit's activation.
**[1:41]** Now, you can then pick a different hidden unit in layer 1 and do the same thing.
**[1:47]** So that's a different hidden unit, and looks like this second one,
**[1:51]** represented by these 9 image patches here.
**[1:54]** Looks like this hidden unit is looking for a line sort of in that portion of its
**[1:58]** input region, we'll also call this receptive field.
**[2:02]** And if you do this for other hidden units, you'll find other hidden units,
**[2:07]** tend to activate in image patches that look like that.
**[2:11]** This one seems to have a preference for a vertical light edge, but
**[2:15]** with a preference that the left side of it be green.
**[2:18]** This one really prefers orange colors, and this is an interesting image patch.
**[2:23]** This red and green together will make a brownish or a brownish-orangish color,
**[2:29]** but the neuron is still happy to activate with that, and so on.
**[2:34]** So this is nine different representative neurons and for
**[2:38]** each of them the nine image patches that they maximally activate on.
**[2:43]** So this gives you a sense that, units, train hidden units in layer 1,
**[2:48]** they're often looking for
**[2:49]** relatively simple features such as edge or a particular shade of color.
**[2:55]** And all of the examples I'm using in
**[2:57]** this video come from this paper by Mathew Zeiler and
**[3:01]** Rob Fergus, titled visualizing and understanding convolutional networks.
**[3:06]** And I'm just going to use one of the simpler ways to visualize
**[3:10]** what a hidden unit in a neural network is computing.
**[3:14]** If you read their paper, they have some other more sophisticated ways of
**[3:18]** visualizing when the ConvNet is running as well.
**[3:22]** But now you have repeated this procedure several times for
**[3:26]** nine hidden units in layer 1.
**[3:28]** What if you do this for
**[3:29]** some of the hidden units in the deeper layers of the neuron network.
**[3:33]** And what does the neural network then learning at a deeper layers.
**[3:37]** So in the deeper layers, a hidden unit will see a larger region of the image.
**[3:43]** Where at the extreme end each pixel
**[3:46]** could hypothetically affect the output of these later layers of the neural network.
**[3:51]** So later units are actually seen larger image patches,
**[3:55]** I'm still going to plot the image patches as the same size on these slides.
**[3:59]** But if we repeat this procedure, this is what you had previously for layer 1,
**[4:04]** and this is a visualization of what maximally activates nine different
**[4:09]** hidden units in layer 2.
**[4:12]** So I want to be clear about what this visualization is.
**[4:15]** These are the nine patches that cause one hidden unit to be highly activated.
**[4:20]** And then each grouping, this is a different set of nine image patches that
**[4:25]** cause one hidden unit to be activated.
**[4:27]** So this visualization shows nine hidden units in layer 2, and
**[4:32]** for each of them shows nine image patches that causes that hidden unit
**[4:36]** to have a very large output, a very large activation.
**[4:39]** And you can repeat these for deeper layers as well.
**[4:44]** Now, on this slide, I know it's kind of hard to see these tiny little
**[4:46]** image patches, so let me zoom in for some of them.
**[4:49]** For layer 1, this is what you saw.
**[4:52]** So for example, this is that first unit we saw which was highly activated, if
**[4:58]** in the region of the input image, you can see there's an edge maybe at that angle.
**[5:03]** Now let's zoom in for layer 2 as well, to that visualization.
**[5:08]** So this is interesting,
**[5:09]** layer 2 looks it's detecting more complex shapes and patterns.
**[5:14]** So for example, this hidden unit looks like it's looking for
**[5:17]** a vertical texture with lots of vertical lines.
**[5:21]** This hidden unit looks like its highly activated when
**[5:24]** there's a rounder shape to the left part of the image.
**[5:27]** Here's one that is looking for very thin vertical lines and so on.
**[5:33]** And so the features the second layer is detecting are getting more complicated.
**[5:38]** How about layer 3?
**[5:39]** Let's zoom into that, in fact let me zoom in even bigger, so
**[5:43]** you can see this better, these are the things that maximally activate layer 3.
**[5:48]** But let's zoom in even bigger, and so this is pretty interesting again.
**[5:52]** It looks like there is a hidden unit that seems to respond highly
**[5:57]** to a rounder shape in the lower left hand portion of the image, maybe.
**[6:01]** So that ends up detecting a lot of cars, dogs and
**[6:06]** wonders is even starting to detect people.
**[6:10]** And this one look like it is detecting certain textures like honeycomb shapes,
**[6:15]** or square shapes, this irregular texture.
**[6:18]** And some of these it's difficult to look at and manually figure out what is it
**[6:22]** detecting, but it is clearly starting to detect more complex patterns.
**[6:26]** How about the next layer?
**[6:27]** Well, here is layer 4, and you'll see that the features or
**[6:30]** the patterns is detecting or even more complex.
**[6:33]** It looks like this has learned almost a dog detector, but
**[6:37]** all these dogs likewise similar, right?
**[6:39]** Is this, I don't know what dog species or dog breed this is.
**[6:42]** But now all those are dogs, but they look relatively similar as dogs go.
**[6:47]** Looks like this hidden unit and therefore it is detecting water.
**[6:53]** This looks like it is actually detecting the legs of a bird and so on.
**[6:58]** And then layer 5 is detecting even more sophisticated things.
**[7:02]** So you'll notice there's also a neuron that seems to be a dog detector,
**[7:07]** but set of dogs detecting here seems to be more varied.
**[7:12]** And then this seems to be detecting keyboards and things with a keyboard
**[7:17]** like texture, although maybe lots of dots against background.
**[7:22]** I think this neuron here may be detecting text, it's always hard to be sure.
**[7:27]** And then this one here is detecting flowers.
**[7:31]** So we've gone a long way from detecting relatively simple things
**[7:35]** such as edges in layer 1 to textures in layer 2,
**[7:38]** up to detecting very complex objects in the deeper layers.
**[7:43]** So I hope this gives you some better intuition about what the shallow and
**[7:48]** deeper layers of a neural network are computing.
**[7:52]** Next, let's use this intuition to start building a neural-style transfer
**[7:56]** algorithm.
