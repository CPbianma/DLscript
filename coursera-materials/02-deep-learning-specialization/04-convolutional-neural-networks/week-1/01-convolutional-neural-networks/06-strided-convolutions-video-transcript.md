---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: Strided Convolutions
duration: 9 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/wfUhx/strided-convolutions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Strided Convolutions — Transcript

**[0:00]** Stride convolutions is another piece of
**[0:04]** the basic building block of
**[0:05]** convolutions as using convolution neural networks.
**[0:09]** Let me show you an example.
**[0:11]** Let's say you want to convolve this serves by
**[0:13]** seven image with this three by three filter.
**[0:16]** Except that instead of doing the usual way,
**[0:19]** we're going to do it with a stride of two.
**[0:23]** What that means, is you take the element wise product as
**[0:28]** usual in this upper left three by
**[0:29]** three region and then multiply and add,
**[0:32]** and that gives you 91.
**[0:35]** But then instead of stepping
**[0:37]** the blue box over by one step,
**[0:38]** we're going to step it over by two steps.
**[0:42]** We're going to make it hop over two steps like so.
**[0:46]** Notice how the upper left-hand corner has
**[0:48]** gone from this start to this start,
**[0:51]** jumping over one position.
**[0:52]** Then you do the usual element-wise product and summing,
**[0:56]** that gives you tones of 100.
**[0:59]** Now we're going to do that again,
**[1:00]** and make the blue box jump over by two steps.
**[1:04]** You end up there and that gives you 83.
**[1:07]** Now when you go to the next row,
**[1:11]** you again actually take two steps instead of one step.
**[1:14]** We're going to move the blue box over there.
**[1:17]** Notice how we're skipping over one of the positions.
**[1:23]** Then just gives you 69,
**[1:25]** and now you gain step over two steps.
**[1:27]** This gives you 91, and so on.
**[1:30]** So 127.
**[1:31]** Then for the final row,
**[1:33]** 44, 72, and 74.
**[1:39]** In this example, we convolve
**[1:42]** with a seven by seven matrix of a,
**[1:44]** three by three matrix,
**[1:45]** and we get a, three by three output.
**[1:49]** The input and output dimensions turns
**[1:51]** out to be governed by the following formula.
**[1:53]** If you have an n by n image convolve
**[1:57]** with an f by f filter.
**[2:00]** If you use adding,
**[2:02]** p and stride s. In this example,
**[2:09]** s is equal to two.
**[2:11]** Then you end up with an output that is n plus 2p,
**[2:16]** minus f. Now because you're
**[2:18]** stepping s steps at
**[2:20]** a time this up just one step at a time,
**[2:22]** you know divide by s plus 1,
**[2:26]** and then by the same thing.
**[2:29]** In our example we have,
**[2:35]** 7+0-3 divided by 2,
**[2:40]** that's a stride plus one equals, let's see,
**[2:45]** that's 4/2+1=3,
**[2:49]** which is why we wind up with this three by three output.
**[2:54]** Now, just one last detail,
**[2:56]** which is one of this fraction is not an integer.
**[3:01]** In that case, we're going to round this down.
**[3:05]** This notation denotes the four or something.
**[3:09]** This is also called the floor of z.
**[3:14]** It means taking z,
**[3:15]** and rounding down to the nearest integer.
**[3:18]** If the way this is implemented is
**[3:20]** that you take this type of
**[3:22]** blue box multiplication only if the blue box is fully
**[3:25]** contained within the image or the image plus the padding.
**[3:29]** If any of this blue box,
**[3:31]** part of it hangs outside then you
**[3:33]** just do not do that computation.
**[3:35]** Then it turns out that if
**[3:38]** that's a convention that your feedback,
**[3:40]** the filter must lie entirely within your image or
**[3:44]** the image plus the padding region
**[3:46]** before there's a corresponding output generator.
**[3:48]** That's convention. Then the right thing to do,
**[3:53]** to compute the output dimension is to round down,
**[3:57]** in case this n+2p-f/s is not an integer.
**[4:01]** Just to summarize the dimensions,
**[4:04]** if you have an n by n matrix or n by n image,
**[4:07]** that you convolve with an f by f matrix and if I
**[4:09]** filter with padding p and stride s,
**[4:12]** then the output size,
**[4:13]** will have this dimension.
**[4:16]** It is nice we can choose all of these numbers,
**[4:19]** so that isn't integer,
**[4:21]** although sometimes you don't have to do
**[4:23]** that and rounding down this is just fine as well.
**[4:27]** But please feel free to work through
**[4:30]** a few examples of values of n, f, p,
**[4:33]** and s for yourself to convince yourself if you want,
**[4:36]** that this formula is correct for the output size.
**[4:41]** Now, before moving on,
**[4:43]** there is a technical comment I want to make
**[4:45]** about cross-correlation verses convolutions.
**[4:48]** This won't affect what you have to
**[4:50]** do to implement convolution neural networks.
**[4:53]** But depending on the DVD,
**[4:56]** different math textbook or signal processing textbook,
**[4:59]** there is one other
**[5:01]** possible inconsistency in the notation.
**[5:04]** Which is that if you look at
**[5:06]** a typical math textbook the way
**[5:08]** that the convolution is defined,
**[5:10]** before doing the element-wise product and summing,
**[5:13]** there's actually one other step
**[5:15]** that you would first take,
**[5:16]** which is to convolve this six by six matrix,
**[5:18]** and this three by three filter,
**[5:20]** you first take the three by three filter,
**[5:23]** and flip it on the
**[5:25]** horizontal as well as the vertical axis.
**[5:28]** There's 3, 4, 5 102 minus 197 will
**[5:32]** become three goes here,
**[5:36]** four goes there, five goes there.
**[5:41]** Then the second row 201 minus 197.
**[5:48]** But this is really taking the three by three filter,
**[5:51]** and mirroring it both on
**[5:53]** the vertical and the horizontal axis.
**[5:57]** Then it was this flipped matrix
**[6:00]** that you would then copy over here.
**[6:03]** To compute the output,
**[6:05]** you would take 2*7 and so on.
**[6:10]** You actually multiply out the elements of
**[6:14]** this filter matrix in order
**[6:15]** to compute the upper left-hand,
**[6:17]** most elements of the four by four output as follows.
**[6:25]** Then you take those nine numbers and your shift them
**[6:28]** over by one, and so on.
**[6:31]** The way we've defined
**[6:33]** the convolution operation in these videos
**[6:35]** is that we've skipped this mirroring operation.
**[6:39]** Technically what we're actually doing?
**[6:42]** Really the operation we've
**[6:43]** been using for the last few videos
**[6:45]** is sometimes cross-correlation instead of convolution.
**[6:50]** That in the deep learning literature,
**[6:52]** by convention, we just call
**[6:54]** this the convolution operation.
**[6:57]** Just to summarize, by convention,
**[7:00]** in machine learning, we usually do
**[7:03]** not bother with this flipping operation.
**[7:05]** Technically this operation is
**[7:08]** maybe better called cross-correlation.
**[7:10]** But most of the deep learning literature just
**[7:12]** causes the convolution operator.
**[7:15]** I'm going to use that convention
**[7:18]** in these videos as well,
**[7:19]** and if you read a lot of the machine learning literature,
**[7:24]** you find most people would just call this,
**[7:26]** the convolution operator without
**[7:28]** bothering to use these flips.
**[7:31]** It turns out that in
**[7:33]** signal processing or in certain branches of mathematics,
**[7:36]** doing the flipping in the definition of
**[7:39]** convolution causes convolution operator,
**[7:43]** to enjoy this property that
**[7:45]** A convolve with B, convolve with C,
**[7:47]** is equal to A convolve with B,
**[7:49]** convolve with C. And this is
**[7:51]** called associativity in mathematics.
**[7:54]** This is nice for some signal processing applications.
**[7:57]** But for deep neural networks,
**[7:59]** it really doesn't matter,
**[8:00]** and so omitting this double mirroring operation
**[8:03]** just simplifies the code,
**[8:05]** and mixing neural network just as well.
**[8:10]** By convention, most of us just call this convolution.
**[8:14]** Even though, the mathematicians prefer to
**[8:16]** call this cross-correlation sometimes.
**[8:20]** But this should not affect anything you have to
**[8:24]** implement in their permanent exercises,
**[8:26]** and should not affect your ability
**[8:29]** to read and understand the deep learning literature.
**[8:33]** You've now seen how to carry out convolutions,
**[8:37]** and you've seen how to use
**[8:38]** padding as well as strides for convolutions.
**[8:41]** But so far all we've been using is convolutions
**[8:44]** over matrices like over a six by six matrix.
**[8:47]** In the next video, you'll see how to
**[8:49]** carry out convolutions over volumes.
**[8:51]** This will make why you can do
**[8:53]** a convolution suddenly much more powerful.
**[8:55]** Let's go on to the next video.
