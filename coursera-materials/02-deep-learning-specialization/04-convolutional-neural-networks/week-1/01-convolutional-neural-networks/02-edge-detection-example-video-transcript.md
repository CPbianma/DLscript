---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 1
section: Convolutional Neural Networks
item_title: Edge Detection Example
duration: 12 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/4Trod/edge-detection-example
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Edge Detection Example — Transcript

**[0:00]** The convolution operation is one of
**[0:03]** the fundamental building blocks of a convolutional neural network.
**[0:05]** Using edge detection as the motivating example in this video,
**[0:10]** you will see how the convolution operation works.
**[0:16]** In previous videos, I have talked about
**[0:19]** how the early layers of the neural network might detect edges and then
**[0:24]** the some later layers might detect cause of objects and then
**[0:27]** even later layers may detect cause of complete objects like people's faces in this case.
**[0:35]** In this video, you see how you can detect edges in an image.
**[0:40]** Lets take an example.
**[0:42]** Given a picture like that for a computer
**[0:44]** to figure out what are the objects in this picture,
**[0:47]** the first thing you might do is maybe detect vertical edges in this image.
**[0:54]** For example, this image has all those vertical lines,
**[0:58]** where the buildings are,
**[0:59]** as well as kind of vertical lines idea all lines of these pedestrians and
**[1:03]** so those get detected in this vertical edge detector output.
**[1:07]** And you might also want to detect horizontal edges so for example,
**[1:13]** there is a very strong horizontal line where
**[1:15]** this railing is and that also gets detected sort of roughly here.
**[1:18]** How do you detect edges in image like this?
**[1:24]** Let us look with an example.
**[1:26]** Here is a 6 by 6 grayscale image and because this is a grayscale image,
**[1:32]** this is just a 6 by 6 by 1 matrix rather
**[1:36]** than 6 by 6 by 3 because they are on a separate rgb channels.
**[1:41]** In order to detect edges or lets say vertical edges in his image,
**[1:45]** what you can do is construct a 3 by 3 matrix
**[1:49]** and in the pollens when the terminology of convolutional neural networks,
**[1:53]** this is going to be called a filter.
**[1:56]** And I am going to construct a 3 by 3 filter or 3 by 3 matrix that looks like this 1,
**[2:03]** 1, 1, 0, 0, 0, -1, -1, -1.
**[2:08]** Sometimes research papers will call this a kernel instead of
**[2:12]** a filter but I am going to use the filter terminology in these videos.
**[2:17]** And what you are going to do is take the 6 by 6 image and convolve it and
**[2:22]** the convolution operation is denoted by this asterisk and
**[2:26]** convolve it with the 3 by 3 filter.
**[2:31]** One slightly unfortunate thing about the notation is that in mathematics,
**[2:37]** the asterisk is the standard symbol for convolution but in Python,
**[2:42]** this is also used to denote multiplication or maybe element wise multiplication.
**[2:48]** This asterisk has dual purposes is overloaded notation
**[2:52]** but I will try to be clear in these videos when this asterisk refers to convolution.
**[2:58]** The output of this convolution operator will be a 4 by 4 matrix,
**[3:04]** which you can interpret, which you can think of as a 4 by 4 image.
**[3:08]** The way you compute this 4 by 4 output is as follows,
**[3:13]** to compute the first elements,
**[3:15]** the upper left element of this 4 by 4 matrix,
**[3:18]** what you are going to do is take the 3 by 3 filter and paste it on
**[3:21]** top of the 3 by 3 region of your original input image.
**[3:26]** I have written here 1, 1, 1,
**[3:29]** 0, 0, 0, -1, -1, -1.
**[3:34]** And what you should do is take the element wise product so the first one would be
**[3:39]** three times 1 and then the second one would be one times one I'm going down here,
**[3:45]** one times one and then plus two times one,
**[3:49]** just one and then add up all of the resulting nine numbers.
**[3:53]** So then the middle column gives you zero times zero,
**[3:57]** plus five times zero,
**[3:58]** plus seven times zero and then the right most column gives one times -1,
**[4:02]** eight times -1, plus two times -1.
**[4:08]** Adding up these nine numbers will give you negative
**[4:13]** 5 and so I'm going to fill in negative 5 over here.
**[4:19]** You can add up these nine numbers in any order of course.
**[4:22]** It is just that I went down the first column,
**[4:27]** then second column, then the third.
**[4:29]** Next, to figure out what is this second element,
**[4:31]** you are going to take the blue square and shift it one step to the right like so.
**[4:37]** Let me get rid of the green marks here.
**[4:41]** You are going to do the same element wise product and then addition.
**[4:46]** You have zero times one,
**[4:49]** plus five times one,
**[4:51]** plus seven times one,
**[4:52]** plus one time zero, plus eight times zero,
**[4:55]** plus two times zero,
**[4:57]** plus two times negative 1, plus nine times negative one,
**[4:59]** plus five times negative one and if you add up those nine numbers,
**[5:06]** you end up with negative four and so on.
**[5:10]** If you shift this to the right, do the nine products and add them up,
**[5:14]** you get zero and then over here you should get 8.
**[5:19]** Just to verify, you have 2 plus 9 plus 5 that's 16.
**[5:26]** Then the middle column gives you zero and
**[5:29]** then the right most column 4 plus 1 plus three times negative 1,
**[5:33]** that's -8 so that is 16 on the left column -8
**[5:37]** and that gives you 8 like we have over here.
**[5:43]** Next, in order to get you this element in the next row
**[5:48]** what you do is take the blue square and now shift it
**[5:50]** one down so you now have it in that position,
**[5:53]** and again repeat the element wise products and then adding exercise.
**[5:59]** If you do that,
**[6:01]** you should get negative 10 here.
**[6:02]** If you shift it one to the right,
**[6:06]** you should get negative 2 and then 2 and then 3 and so on.
**[6:16]** Then fill in all the rest of the elements of the matrix.
**[6:20]** To be clearer, this -16 would be obtained by from this lower right 3 by 3 region.
**[6:29]** A 6 by 6 matrix convolve of the 3 by 3 matrix gives you a 4 by 4 matrix.
**[6:37]** And these are images and filters.
**[6:39]** These are really just matrices of various dimensions.
**[6:43]** But the matrix on the left is convenient to interpret as image,
**[6:48]** and the one in the middle we interpret as a filter and the one on the right,
**[6:53]** you can interpret that as maybe another image.
**[6:56]** And this turns out to be a vertical edge detector,
**[7:00]** and you see why on the next slide.
**[7:03]** Before going on though,
**[7:04]** just one other comment,
**[7:06]** which is that if you implement this in a programming language,
**[7:09]** then in practice, most foreign languages will have
**[7:12]** some different functions rather than an asterisk to denote convolution.
**[7:16]** For example, in the previous exercise,
**[7:18]** you use or you implement a function called conv-forward.
**[7:23]** If you do this in tens of flow,
**[7:27]** there is a function tf.nn.cont2d.
**[7:29]** And then other deep learning programming frameworks in the CARIS program firmware,
**[7:37]** we shall see later in this course,
**[7:39]** there is a function called cont2d that implements convolution and so on.
**[7:44]** But all the deep learning frameworks that have a good support
**[7:49]** for computer vision will have some functions for implementing this convolution operator.
**[7:56]** Why is this doing vertical edge detection?
**[7:59]** Lets look at another example.
**[8:01]** To illustrate this, we are going to use a simplified image.
**[8:06]** Here is a simple 6 by
**[8:09]** 6 image where the left half of the image is 10 and the right half is zero.
**[8:13]** If you plot this as a picture,
**[8:15]** it might look like this,
**[8:16]** where the left half, the 10s,
**[8:18]** give you brighter pixel
**[8:20]** intensive values and the right half gives you darker pixel intensive values.
**[8:24]** I am using that shade of gray to denote zeros,
**[8:28]** although maybe it could also be drawn as black.
**[8:31]** But in this image,
**[8:32]** there is clearly a very strong vertical edge right down the middle of
**[8:37]** this image as it transitions from white to black or white to darker color.
**[8:43]** When you convolve this with the 3 by
**[8:46]** 3 filter and so this 3 by 3 filter can be visualized as follows,
**[8:52]** where is lighter, brighter pixels on
**[8:56]** the left and then this mid tone zeroes in the middle and then darker on the right.
**[9:01]** What you get is this matrix on the right.
**[9:06]** Just to verify this math if you want,
**[9:09]** this zero for example,
**[9:12]** is obtained by taking
**[9:14]** the element wise products and then multiplying with this 3 by 3 block and
**[9:18]** so you get from
**[9:20]** the left column 10 plus 10 plus 10 and then zeroes in the middle and then -10,
**[9:25]** -10, -10 which is why you end up with zero over here.
**[9:30]** Whereas in contrast, if that 30 will be obtained from this,
**[9:36]** which you get from having 10 plus 10 plus 10 and then minus zero,
**[9:42]** minus zero which is why you end up with a 30 over there.
**[9:47]** Now, if you plot this right most matrix's image it will look
**[9:50]** like that where there is this lighter region right in
**[9:54]** the middle and that corresponds to this having
**[9:57]** detected this vertical edge down the middle of your 6 by 6 image.
**[10:02]** In case the dimensions here seem a
**[10:05]** little bit wrong that the detected edge seems really thick,
**[10:08]** that's only because we are working with very small images in this example.
**[10:13]** And if you are using, say a 1000 by 1000 image rather than a 6 by 6 image then
**[10:17]** you find that this does a pretty good job,
**[10:23]** really detecting the vertical edges in your image.
**[10:27]** In this example, this bright region in the middle is
**[10:30]** just the output images way of saying that it looks like there is
**[10:34]** a strong vertical edge right down the middle of the image.
**[10:39]** Maybe one intuition to take away from vertical edge detection is that a vertical edge is
**[10:45]** a three by three region since we are using a 3 by 3 filter
**[10:48]** where there are bright pixels on the left,
**[10:52]** you do not care that much what is in the middle and dark pixels on the right.
**[10:57]** The middle in this 6 by 6 image is really where there could be
**[11:03]** bright pixels on the left and darker pixels on the right and
**[11:07]** that is why it thinks its a vertical edge over there.
**[11:11]** The convolution operation gives you a convenient way to
**[11:15]** specify how to find these vertical edges in an image.
**[11:20]** You have now seen how the convolution operator works.
**[11:23]** In the next video, you will see how to take this and use it
**[11:26]** as one of the basic building blocks of a Convolution Neural Network.
