---
type: video-transcript
specialization: Machine Learning Specialization
course: "Supervised Machine Learning: Regression and Classification"
week: 1
section: Supervised vs. Unsupervised Machine Learning
item_title: Supervised learning part 2
duration: 7 min
source_url: https://www.coursera.org/learn/machine-learning/lecture/Q8Vvp/supervised-learning-part-2
language: en
extracted_at: 2026-10-08T22:15:51+08:00
status: success
---

# Supervised learning part 2 — Transcript

**[0:02]** So supervised learning algorithms learn to predict input, output or X to Y mapping.
**[0:08]** And in the last video you saw that regression algorithms,
**[0:12]** which is a type of supervised learning algorithm learns to predict numbers out
**[0:17]** of infinitely many possible numbers.
**[0:20]** There's a second major type of supervised learning algorithm called a classification
**[0:24]** algorithm.
**[0:25]** Let's take a look at what this means.
**[0:28]** Take breast cancer detection as an example of a classification problem.
**[0:35]** Say you're building a machine learning system so
**[0:37]** that doctors can have a diagnostic tool to detect breast cancer.
**[0:41]** This is important because early detection could potentially save a patient's life.
**[0:46]** Using a patient's medical records your machine learning system tries to
**[0:51]** figure out if a tumor that is a lump is malignant meaning cancerous or dangerous.
**[0:57]** Or if that tumor, that lump is benign, meaning that it's just
**[1:02]** a lump that isn't cancerous and isn't that dangerous?
**[1:06]** Some of my friends have actually been working on this specific problem.
**[1:10]** So maybe your dataset has tumors of various sizes.
**[1:15]** And these tumors are labeled as either benign,
**[1:19]** which I will designate in this example with a 0 or
**[1:23]** malignant, which will designate in this example with a 1.
**[1:28]** You can then plot your data on a graph like this where
**[1:33]** the horizontal axis represents the size of the tumor and
**[1:38]** the vertical axis takes on only two values 0 or
**[1:42]** 1 depending on whether the tumor is benign, 0 or malignant 1.
**[1:48]** One reason that this is different from regression is that we're trying to predict
**[1:48]** only a small number of possible outputs or categories.
**[1:49]** In this case two possible
**[1:55]** outputs 0 or 1,
**[1:59]** benign or malignant.
**[2:04]** This is different from regression which tries to predict any number,
**[2:10]** all of the infinitely many number of possible numbers.
**[2:14]** And so the fact that there are only two possible outputs is
**[2:18]** what makes this classification.
**[2:21]** Because there are only two possible outputs or
**[2:25]** two possible categories in this example,
**[2:28]** you can also plot this data set on a line like this.
**[2:32]** Right now, I'm going to use two different symbols to denote
**[2:38]** the category using a circle an O to denote the benign examples and
**[2:43]** a cross to denote the malignant examples.
**[2:47]** And if new patients walks in for a diagnosis and
**[2:51]** they have a lump that is this size, then the question is,
**[2:57]** will your system classify this tumor as benign or malignant?
**[3:02]** It turns out that in classification problems you can also have more than two
**[3:07]** possible output categories.
**[3:09]** Maybe you're learning algorithm can output multiple types of cancer
**[3:14]** diagnosis if it turns out to be malignant.
**[3:17]** So let's call two different types of cancer type 1 and type 2.
**[3:22]** In this case the average would have three possible output
**[3:27]** categories it could predict.
**[3:29]** And by the way in classification, the terms output classes and
**[3:34]** output categories are often used interchangeably.
**[3:37]** So what I say class or category when referring to the output,
**[3:42]** it means the same thing.
**[3:44]** So to summarize classification algorithms predict categories.
**[3:50]** Categories don't have to be numbers.
**[3:52]** It could be non numeric for example,
**[3:56]** it can predict whether a picture is that of a cat or a dog.
**[4:01]** And it can predict if a tumor is benign or malignant.
**[4:07]** Categories can also be numbers like 0, 1 or 0, 1, 2.
**[4:12]** But what makes classification different from regression when
**[4:17]** you're interpreting the numbers is that classification predicts
**[4:23]** a small finite limited set of possible output categories such as 0, 1 and
**[4:29]** 2 but not all possible numbers in between like 0.5 or 1.7.
**[4:34]** In the example of supervised learning that we've been looking at,
**[4:40]** we had only one input value the size of the tumor.
**[4:45]** But you can also use more than one input value to predict an output.
**[4:51]** Here's an example, instead of just knowing the tumor size,
**[4:55]** say you also have each patient's age in years.
**[4:59]** Your new data set now has two inputs, age and tumor size.
**[5:04]** What in this new dataset we're going to use circles to show patients whose tumors
**[5:11]** are benign and crosses to show the patients with a tumor that was malignant.
**[5:17]** So when a new patient comes in, the doctor can measure the patient's tumor size and
**[5:23]** also record the patient's age.
**[5:25]** And so given this,
**[5:26]** how can we predict if this patient's tumor is benign or malignant?
**[5:32]** Well, given the day said like this, what the learning algorithm might do
**[5:37]** is find some boundary that separates out the malignant tumors from the benign ones.
**[5:44]** So the learning algorithm has to decide how to fit a boundary line
**[5:48]** through this data.
**[5:50]** The boundary line found by the learning algorithm would help the doctor with
**[5:54]** the diagnosis.
**[5:55]** In this case the tumor is more likely to be benign.
**[6:00]** From this example we have seen how to inputs the patient's age and
**[6:05]** tumor size can be used.
**[6:07]** In other machine learning problems often many more input values are required.
**[6:12]** My friends who worked on breast cancer detection use many additional inputs,
**[6:17]** like the thickness of the tumor clump, uniformity of the cell size,
**[6:22]** uniformity of the cell shape and so on.
**[6:24]** So to recap supervised learning maps input x to output y,
**[6:29]** where the learning algorithm learns from the quote right answers.
**[6:35]** The two major types of supervised learning our regression and classification.
**[6:41]** In a regression application like predicting prices of houses, the learning
**[6:45]** algorithm has to predict numbers from infinitely many possible output numbers.
**[6:50]** Whereas in classification the learning algorithm has to make a prediction of
**[6:55]** a category, all of a small set of possible outputs.
**[6:58]** So you now know what is supervised learning,
**[7:01]** including both regression and classification.
**[7:05]** I hope you're having fun.
**[7:06]** Next there's a second major type of machine learning
**[7:10]** called unsupervised learning.
**[7:12]** Let's go on to the next video to see what that is
