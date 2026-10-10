---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 2
section: Case Studies
item_title: Inception Network Motivation
duration: 10 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/5WIZm/inception-network-motivation
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Inception Network Motivation — Transcript

**[0:00]** When designing a layer for
**[0:01]** a conv layer, you might have to pick.
**[0:03]** Do you want a one-by-three filter
**[0:05]** or three-by-three or five-by-five,
**[0:07]** or do you want a polling layer?
**[0:09]** What the exception network
**[0:10]** does is it says, why don't you do them all?
**[0:13]** This makes the network architecture more complicated,
**[0:16]** but it also works remarkably well.
**[0:18]** Let's see how this works.
**[0:19]** Let's say for the second example that you have
**[0:22]** input a 28 by 28 by 192-dimensional volume.
**[0:27]** What the inception network
**[0:30]** or what an inception layer says is,
**[0:32]** instead of choosing what filter size
**[0:34]** you want in a conv layer
**[0:36]** or even do you want
**[0:38]** a convolutional layer or
**[0:39]** polling layer, let's do them all.
**[0:41]** What if you can use a one-by-one convolution,
**[0:46]** and that will output a 28 by 28 by something,
**[0:50]** let's say, 28 by 28 by 64 output,
**[0:56]** and you just have a volume there?
**[0:58]** But maybe you also want to try a three by three,
**[1:01]** and that might output a 20 by 28 by 128.
**[1:06]** Then what you do is just
**[1:09]** stack up this second volume next to the first volume.
**[1:14]** To make the dimensions match up,
**[1:16]** let's make this same convolution,
**[1:19]** so the output dimension is still 28 by 28,
**[1:23]** same as the input dimension in terms of height and width,
**[1:26]** but 28 by 28 but in this example 128.
**[1:31]** Maybe you might say, well,
**[1:33]** I want to hedge my bets.
**[1:34]** Maybe a five-by-five filter
**[1:36]** works better so let's do that too,
**[1:38]** and have that output a 28 by 28 by 32.
**[1:44]** Again, you use the same convolution
**[1:47]** to keep the dimensions same.
**[1:49]** Maybe you don't want convolutional layer.
**[1:52]** Let's apply pulling, and that has some other output,
**[1:56]** and let's stack that up as well.
**[1:58]** Here, pulling outputs 28 by 28 by 32.
**[2:05]** Now, in order to make all the dimensions match,
**[2:09]** you actually need to use padding for Max pooling.
**[2:12]** This is an unusual form of polling because if you want
**[2:15]** the input to have height and worth 28
**[2:17]** by 28 and have the output,
**[2:20]** match the dimension and everything else also by 28 by 28,
**[2:24]** then you need to use
**[2:25]** same padding as well as a stride of one for polling.
**[2:31]** This detail might seem a bit funny to you now,
**[2:34]** but let's keep going.
**[2:36]** We'll make this all work later.
**[2:39]** But with a inception module like this,
**[2:43]** you can input some volume
**[2:45]** and output, in this case, I guess,
**[2:47]** if you add up all these numbers,
**[2:48]** 32 plus 32 plus 128 plus 64 that's equal to 256.
**[2:55]** You will have one inception module input 28 by 28 by 192,
**[3:01]** and output 28 by 28 by 256.
**[3:06]** This is the heart of the inception network,
**[3:10]** which is due to Cristian Zagoi,
**[3:12]** We Lu Yantin Zia,
**[3:14]** Pi, Scott Reed, Dragoma,
**[3:16]** Anglov Dmitri Rhon Vincent VanKok, and Andrew Rabinovich.
**[3:20]** The basic idea is that instead of you needing to
**[3:24]** pick one of these filter sizes
**[3:27]** or pulling you want and committing to that,
**[3:29]** you can do them all and just contact
**[3:32]** all the outputs and let the network learn
**[3:34]** whatever parameters it wants to use
**[3:36]** whatever combinations of these filter sizes it wants.
**[3:40]** Now, it turns out that there's
**[3:41]** a problem with the inception there,
**[3:43]** as we've described it here,
**[3:44]** which is computational cost.
**[3:46]** On the next slide, let's figure
**[3:48]** out what's the computational cost of
**[3:50]** this five-by-five filter resulting
**[3:54]** in this block over here.
**[3:56]** Just focusing on the five by five part
**[4:00]** on the previous slide,
**[4:02]** we had this input a 288 by 28 by 192 block,
**[4:06]** and you implement a five by five same convolution
**[4:10]** with 32 filters output 28 by 28 by 32.
**[4:14]** On the previous slide,
**[4:16]** I had drawn this as a thin purple slide,
**[4:18]** but I'm just I draw this as
**[4:20]** a more normal-looking blue block here.
**[4:23]** Let's look at the computational cost
**[4:26]** of outputting this 20 by 20 by 32.
**[4:31]** You have 32 filters because the output has 32 channels,
**[4:37]** and each filter is going to be five by five by 192.
**[4:44]** The output size is 20 by 20 by 32,
**[4:48]** and so you need to compute 28 by 28 by 32 numbers,
**[4:53]** and for each of them,
**[4:54]** you need to do this many multiplications,
**[4:58]** five by five by 192.
**[5:01]** The total number of multipliers you need
**[5:03]** is the number of multipliers you need
**[5:06]** to compute each of the output values
**[5:08]** times the number of output values you need to compute.
**[5:12]** If you multiply out all these numbers,
**[5:15]** this is equal to 120 million.
**[5:19]** While you can do 120 million
**[5:22]** multipliers on a modern computer,
**[5:24]** this is still a pretty expensive operation.
**[5:27]** On the next slide, you see how
**[5:29]** using the idea of one-by-one convolutions,
**[5:32]** which you learned about in the previous video,
**[5:34]** you'll be able to reduce the computational cost
**[5:36]** by about a factor of 10 to
**[5:38]** go from about 120 million multipliers
**[5:41]** to about one tenth of that.
**[5:44]** Please remember the number 120,
**[5:47]** so you can compare it with what
**[5:49]** you see on the next slide, 128.
**[5:52]** Here's an alternative architecture
**[5:55]** for inputting twenty-eight by 20 by
**[5:57]** 192 and outputting 28 by 20 by 32 which is following.
**[6:03]** You're going to input the volume,
**[6:05]** use a one-by-one convolution,
**[6:07]** to reduce the volume to
**[6:10]** a 16 channels instead of 192 channels,
**[6:14]** and then on this much smaller volume,
**[6:17]** run your five-by-five convolution
**[6:19]** to give you your final output.
**[6:22]** Notice, the input and output
**[6:23]** dimensions are still the same.
**[6:24]** You input 28 by 20 by 182 and output 28 by 28 by two,
**[6:31]** same as the previous line.
**[6:33]** But what we've done is we've taken
**[6:35]** this huge volume we had on the left,
**[6:37]** and we've shrunk it to
**[6:38]** this much smaller intermediate volume,
**[6:42]** which is only has 16 instead of 192 channels.
**[6:46]** Sometimes this is called a bottleneck layer.
**[6:54]** I guess because a bottleneck
**[6:57]** is usually the smallest part of something.
**[6:59]** I guess if you have a glass bottle that looks like this,
**[7:04]** then this is I guess where the core goes.
**[7:08]** Then the bottleneck is the smallest part of this bottle.
**[7:13]** In the same way, the bottleneck layer
**[7:16]** is the smallest part of this network,
**[7:18]** where you strength the representation
**[7:19]** before increasing the size again.
**[7:22]** Now, let's look at the computational costs involved.
**[7:26]** To apply this one-by-one convolution,
**[7:30]** we have 16 filters.
**[7:32]** Each of the filters is going to be
**[7:34]** of dimension one by one by 192.
**[7:37]** This 192 matches that 192.
**[7:40]** The cost of computing this 28
**[7:42]** by 28 by 16 volume is going to be,
**[7:45]** well, you need this many outputs.
**[7:48]** For each of them, you need to do 192 multiplications.
**[7:54]** I could have written one times one times 192, is this?
**[7:59]** If you multiply this out,
**[8:00]** this is 2.4 million.
**[8:02]** It is about 2.4 million.
**[8:04]** How about the second? That's the cost
**[8:06]** of this first convolutional layer.
**[8:11]** The cost of this second convolutional layer will be that.
**[8:15]** Well, you have this many outputs,
**[8:17]** 28 by 28 by two.
**[8:20]** Then for each of the outputs,
**[8:22]** you have to apply a
**[8:24]** five-by-five by 16-dimensional filter.
**[8:28]** Five by five by 16,
**[8:31]** and if we multiply that out is equal to 10.0.
**[8:36]** The total number of multiplications you
**[8:38]** need to do is the sum of those,
**[8:41]** which is 12.4 million multiplications.
**[8:45]** If you compare this with what
**[8:46]** we had on the previous slide,
**[8:47]** you reduce the computational cost
**[8:49]** from about 120 million multipliers
**[8:53]** down to about one-tenth of that
**[8:55]** to 12.4 million multiplications.
**[8:59]** The number of additions you need to do is
**[9:02]** about very similar to
**[9:04]** the number of multiplications you need to do,
**[9:06]** so that's why I'm just counting
**[9:07]** the number of multiplications.
**[9:10]** To summarize, if you're building a layer of
**[9:13]** a neural network and you don't want to have to decide,
**[9:16]** do you want a one by one or
**[9:17]** three by three or five by five, or pulling layer,
**[9:20]** the inception module lets you say,
**[9:22]** let's do them all and let's concate the results.
**[9:25]** Then we ran to the problem
**[9:27]** of computational cost and which you
**[9:29]** saw here was how using a one-by-one convolution,
**[9:32]** you can create this bottleneck layer
**[9:34]** thereby reducing the computational cost significantly.
**[9:38]** Now, you might be wondering,
**[9:39]** does shrinking down
**[9:41]** the representation size so dramatically,
**[9:43]** does it hurt the performance of your neural network?
**[9:46]** It turns out that so long as you
**[9:48]** implement this bottleneck layer so that within reason,
**[9:52]** you can shrink down
**[9:54]** the representation size significantly,
**[9:56]** and it doesn't seem to hurt the performance,
**[9:59]** but saves you a lot of computation.
**[10:01]** So this is the key of these
**[10:04]** are the key ideas of the inception module.
**[10:07]** Let's put them together and in the next video show
**[10:10]** you what the full inception network looks like.
