---
type: video-transcript
specialization: Machine Learning Specialization
course: Advanced Learning Algorithms
week: 1
section: Neural networks intuition
item_title: Neurons and the brain
duration: 11 min
source_url: https://www.coursera.org/learn/advanced-learning-algorithms/lecture/couAA/neurons-and-the-brain
language: en
extracted_at: 2026-10-08T22:15:50+08:00
status: success
---

# Neurons and the brain — Transcript

**[0:00]** When neural networks were first
**[0:01]** invented many decades ago,
**[0:03]** the original motivation was to
**[0:05]** write software that could mimic
**[0:07]** how the human brain or how
**[0:08]** the biological brain learns and thinks.
**[0:11]** Even though today, neural networks,
**[0:14]** sometimes also called artificial neural networks,
**[0:17]** have become very different than how any of
**[0:20]** us might think about how
**[0:21]** the brain actually works and learns.
**[0:23]** Some of the biological motivations
**[0:25]** still remain in the way we think
**[0:26]** about artificial neural networks
**[0:28]** or computer neural networks today.
**[0:30]** Let's start by taking a look at how the brain
**[0:33]** works and how that relates to neural networks.
**[0:36]** The human brain, or maybe more generally,
**[0:39]** the biological brain demonstrates a higher level or more
**[0:43]** capable level of intelligence and
**[0:45]** anything else would be on the bill so far.
**[0:48]** So neural networks has started with
**[0:50]** the motivation of trying to build
**[0:52]** software to mimic the brain.
**[0:55]** Work in neural networks had started back in the 1950s,
**[0:59]** and then it fell out of favor for a while.
**[1:02]** Then in the 1980s and early 1990s,
**[1:05]** they gained in popularity again and showed
**[1:08]** tremendous traction in some applications
**[1:11]** like handwritten digit recognition,
**[1:13]** which were used even backed then to
**[1:15]** read postal codes for writing
**[1:17]** mail and for reading
**[1:19]** dollar figures in handwritten checks.
**[1:22]** But then it fell out of favor again in the late 1990s.
**[1:26]** It was from about 2005 that it enjoyed
**[1:30]** a resurgence and also became
**[1:33]** re-branded little bit with deep learning.
**[1:36]** One of the things that surprised me back then
**[1:39]** was deep learning and
**[1:41]** neural networks meant very similar things.
**[1:43]** But maybe under-appreciated
**[1:45]** at the time that the term deep learning,
**[1:48]** just sounds much better
**[1:49]** because it's deep and this learning.
**[1:51]** So that turned out to be the brand that
**[1:54]** took off in the last decade or decade and a half.
**[1:57]** Since then, neural networks have
**[1:59]** revolutionized application area after application area.
**[2:02]** I think the first application area
**[2:05]** that modern neural networks or deep learning,
**[2:07]** had a huge impact on was probably speech recognition,
**[2:10]** where we started to see
**[2:12]** much better speech recognition systems due to
**[2:14]** modern deep learning and authors such as
**[2:17]** [inaudible] and Geoff Hinton were instrumental to this,
**[2:20]** and then it started to make inroads into computer vision.
**[2:24]** Sometimes people still speak of
**[2:26]** the ImageNet moments in 2012,
**[2:29]** and that was maybe a bigger splash where then [inaudible]
**[2:33]** draw their imagination and
**[2:35]** had a big impact on computer vision.
**[2:37]** Then the next few years,
**[2:39]** it made us inroads into
**[2:40]** texts or into natural language processing,
**[2:43]** and so on and so forth.
**[2:44]** Now, neural networks are used in everything from
**[2:47]** climate change to medical imaging to online advertising
**[2:51]** to prouduct recommendations and really lots of
**[2:53]** application areas of machine learning
**[2:55]** now use neural networks.
**[2:57]** Even though today's neural networks have
**[2:59]** almost nothing to do with how the brain learns,
**[3:03]** there was the early motivation of
**[3:06]** trying to build software to mimic the brain.
**[3:09]** So how does the brain work?
**[3:11]** Here's a diagram illustrating
**[3:13]** what neurons in a brain look like.
**[3:16]** All of human thought is from
**[3:18]** neurons like this in your brain and mine,
**[3:21]** sending electrical impulses and
**[3:23]** sometimes forming new connections of other neurons.
**[3:26]** Given a neuron like this one,
**[3:29]** it has a number of inputs where it receives
**[3:32]** electrical impulses from other neurons,
**[3:35]** and then this neuron that I've
**[3:37]** circled carries out some computations and
**[3:41]** will then send this outputs
**[3:43]** to other neurons by this electrical impulses,
**[3:46]** and this upper neuron's output in turn
**[3:49]** becomes the input to this neuron down below,
**[3:53]** which again aggregates inputs from
**[3:55]** multiple other neurons to then maybe send its own output,
**[3:58]** to yet other neurons,
**[4:00]** and this is the stuff of which human thought is made.
**[4:04]** Here's a simplified diagram of a biological neuron.
**[4:09]** A neuron comprises a cell body shown here on the left,
**[4:14]** and if you have taken a class in biology,
**[4:17]** you may recognize this to be the nucleus of the neuron.
**[4:22]** As we saw on the previous slide,
**[4:24]** the neuron has different inputs.
**[4:26]** In a biological neuron,
**[4:28]** the input wires are called the dendrites,
**[4:32]** and it then occasionally sends electrical impulses
**[4:35]** to other neurons via the output wire,
**[4:38]** which is called the axon.
**[4:40]** Don't worry about these biological terms.
**[4:42]** If you saw them in a biology class,
**[4:44]** you may remember them,
**[4:45]** but you don't really need to
**[4:47]** memorize any of these terms for
**[4:48]** the purpose of building artificial neural networks.
**[4:52]** But this biological neuron may then send
**[4:54]** electrical impulses that become
**[4:56]** the input to another neuron.
**[4:59]** So the artificial neural network uses
**[5:03]** a very simplified Mathematical model
**[5:06]** of what a biological neuron does.
**[5:09]** I'm going to draw a little circle
**[5:12]** here to denote a single neuron.
**[5:16]** What a neuron does is it takes some inputs,
**[5:20]** one or more inputs,
**[5:21]** which are just numbers.
**[5:23]** It does some computation
**[5:26]** and it outputs some other number,
**[5:28]** which then could be an input to a second neuron,
**[5:32]** shown here on the right.
**[5:34]** When you're building an artificial neural network
**[5:36]** or deep learning algorithm,
**[5:38]** rather than building one neuron at a time,
**[5:41]** you often want to
**[5:42]** simulate many such neurons at the same time.
**[5:46]** In this diagram, I'm drawing three neurons.
**[5:52]** What these neurons do
**[5:54]** collectively is input a few numbers,
**[5:57]** carry out some computation,
**[5:59]** and output some other numbers.
**[6:02]** Now, at this point,
**[6:03]** I'd like to give one big caveat,
**[6:05]** which is that even though I made
**[6:07]** a loose analogy between
**[6:09]** biological neurons and artificial neurons,
**[6:12]** I think that today we have
**[6:13]** almost no idea how the human brain works.
**[6:16]** In fact, every few years,
**[6:18]** neuroscientists make some fundamental breakthrough
**[6:20]** about how the brain works.
**[6:22]** I think we'll continue to do
**[6:23]** so for the foreseeable future.
**[6:25]** That to me is a sign that there are
**[6:28]** many breakthroughs that are yet to be
**[6:30]** discovered about how the brain actually works,
**[6:32]** and thus attempts to blindly
**[6:34]** mimic what we know of the human brain today,
**[6:37]** which is frankly very little,
**[6:39]** probably won't get us that far
**[6:41]** toward building raw intelligence.
**[6:43]** Certainly not with our current level
**[6:44]** of knowledge in neuroscience.
**[6:46]** Having said that, even with
**[6:49]** these extremely simplified models of a neuron,
**[6:52]** which we'll talk about, we'll be able to build
**[6:54]** really powerful deep learning algorithms.
**[6:57]** So as you go deeper into
**[6:59]** neural networks and into deep learning,
**[7:01]** even though the origins were biologically motivated,
**[7:04]** don't take the biological motivation too seriously.
**[7:08]** In fact, those of us that do
**[7:09]** research in deep learning have
**[7:11]** shifted away from looking to
**[7:13]** biological motivation that much.
**[7:15]** But instead, they're just using
**[7:17]** engineering principles to figure
**[7:19]** out how to build algorithms that are more effective.
**[7:21]** But I think it might still be fun to speculate and
**[7:24]** think about how biological neurons
**[7:26]** work every now and then.
**[7:27]** The ideas of neural networks have
**[7:29]** been around for many decades.
**[7:31]** A few people have asked me,
**[7:33]** "Hey Andrew, why now?
**[7:34]** Why is it that only in the last handful
**[7:37]** of years that neural networks have really taken off?"
**[7:40]** This is a picture I draw
**[7:42]** for them when I'm asked that question
**[7:44]** and that maybe you could draw
**[7:46]** for others as well if they ask you that question.
**[7:48]** Let me plot on the horizontal axis
**[7:51]** the amount of data you have for a problem,
**[7:54]** and on the vertical axis,
**[7:56]** the performance or the accuracy of
**[7:58]** a learning algorithm applied to that problem.
**[8:01]** Over the last couple of decades,
**[8:04]** with the rise of the Internet,
**[8:05]** the rise of mobile phones,
**[8:07]** the digitalization of our society,
**[8:09]** the amount of data we have for a lot of
**[8:11]** applications has steadily marched to the right.
**[8:14]** Lot of records that use P on paper,
**[8:17]** such as if you order something
**[8:19]** rather than it being on a piece of paper,
**[8:22]** there's much more likely to be a digital record.
**[8:24]** Your health record, if you see a doctor,
**[8:26]** is much more likely to be digital
**[8:28]** now compared to on pieces of paper.
**[8:31]** So in many application areas,
**[8:34]** the amount of digital data has exploded.
**[8:37]** What we saw was with
**[8:39]** traditional machine-learning algorithms,
**[8:41]** such as logistic regression and linear regression,
**[8:45]** even as you fed those algorithms more data,
**[8:48]** it was very difficult to get
**[8:50]** the performance to keep on going up.
**[8:52]** So it was as if
**[8:54]** the traditional learning algorithms like
**[8:56]** linear regression and logistic regression,
**[8:58]** they just weren't able to scale
**[9:00]** with the amount of data we could now feed it
**[9:02]** and they weren't able to take effective advantage
**[9:04]** of all this data we had for different applications.
**[9:08]** What AI researchers started to observe was
**[9:12]** that if you were to train
**[9:13]** a small neural network on this dataset,
**[9:16]** then the performance maybe looks like this.
**[9:19]** If you were to train a medium-sized neural network,
**[9:23]** meaning one with more neurons in it,
**[9:26]** its performance may look like that.
**[9:28]** If you were to train a very large neural network,
**[9:31]** meaning one with a lot of these artificial neurons,
**[9:34]** then for some applications
**[9:36]** the performance will just keep on going up.
**[9:39]** So this meant two things,
**[9:41]** it meant that for a certain class of
**[9:42]** applications where you do have a lot of data,
**[9:45]** sometimes you hear the term big data toss around,
**[9:48]** if you're able to train
**[9:50]** a very large neural network to take advantage
**[9:53]** of that huge amount of data you have,
**[9:55]** then you could attain performance on anything
**[9:58]** ranging from speech recognition, to image recognition,
**[10:01]** to natural language processing applications and many more,
**[10:04]** they just were not possible with
**[10:06]** earlier generations of learning algorithms.
**[10:09]** This caused deep learning algorithms to take off,
**[10:12]** and this too is why faster computer processors,
**[10:17]** including the rise of GPUs or graphics processor units.
**[10:21]** This is hardware originally designed to
**[10:24]** generate nice-looking computer graphics,
**[10:27]** but turned out to be really
**[10:28]** powerful for deep learning as well.
**[10:31]** That was also a major force in
**[10:34]** allowing deep learning algorithms
**[10:36]** to become what it is today.
**[10:38]** That's how neural networks got started,
**[10:41]** as well as why they took off
**[10:42]** so quickly in the last several years.
**[10:45]** Let's now dive more deeply into
**[10:46]** the details of how neural network actually works.
**[10:49]** Please go on to the next video.
