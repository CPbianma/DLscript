---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 3
section: Detection Algorithms
item_title: Region Proposals (Optional)
duration: 6 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/aCYZv/region-proposals-optional
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Region Proposals (Optional) — Transcript

**[0:00]** If you look at the object detection literature,
**[0:03]** there's a set of ideas called region proposals
**[0:06]** that's been very influential in computer vision as well.
**[0:10]** I wanted to make this video optional because I tend to use
**[0:14]** the region proposal instead of algorithm a bit less often but nonetheless,
**[0:19]** it has been an influential body of work
**[0:22]** and an idea that you might come across in your own work.
**[0:25]** Let's take a look. So, if you recall the sliding windows idea,
**[0:29]** you would take a train crossfire and run it
**[0:33]** across all of these different windows and run the detector to see if there's a car,
**[0:37]** pedestrian, or maybe a motorcycle.
**[0:40]** Now, you could run the algorithm convolutionally,
**[0:42]** but one downside that the algorithm is it just
**[0:45]** crossfires a lot of the regions where there's clearly no object.
**[0:49]** So this rectangle down here is pretty much blank.
**[0:52]** It's clearly nothing interesting there to classify,
**[0:55]** and maybe it was also running it on this rectangle,
**[0:58]** which look likes there's nothing that interesting there.
**[1:01]** So what Russ Girshik, Jeff Donahue, Trevor Darrell,
**[1:04]** and Jitendra Malik proposed in the paper,
**[1:06]** as cited to the bottom of the slide,
**[1:07]** is an algorithm called R-CNN,
**[1:10]** which stands for Regions with convolutional networks or regions with CNNs.
**[1:15]** And what that does is it tries to pick
**[1:18]** just a few regions that makes sense to run your continent crossfire.
**[1:22]** So rather than running your sliding windows on every single window,
**[1:27]** you instead select just a few windows, and
**[1:30]** run your continent crossfire on just a few windows.
**[1:33]** The way that they perform
**[1:35]** the region proposals is to run an algorithm called a segmentation algorithm,
**[1:40]** that results in this output on the right,
**[1:42]** in order to figure out what could be objects.
**[1:46]** So, for example, the segmentation algorithm finds a blob over here.
**[1:50]** And so you might pick that pounding balls and say,
**[1:53]** "Let's run a crossfire on that blob."
**[1:55]** It looks like this little green thing finds a blob there,
**[1:58]** as you might also run the crossfire on
**[2:00]** that rectangle to see if there's some interesting there.
**[2:04]** And in this case,
**[2:06]** this blue blob, if you run a crossfire on that,
**[2:08]** hope you find the pedestrian,
**[2:10]** and if you run it on this light cyan blob,
**[2:13]** maybe you'll find a car, maybe not,.
**[2:16]** I'm not sure. So the details of this,
**[2:17]** this is called a segmentation algorithm,
**[2:20]** and what you do is you find maybe 2000 blobs and place bounding
**[2:25]** boxes around about 2000 blobs and value crossfire on just those 2000 blobs,
**[2:31]** and this can be a much smaller number of positions
**[2:34]** on which to run your continent crossfire,
**[2:37]** then if you have to run it at every single position throughout the image.
**[2:40]** And this is a special case if you are running your continent
**[2:44]** not just on square-shaped regions but running them on
**[2:48]** tall skinny regions to try to find pedestrians or running them on
**[2:51]** your white fat regions try to find cars and running them at multiple scales as well.
**[2:57]** So that's the R-CNN or the region with CNN,
**[3:02]** a region of CNN features idea.
**[3:04]** Now, it turns out the R-CNN algorithm is still quite slow.
**[3:08]** So there's been a line of work to explore how to speed up this algorithm.
**[3:13]** So the basic R-CNN algorithm with proposed regions using
**[3:16]** some algorithm and then crossfire the proposed regions one at a time.
**[3:20]** And for each of the regions,
**[3:22]** they will output the label.
**[3:23]** So is there a car? Is there a pedestrian?
**[3:25]** Is there a motorcycle there?
**[3:27]** And then also outputs a bounding box,
**[3:30]** so you can get an accurate bounding box if indeed there is a object in that region.
**[3:36]** So just to be clear,
**[3:37]** the R-CNN algorithm doesn't just trust the bounding box it was given.
**[3:42]** It also outputs a bounding box,
**[3:44]** B X B Y B H B W,
**[3:46]** in order to get a more accurate bounding box and whatever happened
**[3:51]** to surround the blob that the image segmentation algorithm gave it.
**[3:56]** So it can get pretty accurate bounding boxes.
**[3:58]** Now, one downside of the R-CNN algorithm was that it is actually quite slow.
**[4:03]** So over the years,
**[4:04]** there been a few improvements to the R-CNN algorithm.
**[4:08]** Russ Girshik proposed the fast R-CNN algorithm,
**[4:12]** and it's basically the R-CNN algorithm but with
**[4:15]** a convolutional implementation of sliding windows.
**[4:18]** So the original implementation would actually classify the regions one at a time.
**[4:23]** So far, R-CNN use a convolutional implementation of sliding windows,
**[4:28]** and this is roughly similar to the idea you saw in the fourth video of this week.
**[4:35]** And that speeds up R-CNN quite a bit.
**[4:40]** It turns out that one of the problems of fast R-CNN algorithm is that
**[4:46]** the clustering step to propose the regions is still quite slow and so a different group,
**[4:53]** Shaoqing Ren, Kaiming He, Ross Girshick, and Jian Son,
**[4:56]** proposed the faster R-CNN algorithm,
**[4:59]** which uses a convolutional neural network instead of one of
**[5:02]** the more traditional segmentation algorithms to propose a blob on those regions,
**[5:07]** and that wound up running quite a bit faster than the fast R-CNN algorithm.
**[5:12]** Although, I think the faster R-CNN algorithm,
**[5:15]** most implementations are usually still quit a bit slower than the YOLO algorithm.
**[5:21]** So the idea of region proposals has been quite influential in computer vision,
**[5:27]** and I wanted you to know about these ideas because you see others still used these ideas,
**[5:32]** for myself, and this is my personal opinion,
**[5:35]** not the opinion of the computer vision research committee as a whole.
**[5:38]** I think that we can propose an interesting idea but that not having two steps,
**[5:44]** first, proposed region and then crossfire,
**[5:45]** being able to do everything more or at the same time,
**[5:49]** similar to the YOLO or the You Only Look Once algorithm
**[5:53]** that seems to me like a more promising direction for the long term.
**[5:56]** But that's my personal opinion and not necessary
**[5:58]** the opinion of the whole computer vision research committee.
**[6:01]** So feel free to take that with a grain of salt,
**[6:04]** but I think that the R-CNN idea,
**[6:07]** you might come across others using it.
**[6:10]** So it was worth learning as well so you can understand others algorithms better.
**[6:14]** So we're now finished up our material for this week on object detection.
**[6:21]** I hope you enjoy working on this week's problem exercise,
**[6:25]** and I look forward to seeing you this week.
