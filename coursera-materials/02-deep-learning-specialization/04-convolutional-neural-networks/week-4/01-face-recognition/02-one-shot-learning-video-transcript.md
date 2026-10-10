---
type: video-transcript
specialization: Deep Learning Specialization
course: Convolutional Neural Networks
week: 4
section: Face Recognition
item_title: One Shot Learning
duration: 5 min
source_url: https://www.coursera.org/learn/convolutional-neural-networks/lecture/gjckG/one-shot-learning
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# One Shot Learning — Transcript

**[0:00]** One of the challenges of face recognition is that you need to solve the
**[0:05]** one-shot learning problem.
**[0:07]** What that means is that for most face recognition applications
**[0:10]** you need to be able to recognize a person given just one single image, or
**[0:14]** given just one example of that person's face.
**[0:17]** And, historically,
**[0:18]** deep learning algorithms don't work well if you have only one training example.
**[0:23]** Let's see an example of what this means, and
**[0:26]** talk about how to address this problem.
**[0:29]** Let's say you have a database of four pictures of employees in you're
**[0:33]** organization.
**[0:34]** These are actually some of my colleagues at Deeplearning AI; Khan, Danielle,
**[0:38]** Younes, and Thian.
**[0:40]** Now let's say someone shows up at the office and
**[0:43]** they want to be let through the turnstile.
**[0:46]** What the system has to do is, despite ever having seen only one image of Danielle,
**[0:52]** to recognize that this is actually the same person.
**[0:56]** And, in contrast, if it sees someone that's not in this database,
**[0:59]** then it should recognize that this is not any of the four persons in the database.
**[1:04]** So in the one shot learning problem,
**[1:06]** you have to learn from just one example to recognize the person again.
**[1:11]** And you need this for
**[1:12]** most face recognition systems use, because you might have only one picture
**[1:17]** of each of your employees or of your team members in your employee database.
**[1:22]** So one approach you could try is to input the image of the person,
**[1:27]** feed it too a ConvNet.
**[1:30]** And have it output a label, y, using a softmax unit with four outputs or maybe
**[1:36]** five outputs corresponding to each of these four persons or none of the above.
**[1:41]** So that would be 5 outputs in the softmax.
**[1:44]** But this really doesn't work well.
**[1:46]** Because if you have such a small training set it is really not enough
**[1:50]** to train a robust neural network for this task.
**[1:54]** And also what if a new person joins your team?
**[1:57]** So now you have 5 persons you need to recognize, so
**[2:01]** there should now be six outputs.
**[2:03]** Do you have to retrain the ConvNet every time?
**[2:06]** That just doesn't seem like a good approach.
**[2:08]** So to carry out face recognition, to carry out one-shot learning.
**[2:12]** So instead, to make this work,
**[2:14]** what you're going to do instead is learn a similarity function.
**[2:18]** In particular, you want a neural network to learn a function
**[2:22]** which going to denote d, which inputs two images and
**[2:26]** outputs the degree of difference between the two images.
**[2:30]** So if the two images are of the same person,
**[2:34]** you want this to output a small number.
**[2:37]** And if the two images are of two very different people you want it to output
**[2:42]** a large number.
**[2:43]** So during recognition time, if the degree of difference between them is less than
**[2:48]** some threshold called tau, which is a hyperparameter.
**[2:54]** Then you would predict that these two pictures are the same person.
**[2:59]** And if it is greater than tau, you would predict that these are different persons.
**[3:06]** And so this is how you address the face verification problem.
**[3:12]** To use this for a recognition task, what you do is,
**[3:17]** given this new picture, you will use this function d to compare these two images.
**[3:23]** And maybe I'll output a very large number, let's say 10, for this example.
**[3:28]** And then you compare this with the second image in your database.
**[3:32]** And because these two are the same person, hopefully you output a very small number.
**[3:37]** You do this for the other images in your database and so on.
**[3:43]** And based on this, you would figure out that this is actually that person,
**[3:48]** which is Danielle.
**[3:50]** And in contrast, if someone not in your database shows up,
**[3:53]** as you use the function d to make all of these pairwise comparisons,
**[3:57]** hopefully d will output have a very large number for all four pairwise comparisons.
**[4:03]** And then you say that this is not any one of the four persons in the database.
**[4:07]** Notice how this allows you to solve the one-shot learning problem.
**[4:11]** So long as you can learn this function d, which inputs a pair of images and
**[4:16]** tells you, basically, if they're the same person or different persons.
**[4:20]** Then if you have someone new join your team,
**[4:23]** you can add a fifth person to your database, and it just works fine.
**[4:30]** So you've seen how learning this function d, which inputs two images,
**[4:34]** allows you to address the one-shot learning problem.
**[4:38]** In the next video, let's take a look at how you can actually
**[4:41]** train the neural network to learn dysfunction d.
