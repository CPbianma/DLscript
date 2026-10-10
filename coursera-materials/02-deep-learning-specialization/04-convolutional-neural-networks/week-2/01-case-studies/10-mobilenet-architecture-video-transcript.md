---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Case Studies
item_title: MobileNet Architecture
duration: 9 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/9BqTk/mobilenet-architecture
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# MobileNet Architecture — Transcript

**[0:02]** Welcome back, in the last video you
**[0:06]** learned about the depth-wise separable convolution.
**[0:09]** Let's now put this into a neural network
**[0:11]** in order to build the MobileNet.
**[0:14]** The idea of MobileNet is everywhere that
**[0:17]** you previously have used
**[0:19]** an expensive convolutional operation.
**[0:21]** You can now instead use
**[0:23]** a much less expensive
**[0:25]** depthwise separable convolutional operation,
**[0:28]** comprising the depthwise convolution operation
**[0:33]** and the pointwise convolution operation.
**[0:36]** The MobileNet v1 paper had a specific architecture
**[0:41]** in which it use a block like this, 13 times.
**[0:45]** It would use a depthwise convolutional operation
**[0:49]** to genuine outputs and then have a stack of 13 of
**[0:53]** these layers in order to go from
**[0:56]** the original raw input image to
**[0:58]** finally making a classification prediction.
**[1:02]** Just to provide a few more details after these 13 layers,
**[1:07]** the neural networks last few layers
**[1:10]** are the usual Pooling layer,
**[1:12]** followed by a fully connected layer,
**[1:15]** followed by a Softmax
**[1:17]** in order for it to make a classification prediction.
**[1:20]** This turns out to perform well
**[1:23]** while being much less computationally
**[1:25]** expensive than earlier algorithms
**[1:28]** that used a normal convolutional operation.
**[1:31]** In this video, I want to share with you
**[1:34]** one more improvements on
**[1:36]** this basic MobileNet architecture,
**[1:39]** which is the MobileNets v2 architecture.
**[1:42]** I'm going to go through this
**[1:43]** quite quickly to just give you
**[1:45]** a rough sense of what the algorithm
**[1:46]** does without digging into all of the details.
**[1:49]** But this is a paper published by Mark Sandler and
**[1:52]** his colleagues that make mobile network even better.
**[1:55]** In MobileNet v2, there are two main changes.
**[1:59]** One is the addition of a residual connection.
**[2:03]** This is just a residual connections that you
**[2:05]** learned about in the ResNet videos.
**[2:08]** This residual connection or skip connection,
**[2:11]** takes the input from the previous layer
**[2:14]** and sums it or passes it directly to the next layer,
**[2:18]** does allow ingredients to
**[2:19]** propagate backward more efficiently.
**[2:22]** The second change is that it also as an expansion layer,
**[2:27]** which you learn more about on the next slide,
**[2:30]** before the depthwise convolution,
**[2:33]** followed by the pointwise convolution,
**[2:35]** which we're going to call
**[2:37]** projection in a point-wise convolution.
**[2:39]** Is really the same operation,
**[2:40]** but we'll give it a different name,
**[2:42]** for reasons that you see on the next slide.
**[2:44]** What MobileNet v2 does,
**[2:46]** is it uses this block and
**[2:48]** repeats this block some number of times,
**[2:50]** just like we had 13 times here,
**[2:53]** the MobileNet v2 architecture happened to
**[2:55]** choose to do this 17 times,
**[2:57]** surpass the inputs through 17 of these blocks,
**[3:01]** and then finally ends up with
**[3:03]** the usual pooling fully-connected softmax,
**[3:06]** in order to make a classification prediction.
**[3:09]** But the key idea is really how blocks like this,
**[3:14]** or like this reduces computational cost.
**[3:17]** This block over here is also called the bottleneck block.
**[3:24]** Let's dig into the details of how
**[3:26]** the MobileNet v2 block works.
**[3:29]** Given an input that is say,
**[3:31]** n by n by three,
**[3:35]** the MobileNet v2 bottleneck will pass
**[3:38]** that input via the residual connection
**[3:41]** directly to the output,
**[3:43]** just like in the Resnet.
**[3:45]** Then in this main
**[3:47]** non-residual connection parts of the block,
**[3:50]** you'll first apply an expansion operator,
**[3:54]** and what that means is you'll apply a
**[3:56]** 1 by 1 by n c. In this case,
**[3:59]** one by one by three-dimensional filter.
**[4:02]** But you apply a fairly large number of
**[4:04]** them, say 18 filters,
**[4:06]** so that you end up with an n by
**[4:09]** n by 18-dimensional block over here.
**[4:13]** A factor of expansion of six is
**[4:16]** quite typical in MobileNet v2 which is
**[4:19]** why your inputs goes from n
**[4:21]** by n by three to n by n by 18,
**[4:25]** and that's why we call it an expansion as well,
**[4:27]** it increases the dimension of this by a factor of six,
**[4:31]** the next step is then a depthwise separable convolution.
**[4:37]** With a little bit of padding,
**[4:40]** you can then go from n by n by 18 to the same dimension.
**[4:45]** In the last video, we went from 6 by 6 by 3
**[4:49]** to 4 by 4 by 3 because we didn't use padding.
**[4:52]** But with padding, you can maintain the n
**[4:54]** by n by 18 dimension,
**[4:57]** so it doesn't shrink when you
**[4:58]** apply the depthwise convolution.
**[5:02]** Finally, you apply a pointwise convolution,
**[5:07]** which in this case means convolving with a 1 by
**[5:10]** 1 by 18-dimensional filter.
**[5:14]** If you have, say,
**[5:16]** three filters and c prime filters,
**[5:21]** then you end up with an output that is n by
**[5:25]** n by 3 because you have three such filters.
**[5:30]** In this last step,
**[5:32]** we went from n by n by 18 down to n by n by three,
**[5:37]** and in the MobileNet v2 bottleneck block.
**[5:40]** This last step is also called a projection
**[5:44]** step because you're projecting down from
**[5:47]** n by n by 18 down to n by n by 3.
**[5:51]** You might be wondering, why do we
**[5:53]** meet these bottleneck blocks?
**[5:56]** It turns out that the bottleneck block
**[5:59]** accomplishes two things, One,
**[6:02]** by using the expansion operation,
**[6:04]** it increases the size of
**[6:06]** the representation within the bottleneck block.
**[6:09]** This allows the neural network
**[6:11]** to learn a richer function.
**[6:13]** There's just more computation over here.
**[6:16]** But when deploying on a mobile device,
**[6:20]** on edge device, you will
**[6:22]** often be heavy memory constraints.
**[6:24]** The bottleneck block uses the pointwise convolution or
**[6:29]** the projection operation in order to project it back
**[6:32]** down to a smaller set of values,
**[6:36]** so that when you pass this the next block,
**[6:39]** the amount of memory needed to
**[6:41]** store these values is reduced back down.
**[6:44]** The clever idea, The cool thing about
**[6:46]** the bottleneck block is that it
**[6:48]** enables a richer set of computations,
**[6:50]** thus allow your neural network to learn
**[6:52]** richer and more complex functions,
**[6:54]** while also keeping the amounts of memory that is the size
**[6:58]** of the activations you need to pass from
**[7:00]** layer to layer, relatively small.
**[7:02]** That's why the MobileNet v2 can get
**[7:04]** a better performance than MobileNet v1,
**[7:07]** while still continuing to use
**[7:10]** only a modest amount of compute and memory resources.
**[7:14]** Putting It all together again,
**[7:17]** here's our earliest slide describing MobileNet v1 and v2.
**[7:21]** The MobileNet v2 architecture will
**[7:24]** repeat this bottleneck block 17 times.
**[7:28]** Then if your goal is to make a classification,
**[7:33]** then as usual will have
**[7:35]** this pooling fully-connected softmax layer
**[7:40]** to generate the classification output.
**[7:44]** You now know the main ideas of MobileNet v1 and v2.
**[7:48]** If you want to see a few additional details such as
**[7:52]** the exact dimensions of the different layers as
**[7:55]** you flow the data from left to right.
**[7:58]** You can also take a look at
**[8:00]** the paper by Mark Sandler and others as well.
**[8:03]** Congrats on making it to the end of this video,
**[8:05]** you now know how MobileNet v1 and v2 work by using
**[8:09]** depthwise separable convolutions and by
**[8:12]** using the bottleneck blocks that you saw in this video.
**[8:16]** If you are thinking of
**[8:18]** building efficient neural networks,
**[8:20]** there's one other idea to found very useful,
**[8:24]** and I hope you will learn about as well,
**[8:27]** which is efficient nets.
**[8:28]** Let's touch on that idea very briefly in the next video.
