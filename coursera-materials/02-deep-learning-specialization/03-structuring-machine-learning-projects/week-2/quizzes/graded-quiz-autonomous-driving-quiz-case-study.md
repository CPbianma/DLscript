---
type: graded-quiz
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 2
section: Machine Learning Flight Simulator (Quiz)
item_title: Autonomous Driving (Quiz Case Study)   
source_url: https://www.coursera.org/learn/machine-learning-projects/assignment-submission/9QaQK/autonomous-driving-quiz-case-study
language: en
extracted_at: 2026-10-08T22:59:23+08:00
grade: 86.66%
status: success
---
# Autonomous Driving (Quiz Case Study)   

**Grade: 86.66%**

## Question 1 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Machine learning projects are most effective when you start with a basic model, analyze its errors, and then iterate to improve it.

To help you practice strategies for machine learning, this week we’ll present another scenario and ask how you would act. We think this “simulator” of working in a machine learning project will give an idea of what leading a machine learning project could be like!

You are employed by a startup building self-driving cars. You are in charge of detecting road signs (stop sign, pedestrian crossing sign, construction ahead sign) and traffic signals (red and green lights) in images. The goal is to recognize which of these objects appear in each image. As an example, this image contains a pedestrian crossing sign and red traffic lights.   

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/57b5bd22-e3ca-4665-b7db-a34af94411a9_344dac091b784ef59262199ed532b378_0d7d2cfa-4e05-439b-880c-7658cab97ba9image1.png?expiry=1791557830488&hmac=bPb8nqnORMYfYzOdaW9_srAp0xMP6pCktMAXDnj9Ks8)

Your 100,000 labeled images are taken using the front-facing camera of your car. This is also the distribution of data you care most about doing well on. You think you might be able to get a much larger dataset off the internet, which could be helpful for training even if the distribution of internet data is not the same.

You are getting started with this project.

**What is the first thing you do?**

*Assume each of the steps below would take about an equal amount of time (a few days).*

- [x] Train a basic model and do error analysis.
- [ ] Spend some time searching the internet for the data most similar to the conditions you expect on production.
- [ ] Spend a few days collecting more data using the front-facing camera of your car, to better understand how much data per unit time you can collect.
- [ ] Invest a few days in thinking on potential difficulties, and then some more days brainstorming about possible solutions, before training any model.

*Points: 1 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again Softmax would be a good choice if only one of the possibilities (stop sign, speed bump, pedestrian crossing, green light, and red light) was present in each image. However, in this scenario, multiple objects can be present in a single image.

Your goal is to detect road signs (stop sign, pedestrian crossing sign, construction ahead sign) and traffic signals (red and green lights) in images. The goal is to recognize which of these objects appear in each image. You plan to use a deep neural network with ReLU units in the hidden layers.

For the output layer, **which of the following gives you the most appropriate activation function?**

- [ ] ReLU
- [x] Softmax
- [ ] Linear
- [ ] Sigmoid

*Points: 0 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Focusing on images that the algorithm got wrong helps you understand its weaknesses. 500 is a reasonable number to start with to get a good initial understanding of the error patterns.

You are carrying out error analysis and counting up what errors the algorithm makes.

Which of these datasets do you think you should manually go through and carefully examine, one image at a time?

- [ ] 500 randomly chosen images
- [ ] 10,000 images on which the algorithm made a mistake
- [x] 500 images on which the algorithm made a mistake
- [ ] 10,000 randomly chosen images

*Points: 1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work As seen in the lecture on multi-task learning, you can compute the cost function in a way that it is not affected by missing labels. The algorithm can still learn from the available labels in the example.

After working on the data for several weeks, your team ends up with the following data:

* 100,000 labeled images taken using the front-facing camera of your car.
* 900,000 labeled images of roads downloaded from the internet.
* Each image’s labels precisely indicate the presence of any specific road signs and traffic signals or combinations of them. For example, y(i)y^{(i)}y(i)y, start superscript, left parenthesis, i, right parenthesis, end superscript = [10010]\begin{bmatrix} 1 \\ 0 \\ 0 \\ 1 \\ 0 \end{bmatrix}⎣⎢⎢⎢⎢⎢⎡​10010​⎦⎥⎥⎥⎥⎥⎤​\begin{bmatrix} 1 \\ 0 \\ 0 \\ 1 \\ 0 \end{bmatrix} means the image contains a stop sign and a red traffic light.

**True or False:** In multi-task learning, if some examples have missing labels (for example: [0?11?]\begin{bmatrix} 0 \\ ? \\ 1 \\ 1 \\ ? \end{bmatrix}⎣⎢⎢⎢⎢⎢⎡​0?11?​⎦⎥⎥⎥⎥⎥⎤​\begin{bmatrix} 0 \\ ? \\ 1 \\ 1 \\ ? \end{bmatrix}), the learning algorithm **cannot** use those examples.

- [ ] True
- [x] False

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes. It is important that your dev and test set have the closest possible distribution to “real” data. It is also important for the training set to contain enough “real” data to avoid having a data-mismatch problem.

The distribution of data you care about contains images from your car’s front-facing camera; which comes from a different distribution than the images you were able to find and download off the internet.

How should you split the dataset into train/dev/test sets?

- [ ] Choose the training set to be the 900,000 images from the internet along with 20,000 images from your car’s front-facing camera. The 80,000 remaining images will be split equally in dev and test sets.
- [ ] Mix all the 100,000 images with the 900,000 images you found online. Shuffle everything. Split the 1,000,000 images dataset into 980,000 for the training set, 10,000 for the dev set and 10,000 for the test set.
- [x] Choose the training set to be the 900,000 images from the internet along with 80,000 images from your car’s front-facing camera. The 20,000 remaining images will be split equally in dev and test sets.
- [ ] Mix all the 100,000 images with the 900,000 images you found online. Shuffle everything. Split the 1,000,000 images dataset into 600,000 for the training set, 200,000 for the dev set and 200,000 for the test set.

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again The difference between the training error and the training-dev error is not high enough to conclude a high variance problem.

Assume you’ve finally chosen the following split between the data:

|  |  |  |
| --- | --- | --- |
| **Dataset:** | **Contains:** | **Error of the algorithm:** |
| Training | 940,000 images randomly picked from (900,000 internet images + 60,000 car’s front-facing camera images) | 12% |
| Training-Dev | 20,000 images randomly picked from (900,000 internet images + 60,000 car’s front-facing camera images) | 15.1% |
| Dev | 20,000 images from your car’s front-facing camera | 12.6% |
| Test | 20,000 images from the car’s front-facing camera | 15.8% |

You also know that human-level error on the road sign and traffic signals classification task is around 0.5%. **Which of the following is true?**

- [ ] You have a large data-mismatch problem.
- [ ] You have a too low avoidable bias.
- [ ] You have a high bias.
- [x] You have a high variance problem.

*Points: 0 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again The Dev/Test errors are much higher, heavily suggesting a higher Bayes error. However, without per distribution human error rate, it is impossible to know for sure.

Assume you’ve finally chosen the following split between the data:

| **Dataset:** | **Contains:** | **Error of the algorithm:** |
| --- | --- | --- |
| Training | 940,000 images randomly picked from (900,000 internet images + 60,000 car’s front-facing camera images) | 8.8% |
| Training-Dev | 20,000 images randomly picked from (900,000 internet images + 60,000 car’s front-facing camera images) | 9.1% |
| Dev | 20,000 images from your car’s front-facing camera | 14.3% |
| Test | 20,000 images from the car’s front-facing camera | 14.8% |

Human-level error on this task is approximately 0.5%. (Bayes error is the lowest possible error rate for a task. Human-level error is a good estimation of Bayes error.)

A friend believes the mixed internet/car images (Training) have a lower Bayes error than the car camera images (Dev/Test). What do you think?

- [x] Your friend is likely incorrect.
- [ ] Your friend is likely correct.
- [ ] There’s insufficient information to determine if your friend is correct or not.

*Points: 0 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work You should consider the trade-off between the data accessibility and potential improvement of your model trained on this additional data.

You decide to focus on the dev set and check by hand what the errors are due to. Here is a table summarizing your discoveries:

|  |  |
| --- | --- |
| Overall dev set error | 15.3% |
| Errors due to incorrectly labeled data | 4.1% |
| Errors due to foggy pictures | 2.0% |
| Errors due to partially occluded elements. | 8.2% |
| Errors due to other causes | 1.0% |

In this table, 4.1%, 8.2%, etc. are a fraction of the total dev set (not just examples of your algorithm mislabeled). For example, about 8.2/15.3 = 54% of your errors are due to partially occluded elements in the image.

**Which of the following is the correct analysis to determine what to prioritize next?**

- [ ] Since 8.2 > 4.1 + 2.0 + 1.0, the priority should be to get more images with partially occluded elements.
- [ ] You should prioritize getting more foggy pictures since that will be easier to solve.
- [ ] Since there is a high number of incorrectly labeled data in the dev set, you should prioritize fixing the labels on the whole training set.
- [x] You should weigh how costly it would be to get more images with partially occluded elements, to decide if the team should work on it or not.

*Points: 1 / 1*

## Question 9 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work The 4.1% only gives you an estimate of the ceiling of how much the error can be improved by fixing the labels.

You decide to focus on the dev set and check by hand what the errors are due to. Here is a table summarizing your discoveries:

|  |  |
| --- | --- |
| Overall dev set error | 15.3% |
| Errors due to incorrectly labeled data | 4.1% |
| Errors due to foggy pictures | 3.0% |
| Errors due to partially occluded elements. | 7.2% |
| Errors due to other causes | 1.0% |

In this table, 4.1%, 7.2%, etc. are a fraction of the total dev set (not just examples of your algorithm mislabeled). For example, about 7.2/15.3 = 47% of your errors are due to partially occluded elements in the image.

**True or False:** From this table, you can conclude that if you fix the incorrectly labeled data you will reduce the overall dev set error to 11.2%.

- [x] False
- [ ] True

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work The synthetic data can help train the model to get better performance on the dev set, but it shouldn't be added to the dev or test sets because they don't represent our target in a completely accurate way.

You decide to use data augmentation to address foggy images. You find 1,000 pictures of fog off the internet and "add" them to clean images to synthesize foggy days, like this:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/b83c3b3b-d1cd-4436-9bb4-abc1268a508e_d7780dce884d4dbbab1fb07a79bd9b40_0d7d2cfa-4e05-439b-880c-7658cab97ba9image2.png?expiry=1791557830504&hmac=un5B4sy2TmnQg6Jng-RD4NgXo91K9Ug_jU_dzTxpJ5c)

**Which one of the following do you agree with?**

- [ ] With this technique, we duplicate the size of the training set by synthesizing a new foggy image for each image in the training set.
- [ ] If used, the synthetic data should be added to the training/dev/test sets in equal proportions.
- [ ] It is irrelevant how the resulting foggy images are perceived by the human eye; the most important thing is that they are correctly synthesized.
- [x] If used, the synthetic data should be added to the training set.

*Points: 1 / 1*

## Question 11 (GradedCheckboxQuestion)

After working further on the problem, you’ve decided to correct the incorrectly labeled data on the dev set. Which of these statements do you agree with?

- [x] You do not necessarily need to fix the incorrectly labeled data in the training set because it's acceptable for the training set distribution to differ from the dev and test sets. Note that it is important that the dev set and test set have the same distribution. ✅correct
  > Feedback: Nice work True, deep learning algorithms are quite robust to having slightly different train and dev distributions.
- [x] You should also correct the incorrectly labeled data in the test set, so that the dev and test sets continue to come from the same distribution. ✅correct
  > Feedback: Nice work Yes, because you want to ensure that your dev and test data come from the same distribution for your algorithm to make your team’s iterative development process efficient.
- [ ] You should correct incorrectly labeled data in the training set as well to avoid your training set now being even more different from your dev set.
- [ ] You should not correct the incorrectly labeled data in the test set, so that the dev and test sets continue to come from the same distribution.

*Points: 1 / 1*

## Question 12 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work The model can benefit from the pre-trained model since there are many features learned by your model that can be used in the new problem.

One of your colleagues at the startup is starting a project to classify road signs as stop, dangerous curve, construction ahead, dead-end, and speed limit signs. Given how specific the signs are, he has only a small dataset and hasn't been able to create a good model. You offer your help providing the trained weights (parameters) of your model to transfer knowledge.

**True or False:** Your colleague points out that his problem has more specific items than the ones you used to train your model. This makes the transfer of knowledge impossible.

- [x] False
- [ ] True

*Points: 1 / 1*

## Question 13 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again Multi-task learning is beneficial because there are shared high-level features among the different types of road signs that can be leveraged.

One of your colleagues at the startup is starting a project to classify road signs as stop, dangerous curve, construction ahead, dead-end, and speed limit signs. He has approximately 30,000 examples of each image and 30,000 images without a sign.

**True or False:** This case could benefit from using multi-task learning.

- [ ] True
- [x] False

*Points: 0 / 1*

## Question 14 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Approach 1 directly maps the input (x) to the output (y) in a single step, which is the definition of an end-to-end approach.

You want to recognize red and green lights in images. You have two approaches:

* **Approach 1**: Input an image (x) into a neural network that directly predicts whether a red or green light is present (y).
* **Approach 2**: First, detect the traffic light in the image (if any). Then, determine the color of the illuminated lamp.

Which approach is a better example of an end-to-end approach?

- [ ] Approach 2
- [x] Approach 1

*Points: 1 / 1*

## Question 15 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work End-to-end learning typically requires large datasets to perform well, as it needs to learn all features directly from the data.

Consider the following two approaches, **A** and **B**:

* **(A)** Input an image (x) to a neural network and have it directly learn a mapping to make a prediction as to whether there’s a red light and/or green light (y).
* **(B)** In this two-step approach, you would first (i) detect the traffic light in the image (if any), then (ii) determine the color of the illuminated lamp in the traffic light.

Approach **A** tends to be more promising than approach **B** if you have a \_\_\_\_\_\_\_\_ (fill in the blank).

- [ ] Problem with a high Bayes error.
- [x] Large training set.
- [ ] Multi-task learning problem.
- [ ] Large bias problem.

*Points: 1 / 1*

