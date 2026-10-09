---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Transpose Convolutions
duration: 8 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/kyoqR/transpose-convolutions
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Transpose Convolutions — Transcript

**[0:02]** The transpose convolution is
**[0:05]** a key part of the unit architecture.
**[0:07]** How do you take a two-by-two inputs
**[0:10]** and blow it up into a four- by-four-dimensional output?
**[0:14]** The transpose convolution lets you do that.
**[0:17]** Let's dig into the details.
**[0:19]** You're familiar with the normal convolution in which
**[0:22]** a typical layer of a new network may
**[0:24]** input a six by six by three image,
**[0:28]** convolve that with a set of, say,
**[0:31]** three by three by three filters
**[0:33]** and if you have five of these,
**[0:35]** then you end up with an output
**[0:37]** that is four by four by five.
**[0:39]** A transpose convolution looks a bit difference.
**[0:42]** You might inputs a two-by-two, said that activation,
**[0:47]** convolve that with a three by three filter,
**[0:51]** and end up with an output that is four by four,
**[0:54]** that's bigger than the original inputs.
**[0:57]** Let's step through a more detailed example
**[1:00]** of how this works.
**[1:02]** In this example, we're going to take
**[1:05]** a two-by-two inputs like they're
**[1:08]** shown on the left and we want to end
**[1:11]** up with a four by four outputs.
**[1:14]** But to go from two-by-two to four-by-four,
**[1:17]** I'm going to choose to use
**[1:19]** a filter that is three by three.
**[1:22]** The filter is f by f,
**[1:25]** and I'm going to choose three by three
**[1:28]** and let's say that's the filter we will use.
**[1:31]** I'm also going to use
**[1:32]** a padding p is equal to one and in the outputs,
**[1:38]** I'm going to apply,
**[1:39]** that's one p padding, ,and then finally,
**[1:43]** the last parameter, I'm going to use
**[1:45]** a stride s equal to two for this example.
**[1:49]** Let's see how the transpose convolution will work.
**[1:52]** In the regular convolution,
**[1:54]** you would take the filter and place it on
**[1:56]** top of the inputs and then multiply and sum up.
**[2:00]** In the transpose convolution,
**[2:02]** instead of placing the filter on the input,
**[2:05]** you would instead place a filter on the output.
**[2:08]** Let me illustrate that by mechanically stepping
**[2:12]** through the steps of
**[2:13]** the transpose convolution calculation.
**[2:16]** Let's starts with this upper left entry
**[2:19]** of the input, which is a two.
**[2:22]** We are going to take this number two and
**[2:26]** multiply it by every single value in
**[2:30]** the filter and we're going
**[2:32]** to take the output which is three by
**[2:34]** three and paste it in this position.
**[2:39]** Now, the padding area isn't going to contain any values.
**[2:44]** What we're going to end up doing is
**[2:46]** ignore this paddy region and just throw
**[2:50]** in four values in the red highlighted area
**[2:54]** and specifically,
**[2:56]** the upper left entry is zero times two, so that's zero.
**[3:01]** The second entry is one times two, that is two.
**[3:07]** Down here is two times two,
**[3:11]** that's four, and then over here
**[3:14]** is one times two so that's equal to two.
**[3:17]** Next, let's look at
**[3:19]** the second entry of the input which is a one.
**[3:23]** I'm going to switch to green pen for this.
**[3:26]** Once again, we're going to take a one and
**[3:28]** multiply by one every single elements of the filter,
**[3:32]** because we're using a stride of two,
**[3:36]** we're now going to shift to box in which
**[3:40]** we copy the numbers over by two steps.
**[3:44]** Again, we'll ignore the area which is in the padding and
**[3:48]** the only area that we need to copy
**[3:51]** the numbers over is this green shaded area.
**[3:54]** You may notice that there is
**[3:56]** some overlap between the places where we copy
**[3:58]** the red-colored version of the filter and
**[4:02]** the green version and we cannot simply
**[4:05]** copy the green value over the red one.
**[4:09]** Where the red and the green boxes overlap,
**[4:13]** you add two values together.
**[4:18]** Where there's already a
**[4:20]** two from the first weighted filter,
**[4:23]** you add to it this first
**[4:25]** value from the green region which is also two.
**[4:28]** You end up with two plus two.
**[4:30]** The next entry, zero times one is zero,
**[4:33]** then you have one, two plus zero times one,
**[4:37]** so two plus zero followed by two,
**[4:42]** followed by one and again,
**[4:44]** we shifted two squares over from
**[4:47]** the red box here to the green box
**[4:49]** here because it using a stride of two.
**[4:52]** Next, let's look at
**[4:54]** the lower-left entry of the input, which is three.
**[4:58]** We'll take the filter,
**[5:00]** multiply every element by three
**[5:02]** and we've gone down by one step here.
**[5:05]** We're going to go down by two steps here.
**[5:08]** We will be filling in our numbers in this
**[5:13]** three by three square and you find that
**[5:16]** the numbers you copying over are two times three,
**[5:18]** which is six, one times three,
**[5:21]** which is three, zero times three,
**[5:24]** which is zero, and so on,
**[5:26]** three, six, three ,and then lastly,
**[5:29]** let's go into the last input element, which is two.
**[5:35]** We will multiply every elements of the filter by
**[5:38]** two and add them to
**[5:42]** this block and you end up with adding
**[5:45]** one times two which is plus two,
**[5:50]** and so on for the rest of the elements.
**[5:55]** The final step is to take all the numbers in
**[5:57]** these four by four matrix of
**[6:00]** values in the 16 values and add them up.
**[6:03]** You end up with zero here,
**[6:04]** two plus two is four, zero, one,
**[6:09]** four plus six is 10,
**[6:11]** two plus zero plus three plus two is seven,
**[6:15]** two plus four is six.
**[6:17]** I know this looks like a little bit of a mess because I'm
**[6:19]** writing on top of things there is zero,
**[6:21]** three plus four was seven, zero, two,
**[6:25]** six, three plus zero was three,
**[6:28]** four, two, hence that's your four-by-four outputs.
**[6:34]** In case you're wondering why
**[6:36]** do we have to do it this way,
**[6:38]** I think there are multiple possible ways to
**[6:41]** take small inputs and turn it into bigger outputs,
**[6:45]** but the transpose convolution happens to be one that is
**[6:49]** effective and when you learn
**[6:52]** all the parameters of the filter here,
**[6:54]** this turns out to give good results when you put this in
**[6:57]** the context of the union which
**[6:59]** is the learning algorithm will use now.
**[7:02]** Let's go back and keep on building the unit.
**[7:06]** In this video, we step through step-by-step how
**[7:09]** the transpose convolution lets you take a small input,
**[7:12]** say two-by-two, and blow it up into larger output,
**[7:15]** say four by four.
**[7:17]** This is the key building block of the unit architecture
**[7:21]** which you get to implement and play within
**[7:23]** this week's programming exercises well.
**[7:26]** Now that you understand a transpose convolution,
**[7:28]** let's take this building block you now
**[7:30]** have and see how it fits into
**[7:32]** the overall unit architecture
**[7:35]** that you can use for semantic segmentation.
**[7:37]** Let's go on to the next video.
