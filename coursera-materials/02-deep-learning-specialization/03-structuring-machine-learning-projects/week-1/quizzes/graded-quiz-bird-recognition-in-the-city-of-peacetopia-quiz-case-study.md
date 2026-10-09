---
type: graded-quiz
specialization: Deep Learning Specialization
course: Structuring Machine Learning Projects
week: 1
section: Machine Learning Flight Simulator (Quiz)
item_title: Bird Recognition in the City of Peacetopia (Quiz Case Study)   
source_url: https://www.coursera.org/learn/machine-learning-projects/assignment-submission/JBzL3/bird-recognition-in-the-city-of-peacetopia-quiz-case-study
language: en
extracted_at: 2026-10-08T22:59:23+08:00
grade: 83.33%
status: success
---
# Bird Recognition in the City of Peacetopia (Quiz Case Study)   

**Grade: 83.33%**

## Question 1 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again While multiple metrics can provide a comprehensive evaluation, focusing on a single primary metric is crucial for streamlining development and decision-making processes.

This example is adapted from a real production application, with details modified for confidentiality.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ed7e4610-be46-4a3a-8a2e-bc18bd2ad6aa_2ac993d440b54dc8b181f30c1021cc3e_8a8b436a-5102-4743-a9b5-37aed930071fimage1.png?expiry=1791557803793&hmac=tXNDTy1aiIgPs3bVVYLrWHiPXcUvbwHQCZB8CjF774k)

You are a renowned researcher in the City of Peacetopia. The residents of Peacetopia share a unique characteristic: they are afraid of birds. To protect them, you are tasked with developing an algorithm that will detect any bird flying over Peacetopia and alert the population.

The City Council provides you with a dataset of 10,000,000 images of the sky above Peacetopia, captured by the city’s security cameras. They are labeled:

* y = 0: There is no bird on the image
* y = 1: There is a bird on the image

**Your goal is to create an algorithm capable of classifying new images taken by security cameras in Peacetopia.** You have several decisions to make regarding the evaluation metric and how to structure your data into train/dev/test sets.

The City Council specifies that they want an algorithm that:

1. Has high accuracy.
2. Operates quickly and takes only a short time to classify a new image.
3. Requires minimal memory, allowing it to run on a small processor attached to various security cameras.

**True or False:** You discuss with them the need for a singular evaluation metric to guide development.

- [ ] True
- [x] False

*Points: 0 / 1*

## Question 2 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work The runtime is less than 10 seconds, and the accuracy meets the minimum 98% requirement.

After further discussions, the city narrows down its criteria to:

* "We need an algorithm that can let us know a bird is flying over Peacetopia as accurately as possible."
* "We want the trained model to take no more than 10 seconds to classify a new image.”
* “We want the model to fit in 10MB of memory.”
* "We require a minimum of 98% test accuracy."

If you had the three following models, which one would you choose?

- [ ] Test AccuracyRuntimeMemory size97%3 sec2MB
- [ ] Test AccuracyRuntimeMemory size97%1 sec3MB
- [ ] Test AccuracyRuntimeMemory size99%13 sec9MB
- [x] Test AccuracyRuntimeMemory size98%9 sec9MB

*Points: 1 / 1*

## Question 3 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Setting thresholds for satisficing metrics is crucial for evaluating whether key project constraints are met.

Which of the following **best explains** why it is important to identify optimizing and satisficing metrics in a project?

- [x] Identifying the metric types sets thresholds for satisficing metrics. This provides explicit evaluation criteria.
- [ ] It isn’t. All metrics must be met for the model to be acceptable.
- [ ] Knowing the metrics provides input for efficient project planning.
- [ ] Identifying the optimizing metric informs the team which models they should try first.

*Points: 1 / 1*

## Question 4 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work The size of the data set allows for effective bias and variance evaluation with smaller data sets.

With 10,000,000 data points, what is the best option for train/dev/test splits?

- [ ] train - 60%, dev - 10%, test - 30%
- [ ] train - 60%, dev - 30%, test - 10%
- [x] train - 95%, dev - 2.5%, test - 2.5%
- [ ] train - 33.3%, dev - 33.3%, test - 33.3%

*Points: 1 / 1*

## Question 5 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work It is not a problem to have different training and dev distributions. Different dev and test distributions would be an issue.

Now that you’ve set up your train/dev/test sets, the City Council comes across another 1,000,000 images from social media and offers them to you. These images have a different distribution from the images the City Council originally provided, but you think they could help your algorithm.

**Which of the following is the best use of that additional data?**

- [ ] Do not use the data. It will change the distribution of any set it is added to.
- [x] Add it to the training set.
- [ ] Add it to the dev set to evaluate how well the model generalizes across a broader set.
- [ ] Split it among train/dev/test equally.

*Points: 1 / 1*

## Question 6 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work The test set must accurately represent the real-world data distribution to properly evaluate model performance. Adding citizen data images to the test set would skew this distribution.

One member of the City Council wants to add 1,000,000 citizen data images evenly to the training, development (dev), and test sets. Your original data is from security cameras, and you object because:

- [x] If we add the images to the test set, then it won't reflect the distribution of data (security cameras) expected in production.
- [ ] The additional data would significantly slow down training time.
- [ ] The 1,000,000 citizen data images do not have a consistent input-output relationship as the security camera data.
- [ ] The training set will not be as accurate because of the different distributions.

*Points: 1 / 1*

## Question 7 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Avoidable bias is 4.2%, which is larger than the 2.1% variance, so reducing bias is the priority.

Human performance for identifying birds is < 1%, training set error is 5.2%, and dev set error is 7.3%.

**Which of the options below is the best next step?**

- [ ] Try an ensemble model to reduce bias and variance.
- [ ] Get more data or apply regularization to reduce variance.
- [ ] Validate the human data set with a sample of your data to ensure the images are of sufficient quality.
- [x] Train a bigger network to reduce the 5.2% training error.

*Points: 1 / 1*

## Question 8 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work The best human performance, represented by the lowest error rate, is the closest practical estimate of Bayes' error.

You want to define "human-level performance" for a bird species identification project to present to the city council. Which of the following is the best way to define it?

- [ ] The average performance of regular citizens of Peacetopia (1.2%).
- [ ] The average performance of all the city's ornithologists (0.5%).
- [x] The performance of the city's best ornithologist (0.3% error rate).
- [ ] The average of all recorded error rates (0.66%, ornithologists and citizens).

*Points: 1 / 1*

## Question 9 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work By definition, a learning algorithm can outperform human-level performance but not surpass Bayes error, which is the theoretical limit of accuracy.

**True or False:** A learning algorithm’s performance can be better than human-level performance but it can never be better than Bayes error.

- [x] True.
- [ ] False.

*Points: 1 / 1*

## Question 10 (GradedMultipleChoiceQuestion)

**✅ Correct** — Nice work Yes, addressing the largest performance gap (between human-level and training error) is the most efficient strategy.

Which of the following best describes the **most effective next step in your project**, given the following performance metrics?

* Human-level performance: 0.1%
* Training set error: 2.0%
* Dev set error: 2.1%

- [ ] Evaluate the test set to determine the variance.
- [ ] Deploy the model to target devices to evaluate against satisficing metrics.
- [x] Prioritize actions to decrease bias by increasing model complexity, as the training error significantly exceeds human-level performance.
- [ ] Continue tuning until the training set error matches human-level performance, focusing solely on the optimizing metric.

*Points: 1 / 1*

## Question 11 (GradedCheckboxQuestion)

After running your model with the test set, you find the error rate is 7.0% compared to a 2.1% error rate for the dev set and 2.0% for the training set. What can you conclude? (Choose all that apply)

- [x] Try decreasing regularization for better generalization with the dev set.
  > Feedback: This should not be selected Decreasing regularization would likely increase overfitting.
- [ ] You have overfitted to the dev set.
- [ ] You have underfitted to the dev set.
- [ ] You should try to get a bigger dev set.

*Points: 0.3 / 1*

## Question 12 (GradedCheckboxQuestion)

After working on this project for a year, you finally achieve:

|  |  |
| --- | --- |
| Human-level performance | 0.10% |
| Training set error | 0.05% |
| Dev set error | 0.05% |

What can you conclude? (Check all that apply.)

- [ ] With only 0.05% further progress to make, you should quickly be able to close the remaining gap to 0%.
- [ ] It is now harder to measure avoidable bias, thus progress will be slower going forward.
- [ ] It is highly unlikely this result is purely a statistical anomaly, but statistical noise may still contribute to the error.
- [x] If the test set is big enough for the 0.05% error estimate to be accurate, this implies Bayes error is ≤0.05\leq 0.05%≤0.05is less than or equal to, 0, point, 05 ✅correct
  > Feedback: Nice work Bayes error is the theoretical minimum error, and if the test error is accurate, it implies the Bayes error is at or below that level.

*Points: 0.8 / 1*

## Question 13 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again You must maintain overall accuracy while addressing false negatives.

It turns out Peacetopia has hired one of your competitors to build a system as well. Your system and your competitor both deliver systems with about the same running time and memory size. However, your system has higher accuracy!

Still, when Peacetopia tries out both your system and your competitor’s system, they conclude they actually like your competitor’s system better, because even though you have higher overall accuracy, you have more false negatives (failing to raise an alarm when a bird is in the air).

What should you do?

- [ ] Pick false negative rate as the new metric, and use this new metric to drive all further development.
- [ ] Rethink the appropriate metric for this task, and ask your team to tune to the new metric.
- [x] Look at all the models you’ve developed during the development process and find the one with the lowest false negative error rate.
- [ ] Ask your team to take into account both accuracy and false negative rate during development.

*Points: 0 / 1*

## Question 14 (GradedMultipleChoiceQuestion)

**❌ Incorrect** — Try again 1,000 images are too few to reliably evaluate bias in the dev set for a new species. Augmenting data to increase the training set size is more effective.

You’ve handily beaten your competitor, and your system is now deployed in Peacetopia and is protecting the citizens from birds! But over the last few months, a new species of bird has been slowly migrating into the area, so the performance of your model is being tested on a new type of data.   

There are only 1,000 images of the new species. The city expects a better system from you within the next 3 months.

**Which of these should you do first?**

- [ ] Augment your data to increase the number of images of the new bird species.
- [ ] Add hidden layers to further refine feature development.
- [x] Put the 1,000 images into the dev set to evaluate the bias and re-tune.
- [ ] Add the new images and split them among train/dev/test.

*Points: 0 / 1*

## Question 15 (GradedCheckboxQuestion)

The City Council thinks that having more cats in the city would help scare off birds. They are so happy with your work on the Bird detector that they also hire you to build a Cat detector.

You have a huge dataset of 100,000,000 cat images. Training on this data takes about two weeks.

Which of the statements do you agree with? (Check all that agree.)

- [x] Accuracy should exceed the City Council’s requirements, but the project may take as long as the bird detector because of the two-week training/iteration time. ✅correct
  > Feedback: Nice work The increased dataset size adds a small amount of accuracy, but the longer training time is a constraint.
- [ ] Given a significant budget for cloud GPUs, you could mitigate the training time.
- [ ] With the experience gained from the Bird detector, you are confident to build a good Cat detector on the first try.
- [ ] You could consider a tradeoff where you use a subset of the cat data to find reasonable performance with reasonable iteration pacing.

*Points: 0.5 / 1*

