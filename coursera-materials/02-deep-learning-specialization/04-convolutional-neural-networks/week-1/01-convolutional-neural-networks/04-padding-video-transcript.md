---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: Padding
duration: 10 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/o7CWi/padding
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Padding — Transcript

**[0:01]** In order to build deep neural networks one modification to
**[0:05]** the basic convolutional operation that you need to really use is padding.
**[0:10]** Let's see how it works.
**[0:12]** What we saw in earlier videos is that if you take
**[0:15]** a six by six image and convolve it with a three by three filter,
**[0:19]** you end up with a four by four output with a four by four matrix,
**[0:23]** and that's because the number of possible positions with the three by three filter,
**[0:28]** there are only, sort of,
**[0:29]** four by four possible positions,
**[0:31]** for the three by three filter to fit in your six by six matrix.
**[0:37]** And the math of this this turns out to be that if you have
**[0:41]** a end by end image and to involved that with an f by f filter,
**[0:45]** then the dimension of the output will be;
**[0:48]** n minus f plus one by n minus f plus one.
**[0:58]** And in this example,
**[0:59]** six minus three plus one is equal to four,
**[1:03]** which is why you wound up with a four by four output.
**[1:07]** So the two downsides to this; one is that,
**[1:10]** if every time you apply a convolutional operator, your image shrinks,
**[1:14]** so you come from six by six down to four by four then,
**[1:17]** you can only do this a few times before your image starts getting really small,
**[1:21]** maybe it shrinks down to one by one or something,
**[1:23]** so maybe, you don't want your image to shrink
**[1:26]** every time you detect edges or to set other features on it,
**[1:29]** so that's one downside,
**[1:31]** and the second downside is that,
**[1:33]** if you look the pixel at the corner or the edge,
**[1:36]** this little pixel is touched as used only in one of the outputs,
**[1:40]** because this touches that three by three region.
**[1:43]** Whereas, if you take a pixel in the middle, say this pixel,
**[1:48]** then there are a lot of three by three regions that overlap that pixel and so,
**[1:55]** is as if pixels on the corners or on the edges are use much less in the output.
**[2:01]** So you're throwing away a lot of the information near the edge of the image.
**[2:06]** So, to solve both of these problems,
**[2:08]** both the shrinking output,
**[2:12]** and when you build really deep neural networks,
**[2:15]** you see why you don't want the image to shrink on every step because if you have,
**[2:19]** maybe a hundred layer of deep net,
**[2:22]** then it'll shrinks a bit on every layer,
**[2:23]** then after a hundred layers you end up with a very small image.
**[2:27]** So that was one problem,
**[2:29]** the other is throwing away a lot of the information from the edges of the image.
**[2:38]** So in order to fix both of these problems,
**[2:40]** what you can do is the full apply of convolutional operation.
**[2:44]** You can pad the image.
**[2:46]** So in this case, let's say you pad the image with an additional one border,
**[2:56]** with the additional border of one pixel all around the edges.
**[3:00]** So, if you do that,
**[3:02]** then instead of a six by six image,
**[3:05]** you've now padded this to eight by eight image and if you
**[3:09]** convolve an eight by eight image with a three by three image you now get that out.
**[3:14]** Now, the four by four by the six by six image,
**[3:16]** so you managed to preserve the original input size of six by six.
**[3:23]** So by convention when you pad,
**[3:25]** you padded with zeros and if p is the padding amounts.
**[3:33]** So in this case,
**[3:34]** p is equal to one,
**[3:36]** because we're padding all around with an extra boarder of one pixels,
**[3:41]** then the output becomes n plus 2p
**[3:47]** f plus one by n plus 2p minus f by one.
**[3:54]** So, this becomes six plus two times one minus three plus one by the same thing on that.
**[4:02]** So, six plus two minus three plus one, that's equals to six.
**[4:06]** So you end up with a six by six image that preserves the size of the original image.
**[4:12]** So this being pixel actually influences all of
**[4:16]** these cells of the output and so this effective,
**[4:23]** maybe not by throwing away but counting less
**[4:26]** the information from the edge of the corner or the edge of the image is reduced.
**[4:32]** And I've shown here,
**[4:34]** the effect of padding deep border with just one pixel.
**[4:38]** If you want, you can also pad the border with two pixels, in which case I guess,
**[4:42]** you do add on another border
**[4:44]** here and they can pad it with even more pixels if you choose.
**[4:50]** So, I guess what I'm drawing here,
**[4:52]** this would be a padded equals to p plus two.
**[4:55]** In terms of how much to pad,
**[5:00]** it turns out there two common choices that are called,
**[5:04]** Valid convolutions and Same convolutions.
**[5:07]** Not really is a great names but in a valid convolution,
**[5:10]** this basically means no padding.
**[5:15]** And so in this case you might have n by n image convolve with an f by f filter
**[5:22]** and this would give you an n minus f plus one
**[5:25]** by n minus f plus one dimensional output.
**[5:30]** So this is like the example we had previously on the previous videos where we
**[5:35]** had an n by n image convolve with
**[5:37]** the three by three filter and that gave you a four by four output.
**[5:43]** The other most common choice of padding is called
**[5:48]** the same convolution and that means when you pad,
**[5:52]** so the output size is the same as the input size.
**[5:58]** So if we actually look at this formula,
**[6:01]** when you pad by p pixels then,
**[6:04]** its as if n goes to n plus 2p and then you have from the rest of this, right?
**[6:11]** Minus f plus one.
**[6:15]** So we have an n by n image and the padding of a border of p pixels all around,
**[6:22]** then the output sizes of this dimension is xn plus 2p minus f plus one.
**[6:28]** And so, if you want n plus 2p minus f plus one to be equal to one,
**[6:36]** so the output size is same as input size,
**[6:38]** if you take this and solve for, I guess,
**[6:42]** n cancels out on both sides and if you solve for p,
**[6:46]** this implies that p is equal to f minus one over two.
**[6:53]** So when f is odd,
**[6:56]** by choosing the padding size to be as follows,
**[6:58]** you can make sure that the output size is same as
**[7:01]** the input size and that's why, for example,
**[7:06]** when the filter was three by three as this had happened in the previous slide,
**[7:10]** the padding that would make the output size the same as the input size was three minus
**[7:15]** one over two, which is one.
**[7:21]** And as another example,
**[7:23]** if your filter was five by five,
**[7:28]** so if f is equal to five, then,
**[7:30]** if you pad it into that equation you find that the padding of two is required to keep
**[7:35]** the output size the same as the input size when the filter is five by five.
**[7:43]** And by convention in computer vision,
**[7:46]** f is usually odd.
**[7:50]** It's actually almost always odd and you rarely see even numbered filters,
**[7:59]** filter works using computer vision.
**[8:02]** And I think that two reasons for that;
**[8:05]** one is that if f was even,
**[8:07]** then you need some asymmetric padding.
**[8:10]** So only if f is odd that this type of same convolution gives a natural padding region,
**[8:15]** had the same dimension all around rather than
**[8:17]** pad more on the left and pad less on the right,
**[8:20]** or something that asymmetric.
**[8:22]** And then second, when you have an odd dimension filter,
**[8:27]** such as three by three or five by five,
**[8:29]** then it has a central position and sometimes in
**[8:32]** computer vision its nice to have a distinguisher,
**[8:36]** it's nice to have a pixel,
**[8:37]** you can call the central pixel so you can talk about the position of the filter.
**[8:43]** Right, maybe none of this is a great reason for using f to be pretty much always
**[8:48]** odd but if you look a convolutional literature you
**[8:50]** see three by three filters are very common.
**[8:53]** You see some five by five, seven by sevens.
**[8:56]** And actually sometimes, later we'll also talk
**[8:58]** about one by one filters and that why that makes sense.
**[9:02]** But just by convention,
**[9:04]** I recommend you just use odd number filters as well.
**[9:08]** I think that you can probably get
**[9:10]** just fine performance even if you want to use an even number value for f,
**[9:14]** but if you stick to the common computer vision convention,
**[9:18]** I usually just use odd number f. So you've now seen how to use padded convolutions.
**[9:25]** To specify the padding for your convolution operation,
**[9:28]** you can either specify the value for
**[9:31]** p or you can just say that this is a valid convolution,
**[9:34]** which means p equals zero or you can say this is a same convolution,
**[9:38]** which means pad as much as you need to make sure
**[9:40]** the output has same dimension as the input.
**[9:43]** So that's it for padding.
**[9:45]** In the next video, let's talk about how you can implement Strided convolutions.
