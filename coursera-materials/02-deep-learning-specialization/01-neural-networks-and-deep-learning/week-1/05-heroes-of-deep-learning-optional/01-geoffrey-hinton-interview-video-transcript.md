---
type: video-transcript
specialization: Deep Learning Specialization
course: Neural Networks and Deep Learning
week: 1
section: Heroes of Deep Learning (Optional)
item_title: Geoffrey Hinton Interview
duration: 40 min
source_url: https://www.coursera.org/learn/neural-networks-deep-learning/lecture/dcm5r/geoffrey-hinton-interview
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Geoffrey Hinton Interview — Transcript

**[0:00]** As part of this course by deeplearning.ai, I
**[0:03]** hope to not just teach you the technical ideas in deep learning, but
**[0:07]** also introduce you to some of the people, some of the heroes in deep learning.
**[0:11]** The people that invented so
**[0:13]** many of these ideas that you learn about in this course or in this specialization.
**[0:17]** In these videos, I hope to also ask these leaders of deep learning
**[0:21]** to give you career advice for how you can break into deep learning, for
**[0:24]** how you can do research or find a job in deep learning.
**[0:27]** As the first of this interview series,
**[0:30]** I am delighted to present to you an interview with Geoffrey Hinton.
**[0:38]** Welcome Geoff, and thank you for doing this interview with deeplearning.ai.
**[0:44]** Thank you for inviting me.
**[0:46]** I think that at this point you more than anyone else on this planet has
**[0:50]** invented so many of the ideas behind deep learning.
**[0:52]** And a lot of people have been calling you the godfather of deep learning.
**[0:57]** Although it wasn't until we were chatting a few minutes ago, until I realized
**[1:01]** you think I'm the first one to call you that, which I'm quite happy to have done.
**[1:06]** But what I want to ask is, many people know you as a legend,
**[1:11]** I want to ask about your personal story behind the legend.
**[1:15]** So how did you get involved in, going way back, how did you get involved in AI and
**[1:19]** machine learning and neural networks?
**[1:22]** So when I was at high school, I had a classmate who was always
**[1:26]** better than me at everything, he was a brilliant mathematician.
**[1:31]** And he came into school one day and said, did you know the brain uses holograms?
**[1:38]** And I guess that was about 1966, and I said, sort of what's a hologram?
**[1:44]** And he explained that in a hologram you can chop off half of it, and
**[1:47]** you still get the whole picture.
**[1:49]** And that memories in the brain might be distributed over the whole brain.
**[1:53]** And so I guess he'd read about Lashley's experiments,
**[1:56]** where you chop off bits of a rat's brain and
**[1:57]** discover that it's very hard to find one bit where it stores one particular memory.
**[2:04]** So that's what first got me interested in how does the brain store memories.
**[2:10]** And then when I went to university,
**[2:12]** I started off studying physiology and physics.
**[2:16]** I think when I was at Cambridge,
**[2:17]** I was the only undergraduate doing physiology and physics.
**[2:21]** And then I gave up on that and
**[2:25]** tried to do philosophy, because I thought that might give me more insight.
**[2:29]** But that seemed to me actually
**[2:32]** lacking in ways of distinguishing when they said something false.
**[2:37]** And so then I switched to psychology.
**[2:41]** And in psychology they had very, very simple theories, and it seemed to me
**[2:45]** it was sort of hopelessly inadequate to explaining what the brain was doing.
**[2:49]** So then I took some time off and became a carpenter.
**[2:52]** And then I decided that I'd try AI, and went of to Edinburgh,
**[2:57]** to study AI with Langer Higgins.
**[2:59]** And he had done very nice work on neural networks, and
**[3:02]** he'd just given up on neural networks, and been very impressed by Winograd's thesis.
**[3:07]** So when I arrived he thought I was kind of doing this old fashioned stuff, and
**[3:11]** I ought to start on symbolic AI.
**[3:14]** And we had a lot of fights about that, but I just kept on doing what I believed in.
**[3:18]** And then what?
**[3:21]** I eventually got a PhD in AI, and then I couldn't get a job in Britain.
**[3:28]** But I saw this very nice advertisement for
**[3:30]** Sloan Fellowships in California, and I managed to get one of those.
**[3:36]** And I went to California, and everything was different there.
**[3:40]** So in Britain, neural nets was regarded as kind of silly,
**[3:46]** and in California, Don Norman and
**[3:50]** David Rumelhart were very open to ideas about neural nets.
**[3:56]** It was the first time I'd been somewhere where thinking about how the brain works,
**[4:00]** and thinking about how that might relate to psychology,
**[4:03]** was seen as a very positive thing.
**[4:05]** And it was a lot of fun there,
**[4:06]** in particular collaborating with David Rumelhart was great.
**[4:09]** I see, great. So this was when you were at UCSD, and
**[4:12]** you and Rumelhart around what, 1982,
**[4:16]** wound up writing the seminal backprop paper, right?
**[4:20]** Actually, it was more complicated than that.
**[4:23]** What happened?
**[4:24]** In, I think, early 1982,
**[4:28]** David Rumelhart and me, and Ron Williams,
**[4:32]** between us developed the backprop algorithm,
**[4:37]** it was mainly David Rumelhart's idea.
**[4:42]** We discovered later that many other people had invented it.
**[4:46]** David Parker had invented, it probably after us, but before we'd published.
**[4:52]** Paul Werbos had published it already quite a few years earlier, but
**[4:56]** nobody paid it much attention.
**[4:58]** And there were other people who'd developed very similar algorithms,
**[5:01]** it's not clear what's meant by backprop.
**[5:04]** But using the chain rule to get derivatives was not a novel idea.
**[5:08]** I see, why do you think it was your paper that helped so
**[5:12]** much the community latch on to backprop?
**[5:15]** It feels like your paper marked an infection in the acceptance of this
**[5:20]** algorithm, whoever accepted it.
**[5:22]** So we managed to get a paper into Nature in 1986.
**[5:26]** And I did quite a lot of political work to get the paper accepted.
**[5:30]** I figured out that one of the referees was probably going to be Stuart Sutherland,
**[5:34]** who was a well known psychologist in Britain.
**[5:36]** And I went to talk to him for a long time, and
**[5:38]** explained to him exactly what was going on.
**[5:41]** And he was very impressed by the fact
**[5:44]** that we showed that backprop could learn representations for words.
**[5:48]** And you could look at those representations, which are little vectors,
**[5:52]** and you could understand the meaning of the individual features.
**[5:55]** So we actually trained it on little triples of words about family trees,
**[6:01]** like Mary has mother Victoria.
**[6:06]** And you'd give it the first two words, and it would have to predict the last word.
**[6:11]** And after you trained it,
**[6:12]** you could see all sorts of features in the representations of the individual words.
**[6:17]** Like the nationality of the person there,
**[6:19]** what generation they were, which branch of the family tree they were in, and so on.
**[6:25]** That was what made Stuart Sutherland really impressed with it, and
**[6:27]** I think that's why the paper got accepted.
**[6:29]** Very early word embeddings, and you're already seeing learned
**[6:33]** features of semantic meanings emerge from the training algorithm.
**[6:38]** Yes, so from a psychologist's point of view, what was interesting was it unified
**[6:44]** two completely different strands of ideas about what knowledge was like.
**[6:49]** So there was the old psychologist's view that a concept is just a big
**[6:53]** bundle of features, and there's lots of evidence for that.
**[6:56]** And then there was the AI view of the time, which is a formal structurist view.
**[7:02]** Which was that a concept is how it relates to other concepts.
**[7:06]** And to capture a concept, you'd have to do something like a graph structure or
**[7:09]** maybe a semantic net.
**[7:11]** And what this back propagation example showed was, you could give it
**[7:15]** the information that would go into a graph structure, or in this case a family tree.
**[7:22]** And it could convert that information into features in such a way that it could then
**[7:26]** use the features to derive new consistent information, ie generalize.
**[7:33]** But the crucial thing was this to and fro between the graphical representation or
**[7:38]** the tree structured representation of the family tree, and
**[7:43]** a representation of the people as big feature vectors.
**[7:46]** And in fact that from the graph-like representation you could get feature
**[7:50]** vectors.
**[7:51]** And from the feature vectors, you could get more of the graph-like representation.
**[7:54]** So this is 1986?
**[7:57]** In the early 90s, Bengio showed that you can actually take real data,
**[8:02]** you could take English text, and apply the same techniques there, and
**[8:07]** get embeddings for real words from English text, and that impressed people a lot.
**[8:13]** I guess recently we've been talking a lot about how fast computers like GPUs and
**[8:18]** supercomputers that's driving deep learning.
**[8:21]** I didn't realize that back between 1986 and the early 90's, it sounds like between
**[8:26]** you and Benjio there was already the beginnings of this trend.
**[8:30]** Yes, it was a huge advance.
**[8:32]** In 1986, I was using a list machine which was less than a tenth of a mega flop.
**[8:41]** And by about 1993 or thereabouts, people were seeing ten mega flops.
**[8:47]** I see. So there was a factor of 100,
**[8:49]** and that's the point at which is was easy to use,
**[8:51]** because computers were just getting faster.
**[8:53]** Over the past several decades, you've invented so
**[8:56]** many pieces of neural networks and deep learning.
**[8:59]** I'm actually curious, of all of the things you've invented,
**[9:02]** which of the ones you're still most excited about today?
**[9:06]** So I think the most beautiful one is the work I do with
**[9:09]** Terry Sejnowski on Boltzmann machines.
**[9:12]** So we discovered there was this really,
**[9:14]** really simple learning algorithm that applied to great big
**[9:18]** density connected nets where you could only see a few of the nodes.
**[9:23]** So it would learn hidden representations and it was a very simple algorithm.
**[9:27]** And it looked like the kind of thing you should be able to get in a brain because
**[9:31]** each synapse only needed to know about the behavior of the two
**[9:34]** neurons it was directly connected to.
**[9:37]** And the information that was propagated was the same.
**[9:41]** There were two different phases, which we called wake and sleep.
**[9:45]** But in the two different phases,
**[9:46]** you're propagating information in just the same way.
**[9:48]** Where as in something like back propagation, there's a forward pass and
**[9:52]** a backward pass, and they work differently.
**[9:54]** They're sending different kinds of signals.
**[9:58]** So I think that's the most beautiful thing.
**[10:01]** And for many years it looked just like a curiosity,
**[10:03]** because it looked like it was much too slow.
**[10:06]** But then later on, I got rid of a little bit of the beauty, and it started letting
**[10:10]** me settle down and just use one iteration, in a somewhat simpler net.
**[10:13]** And that gave restricted Boltzmann machines,
**[10:16]** which actually worked effectively in practice.
**[10:19]** So in the Netflix competition, for example,
**[10:21]** restricted Boltzmann machines were one of the ingredients of the winning entry.
**[10:26]** And in fact, a lot of the recent resurgence of neural net and
**[10:30]** deep learning, starting about 2007, was the restricted Boltzmann machine,
**[10:34]** and derestricted Boltzmann machine work that you and your lab did.
**[10:38]** Yes so that's another of the pieces of work I'm very happy with,
**[10:42]** the idea of that you could train your restricted Boltzmann machine, which just
**[10:46]** had one layer of hidden features and you could learn one layer of feature.
**[10:51]** And then you could treat those features as data and do it again, and
**[10:54]** then you could treat the new features you learned as data and do it again,
**[10:57]** as many times as you liked.
**[10:59]** So that was nice, it worked in practice.
**[11:03]** And then UY Tay realized that the whole thing could be treated as a single model,
**[11:08]** but it was a weird kind of model.
**[11:11]** It was a model where at the top you had a restricted Boltzmann machine, but
**[11:15]** below that you had a Sigmoid belief net which was something that
**[11:20]** invented many years early.
**[11:23]** So it was a directed model and
**[11:24]** what we'd managed to come up with by training these restricted Boltzmann
**[11:28]** machines was an efficient way of doing inferences in Sigmoid belief nets.
**[11:33]** So, around that time,
**[11:36]** there were people doing neural nets, who would use densely connected nets, but
**[11:41]** didn't have any good ways of doing probabilistic imprints in them.
**[11:45]** And you had people doing graphical models, unlike my children,
**[11:50]** who could do inference properly, but only in sparsely connected nets.
**[11:55]** And what we managed to show was the way of learning these deep
**[12:01]** belief nets so that there's an approximate form of inference that's very fast,
**[12:06]** it's just hands in a single forward pass and that was a very beautiful result.
**[12:10]** And you could guarantee that each time you learn that extra layer of features
**[12:16]** there was a band, each time you learned a new layer, you got a new band, and
**[12:19]** the new band was always better than the old band.
**[12:22]** The variational bands, showing as you add layers.
**[12:25]** Yes, I remember that video.
**[12:26]** So that was the second thing that I was really excited about.
**[12:29]** And I guess the third thing was the work I did with on variational methods.
**[12:35]** It turns out people in statistics had done similar work earlier,
**[12:40]** but we didn't know about that.
**[12:44]** So we managed to make
**[12:47]** EN work a whole lot better by showing you didn't need to do a perfect E step.
**[12:50]** You could do an approximate E step.
**[12:52]** And EN was a big algorithm in statistics.
**[12:55]** And we'd showed a big generalization of it.
**[12:58]** And in particular, in 1993, I guess, with Van Camp.
**[13:02]** I did a paper, with I think, the first variational Bayes paper,
**[13:07]** where we showed that you could actually do a version of Bayesian learning
**[13:12]** that was far more tractable, by approximating the true posterior with a.
**[13:17]** And you could do that in neural net.
**[13:20]** And I was very excited by that.
**[13:22]** I see. Wow, right.
**[13:23]** Yep, I think I remember all of these papers.
**[13:26]** You and Hinton, approximate Paper, spent many hours reading over that.
**[13:32]** And I think some of the algorithms you use today, or
**[13:36]** some of the algorithms that lots of people use almost every day, are what,
**[13:41]** things like dropouts, or I guess ReLU activations came from your group?
**[13:46]** Yes and no.
**[13:47]** So other people have thought about rectified linear units.
**[13:51]** And we actually did some work with restricted Boltzmann machines showing
**[13:56]** that a ReLU was almost exactly equivalent to a whole stack of logistic units.
**[14:02]** And that's one of the things that helped ReLUs catch on.
**[14:05]** I was really curious about that.
**[14:07]** The value paper had a lot of math showing that this function
**[14:12]** can be approximated with this really complicated formula.
**[14:15]** Did you do that math so your paper would get accepted into an academic conference,
**[14:19]** or did all that math really influence the development of max of 0 and x?
**[14:26]** That was one of the cases where actually the math was important
**[14:30]** to the development of the idea.
**[14:32]** So I knew about rectified linear units, obviously, and
**[14:35]** I knew about logistic units.
**[14:36]** And because of the work on Boltzmann machines,
**[14:39]** all of the basic work was done using logistic units.
**[14:42]** And so the question was,
**[14:45]** could the learning algorithm work in something with rectified linear units?
**[14:49]** And by showing the rectified linear units were almost exactly equivalent to a stack
**[14:54]** of logistic units, we showed that all the math would go through.
**[15:00]** I see.
**[15:01]** And it provided the inspiration for today, tons of people use ReLU and
**[15:05]** it just works without- Yeah.
**[15:08]** Without necessarily needing to understand the same motivation.
**[15:13]** Yeah, one thing I noticed later when I went to Google.
**[15:16]** I guess in 2014, I gave a talk at Google about using ReLUs and
**[15:22]** initializing with the identity matrix.
**[15:26]** because the nice thing about ReLUs is that if you keep replicating the hidden
**[15:30]** layers and you initialize with the identity,
**[15:32]** it just copies the pattern in the layer below.
**[15:36]** And so I was showing that you could train networks with 300 hidden layers and
**[15:40]** you could train them really efficiently if you initialize with their identity.
**[15:44]** But I didn't pursue that any further and I really regret not pursuing that.
**[15:48]** We published one paper with showing you could initialize an active
**[15:52]** showing you could initialize recurringness like that.
**[15:55]** But I should have pursued it further because Later on these residual
**[16:00]** networks is really that kind of thing.
**[16:03]** Over the years I've heard you talk a lot about the brain.
**[16:06]** I've heard you talk about relationship being backprop and the brain.
**[16:09]** What are your current thoughts on that?
**[16:13]** I'm actually working on a paper on that right now.
**[16:18]** I guess my main thought is this.
**[16:21]** If it turns out the back prop is a really good algorithm for doing learning.
**[16:26]** Then for sure evolution could've figured out how to implement it.
**[16:32]** I mean you have cells that could turn into either eyeballs or teeth.
**[16:37]** Now, if cells can do that, they can for sure implement backpropagation and
**[16:42]** presumably this huge selective pressure for it.
**[16:45]** So I think the neuroscientist idea that it doesn't look plausible is just silly.
**[16:50]** There may be some subtle implementation of it.
**[16:52]** And I think the brain probably has something that may not be exactly be
**[16:56]** backpropagation, but it's quite close to it.
**[16:58]** And over the years, I've come up with a number of ideas about how this might work.
**[17:02]** So in 1987, working with Jay McClelland,
**[17:06]** I came up with the recirculation algorithm,
**[17:11]** where the idea is you send information round a loop.
**[17:17]** And you try to make it so
**[17:18]** that things don't change as information goes around this loop.
**[17:22]** So the simplest version would be you have input units and hidden units, and
**[17:26]** you send information from the input to the hidden and then back to the input, and
**[17:31]** then back to the hidden and then back to the input and so on.
**[17:34]** And what you want, you want to train an autoencoder,
**[17:38]** but you want to train it without having to do backpropagation.
**[17:42]** So you just train it to try and get rid of all variation in the activities.
**[17:47]** So the idea is that the learning rule for
**[17:51]** synapse is change the weighting proportion to the presynaptic input and
**[17:57]** in proportion to the rate of change at the post synaptic input.
**[18:01]** But in recirculation, you're trying to make the post synaptic input,
**[18:04]** you're trying to make the old one be good and the new one be bad, so
**[18:08]** you're changing in that direction.
**[18:11]** We invented this algorithm before neuroscientists come up with
**[18:14]** spike-timing-dependent plasticity.
**[18:16]** Spike-timing-dependent plasticity is actually the same algorithm but the other
**[18:20]** way round, where the new thing is good and the old thing is bad in the learning rule.
**[18:26]** So you're changing the weighting proportions to the preset outlook activity
**[18:30]** times the new person outlook activity minus the old one.
**[18:37]** Later on I realized in 2007, that if you took a stack of
**[18:42]** Restricted Boltzmann machines and you trained it up.
**[18:47]** After it was trained, you then had exactly the right conditions for
**[18:52]** implementing backpropagation by just trying to reconstruct.
**[18:56]** If you looked at the reconstruction era, that reconstruction era would
**[19:01]** actually tell you the derivative of the discriminative performance.
**[19:05]** And at the first deep learning workshop at in 2007, I gave a talk about that.
**[19:12]** That was almost completely ignored.
**[19:16]** Later on, Joshua Benjo, took up the idea and
**[19:19]** that's actually done quite a lot of more work on that.
**[19:24]** And I've been doing more work on it myself.
**[19:26]** And I think this idea that if you have a stack of autoencoders, then you can
**[19:33]** get derivatives by sending activity backwards and locate reconstructionaires,
**[19:38]** is a really interesting idea and may well be how the brain does it.
**[19:42]** One other topic that I know you follow about and that I hear you're still
**[19:47]** working on is how to deal with multiple time skills in deep learning?
**[19:51]** So, can you share your thoughts on that?
**[19:54]** Yes, so actually, that goes back to my first years of graduate student.
**[19:58]** The first talk I ever gave was about using what I called fast weights.
**[20:04]** So weights that adapt rapidly, but decay rapidly.
**[20:07]** And therefore can hold short term memory.
**[20:08]** And I showed in a very simple system in 1973 that you could do
**[20:13]** true recursion with those weights.
**[20:16]** And what I mean by true recursion is that the neurons that is used
**[20:23]** in representing things get re-used for representing things in the recursive core.
**[20:30]** And the weights that is used for
**[20:31]** actually knowledge get re-used in the recursive core.
**[20:34]** And so that leads the question of when you pop out your recursive core,
**[20:39]** how do you remember what it was you were in the middle of doing?
**[20:41]** Where's that memory?
**[20:42]** because you used the neurons for the recursive core.
**[20:46]** And the answer is you can put that memory into fast weights, and
**[20:49]** you can recover the activities neurons from those fast weights.
**[20:53]** And more recently working with Jimmy Ba,
**[20:56]** we actually got a paper in it by using fast weights for recursion like that.
**[21:00]** I see.
**[21:00]** So that was quite a big gap.
**[21:04]** The first model was unpublished in 1973 and
**[21:08]** then Jimmy Ba's model was in 2015, I think, or 2016.
**[21:14]** So it's about 40 years later.
**[21:16]** And, I guess, one other idea of Quite a few years now,
**[21:22]** over five years, I think is capsules, where are you with that?
**[21:29]** Okay, so I'm back to the state I'm used to being in.
**[21:34]** Which is I have this idea I really believe in and nobody else believes it.
**[21:39]** And I submit papers about it and they would get rejected.
**[21:42]** But I really believe in this idea and I'm just going to keep pushing it.
**[21:45]** So it hinges on, there's a couple of key ideas.
**[21:53]** One is about how you represent multi dimensional entities, and you
**[22:00]** can represent multi-dimensional entities by just a little backdoor activities.
**[22:05]** As long as you know there's any one of them.
**[22:07]** So the idea is in each region of the image, you'll assume there's at most,
**[22:12]** one of the particular kind of feature.
**[22:15]** And then you'll use a bunch of neurons, and
**[22:18]** their activities will represent the different aspects to that feature,
**[22:24]** like within that region exactly what are its x and y coordinates?
**[22:27]** What orientation is it at?
**[22:28]** How fast is it moving?
**[22:29]** What color is it?
**[22:30]** How bright is it?
**[22:31]** And stuff like that.
**[22:32]** So you can use a whole bunch of neurons to represent different dimensions of
**[22:36]** the same thing.
**[22:37]** Provided there's only one of them.
**[22:40]** That's a very different way of doing representation
**[22:46]** from what we're normally used to in neural nets.
**[22:48]** Normally in neural nets, we just have a great big layer,
**[22:49]** and all the units go off and do whatever they do.
**[22:52]** But you don't think of bundling them up into little groups that represent
**[22:55]** different coordinates of the same thing.
**[22:58]** So I think we should beat this extra structure.
**[23:02]** And then the other idea that goes with that.
**[23:05]** So this means in the trut 367 00:23:09,280 --> 00:23:11,270 Yes. To different subsets.
**[23:11]** Yes. To represent, right, rather than-
**[23:13]** I call each of those subsets a capsule.
**[23:15]** I see.
**[23:16]** And the idea is a capsule is able to represent an instance of a feature, but
**[23:21]** only one.
**[23:21]** And it represents all the different properties of that feature.
**[23:27]** It's a feature that has a lot of properties as opposed to
**[23:29]** a normal neuron and normal neural nets, which has just one scale of property.
**[23:34]** Yeah, I see yep.
**[23:36]** And then what you can do if you've got that, is you can do something that normal
**[23:41]** neural nets are very bad at, which is you can do what I call routine by agreement.
**[23:48]** So let's suppose you want to do segmentation and
**[23:52]** you have something that might be a mouth and something else that might be a nose.
**[23:57]** And you want to know if you should put them together to make one thing.
**[24:02]** So the idea should have a capsule for
**[24:03]** a mouth that has the parameters of the mouth.
**[24:06]** And you have a capsule for a nose that has the parameters of the nose.
**[24:10]** And then to decipher whether to put them together or
**[24:13]** not, you get each of them to vote for what the parameters should be for a face.
**[24:19]** Now if the mouth and the nose are in the right spacial relationship,
**[24:23]** they will agree.
**[24:24]** So when you get two captures at one level voting for the same set of parameters at
**[24:28]** the next level up, you can assume they're probably right,
**[24:32]** because agreement in a high dimensional space is very unlikely.
**[24:36]** And that's a very different way of doing filtering,
**[24:42]** than what we normally use in neural nets.
**[24:46]** So I think this routing by agreement is going to be crucial for
**[24:50]** getting neural nets to generalize much better from limited data.
**[24:56]** I think it'd be very good at getting the changes in viewpoint,
**[24:59]** very good at doing segmentation.
**[25:01]** And I'm hoping it will be much more statistically efficient than what we
**[25:04]** currently do in neural nets.
**[25:06]** Which is, if you want to deal with changes in viewpoint,
**[25:08]** you just give it a whole bunch of changes in view point and training on them all.
**[25:12]** I see, right, so rather than FIFO learning, supervised learning,
**[25:16]** you can learn this in some different way.
**[25:20]** Well, I still plan to do it with supervised learning, but
**[25:24]** the mechanics of the forward paths are very different.
**[25:27]** It's not a pure forward path in the sense that there's little bits of iteration
**[25:32]** going on, where you think you found a mouth and you think you found a nose.
**[25:36]** And use a little bit of iteration to decide
**[25:39]** whether they should really go together to make a face.
**[25:42]** And you can do back props from that iteration.
**[25:46]** So you can try and do it a little discriminatively,
**[25:50]** and we're working on that now at my group in Toronto.
**[25:54]** So I now have a little Google team in Toronto, part of the Brain team.
**[26:00]** That's what I'm excited about right now.
**[26:02]** I see, great, yeah.
**[26:02]** Look forward to that paper when that comes out.
**[26:05]** Yeah, if it comes out [LAUGH].
**[26:10]** You worked in deep learning for several decades.
**[26:13]** I'm actually really curious, how has your thinking,
**[26:15]** your understanding of AI changed over these years?
**[26:20]** So I guess a lot of my intellectual history has been around back propagation,
**[26:27]** and how to use back propagation, how to make use of its power.
**[26:33]** So to begin with, in the mid 80s, we were using it for
**[26:36]** discriminative learning and it was working well.
**[26:40]** I then decided, by the early 90s,
**[26:42]** that actually most human learning was going to be unsupervised learning.
**[26:46]** And I got much more interested in unsupervised learning, and
**[26:50]** that's when I worked on things like the Wegstein algorithm.
**[26:54]** And your comments at that time really influenced my thinking as well.
**[26:58]** So when I was leading Google Brain, our first project spent a lot of
**[27:03]** work in unsupervised learning because of your influence.
**[27:07]** Right, and I may have misled you.
**[27:09]** Because in the long run,
**[27:11]** I think unsupervised learning is going to be absolutely crucial.
**[27:15]** But you have to sort of face reality.
**[27:19]** And what's worked over the last ten years or so is supervised learning.
**[27:24]** Discriminative training, where you have labels, or
**[27:27]** you're trying to predict the next thing in the series, so that acts as the label.
**[27:31]** And that's worked incredibly well.
**[27:37]** I still believe that unsupervised learning is going to be crucial, and things will
**[27:42]** work incredibly much better than they do now when we get that working properly, but
**[27:47]** we haven't yet.
**[27:49]** Yeah, I think many of the senior people in deep learning,
**[27:53]** including myself, remain very excited about it.
**[27:56]** It's just none of us really have almost any idea how to do it yet.
**[28:01]** Maybe you do, I don't feel like I do.
**[28:04]** Variational altering code is where you use the reparameterization tricks.
**[28:08]** Seemed to me like a really nice idea.
**[28:10]** And generative adversarial nets also seemed to me to be a really nice idea.
**[28:15]** I think generative adversarial nets are one of
**[28:18]** the sort of biggest ideas in deep learning that's really new.
**[28:23]** I'm hoping I can make capsules that successful, but
**[28:26]** right now generative adversarial nets, I think, have been a big breakthrough.
**[28:31]** What happened to sparsity and slow features,
**[28:34]** which were two of the other principles for building unsupervised models?
**[28:41]** I was never as big on sparsity as you were, buddy.
**[28:47]** But slow features, I think, is a mistake.
**[28:52]** You shouldn't say slow.
**[28:53]** The basic idea is right, but you shouldn't go for features that don't change,
**[28:57]** you should go for features that change in predictable ways.
**[29:01]** So here's a sort of basic principle about how you model anything.
**[29:08]** You take your measurements, and you're applying nonlinear
**[29:13]** transformations to your measurements until you get to
**[29:17]** a representation as a state vector in which the action is linear.
**[29:22]** So you don't just pretend it's linear like you do with common filters.
**[29:26]** But you actually find a transformation from the observables to
**[29:29]** the underlying variables where linear operations,
**[29:32]** like matrix multipliers on the underlying variables, will do the work.
**[29:37]** So for example, if you want to change viewpoints.
**[29:39]** If you want to produce the image from another viewpoint,
**[29:42]** what you should do is go from the pixels to coordinates.
**[29:47]** And once you got to the coordinate representation,
**[29:50]** which is a kind of thing I'm hoping captures will find.
**[29:54]** You can then do a matrix multiplier to change viewpoint, and
**[29:57]** then you can map it back to pixels.
**[29:59]** Right, that's why you did all that.
**[29:59]** I think that's a very, very general principle.
**[30:02]** That's why you did all that work on face synthesis, right?
**[30:04]** Where you take a face and compress it to very low dimensional vector, and so
**[30:09]** you can fiddle with that and get back other faces.
**[30:12]** I had a student who worked on that, I didn't do much work on that myself.
**[30:17]** Now I'm sure you still get asked all the time,
**[30:19]** if someone wants to break into deep learning, what should they do?
**[30:23]** So what advice would you have?
**[30:25]** I'm sure you've given a lot of advice to people in one on one settings, but for
**[30:28]** the global audience of people watching this video.
**[30:31]** What advice would you have for them to get into deep learning?
**[30:35]** Okay, so my advice is sort of read the literature, but don't read too much of it.
**[30:42]** So this is advice I got from my advisor, which is very unlike what most people say.
**[30:48]** Most people say you should spend several years reading the literature and
**[30:52]** then you should start working on your own ideas.
**[30:55]** And that may be true for some researchers, but for creative researchers I think
**[31:00]** what you want to do is read a little bit of the literature.
**[31:03]** And notice something that you think everybody is doing wrong,
**[31:07]** I'm contrary in that sense.
**[31:10]** You look at it and it just doesn't feel right.
**[31:13]** And then figure out how to do it right.
**[31:16]** And then when people tell you, that's no good, just keep at it.
**[31:22]** And I have a very good principle for helping people keep at it,
**[31:26]** which is either your intuitions are good or they're not.
**[31:29]** If your intuitions are good, you should follow them and
**[31:32]** you'll eventually be successful.
**[31:34]** If your intuitions are not good, it doesn't matter what you do.
**[31:36]** I see [LAUGH].
**[31:40]** Inspiring advice, might as well go for it.
**[31:43]** You might as well trust your intuitions.
**[31:45]** There's no point not trusting them.
**[31:47]** I see, yeah.
**[31:49]** I usually advise people to not just read, but replicate published papers.
**[31:55]** And maybe that puts a natural limiter on how many you could do,
**[31:58]** because replicating results is pretty time consuming.
**[32:01]** Yes, it's true that when you're trying to replicate a published
**[32:05]** you discover all over little tricks necessary to make it work.
**[32:08]** The other advice I have is, never stop programming.
**[32:11]** Because if you give a student something to do, if they're a bad student,
**[32:15]** they'll come back and say, it didn't work.
**[32:18]** And the reason it didn't work would be some little decision they made,
**[32:22]** that they didn't realize is crucial.
**[32:25]** And if you give it to a good student, like for example.
**[32:28]** You can give him anything and he'll come back and say, it worked.
**[32:32]** I remember doing this once, and I said, but wait a minute.
**[32:36]** Since we last talked,
**[32:37]** I realized it couldn't possibly work for the following reason.
**[32:40]** And said, yeah, I realized that right away, so I assumed you didn't mean that.
**[32:43]** [LAUGH] I see, yeah, that's great, yeah.
**[32:47]** Let's see, any other advice for
**[32:51]** people that want to break into AI and deep learning?
**[32:57]** I think that's basically, read enough so you start developing intuitions.
**[33:02]** And then, trust your intuitions and go for it,
**[33:05]** don't be too worried if everybody else says it's nonsense.
**[33:10]** And I guess there's no way to know if others are right or
**[33:14]** wrong when they say it's nonsense, but you just have to go for it, and then find out.
**[33:19]** Right, but there is one thing, which is, if you think it's a really good idea,
**[33:24]** and other people tell you it's complete nonsense,
**[33:27]** then you know you're really on to something.
**[33:29]** So one example of that is when and I first came up with variational methods.
**[33:35]** I sent mail explaining it to a former student of mine called Peter Brown,
**[33:40]** who knew a lot about.
**[33:43]** And he showed it to people who worked with him,
**[33:46]** called the brothers, they were twins, I think.
**[33:51]** And he then told me later what they said, and they said,
**[33:55]** either this guy's drunk, or he's just stupid, so
**[34:00]** they really, really thought it was nonsense.
**[34:04]** Now, it could have been partly the way I explained it,
**[34:06]** because I explained it in intuitive terms.
**[34:09]** But when you have what you think is a good idea and
**[34:13]** other people think is complete rubbish, that's the sign of a really good idea.
**[34:18]** I see, and research topics,
**[34:21]** new grad students should work on capsules and
**[34:26]** maybe unsupervised learning, any other?
**[34:30]** One good piece of advice for new grad students is,
**[34:34]** see if you can find an advisor who has beliefs similar to yours.
**[34:38]** Because if you work on stuff that your advisor feels deeply about,
**[34:42]** you'll get a lot of good advice and time from your advisor.
**[34:47]** If you work on stuff your advisor's not interested in,
**[34:50]** all you'll get is, you get some advice, but it won't be nearly so useful.
**[34:55]** I see, and last one on advice for learners,
**[34:58]** how do you feel about people entering a PhD program?
**[35:02]** Versus joining a top company, or a top research group?
**[35:09]** Yeah, it's complicated, I think right now, what's happening is,
**[35:13]** there aren't enough academics trained in deep learning to educate all the people
**[35:18]** that we need educated in universities.
**[35:21]** There just isn't the faculty bandwidth there, but
**[35:25]** I think that's going to be temporary.
**[35:27]** I think what's happened is, most departments have been very slow to
**[35:32]** understand the kind of revolution that's going on.
**[35:34]** I kind of agree with you, that it's not quite a second industrial revolution, but
**[35:38]** it's something on nearly that scale.
**[35:41]** And there's a huge sea change going on,
**[35:43]** basically because our relationship to computers has changed.
**[35:47]** Instead of programming them, we now show them, and they figure it out.
**[35:53]** That's a completely different way of using computers, and
**[35:56]** computer science departments are built around the idea of programming computers.
**[36:01]** And they don't understand that sort of,
**[36:05]** this showing computers is going to be as big as programming computers.
**[36:09]** Except they don't understand that half the people in the department should be people
**[36:13]** who get computers to do things by showing them.
**[36:16]** So my department refuses to acknowledge that it should have lots and
**[36:22]** lots of people doing this.
**[36:24]** They think they got a couple, maybe a few more, but not too many.
**[36:31]** And in that situation,
**[36:32]** you have to remind the big companies to do quite a lot of the training.
**[36:36]** So Google is now training people, we call brain residence,
**[36:40]** I suspect the universities will eventually catch up.
**[36:43]** I see, right, in fact, maybe a lot of students have figured this out.
**[36:48]** A lot of top 50 programs, over half of the applicants are actually
**[36:53]** wanting to work on showing, rather than programming.
**[36:57]** Yeah, cool, yeah, in fact, to give credit where it's due,
**[37:00]** whereas a deep learning AI is creating a deep learning specialization.
**[37:04]** As far as I know, their first deep learning MOOC was actually yours taught
**[37:09]** on Coursera, back in 2012, as well.
**[37:12]** And somewhat strangely,
**[37:14]** that's when you first published the RMS algorithm, which also is a rough.
**[37:20]** Right, yes, well, as you know, that was because you invited me to do the MOOC.
**[37:25]** And then when I was very dubious about doing, you kept pushing me to do it, so
**[37:30]** it was very good that I did, although it was a lot of work.
**[37:34]** Yes, and thank you for doing that, I remember you complaining to me,
**[37:37]** how much work it was.
**[37:38]** And you staying out late at night, but I think many, many learners have
**[37:42]** benefited for your first MOOC, so I'm very grateful to you for it, so.
**[37:47]** That's good, yeah Yeah, over the years,
**[37:49]** I've seen you embroiled in debates about paradigms for AI, and
**[37:53]** whether there's been a paradigm shift for AI.
**[37:57]** What are your, can you share your thoughts on that?
**[37:59]** Yes, happily, so I think that in the early days, back in the 50s,
**[38:05]** people like von Neumann and Turing didn't believe in symbolic AI,
**[38:10]** they were far more inspired by the brain.
**[38:14]** Unfortunately, they both died much too young, and their voice wasn't heard.
**[38:20]** And in the early days of AI,
**[38:21]** people were completely convinced that the representations you need for
**[38:26]** intelligence were symbolic expressions of some kind.
**[38:30]** Sort of cleaned up logic, where you could do non-monotonic things, and not quite
**[38:35]** logic, but something like logic, and that the essence of intelligence was reasoning.
**[38:41]** What's happened now is, there's a completely different view,
**[38:45]** which is that what a thought is, is just a great big vector of neural activity,
**[38:50]** so contrast that with a thought being a symbolic expression.
**[38:55]** And I think the people who thought that thoughts were symbolic expressions just
**[38:59]** made a huge mistake.
**[39:01]** What comes in is a string of words, and what comes out is a string of words.
**[39:08]** And because of that, strings of words are the obvious way to represent things.
**[39:12]** So they thought what must be in between was a string of words, or
**[39:15]** something like a string of words.
**[39:18]** And I think what's in between is nothing like a string of words.
**[39:21]** I think the idea that thoughts must be in some kind of language is as silly as
**[39:26]** the idea that understanding the layout of a spatial scene
**[39:30]** must be in pixels, pixels come in.
**[39:34]** And if we could, if we had a dot matrix printer attached to us,
**[39:37]** then pixels would come out, but what's in between isn't pixels.
**[39:43]** And so I think thoughts are just these great big vectors, and
**[39:46]** that big vectors have causal powers.
**[39:48]** They cause other big vectors, and
**[39:50]** that's utterly unlike the standard AI view that thoughts are symbolic expressions.
**[39:56]** I see, good,
**[39:57]** I guess AI is certainly coming round to this new point of view these days.
**[40:01]** Some of it,
**[40:02]** I think a lot of people in AI still think thoughts have to be symbolic expressions.
**[40:08]** Thank you very much for doing this interview.
**[40:09]** It was fascinating to hear how deep learning has evolved over the years,
**[40:12]** as well as how you're still helping drive it into the future, so thank you, Jeff.
